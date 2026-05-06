---
title: Modifications de la structure d’extension pour l’éditeur 2.0
description: Découvrez les modifications apportées au framework d’extension pour l’éditeur 2.0
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 670a7557746baf16cf9786ba61a19448315ed59b
workflow-type: tm+mt
source-wordcount: '2003'
ht-degree: 4%

---

# Modifications de la structure d’extension pour l’éditeur 2.0 (nouvel éditeur)

Ce document couvre toutes les API ajoutées à `guides.editor` (et `guides`) dans le cadre de la structure d’extension du nouvel éditeur (éditeur basé sur ProseMirror). Ces API permettent aux extensions externes d’interagir avec l’éditeur sans manipulation DOM directe ni connaissance de l’implémentation interne.

## Vue d’ensemble

L’objet `guides` global est le point d’entrée pour toutes les intégrations d’extension :

```js
guides.editor    // Editor interaction APIs
guides.util      // Utility libraries (lodash, async)
guides.ready(cb) // Lifecycle hook fires when the editor is fully loaded
```

Toutes les API `guides.editor` peuvent être appelées en toute sécurité à partir des contrôleurs d’extension, des gestionnaires de barre d’outils et de la logique de boîte de dialogue.

## Cycle de vie

`guides.ready(callback)` : enregistre un rappel à exécuter une fois le gestionnaire de pages vues entièrement chargé. Utilisez ceci avant d’enregistrer des modules externes ou d’effectuer une configuration d’éditeur.

**Signature:**

```ts
guides.ready(callback: () => void): void
```

**Exemple :**

```js
guides.ready(() => {
  // Safe to access guides.editor APIs here
  guides.editor.registerPlugin(createMyPlugin);
});
```

## Propriétés de l’état de l’éditeur

- `guides.editor.filePath` : renvoie le chemin d’accès au fichier du document actif.

  **Type :** `string | undefined`

  **Exemple : lecture du chemin d’accès au fichier pour un appel API de métadonnées :**

  ```js
  const filePath = guides.editor.filePath;
  if (filePath) {
  tcx.api.getMetadata(filePath).subscribe((metadata) => {
    // use metadata...
    });
  }
  ```

  **Exemple : logique conditionnelle basée sur l’emplacement du fichier**

  ```js
  const filePath = guides.editor.filePath;
  if (filePath?.endsWith(".ditamap")) {
    // ditamap-specific handling
  }
  ```

- `guides.editor.version` : renvoie la chaîne de version de l’éditeur actuellement chargé.

  | Valeur | Éditeur |
  |---------|------------------------------------|
  | `1.0.0` | Ancien éditeur de clé CKE (`xml_author_view`) |
  | `2.0.0` | Nouvel éditeur (basé sur ProseMirror) |

  **Type :** `string`

  **Exemple :**

  ```js
  if (guides.editor.version  === '1.0.0') {
    // CKEditor specific logic 
  }
  ```

- `guides.editor.appState(keyName)` : lit une valeur du modèle d’application par nom de clé.

  **Signature:**

  ```ts
  guides.editor.appState(keyName: string): unknown
  ```

  **Exemple :**

  ```js
  const editorMode = guides.editor.appState('editorMode');
  ```

## Interaction de l’éditeur

- `guides.editor.focus()` : permet de se concentrer sur l’éditeur actif. Appelez cette option avant d’exécuter les commandes qui nécessitent le focus de l’éditeur.

  **Signature:**

  ```ts
  guides.editor.focus(): boolean
  ```

  **Exemple : focus avant insertion de contenu**

  ```js
  guides.editor.focus();
  const hasSelection = !!guides.editor.runUtil('hasSelection');
  // ...proceed with wrap or insert
  ```

- `guides.editor.canInsertXmlElement(tagName, insertAfter?)` : vérifie si un élément XML donné peut être inséré à la position actuelle du curseur.

  **Signature:**

  ```ts
  guides.editor.canInsertXmlElement(tagName: string, insertAfter?: boolean): boolean
  ```

  **Exemple : protection avant insertion de`<xref>`**

  ```js
  const canInsert = guides.editor.canInsertXmlElement("xref");
  if (!canInsert) {
    return tcx.util.showAlert("warning", "xref is not allowed here");
  }
  ```

  **Exemple : protection avant insertion `<sup>` /`<sub>`**

  ```js
  const canInsert = guides.editor.canInsertXmlElement("sup");
  if (!canInsert) {
    return tcx.util.showAlert("warning", "superscript is not allowed here");
  }
  ```

- `guides.editor.selectCurrentBlockElement()` : sélectionne l’élément actuel au niveau du bloc dans l’éditeur.

  **Signature:**

  ```ts
  guides.editor.selectCurrentBlockElement(): boolean
  ```

  **Exemple :**

  ```js
  guides.editor.selectCurrentBlockElement();
  ```

- `guides.editor.getValidElementNamesForInsertion(args)` : renvoie une liste de noms d’éléments XML valides qui peuvent être insérés à la position actuelle.

  **Signature:**

  ```ts
  guides.editor.getValidElementNamesForInsertion(args: {
    insertMode?: 'after' | 'before' | 'rename',
    strict: boolean
  }): string[] | false
  ```

  **Exemple :**

  ```js
  const validElements = guides.editor.getValidElementNamesForInsertion({
    insertMode: 'after',
    strict: true
  });
  ```

