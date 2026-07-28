---
title: Migration des modifications de la structure d’extension pour l’éditeur 2.0
description: En savoir plus sur la migration vers le framework d’extension pour l’éditeur 2.0
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 75954eab3ac1738705fe2a7280973af39b9214df
workflow-type: tm+mt
source-wordcount: '1904'
ht-degree: 0%

---


# Migration de la structure d’extension vers l’éditeur 2.0 (nouvel éditeur)

Ce guide aide les auteurs d’extensions à comprendre ce qui est impliqué dans le déplacement de leurs personnalisations de l’**ancien éditeur** vers l’**nouvel éditeur** dans AEM Guides, afin qu’ils puissent planifier leur transition en douceur et avec un minimum d’interruption.

>[!IMPORTANT]
> 
> Si vous disposez déjà d’une extension AEM Guides (ancien éditeur), y compris d’éléments de menu contextuel personnalisés, de boutons de barre d’outils, de boîtes de dialogue, d’une logique d’attribut ou de métadonnées ou d’un style de contenu, ce guide vous aide à continuer à utiliser le nouvel éditeur.

## Vue d’ensemble

- **Votre enregistrement ne change pas** : Continuez à utiliser `window.extension` / `tcx.extension.register`.
- **La zone de travail de l’éditeur est une nouvelle surface.** Les éléments de menu contextuel doivent déclarer le nouvel identifiant du widget
  `markup_editor_menu` ; le comportement dans l’éditeur doit arrêter de toucher le DOM.