- `guides.editor.updateAttributeByXpath(args)` : met à jour un attribut XML spécifique sur un nœud identifié par son XPath. Délègue à la méthode de `updateAttributeByXpath` de l’éditeur actif.

  **Signature:**

  ```ts
  guides.editor.updateAttributeByXpath(args: UpdateXpathArgs): any
  ```

## Exécution de commande

- `guides.editor.runCommand(commandName, ...args)` : exécute une commande nommée dans le nouvel éditeur. Renvoie `true` si la commande a réussi, `false` dans le cas contraire.

  **Signature:**

  ```ts
  guides.editor.runCommand(commandName: string, ...args: any[]): boolean
  ```

  **Commandes disponibles**

  >[!NOTE]
  >
  > Stabilité : les commandes répertoriées ci-dessous font partie de l’interface publique d’. Leurs noms, signatures et comportements observables sont considérés comme stables et sont conservés pour des raisons de compatibilité. D’autres commandes peuvent être présentes dans l’éditeur. Toutefois, elles sont internes, ne sont pas destinées à une utilisation externe et peuvent être modifiées ou supprimées sans préavis.

  | Catégorie | Commande | Arguments | Description |
  |---|---|---|---|
  | Général | `undo` | _(aucune)_ | Annule la dernière modification du document |
  | Général | `redo` | _(aucune)_ | Rétablit la dernière modification annulée |
  | Sélection | `select` | `from: number, to?: number` | Sélectionne la plage de `from` à `to` (ou simplement `from` si `to` est omis). |
  | Sélection | `cursor` | `pos: number` | Déplace le curseur sur `pos` |
  | Sélection | `selectNodesFromXpaths` | `xpaths: Array<{path: Array<{name: string, count: number}>}>` | Sélectionne les nœuds identifiés par les positions XPath |
  | Mise en forme | `toggleBold` | _(aucune)_ | Active/désactive la mise en forme Gras de la sélection en cours |
  | Mise en forme | `toggleItalic` | _(aucune)_ | Active/désactive la mise en forme italique de la sélection en cours |
  | Mise en forme | `toggleUnderline` | _(aucune)_ | Active/désactive le soulignement de la sélection en cours |
  | Mise en forme | `toggleFormatting` | `markType: string, allowEmptySelection?: boolean` | Fait basculer un élément de mise en forme (par exemple, `'b'`, `'i'`, `'sup'`, `'sub'`) sur la sélection |
  | Insertion | `insertText` | `text: string` | Insère du texte brut au niveau du curseur |
  | Insertion | `insertXml` | `xml: string, position?: number, options?: InsertXmlOptions` | Insère du code XML brut à la position du curseur ou donnée |
  | Insertion | `insertXmlAfterElement` | `elementName: string, xmlString: string` | Insère le XML immédiatement après l&#39;ancêtre correspondant le plus proche `elementName` |
  | Insertion | `replaceSelectionWithXml` | `xmlString: string` | Remplace la sélection en cours par le code XML donné |
  | Opérations de nœuds | `surroundWithElement` | `tagName: string, attrs?: Record<string,unknown>, replaceTextWithEmptyNode?: boolean` | Enveloppe la sélection en cours avec l’élément donné |
  | Opérations de nœuds | `wrapNode` | `type: string, target?: number, attrs?: Record<string, unknown>` | Enveloppe le nœud à `target` (ou le nœud actif) dans un élément de `type` |
  | Opérations de nœuds | `renameNode` | `newNodeName: string` | Renomme l’élément du nœud actif |
  | Opérations de nœuds | `unwrapNode` | _(aucune)_ | Supprime l’élément wrapper du nœud actif et conserve son contenu |
  | Supprimer | `deleteSelection` | _(aucune)_ | Supprime le contenu actuellement sélectionné |
  | Supprimer | `deleteNode` | _(aucune)_ | Supprime l’intégralité du nœud actif |
  | Attributs | `setNodeXmlAttributes` | `position: number, attrs: Record<string, unknown>` | Définit plusieurs attributs XML sur le nœud à l’emplacement `position` |
  | Attributs | `setNodeXmlAttribute` | `position: number, attrName: string, value: string` | Définit un attribut XML unique sur le nœud à l’emplacement `position` |
  | Listes | `toggleList` | `listName: 'ol' \| 'ul'` | Fait basculer le bloc actif entre une liste du type donné et un paragraphe |
  | Tableaux | `addRowAfter` | `count?: number` | Ajoute `count` lignes sous la ligne active (1 par défaut) |
  | Tableaux | `addColumnAfter` | `count?: number` | Ajoute `count` colonnes à droite de la colonne active (1 par défaut) |
  | Tableaux | `deleteRow` | _(aucune)_ | Supprime la ligne courante |
  | Tableaux | `deleteColumn` | _(aucune)_ | Supprime la colonne courante |
  | Tableaux | `mergeCells` | _(aucune)_ | Fusionne les cellules actuellement sélectionnées |
  | Presse-papiers | `copy` | _(aucune)_ | Copie la sélection en cours dans le presse-papiers |
  | Presse-papiers | `cut` | _(aucune)_ | Coupe la sélection courante dans le presse-papiers |
  | Rechercher et remplacer | `setSearchQuery` | `query: string, options?: { caseSensitive?: boolean, regex?: boolean }` | Définit la requête de recherche active |
  | Rechercher et remplacer | `findNext` | _(aucune)_ | Passe à la recherche correspondante suivante |
  | Rechercher et remplacer | `replaceAll` | `replacement?: string` | Remplace chaque correspondance de la requête actuelle par `replacement` |

   - **Exemple : définissez plusieurs attributs sur un nœud**

     ```js
     guides.editor.runCommand(
       "setNodeXmlAttributes",
       rootRange.from,
       { createdDate: "2024-01-01", author: "Jane Doe" }
     );
     ```

   - **Exemple : définissez un attribut unique sur un nœud**

     ```js
     guides.editor.runCommand(
       "setNodeXmlAttribute",
       range.from,
       "placeholdertext",
       "Chapter 3 — Safety Requirements"
     );
     ```

   - **Exemple : encapsuler la sélection avec un élément et définir des attributs**

     ```js
     const didWrap = guides.editor.runCommand(
       "surroundWithElement",
       "ph",
       { outputclass: "highlight" },
       true   // replace text content with empty node
     );
     ```

   - **Exemple : encapsuler la sélection dans `<sup>` (activer/désactiver l’exposant)**

     ```js
     const didWrap = guides.editor.runCommand('surroundWithElement', 'sup');
     if (!didWrap) {
       tcx.util.showAlert("warning", "superscript is not allowed here");
     }
     ```

   - **Exemple : déplier le nœud actuel (désactiver l’exposant)**

     ```js
     const didUnwrap = guides.editor.runCommand('unwrapNode');
     ```

   - **Exemple : insérez du code XML à l’emplacement du curseur avec un signe d’insertion**

     ```js
     guides.editor.runCommand(
       'insertXml',
       '<sup></sup>',
       undefined,
       { setCursorInContent: true, focusEditor: true, selectInsertedXml: false }
     );
     ```

- `guides.editor.canRunCommand(commandName, ...args)` : vérifie si une commande nommée peut actuellement être exécutée, sans réellement l’exécuter.

  **Signature:**

  ```ts
  guides.editor.canRunCommand(commandName: string, ...args: any[]): boolean
  ```

  **Exemple :**

  ```js
  if (guides.editor.canRunCommand('surroundWithElement', 'sup')) {
    guides.editor.runCommand('surroundWithElement', 'sup');
  }
  ```

## Fonctions Utilitaires

- `guides.editor.runUtil(utilName, ...args)` : appelle un utilitaire nommé à partir du registre des utilitaires du nouvel éditeur. Renvoie le résultat de l&#39;utilitaire ou `undefined` si l&#39;utilitaire est introuvable.

  **Signature:**

  ```ts
  guides.editor.runUtil(utilName: string, ...args: any[]): any
  ```

  **Utilitaires disponibles**

  >[!NOTE]
  >
  > Stabilité : les utilitaires répertoriés ci-dessous font partie de l’interface publique d’. Leurs noms, signatures et comportements observables sont considérés comme stables et sont conservés pour des raisons de compatibilité. D’autres commandes peuvent être présentes dans l’éditeur. Toutefois, elles sont internes, ne sont pas destinées à une utilisation externe et peuvent être modifiées ou supprimées sans préavis.


  | Catégorie | Utilitaire | Arguments | Renvoie | Description |
  |---|---|---|---|---|
  | Position | `getTextPos` | _(aucune)_ | `{ start: number, end: number }` | Position de début et de fin de la sélection en cours dans le document ProseMirror |
  | Position | `getNodePosition` | `position?: number` | `number` | Position du document du nœud actuellement sélectionné/ciblé |
  | Position | `mapToXpath` | `position: number` | `XPathPosition` | Mappe une position ProseMirror à un descripteur XPath |
  | Position | `inverseMap` | `xpath: XPathPosition \| number` | `number` | Mappe un descripteur XPath (ou une position numérique) à une position ProseMirror. |
  | Document | `getNodeTree` | _(aucune)_ | `NodeTree \| null` | Représentation arborescente du document, adaptée au rendu des contours |
  | Document | `getAncestorsNames` | `position?: number` | `string[]` | Noms de balises XML des nœuds ancêtres à l’adresse `position` |
  | Document | `getAncestorsDetails` | `position?: number` | `{ currNode: string, ancestors: Array<{tagName: string}>, previousSibling?: string, nextSibling?: string } \| undefined` | Nœud actuel, ancêtres et frères immédiats à `position` |
  | Document | `getAncestorXpaths` | `includeId?: boolean` | `AncestorXpathItem[]` | Chaînes XPath de tous les nœuds ancêtres |
  | Document | `getPreviousSibling` | `position?: number` | `string \| undefined` | Nom de la balise du frère précédent, le cas échéant |
  | Document | `getNextSibling` | `position?: number` | `string \| undefined` | Nom de la balise du frère suivant, le cas échéant |
  | Document | `getTagName` | `position?: number` | `string \| null` | Nom de la balise de l’élément en `position` (ou curseur) |
  | Recherche d’éléments | `findPositionRange` | `tagName: string` | `{ from: number, to: number } \| undefined` | Plage du premier élément avec la balise donnée |
  | Recherche d’éléments | `findPositionRanges` | `tagName: string` | `Array<{ from: number, to: number }>` | Toutes les plages pour les éléments correspondant à `tagName` |
  | Attributs | `getAttributeAtPosition` | `position: number, attrName: string` | `unknown` | Lit une valeur d’attribut XML à partir du nœud sur `position` |
  | Attributs | `getSerializableAttributes` | `xpath: string` | `Record<string, unknown>` | Tous les attributs XML sérialisables pour le nœud à l’adresse `xpath` |
  | Sérialisation | `serialize` | _(aucune)_ | `string` | Sérialise l’intégralité du document au format XML |
  | Sérialisation | `serializeToText` | _(aucune)_ | `string` | Sérialise l’intégralité du document en texte brut |
  | Sérialisation | `getRangeXml` | `xpaths: AncestorXpathItem[]` | `string` | Renvoie le XML pour une plage définie par XPath |
  | Sélection | `getSelectedXml` | _(aucune)_ | `string` | Contenu actuellement sélectionné sous forme de chaîne XML |
  | Sélection | `getSelectedText` | _(aucune)_ | `string` | Texte sélectionné sans balises |
  | Sélection | `hasSelection` | _(aucune)_ | `boolean` | `true` s’il existe une sélection de texte/nœud active |
  | Sélection | `isSelectionEditable` | _(aucune)_ | `boolean` | Indique si la sélection en cours se trouve dans le contenu modifiable. |
  | Sélection | `isPositionEditable` | `position: number` | `boolean` | Indique si `position` se trouve dans le contenu modifiable. |
  | Insertion | `canInsert` | `name: string, position?: number, insertMode?: 'after' \| 'before' \| 'rename'` | `boolean` | Indique si `name` peut être inséré au niveau du `position` (ou du curseur). |
  | Insertion | `getInsertPosition` | `name: string, position?: number, insertMode?: 'after' \| 'before' \| 'rename'` | `number \| null` | Position d’insertion valide pour `name` ou `null` si elle n’est pas insérable |
  | Insertion | `getNodeXml` | `nodeName: string, nodeContent?: string` | `string \| null` | Modèle XML pour un type de nœud |
  | Développer/Renommer | `getValidWrapNodeElementNames` | _(aucune)_ | `string[]` | Noms d’éléments pouvant encapsuler la sélection en cours |
  | Développer/Renommer | `getValidRenameNodeElementNames` | _(aucune)_ | `string[]` | Noms des éléments auxquels le nœud actuel peut être renommé |
  | Tableaux | `getTableInfo` | `position?: number` | `{ rows: number, cols: number, header: number }` | Dimensions de la table courante |
  | Vue Balise | `isTagViewActive` | _(aucune)_ | `boolean` | Indique si le rendu des vues de balises est actif. |

  **Exemple : obtenez la position du curseur et les noms d’ancêtres**

  ```js
  const textPos = guides.editor.runUtil("getTextPos");
  const ancestorNames = guides.editor.runUtil(
    "getAncestorsNames",
    typeof textPos === "number" ? textPos : undefined
  );
  ```

  **Exemple : rechercher tous les éléments `<xref>` et lire leurs attributs**

  ```js
  const xrefRanges = guides.editor.runUtil("findPositionRanges", "xref") || [];
  xrefRanges.forEach((range) => {
    const id = guides.editor.runUtil("getAttributeAtPosition", range.from, "id");
    const placeholderText = guides.editor.runUtil(
      "getAttributeAtPosition",
      range.from,
      "placeholdertext"
    );
  });
  ```

  **Exemple : recherchez la plage d’éléments racines et lisez ses attributs**

  ```js
  const rootRange = guides.editor.runUtil("findPositionRange", "concept"); // or "topic"
  if (rootRange) {
    const createdDate = guides.editor.runUtil(
      "getAttributeAtPosition",
      rootRange.from,
      "createdDate"
    );
    const author = guides.editor.runUtil(
      "getAttributeAtPosition",
      rootRange.from,
      "author"
    );
  }
  ```

  **Exemple : vérifier la sélection et valider le contexte ancêtre avant une opération**

  ```js
  const ancestorsDetails = guides.editor.runUtil('getAncestorsDetails');
  const selectedText = guides.editor.runUtil('getSelectedPlainText');
  const hasSelection = !!guides.editor.runUtil('hasSelection');
  
  const firstAncestor = ancestorsDetails?.currNode || ancestorsDetails?.ancestors?.[0]?.tagName;
  if (firstAncestor === 'ph') {
    tcx.util.showAlert("warning", "Operation is not allowed inside this element type.");
    return;
  }
  ```

  **Exemple : obtenir les identifiants d&#39;élément des XPaths ancêtres**

  ```js
  const ancestorItems = guides.editor.runUtil('getAncestorXpaths', true);
  for (const item of ancestorItems) {
    const attrs = guides.editor.runUtil('getSerializableAttributes', item.xpath);
    if (attrs?.id) { /* use element ID */ }
  }
  ```