- **Arrêter la lecture/l’écriture du DOM** : remplacez `tcx.curEditor.*` accès DOM par
  API `guides.editor` : [lecture avec `runUtil(...)`](#migrate-reads-dom-runutil), [écriture avec `runCommand(...)`](#migrate-writes-dom-mutation-runcommand), [style avec décorations](#migrate-rendering-only-logic-dom-paint-decorations) et [exécution d’actions globales (enregistrement) par le biais d’événements d’application](#migrate-global-actions-savefocus-app-events) .
- **Les menus App-Shell (référentiel, visionneuse de mappages, fichier/dossier) restent inchangés** : ils s’exécutent toujours sur
le framework hérité.
- **Les deux éditeurs coexistent** : ciblez les deux avec des tableaux. Lors du chargement des modules externes **Register** sans condition ; activez uniquement les actions *runtime* par `guides.editor.version` (qui restent `1.0.0` jusqu&#39;à ce qu&#39;un fichier soit ouvert, consultez [Détecter l&#39;éditeur et amorcer en toute sécurité](#detect-the-Editor-and-bootstrap-safely)).


## Pourquoi ce changement ?

| Critères | Ancien éditeur de clés | Nouvel éditeur de balises |
|---|---|---|
| Source de vérité | DOM | Document ProseMirror |
| Sélection | `getSelection()` sur un document racine | Sélection de ProseMirror (positions/plages) |
| Pour modifier le contenu | Mutations des attributs/classes DOM | Distribuer une commande (transaction) |
| Création de rendu | DOM est permanent | DOM est un rendu éphémère dans un DOM fantôme, reconstruit à tout moment |
| Style | Page ou bibliothèque cliente CSS | DOM fantôme injecté par CSS via le plug-in de registre. Référez-vous à [Hello world : un plug-in de mise en surbrillance CSS uniquement](#hello-world-a-css-only-highlight-plugin) pour utiliser les classes existantes et ajouter CSS et [logique de rendu de migration uniquement](#migrate-rendering-only-logic-dom-paint-decorations) pour ajouter une nouvelle classe et ajouter du style. |

Toute extension qui mute le DOM ou toute modification du DOM ne sont pas conservées, elles sont effacées lors du rendu suivant. La migration est fondamentalement *passer de DOM-first à model-first*.

## Détecter l’éditeur et amorcer en toute sécurité

L’objet `guides` global est le point d’entrée pour toutes les nouvelles intégrations :

```js
guides.editor    // editor interaction APIs
guides.util      // bundled utility libs (lodash, async)
guides.ready(cb) // fires once at app load (view system ready) — before any file is open
```

`guides.editor.version` signale l’**éditeur actuellement ouvert** afin qu’il n’ait de sens qu’une seule fois.
Le fichier est actuellement ouvert :

| `guides.editor.version` | Signification |
|---|---|
| `2.0.0` | Un fichier MarkupEditor (ProseMirror) est ouvert |
| `1.0.0` | Un fichier CKEditor hérité est ouvert ou aucun fichier n&#39;est ouvert pour le moment |

>[!IMPORTANT]
>
> Lorsque l’événement `guides.ready` se produit, aucun fichier n’a encore été ouvert. Par conséquent, `version` signalera comme `1.0.0`, que l’éditeur de balises soit activé ou non. N’utilisez pas `version` pour déterminer si les plug-ins sont *enregistrés* (consultez la section [Enregistrement de plug-in et contrôle d’exécution](#plugin-registration-and-runtime-gating)). Utilisez-le uniquement pour créer une branche *comportement d’exécution* et pour l’évaluer au point d’exécution (dans un gestionnaire de menus, par exemple), où l’ouverture d’un fichier est garantie.

### Enregistrement et contrôle d’exécution du plug-in

- **Enregistrement** (`registerPlugin`, configuration unique) : exécutez-le **sans condition** en `guides.ready`. Il s’agit d’une opération nulle inoffensive sur l’éditeur hérité : l’éditeur hérité ne lit jamais le registre du plug-in et votre usine s’exécute uniquement lorsqu’un éditeur de balises est réellement créé. Il ne lance **pas**.

- **Appels d’exécution** (`runCommand`, `runUtil`, `addDecoration`, etc.) : la porte par version existe et n’est pas égale à « 1.0.0 » au moment de l’appel. Ils ne lancent pas sur l’éditeur hérité (ils renvoient en toute sécurité `false`/`undefined`), mais le point de contrôle évite les avertissements d’absence d’opération et vous permet de conserver un ancien éditeur de secours.

```js
guides.ready(() => {
  // Always register — inert on legacy, applied only when a MarkupEditor opens.
  guides.editor.registerPlugin(createMyPlugin);
});

function onMenuClick() {
  if (guides.editor.version && guides.editor.version !== "1.0.0") {
    guides.editor.runCommand('surroundWithElement', 'sup'); // MarkupEditor path
  } else {
    // legacy path (or no-op)
  }
}
```

Transmettez une **factory** `() => ({ plugin, css })` — à `registerPlugin`, jamais une instance de plug-in construite. Une non-fonction est la seule entrée qu’elle rejette (lance sur les deux éditeurs). Ne mettez pas en cache l’instance d’éditeur ; appelez `guides.editor.*` à nouveau à chaque fois.

### Hello world : un plug-in de surbrillance CSS uniquement

La plus petite extension utile est fournie **uniquement CSS** un plug-in ProseMirror sans opération ainsi que des styles. Ce(tte)
met en surbrillance chaque élément `<note>` avec un arrière-plan jaune dans l’éditeur :

```js
guides.ready(() => {
  guides.editor.registerPlugin(() => ({
    plugin: new guides.editor.prosemirror.state.Plugin({}), // no behavior — CSS only
    css: `[data-xml-element="note"] { background: #fff3cd; outline: 1px solid #ffe08a; }`
  }));
});
```

- Chaque élément est rendu en tant que `data-xml-element="<tag>"`, vous pouvez donc cibler n&#39;importe quel élément DITA de cette manière
(`note`, `codeblock`, `section`, `table`, ...).
- CSS **must** fourni via le registerPlugin : l’éditeur vit dans un DOM fantôme, donc le CSS de la page/bibliothèque cliente ne peut pas
atteignez-le.
- Ouvrez une rubrique DITA contenant un `<note>` pour l&#39;appliquer. L&#39;enregistrement est inconditionnel (§2.1),
c&#39;est donc sans danger même si `version` est encore `1.0.0` à `guides.ready` moment.


## Inventaire de votre extension (liste de contrôle verte)

```bash
# DOM-first reads that will break
grep -rnE "rootDocument|rootElement|getSelection\(|selectedHtml|selectedText|\.xmlDoc|\.ancestors\b" src

# DOM/legacy writes that will break
grep -rnE "updateAttributes\(|setAttribute\(|classList\.|\.saveFile\(|resetDirty\(|validateRangeForInsertion\(" src

# The editor handle itself
grep -rn "tcx.curEditor" src

# Context-menu targeting + page CSS
grep -rnE "contextMenuWidget|dita_editor_menu|author_outline_element" src
grep -rn "dita_content_overrides" .
```

Chaque accès est un élément de migration. Classez chaque élément comme suit : *surface du menu contextuel*, *lecture d’état*, *contenu
écriture*, *action globale*, *rendu uniquement* ou *CSS*.


## Commun pour les deux éditeurs

Les comportements et structures suivants s’appliquent de manière identique aux deux éditeurs :

- **Inscription :** `window.extension[id] = config` et/ou `tcx.extension.register(id, config)` le
l’événement `tcx-loaded`.
- **Forme d&#39;objet Config :** `{ id, contextMenuWidget, view: { items }, controller }`.
- **Menus contextuels App-Shell** conservez leurs identifiants de widget existants et le comportement hérité :

  | Surface | Identifiant du widget (inchangé) |
  |---|---|
  | Panneau Référentiel (fichier/dossier) | `repository_panel` / `file_options` / `folder_options` |
  | Visionneuse de cartes | `ditamap_viewer` / `map_view_options` |
  | Panneaux de ligne de base/paramètres prédéfinis | `baseline_panel_menu` / `preset_item_menu` |

  Les éléments ciblant ces surfaces n’ont pas besoin d’être modifiés **pour le nouvel éditeur, ne les déplacez pas vers .**  `markup_editor_menu`.

## Référence de remplacement d’API

| Hérité (`tcx.curEditor…` / DOM) | Nouvel éditeur de balises |
|---|---|
| `tcx.curEditor.filePath` | `guides.editor.filePath` |
| `getSelection()` / `selectedHtml` / `selectedText` | `runUtil('getSelectedXml' / 'getSelectedPlainText' / 'hasSelection')` |
| `rootDocument.querySelector(tag)` | `runUtil('findPositionRange' / 'findPositionRanges', tag)` |
| élément `.getAttribute` / `xmlDoc.attributes` | `runUtil('getAttributeAtPosition', pos, name)` / `getSerializableAttributes(xpath)` |
| identifiant racine (`querySelector('[concept]').id`) | `runUtil('getAttributeAtPosition', 0, 'id')` |
| `editor.ancestors` | `runUtil('getAncestorsDetails' / 'getAncestorXpaths')` |
| `editor.updateAttributes(attrs, root)` | `runCommand('setNodeXmlAttributes', 0, attrs)` |
| définir attr sur l’élément | `runCommand('setNodeXmlAttribute', pos, name, value)` |
| encapsuler / insérer / déplier la sélection | `runCommand('surroundWithElement' / 'insertXml' / 'unwrapNode', …)` |
| `canInsertXmlElement` / `validateRangeForInsertion` | `canRunCommand(name, …)` / `canInsertXmlElement(tag)` |
| `editor.focus()` | `guides.editor.focus()` |
| `tcx.curEditor.saveFile()` | `tcx.eventHandler.next(KEYS.AUTHOR_SAVE_KEY)` |
| `setAttribute`/`classList` pour le style | `addDecoration` / `batchDecorations` / `registerPlugin` |
| page/clientlib CSS pour le contenu de l’éditeur | `registerPlugin({ css })` (DOM fantôme) |
| `contextMenuWidget: 'dita_editor_menu'` | `['dita_editor_menu', 'markup_editor_menu']` |


## Migration des éléments de menu contextuel (zone de travail de l’éditeur)

Cela s’applique uniquement aux menus qui ciblaient l’**éditeur** (`dita_editor_menu`,
`author_outline_element`), c’est-à-dire le menu contextuel / chemin de navigation dans la surface d’édition.

### Acheminement dans le nouvel éditeur

```
window.extension[id]  ─►  filtered by contextMenuWidget == 'markup_editor_menu'
                      ─►  view.items rendered in the canvas menu
   (click) ───────────►  fires an extension event:
                          • eventid is a known global key  → run as a built-in editor command
                          • otherwise                       → your controller[eventid]() runs
```

### Ajoutez le nouvel identifiant de widget (le tableau reste actif).

```js
// BEFORE
contextMenuWidget: 'dita_editor_menu',
// AFTER
contextMenuWidget: ['dita_editor_menu', 'markup_editor_menu'],
```

### Conserver la forme attendue

- Les éléments exploitables se trouvent sous `view.items` avec un `data.eventid`.
- Chaque nom de méthode de `controller` **correspond** correspond exactement à son `eventid`.

```js
view: {
  items: [{
    displayName: 'Edit Cross Reference',
    icon: 'link',
    data: { eventid: 'editCrossReference' },
    target: { key: 'displayName', value: 'Cut', viewState: 'prepend' }
  }]
},
controller: {
  editCrossReference() { /* runs on click */ }
}
```

### `target` de réancrage

Le nouveau menu résout les `target` par rapport aux propres éléments de menu de l’éditeur de balises.

- `target.key`: `displayName | id | icon | eventid`
- `target.viewState`: `append | prepend | replace`
- Ancrer à un élément natif stable tel que **`Cut`**.
- Si l’ancre ne se résout pas, l’élément s’affiche toujours, mais il arrive à la position par défaut
(pas d&#39;erreur, fixer l&#39;ancre).

### Choisir la gamme par article

```js
data: { eventid: 'AUTHOR_CUT' }          // built-in command → routed natively, no controller needed
data: { eventid: 'editCrossReference' }  // custom → runs controller.editCrossReference()
```

Ajoutez des `readOnly: true` sur un élément qui doit rester activé dans le contenu en lecture seule.

### Réécriture du corps du gestionnaire

Les gestionnaires lisent généralement la sélection et mutent un nœud, puis migrent ceux du DOM.

## Migrer les lectures (DOM : `runUtil`)

```js
// BEFORE — DOM selection / queries
const { editor } = tcx.curEditor;
const html = editor.selectedHtml;
const topicId = editor.rootDocument.querySelector('[data-tcx-tag="concept"]').id;

// AFTER — read from the document model
const selectedXml = guides.editor.runUtil('getSelectedXml');
const hasSel      = !!guides.editor.runUtil('hasSelection'); // check if selection is empty
const topicId     = guides.editor.runUtil('getAttributeAtPosition', 0, 'id'); // root = position 0
```

Recherchez un nœud par balise, faites une correspondance par ID et lisez un attribut XML :

```js
let value = '';
for (const range of (guides.editor.runUtil('findPositionRanges', 'xref') || [])) {
  const id = guides.editor.runUtil('getAttributeAtPosition', range.from, 'id');
  if (String(id) !== String(targetId)) continue;
  value = guides.editor.runUtil('getAttributeAtPosition', range.from, 'placeholdertext') || '';
  break;
}
```

**Lecture des utilitaires :** `getTextPos`, `getNodePosition`, `getSelectedXml`, `getSelectedPlainText`,
`hasSelection`, `getAncestorsNames`, `getAncestorsDetails`, `getAncestorXpaths`,
`findPositionRange`, `findPositionRanges`, `getAttributeAtPosition`, `getSerializableAttributes`. Voir [Annexe](#appendix-a-more-exposed-utils-examples).


## Migration des écritures (mutation DOM : `runCommand`)

```js
// BEFORE
const root = editor.rootElement.findOne('[data-tcx-tag="concept"]');
editor.updateAttributes({ docOwner: 'Jane' }, root);

// AFTER — update the model; persists across rerenders
guides.editor.runCommand('setNodeXmlAttributes', 0, { docOwner: 'Jane' });
```

```js
// Set one attribute at a found position
guides.editor.runCommand('setNodeXmlAttribute', pos, 'placeholdertext', text);

// Wrap / insert / unwrap
guides.editor.runCommand('surroundWithElement', 'sup');
guides.editor.runCommand('insertXml', '<sup></sup>', undefined, { setCursorInContent: true });
guides.editor.runCommand('unwrapNode');
```

**Prérequis**

```js
guides.editor.focus();
if (!guides.editor.canInsertXmlElement('xref')) {
  return tcx.util.showAlert('warning', 'xref is not allowed here'); 
}
if (guides.editor.canRunCommand('surroundWithElement', 'sup')) {
  guides.editor.runCommand('surroundWithElement', 'sup');
}
```

**Commandes :** `setNodeXmlAttributes`, `setNodeXmlAttribute`, `surroundWithElement`, `insertXml`,
`unwrapNode`. Voir [Annexe](#appendix-b-more-exposed-commands-examples).

## Migrer les actions globales (enregistrer/cibler : événements d&#39;application)

```js
// BEFORE
tcx.curEditor?.saveFile?.();
// AFTER
tcx.eventHandler.next(tcx.eventHandler.KEYS.AUTHOR_SAVE_KEY);
```

`resetDirty(...)` et `tcx.curEditor.html` n’ont pas d’équivalent dans MarkupEditor, alors déposez-les ; enregistrement
via l’événement , gère l’état d’intégrité de manière centralisée. Utilisez `guides.editor.focus()` pour la sélection.


## Migration de la logique de rendu uniquement (peinture DOM : décorations)

Tout élément qui a ajouté des classes CSS, des attributs `data-*` ou du « texte affiché » en mutant le DOM doit :
devenir une **décoration**, ou disparaître sur le rendu. Vous trouverez ci-dessous des cas déclaratifs simples :

```js
guides.editor.addDecoration('important-sections', 'section', {
  class: 'section-important',
  computeAttributes: (node, ctx) => ({ 'data-number-label': String(ctx.index + 1) }),
  filter: (node) => node.attrs?.xmlAttrs?.importance === 'high'
});

guides.editor.batchDecorations([
  { action: 'remove', id: 'legacy-numbering' },
  { action: 'add', id: 'division-numbering', selector: 'conbody', options: { class: 'division-numbering' } }
]);

guides.editor.removeDecoration('important-sections');
guides.editor.clearDecorations();
guides.editor.getDecorations();
```

Cas complexes (état personnalisé, état rompu via méta de transaction, texte de widget) : enregistrer un
Plug-in ProseMirror unique, utilisant les bibliothèques exposées :

```js
const createXrefPlugin = () => {
  const { Plugin, PluginKey } = guides.editor.prosemirror.state;
  const { Decoration, DecorationSet } = guides.editor.prosemirror.view;
  return {
    plugin: new Plugin({ key: new PluginKey('xrefDisplay'), props: { decorations(state) { /* … */ } } }),
    css: `.xref-broken { text-decoration: underline wavy red; }`
  };
};

guides.ready(() => guides.editor.registerPlugin(createXrefPlugin));
```

Enregistrez les plug-ins au chargement de l’application (une fois), et non dans des boîtes de dialogue ou à plusieurs reprises. Le registre ne déduplique pas. `registerPlugin` accepte uniquement une fonction **factory**, et non une instance de plug-in.
`guides.editor.prosemirror` expose : `state`, `model`, `view`, `transform`, `commands`, `keymap`,
`history`, `tables`, `dropcursor`, `collab`, `markdown`.


## Migrer CSS (bibliothèque cliente de page → DOM fantôme)

L’éditeur de balises effectue le rendu dans un **DOM fantôme** ; les fichiers CSS au niveau de la page et de la bibliothèque cliente AEM ne l’atteignent pas.

```js
guides.editor.registerPlugin(() => ({
  plugin: new guides.editor.prosemirror.state.Plugin({}),   // no-op, CSS only
  css: `[data-xml-element="codeblock"] { font-family: monospace; background: #f5f5f5; }`
}));
```

La catégorie de bibliothèque cliente de contenu héritée (`apps.guides.xml_editor.dita_content_overrides`) existe toujours
applique uniquement un style à l’éditeur hérité ; conservez-le si vous prenez en charge les deux, mais sachez qu’il est inerte sur l’éditeur de balises.

## Accès à la vue active de l’éditeur (plug-in `view` prop) : trappe d’échappement DOM

Les décorations et les commandes sont l’approche préférée. Cependant, certains effets ne peuvent pas être implémentés en tant que décorations. Dans ce cas, utilisez la propriété de `view` du plug-in pour accéder à la Live `EditorView` et agir sur `editorView.dom`. Il s’agit de la seule façon prise en charge d’interagir directement avec le DOM de l’éditeur rendu.

```js
const createMyPlugin = () => {
  const { Plugin } = guides.editor.prosemirror.state;
  return {
    plugin: new Plugin({
      view(editorView) {
        const root = editorView.dom;          // the shadow-DOM editor node
        const apply = () => { /* re-color / rewrite target nodes in `root` */ };
        apply();
        return {
          update(view, prevState): apply,                       // re-apply after every rerender
          destroy() { /* remove any listeners/observers */ },
        };
      },
    }),
    css: `/* ... */`,
  };
};

guides.ready(() => guides.editor.registerPlugin(createMyPlugin));
```

**Mécanismes de sécurisation** :

- Échapper la trappe uniquement, utilisez des décorations pour les classes, les libellés et le style.
- `editorView.dom` est la seule poignée prise en charge ;
- Appliquez à nouveau à partir de `update()` afin que la modification survive aux rendus ; nettoyez dans `destroy()`.

## Cycle de vie de l&#39;enregistrement du plug-in

`registerPlugin` dans `guides.ready` enregistre l’usine une seule fois. L’usine elle-même fonctionne à nouveau
chaque fois qu’un fichier est ouvert — chaque fichier MarkupEditor ouvert l’appelle à nouveau pour générer la variable
instance du plug-in.

## Problèmes courants

- Lorsque le code DOM s’adresse aux nœuds et aux `Range`, MarkupEditor adresse les **positions**, entiers simples indexés dans le document (`0` = début du document, c’est-à-dire la racine). Une `range` est `{ from, to }`, deux positions délimitant une étendue, et non un `Range` DOM. Les positions changent au fur et à mesure que le document change. Par conséquent, ne mettez pas en cache une modification.
- **L’élément n’apparaît pas dans le menu Nouvel éditeur** : `contextMenuWidget` est manquant
  `markup_editor_menu` ou la configuration a été enregistrée *après* l’ouverture de l’éditeur (la configuration est lue).
  une fois à l’éditeur (enregistrez la construction au chargement de l’application).
- **L’élément s’affiche au mauvais endroit** : `target` ancre ne se résout pas ; ancrez-la à un élément qui
existe dans le nouveau menu (par exemple, `Cut`).
- **La modification de « fonctionne » puis disparaît** : vous avez muté le DOM. Utiliser une commande (write) ou une décoration
(style) à la place.
- **CSS n’a aucun effet** : il se situe au niveau de la page ; l’éditeur se trouve dans un DOM fantôme. Utilisation `registerPlugin({ css })`.
- **Lancement de gardes non sécurisés** : Les modèles tels que `if (!tcx.curEditor && !tcx.curEditor.editor)` évaluent
  `.editor` sur un objet faux. Gardez-vous plutôt des fonctionnalités `guides.editor` :
  `if (!guides?.editor) return;`.
- **Tentative de migration de menus app-shell** : les menus de référentiel/map/fichier ne sont pas la zone de travail de l’éditeur ;
conservez-les sur leurs identifiants de widget hérités.

## Liste de contrôle de vérification

- Les éléments de menu contextuel apparaissent à la fois dans **les menus hérités** et dans l’éditeur de balises.
- Les articles arrivent dans la position prévue.
- Le `eventid` personnalisé s’exécute `controller[eventid]` ; les clés globales déclenchent la commande intégrée.
- Les lectures d’état renvoient des valeurs correctes après la saisie/le rendu (modèle, et non DOM obsolète).
- Les écritures de contenu *persistent après l’enregistrement et la réouverture*.
- Les décorations survivent à un rendu.
- Le code CSS Shadow-DOM s’applique visiblement dans l’éditeur.
- Sauve les incendies via `AUTHOR_SAVE_KEY` et efface l&#39;état sale.
- `readOnly` éléments se comportent correctement dans le contenu verrouillé.
- Aperçu ou côte à côte ; le travail DOM intentionnel en lecture seule est laissé en l’état.
- `grep -rn "tcx.curEditor" src` est propre (ou uniquement le reste intentionnel et documenté).
- Les plug-ins se sont enregistrés une seule fois, dans `guides.ready`.


## Ordre de déploiement suggéré

1. **&#x200B;**&#x200B;: encapsuler la configuration dans `guides.ready` ; enregistrer les modules externes sans condition et ajouter des points de contrôle `version` autour des actions *runtime* uniquement (pour plus de détails, consultez [Enregistrement des modules externes et point de contrôle Runtime](#plugin-registration-and-runtime-gating)).
2. **Surface du menu contextuel** : ajoutez des `markup_editor_menu`, corrigez `target` ancres. Les éléments s’affichent maintenant.
3. **Lectures** : migrez les lectures de sélection/d’attributs vers `runUtil`.
4. **Écritures** : migration des mutations vers `runCommand` ; enregistrement dans les événements d’application.
5. **Rendu** : déplacer le style DOM vers les décorations/`registerPlugin` ; déplacer le CSS vers le DOM fantôme.
6. **Durcir** : corrigez les protections non sécurisées, supprimez la poignée de l’éditeur et vérifiez sur les deux éditeurs.

Migrez une surface à la fois et conservez le fonctionnement des chemins hérités (tableaux + point de contrôle de version) afin de :
une seule version d’extension s’exécute sur les deux éditeurs tout au long de la transition.

## Annexe A : URL plus exposées (exemples)

Recherchez les utils ci-dessous à utiliser via `runUtil`.

| Util | Paramètres → retours | Effets |
|---|---|---|
| `getTextPos` | `(): { start, end }` | Limites du nœud de texte sélectionné actuel |
| `getValidElementNames` | `(ancestorLevel?): ElementName[]` | Noms d’éléments qui peuvent légalement être insérés/placés dans la sélection en cours. |
| `getValidElementNamesBefore` | `(): ElementName[]` | Noms d’éléments valides juste avant la sélection en cours. |
| `getSelectedText` | `(): string` | Texte sélectionné brut. |
| `getSerializableAttributes` | `(): { [key]: string }` | Mappage d’attributs XML pour le nœud actuel, indexé par nom d’attribut. |
| `getTagName` | `(): string \| null` | Nom de la balise du nœud actif. |
| `hasSelection` | `(): boolean` | Si du contenu est actuellement sélectionné. |
| `isSelectionEditable` | `(): boolean` | Indique si la sélection en cours peut être modifiée. |
| `getAncestorPos` | `(name): number \| undefined` | Position de l’ancêtre le plus proche avec le nom d’élément donné, à partir de la sélection en cours. |
| `getValidWrapNodeElementNames` | `(): ElementName[]` | Noms d’éléments valides pour `wrapNode` dans la sélection en cours. |
| `getValidRenameNodeElementNames` | `(): ElementName[]` | Les noms d’éléments auxquels le nœud actuel peut légalement être renommé. |
| `getValidSurroundElementNames` | `(): ElementName[]` | Noms d’éléments valides pour `surroundWithElement` dans la sélection en cours. |
| `serialize` | `(doc?): string` | Sérialise un document ProseMirror (ou l’intégralité du document) au format XML. |
| `getSelectedXml` | `(range?): string` | XML pour la sélection en cours ou une plage de `{ from, to }` explicite. |
| `getRangeXml` | `(xpaths): string` | XML pour une ou plusieurs plages xpath-object (voir caveat xpath de §8 — il s&#39;agit du formulaire de l&#39;objet, pas du formulaire de la chaîne). |
| `mapToXpath` | `(position, doc?): XPathPosition` | Convertit une position en xpath de formulaire-objet. |
| `inverseMap` | `(xpath \| position, doc?): number` | Reconvertit un xpath (ou une position) de formulaire objet en une position. |
| `getAncestorsDetails` | `(): { ancestors, previousSibling, nextSibling, currNode } \| undefined` | Chaîne d’ancêtres plus frères immédiats pour le nœud actuel. |
| `getAncestorsNames` | `(): ElementName[]` | Chaîne d’ancêtres comme noms d’éléments uniquement, pour le nœud actuel. |
| `getPreviousSibling` | `(): ElementName \| undefined` | Nom de l’élément frère précédent. |
| `getNextSibling` | `(): ElementName \| undefined` | Nom de l’élément frère suivant. |
| `getAncestorXpaths` | `(includeNodeAtPosition?): { tag, xpath }[]` | Chaîne d&#39;ancêtres comme paires de `{tag, xpath}` — xpath objet-forme, pas la forme de chaîne `updateAttributeByXpath` (§8). |
| `getSelectedPlainText` | `(range?): string` | Texte brut de la sélection en cours ou plage explicite. |
| `getDecorations` | `(): string[]` | ID de toutes les décorations actuellement appliquées. |
| `getResolvedDitaDocumentTitle` | `(props?): string` | Titre affiché résolu du document DITA. `props` : `doc` de cibler un document spécifique, `allowedPrefixElements` d’autoriser les éléments de préfixe de titre. |

## Annexe B : commandes plus exposées (exemples)

Les commandes ci-dessous sont des exemples supplémentaires de ce qui est exposé via `guides.editor.runCommand(name, ...args)`.
Commencez par protéger toute commande avec `guides.editor.canRunCommand(name, ...args)` si elle ne s’applique pas dans le contexte actuel.

| Commande | Params | Effets |
|---|---|---|
| `focusEditor` | `()` | Met l’accent sur l’éditeur. |
| `unwrapNode` | `()` | Supprime l’élément d’habillage de la sélection en cours et conserve ses enfants. |
| `surroundWithElement` | `(elementName, attrs?, groupInline?)` | Enveloppe la sélection en cours dans un nouvel élément intégré/de bloc. `attrs` : mappage d’attributs XML à définir sur le nouvel élément d’encapsulation. |
| `insertXml` | `(xml)` | Insère un fragment XML au niveau du curseur. |
| `replaceSelectionWithXml` | `(xml)` | Remplace la sélection courante par XML. |
| `insertText` | `(text)` | Insère du texte brut au niveau du curseur. |
| `selectNodesFromXpaths` | `(xpaths)` | Sélectionne un ou plusieurs nœuds auxquels sont attribués des chemins d’accès de formulaire d’objet. |
| `delete` | `()` | Supprime la sélection en cours. |
| `undo` / `redo` | `()` | Annuler/rétablir standard. |
| `removeDecoration` | `(id)` | Supprime une seule décoration par ID. |
| `clearDecorations` | `()` | Supprime toutes les décorations du fichier ouvert actuel. |
| `setFileReadOnly` | `(readOnly: boolean)` | Active/désactive le mode lecture seule pour le fichier. |
| `generateUniqueId` | `()` | Génère et affecte un attribut d’identifiant unique au nœud actuel. |