## API de décoration

L’API Decoration offre une alternative de niveau supérieur à l’écriture de modules externes ProseMirror complets pour des personnalisations visuelles courantes. Au lieu de gérer manuellement les `Plugin`, les `PluginKey` et les `DecorationSet`, vous décrivez *quoi* décorer et *comment*, et le responsable central de la décoration de l’éditeur gère l’état ProseMirror en interne.

Les décorations sont identifiées par une `id` de chaîne afin qu’elles puissent être mises à jour ou supprimées indépendamment à tout moment.

>[!NOTE]
>
> **Nouvel éditeur uniquement** ces API ne sont pas opérationnelles sur l’éditeur hérité (`version === '1.0.0'`).

- `guides.editor.addDecoration(id, selector, options)` : ajoute ou remplace une règle de décoration. Tous les nœuds correspondant à `selector` dans le document actif seront décorés en fonction de `options`. La décoration est réappliquée automatiquement à chaque modification du document.

  **Signature:**

  ```ts
  guides.editor.addDecoration(
    id: string,
    selector: string,
    options: DecorationOptions
  ): boolean
  ```

  **`DecorationOptions`champs :**

  | Champ | Type | Description |
  |---|---|---|
  | `class` | `string` | Nom(s) de classe CSS ajouté(s) aux nœuds correspondants |
  | `computeAttributes` | `(node, context) => Record<string, string>` | Fonction renvoyant des `data-*` dynamiques ou d’autres attributs HTML par nœud |
  | `filter` | `(node) => boolean` | Prédicat facultatif : seuls les nœuds pour lesquels ce paramètre renvoie des `true` sont décorés |

  L’objet `context` transmis à `computeAttributes` comprend :
   - `index` — Position basée sur 0 du nœud parmi les frères correspondant au sélecteur

  **Exemple : ajoutez une classe CSS à tous `<section>` éléments**

  ```js
  guides.editor.addDecoration('highlight-sections', 'section', {
    class: 'my-section-highlight'
  });
  ```

  **Exemple : ajoutez un attribut `data-number-label` calculé à chaque section**

  ```js
  guides.editor.addDecoration('section-numbers', 'section', {
    computeAttributes: (node, context) => ({
      'data-number-label': String(context.index + 1)
    })
  });
  ```

  **Exemple : décorez uniquement les sections qui ont `importance="high"` attribut**

  ```js
  guides.editor.addDecoration('important-sections', 'section', {
    class: 'section-important',
    filter: (node) => node.attrs?.xmlAttrs?.importance === 'high'
  });
  ```

  **Exemple : combiner la classe et les attributs calculés**

  ```js
  guides.editor.addDecoration('numbering-mode', 'conbody', {
    class: 'legacy-numbering'
  });
  
  guides.editor.addDecoration('section-numbers', 'section', {
    computeAttributes: (node, context) => ({
      'data-number-label': String(context.index + 1)
    })
  });
  ```

- `guides.editor.removeDecoration(id)` : supprime une décoration ajoutée précédemment par son identifiant.

  **Signature:**

  ```ts
  guides.editor.removeDecoration(id: string): boolean
  ```

  **Exemple :**

  ```js
  guides.editor.removeDecoration('section-numbers');
  ```

- `guides.editor.batchDecorations(changes)` : applique plusieurs modifications d&#39;ornement dans une seule distribution ProseMirror. Utilisez cette option pour activer ou désactiver plusieurs décorations à la fois afin d’éviter plusieurs rendus.

  **Signature:**

  ```ts
  guides.editor.batchDecorations(changes: DecorationBatchChange[]): boolean
  
  type DecorationBatchChange =
    | { action: 'add', id: string, selector: string, options: DecorationOptions }
    | { action: 'remove', id: string }
  ```

  **Exemple : basculer automatiquement entre deux modes de numérotation**

  ```js
  guides.editor.batchDecorations([
    { action: 'remove', id: 'legacy-numbering' },
    {
      action: 'add',
      id: 'division-numbering',
      selector: 'conbody',
      options: { class: 'division-numbering' }
    }
  ]);
  ```

  **Exemple : effacer une décoration et en ajouter deux nouvelles**

  ```js
  guides.editor.batchDecorations([
    { action: 'remove', id: 'old-highlights' },
    {
      action: 'add',
      id: 'section-labels',
      selector: 'section',
      options: {
        computeAttributes: (node, ctx) => ({ 'data-section-index': String(ctx.index) })
      }
    },
    {
      action: 'add',
      id: 'note-style',
      selector: 'note',
      options: { class: 'styled-note' }
    }
  ]);
  ```

- `guides.editor.clearDecorations()` : supprime toutes les décorations actives gérées par le gestionnaire de décoration.

  **Signature:**

  ```ts
  guides.editor.clearDecorations(): boolean
  ```

  **Exemple :**

  ```js
  guides.editor.clearDecorations();
  ```

- `guides.editor.getDecorations()` : renvoie les identifiants de toutes les décorations actuellement actives.

  **Signature:**

  ```ts
  guides.editor.getDecorations(): string[]
  ```

  **Exemple :**

  ```js
  const active = guides.editor.getDecorations();
  console.log('Active decorations:', active);
  // e.g. ['section-numbers', 'numbering-mode', 'note-style']
  ```


### API de décoration ou `registerPlugin`

| Scénario | Utiliser |
|---|---|
| Application d’une classe CSS ou d’attributs de `data-*` aux éléments correspondants | `addDecoration` |
| Activer/désactiver ou mettre à jour le style en fonction du statut d’exécution (métadonnées, action utilisateur) | `addDecoration` / `removeDecoration` / `batchDecorations` |
| Logique de module externe complexe : état personnalisé, liaisons de clés, décorations de widget, gestionnaires d’événements | `registerPlugin` |
| Injection de CSS dans le DOM fantôme | `registerPlugin` avec `css` champ |


## Enregistrement du plug-in ProseMirror

- `guides.editor.registerPlugin(factory)` : enregistre une fabrique de plug-ins ProseMirror à inclure dans chaque nouvelle instance d’éditeur. Seules les fonctions d’usine sont acceptées. Les instances de plug-in direct sont rejetées. La fabrique est appelée une fois par instance d’éditeur, ce qui garantit l’état isolé du plug-in.

  **Signature:**

  ```ts
  guides.editor.registerPlugin(factory: () => PluginConfig): void
  
  interface PluginConfig {
    plugin: ProseMirrorPlugin | ProseMirrorPlugin[]
    css?: string  // Injected into editor's shadow DOM
  }
  ```

  **Exemple : enregistrer des modules externes une fois que l’éditeur est prêt**

  ```js
  guides.ready(() => {
    guides.editor.registerPlugin(createNumberingPlugin);
    guides.editor.registerPlugin(createXrefPlugin);
  });
  ```

  **Exemple : fabrique intégrée avec CSS**

  ```js
  guides.editor.registerPlugin(() => ({
    plugin: new guides.editor.prosemirror.state.Plugin({
      key: new guides.editor.prosemirror.state.PluginKey("myPlugin"),
      props: {
        decorations(state) {
          // return DecorationSet...
        }
      }
    }),
    css: `.my-decoration { background: yellow; }`
  }));
  ```

  >[!NOTE]
  >
  > Le CSS transmis via `css` est injecté dans le DOM fantôme de l’éditeur. Les feuilles de style standard au niveau de la page ne s’appliquent pas dans l’éditeur.

## Bibliothèques ProseMirror

- `guides.editor.prosemirror` : expose les packages ProseMirror directement à utiliser dans le développement de plug-ins. Cela évite d’avoir à regrouper ProseMirror séparément dans le code d’extension.

  | Propriété | Module |
  |---|---|
  | `state` | `prosemirror-state` |
  | `model` | `prosemirror-model` |
  | `view` | `prosemirror-view` |
  | `transform` | `prosemirror-transform` |
  | `commands` | `prosemirror-commands` |
  | `keymap` | `prosemirror-keymap` |
  | `history` | `prosemirror-history` |
  | `tables` | `prosemirror-tables` |
  | `dropcursor` | `prosemirror-dropcursor` |
  | `markdown` | `prosemirror-markdown` |

  **Exemple : créez un plug-in de décoration de nœud**

  ```js
  const myPluginKey = new guides.editor.prosemirror.state.PluginKey("myPlugin");
  
  const createMyPlugin = () => {
    const { Plugin } = guides.editor.prosemirror.state;
    const { Decoration, DecorationSet } = guides.editor.prosemirror.view;
  
    return {
      plugin: new Plugin({
        key: myPluginKey,
        state: {
          init() { return { enabled: true }; },
          apply(tr, value) {
            const meta = tr.getMeta(myPluginKey);
            return meta ? { ...value, ...meta } : value;
          }
        },
        props: {
          decorations(state) {
            const decorations = [];
            state.doc.descendants((node, pos) => {
              if (node.type.name === "section") {
                decorations.push(
                  Decoration.node(pos, pos + node.nodeSize, { class: "my-section" })
                );
              }
            });
            return DecorationSet.create(state.doc, decorations);
          }
        }
      }),
      css: `.my-section { border-left: 3px solid #ccc; padding-left: 8px; }`
    };
  };
  ```

  **Exemple : création d’un module externe de décoration de widget (texte d’affichage en ligne)**

  ```js
  const xrefPluginKey = new guides.editor.prosemirror.state.PluginKey("xrefDisplay");
  
  const createXrefPlugin = () => {
    const { Plugin } = guides.editor.prosemirror.state;
    const { Decoration, DecorationSet } = guides.editor.prosemirror.view;
  
    return {
      plugin: new Plugin({
        key: xrefPluginKey,
        props: {
          decorations(state) {
            const decorations = [];
            state.doc.descendants((node, pos) => {
              if (node.type.name.includes("xref")) {
                const display = node.attrs?.xmlAttrs?.placeholdertext;
                if (display) {
                  decorations.push(
                    Decoration.widget(pos + 1, () => {
                      const el = document.createElement("span");
                      el.textContent = `[${display}]`;
                      el.setAttribute("contenteditable", "false");
                      return el;
                    }, { key: `xref-${pos}` })
                  );
                }
              }
            });
            return DecorationSet.create(state.doc, decorations);
          }
        }
      }),
      css: `.xref-display-text { color: #0074d9; pointer-events: none; }`
    };
  };
  ```

## Injection de CSS dans l’éditeur

L’éditeur DITA Guides charge ses styles de contenu en mode création à partir d’une bibliothèque cliente avec des `apps.guides.dita_editor.content` de catégorie. Cette bibliothèque cliente possède une déclaration `embed` qui extrait automatiquement toute bibliothèque cliente enregistrée sous la catégorie :

```
apps.guides.xml_editor.dita_content_overrides
```

Pour injecter un CSS personnalisé dans la zone de contenu de l’éditeur, créez un nœud de bibliothèque cliente AEM avec cette catégorie. Aucun câblage supplémentaire n’est nécessaire, Guides le sélectionne automatiquement au chargement de la page de l’éditeur.

**Structure de nœud clientlib AEM (`/apps/my-extension/clientlibs/editor-content-overrides/.content.xml`)**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:cq="http://www.day.com/jcr/cq/1.0"
          xmlns:jcr="http://www.jcp.org/jcr/1.0"
    jcr:primaryType="cq:ClientLibraryFolder"
    categories="[apps.guides.xml_editor.dita_content_overrides]"/>
```

Placez votre fichier CSS (`css.txt` + votre fichier `.css`) dans ce dossier. Elle sera automatiquement incorporée dans la feuille de style de contenu de l’éditeur.

**Exemple : remplacement des styles d’en-tête de section en mode création**

```css
/* /apps/my-extension/clientlibs/editor-content-overrides/css/content.css */

/* Increase section title font size in author mode */
.section > title {
  font-size: 1.4em;
  font-weight: bold;
  color: #333;
}

/* Highlight note blocks */
.note {
  border-left: 4px solid #0074d9;
  padding-left: 12px;
  background: #f0f7ff;
}
```

>[!NOTE]
>
>Ce CSS cible uniquement la surface de création héritée basée sur CKEditor. Il n’a aucun effet dans le nouvel éditeur (ProseMirror), qui utilise un DOM fantôme.


### Nouvel éditeur : `css` dans `registerPlugin`

Le rendu du nouvel éditeur s’effectue dans un **DOM fantôme**, ce qui l’isole de tous les styles au niveau de la page, y compris des `clientlibs` AEM. Pour injecter le code CSS dans la surface de création du nouvel éditeur, transmettez une chaîne `css` dans le cadre du `PluginConfig` renvoyé par votre fabrique de modules externes.

Le CSS est injecté sous la forme d’une balise `<style>` directement à l’intérieur de la racine fantôme de l’éditeur chaque fois qu’une instance d’éditeur est créée.

**Exemple : injecter des styles avec un module externe de décoration**

```js
guides.ready(() => {
  guides.editor.registerPlugin(() => ({
    plugin: createMyPlugin(), // your ProseMirror plugin
    css: `
      /* Styles scoped to the New Editor shadow DOM */
      .section > .title-node {
        font-size: 1.4em;
        font-weight: bold;
        color: #333;
      }

      .note-node {
        border-left: 4px solid #0074d9;
        padding-left: 12px;
        background: #f0f7ff;
      }
    `
  }));
});
```

**Exemple : plug-in CSS uniquement (pas de logique de décoration)**

```js
guides.ready(() => {
  guides.editor.registerPlugin(() => ({
    plugin: new guides.editor.prosemirror.state.Plugin({}), // no-op plugin
    css: `
      /* Custom author-mode typography */
      [data-xml-element="codeblock"] {
        font-family: monospace;
        background: #f5f5f5;
        padding: 8px;
        border-radius: 4px;
      }
    `
  }));
});
```

>[!NOTE]
>
> Ce CSS s’applique uniquement dans le DOM fantôme du nouvel éditeur. Cela n’a aucun effet sur le reste de la page ou sur l’éditeur hérité.


## Extensions de menu contextuel (`contextMenuWidget`)

Les extensions peuvent ajouter des éléments au menu contextuel de l’éditeur accessible par un clic droit / chemin de navigation en déclarant un champ `contextMenuWidget` dans leur configuration d’extension. Indique au framework le menu de l’éditeur à cibler.

### Identifiants de widget

| Identifiant du widget | Éditeur |
|---|---|
| `dita_editor_menu` | Surface de création CKEditor héritée (chemin de navigation + menu contextuel d’élément) |
| `markup_editor_menu` | Nouveau chemin de navigation de l’éditeur (ProseMirror) et menu contextuel des éléments |

Les deux widgets sont montés simultanément sur la page. Le framework fait correspondre chaque extension au menu approprié en fonction de ce champ.

> Les extensions peuvent également cibler les deux éditeurs en transmettant un tableau : `contextMenuWidget: ["dita_editor_menu", "markup_editor_menu"]`

### Ancien éditeur : `dita_editor_menu`

Utilisez cette option pour les extensions qui doivent apparaître dans l’ancien menu contextuel de l’éditeur de clés CKE.

```js
const myContextMenuExtension = {
  id: "dita_author_view_menu",
  contextMenuWidget: "dita_editor_menu",
  view: {
    items: [
      {
        displayName: "My Custom Action",
        data: { eventid: "myCustomAction" },
        icon: "textSpaceAfter",
        target: {
          key: "displayName",
          value: "Wrap Element",   // insert after this existing menu item
          viewState: "append",
        },
      },
    ],
  },
  controller: {
    myCustomAction() {
      console.log("Custom action triggered");
    },
  },
};
```

### Nouvel éditeur : `markup_editor_menu`

Utilisez cette option pour les extensions qui doivent apparaître dans le menu contextuel Nouvel éditeur (chemins de navigation et clic droit sur les éléments). Le contrôleur reçoit les événements par l&#39;intermédiaire de `handleExtensionEvent`, qui achemine les gestionnaires locaux vers le contrôleur `markup_editor_menu` et distribue les événements globaux par l&#39;intermédiaire du gestionnaire d&#39;événements d&#39;application.

```js
const myMarkupContextMenu = {
  id: "dita_author_view_menu",
  contextMenuWidget: "markup_editor_menu",
  view: {
    items: [
      {
        displayName: "Edit Cross Reference",
        data: { eventid: "editCrossReference" },
        icon: "link",
        target: {
          key: "displayName",
          value: "Cut",
          viewState: "prepend",
        },
      },
      {
        displayName: "Remove Cross Reference",
        data: { eventid: "removeCrossReference" },
        icon: "deleteOutline",
        target: {
          key: "displayName",
          value: "Edit Cross Reference",
          viewState: "append",
        },
      },
    ],
  },
  controller: {
    editCrossReference() {
      // Use guides.editor APIs to read context
      const ancestorXpaths = guides.editor.runUtil("getAncestorXpaths", true);
      // open dialog or take action...
    },
    removeCrossReference() {
      guides.editor.runCommand("unwrapNode");
    },
  },
};
```

## Bibliothèques utilitaires

- `guides.util.lodash`:The bibliothèque utilitaire lodash, même instance fournie avec l’éditeur.

  ```js
  const uniqueIds = guides.util.lodash.uniq(ids);
  ```

- `guides.util.async` : bibliothèque utilitaire asynchrone pour l’utilisation de l’extension.

  ```js
  guides.util.async.parallel([task1, task2], callback);
  ```

## Référence API complète

| API | Description |
|---|---|
| `filePath` | Récupérer le chemin d&#39;accès au fichier du document actif |
| `version` | Obtenir la chaîne de version de l’éditeur chargée |
| `appState(key)` | Lire une valeur à partir du modèle d’application |
| `focus()` | Mettre au point l’éditeur actif |
| `canInsertXmlElement(tag, insertAfter?)` | Vérifier si un élément peut être inséré au niveau du curseur |
| `selectCurrentBlockElement()` | Sélectionner l’élément du bloc actif |
| `getValidElementNamesForInsertion(args)` | Liste des noms d’éléments valides à insérer |
| `updateAttributeByXpath(args)` | Mise à jour d’un attribut par XPath |
| `runCommand(name, ...args)` | Exécuter une commande d’éditeur nommé |
| `canRunCommand(name, ...args)` | Vérifier si une commande peut s’exécuter |
| `runUtil(name, ...args)` | Appeler un utilitaire d’éditeur nommé |
| `addDecoration(id, selector, options)` | Ajouter ou remplacer une règle de décoration nommée sur les éléments correspondants |
| `removeDecoration(id)` | Supprimer une règle de décoration par ID |
| `batchDecorations(changes)` | Appliquer plusieurs modifications de décoration en une seule intervention |
| `clearDecorations()` | Supprimer toutes les règles de décoration actives |
| `getDecorations()` | Obtention des identifiants de toutes les décorations actuellement actives |
| `registerPlugin(factory)` | Enregistrez une fabrique de plug-ins ProseMirror (également le mécanisme d’injection CSS de shadow DOM). |
| `prosemirror.state` | package `prosemirror-state` |
| `prosemirror.model` | package `prosemirror-model` |
| `prosemirror.view` | package `prosemirror-view` |
| `prosemirror.transform` | package `prosemirror-transform` |
| `prosemirror.commands` | package `prosemirror-commands` |
| `prosemirror.keymap` | package `prosemirror-keymap` |
| `prosemirror.history` | package `prosemirror-history` |
| `prosemirror.tables` | package `prosemirror-tables` |
| `prosemirror.dropcursor` | package `prosemirror-dropcursor` |
| `prosemirror.collab` | package `prosemirror-collab` |
| `prosemirror.markdown` | package `prosemirror-markdown` |
