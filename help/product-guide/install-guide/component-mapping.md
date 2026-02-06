---
title: Mappage des composants pour AEM Sites
description: Découvrez comment effectuer le mappage des composants pour AEM Sites
feature: Installation
role: Admin
level: Experienced
exl-id: 376aea7a-7850-44d4-a620-6b1a798a0801
source-git-commit: beb1ca15fdfb0e7ea30e6e685ac67a2a398cc064
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 0%

---

# Mappage des composants pour AEM Sites

L’article aborde les différents aspects du mappage des composants pour les sites AEM (à l’aide du mappage des composants composites).

## Règles de mappage des composants

Utilisez un tableau JSON de règles (votre `componentmapping.json`) pour convertir HTML en composants. Veillez à ce que les règles soient aussi simples, explicites et spécifiques que possible.

### Cibler l’élément HTML et sa classe

- Écrivez le nom de balise HTML en `name`.
- Incluez la classe CSS appliquée à cet élément dans `class`, si la classe existe.
Exemple :

  ```html
  <div class ="sample-class">
  <p> Sample html element </p>
  </div>
  ```

  ```json
  {
  "name": "div",
  "class": "sample-class",
  "resourceType": "guides-components/components/table",
  "attributeMap": []
  }
  ```

Lors de la définition des éléments ci-dessus, assurez-vous des points suivants :

- `name` peut s’agir d’une liste séparée par des virgules (par exemple, `"h1, h2"`).
- `class` doit être présent sur l’élément (toutes les classes répertoriées doivent correspondre).
- `resourceType` indique que vous avez l’intention d’utiliser le composant `table`. Le package `guides-components` est une version prête à l’emploi fournie par Guides. Vous pouvez également utiliser d’autres packages de composants, tels que `core/wcm/`, si nécessaire.

### Utilisez attributeMap pour enregistrer les propriétés sur le nœud JCR

Ajoutez des entrées à `attributeMap` pour définir des propriétés sur le nœud de sortie. Chaque entrée génère des `attrs[to] = value`.
Modèles courants :

```json
// copy an attribute
{ "attribute": "src", "to": "image-src" }
// read content or tag name
{ "from": "textContent", "to": "jcr:title" }
{ "from": "outerHTML",  "to": "text" }
{ "from": "innerHTML",  "to": "text" }
{ "from": "name",       "to": "type" }  // the tag name, e.g., "h2"
// constant value
{ "value": true, "to": "textIsRich" }
```

Vous trouverez ci-dessous un exemple d’HTML au format JSON pour un élément d’image.

```html
<img src="/content/dam/aemg-docs/tragopan.svg" class="cmp-image__image" itemprop="contentUrl" data-cmp-hook-image="image" alt="">
```

```json
{
    "name": "img",
    "resourceType": "core/wcm/components/image/v2/image",
    "attributeMap": [
      {
        "from": "src",
        "to": "fileReference"
      },
      {
        "value": ["fileReference"],
        "to": "path-attributes"
      }
    ]
  }
```

### Normalisation des chemins via une entrée dédiée

Si vous souhaitez normaliser (rendre absolues) les valeurs, déclarez les clés d’attribut qui doivent être normalisées en utilisant :

```json
{
  "value": ["text"],
  "to": "path-attributes"
}
```

Veillez à tenir compte des points importants suivants :

- Insérez la liste des noms de propriété que vous souhaitez normaliser dans `value` (par exemple, `["text"]` ou `["href", "src"]`).
- Le système normalisera toutes les valeurs trouvées sous ces noms de propriété lors de la création du composant final.


### Extraire des valeurs HTML avant de diviser en composants

Utilisez `from` pour spécifier comment lire une valeur à partir de l’élément avant que le document ne soit divisé en composants distincts :

- `"textContent"` : texte brut de l’élément
- `"outerHTML"` : l’élément et son balisage interne
- `"innerHTML"` : balisage interne de l’élément uniquement
- Toute autre chaîne : traitée comme un nom d’attribut (par exemple, `"src"`, `"href"`)


Exemples :

```json
{ "from": "textContent", "to": "jcr:title" }
{ "from": "outerHTML",  "to": "text" }
{ "from": "innerHTML",  "to": "snippet" }
{ "from": "src",        "to": "image#src" }
```

### Exemple complet minimal dans componentmapping.json

```json
[
  {
    "name": "h1, h2",
    "class": "topic-title",
    "resourceType": "core/wcm/components/title/v2/title",
    "attributeMap": [
      { "from": "textContent", "to": "text" },
      { "from": "name",        "to": "type" }
    ]
  },
  {
    "name": "img",
    "class": "hero",
    "resourceType": "weretail/components/content/heroimage",
    "attributeMap": [
      { "from": "src", "to": "image#src" },
      { "value": ["image#src"], "to": "path-attributes" }
    ]
  },
  {
    "name": "#element",
    "resourceType": "core/wcm/components/text/v2/text",
    "attributeMap": [
      { "from": "outerHTML", "to": "text" },
      { "value": true,        "to": "textIsRich" }
    ]
  }
]
```

Définissez l’élément et la classe à cibler, utilisez `attributeMap` pour définir les propriétés du nœud, ajoutez une entrée de `path-attributes` pour normaliser les chemins d’accès et sélectionnez le `from` approprié pour les valeurs que vous souhaitez extraire. L’`heroimage` utilisé ci-dessus est un composant d’un site `we-retail`.

**Remarque** : il est important de discuter du texte enrichi par défaut et d’identifier les éléments pour lesquels il est utilisé.

## Créer un composant personnalisé

Découvrez comment créer un composant de tableau personnalisé qui affiche des images dans ses cellules. Cette approche garantit une conception propre et réutilisable pour le contenu dynamique. Il couvre ce que vous allez créer, ses raisons d’efficacité, les principales conditions préalables, la conception de haut niveau, etc.

### Ce que vous allez créer

Composant de tableau personnalisé qui accepte le contenu du tableau HTML et qui remplace chaque `<img>` qu’il contient par la sortie du composant Image principal AEM. Vous pouvez ainsi réutiliser les fonctionnalités de Core Image (images réactives, gestion des alternatives, accessibilité) tout en gardant un contrôle total sur les balises de votre tableau.
Grâce à cette approche, vous pouvez créer d’autres composants personnalisés pour votre site web AEM (à l’aide du mappage des composants composites).

### Pourquoi cette approche

- **Réutilisation** : utilisez le comportement mature de l’image principale au lieu de la réimplémenter.
- **Cohérence** : les images de votre tableau se comportent de la même manière que les images ailleurs sur le site.
- **Côté serveur** : les images sont rendues sur le serveur pour des raisons de performances, d’optimisation du moteur de recherche et d’accessibilité.

### Prérequis

- AEM SDK en cours d’exécution et ce projet a été extrait.
- Composants principaux installés sur votre instance AEM.
- Maven disponible pour génération et déploiement.

### Conception de haut niveau.

- L’auteur fournit HTML pour le tableau dans la boîte de dialogue du composant.
- Un modèle Sling analyse cette HTML, détecte les balises `<img>` et, pour chaque image, appelle un service qui effectue le rendu du composant Image principal côté serveur.
- Le modèle permute le `<img>` d’origine avec l’image principale HTML capturée et transmet l’HTML terminée à HTL pour la sortie.

Votre tableau est généré une seule fois, contenant déjà le balisage de l’image principale. Aucune manipulation DOM côté client n’est nécessaire.

### Structure des dossiers et fichiers de clé (dans ce référentiel)

- HTL du composant et clientlibs : `ui.apps/src/main/content/jcr_root/apps/guides-components/components/table/`
   - `table.html` (rendu HTL)
   - `_cq_editConfig.xml` (actualiser les écouteurs)
   - `clientlibs/` avec `css.txt`, `js.txt`, `css/table.css`, `js/table.js`
- Modèle Sling : `core/src/main/java/com/adobe/guides/aem/components/core/models/TableModel.java`
- Service de rendu d&#39;image : `core/src/main/java/com/adobe/guides/aem/components/core/services/ImageComponentRenderer.java`

### Étapes de mise en œuvre

**Définissez le composant Tableau (nœud de composant)**

Créez le composant sous `apps/guides-components/components/table`. Si vous n’en avez pas encore, ajoutez une `.content.xml` minimale comme ci-dessous pour l’enregistrer dans le panneau latéral.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          xmlns:jcr="http://www.jcp.org/jcr/1.0"
          jcr:primaryType="cq:Component"
          jcr:title="Table"
          componentGroup="Guides - Custom"/>
```

Indique à AEM qu’il s’agit d’un composant que les auteurs peuvent ajouter aux pages.

**Rendu avec HTL et inclusion des styles**

Utilisez un modèle Sling et générez les HTML traitées. Incluez votre catégorie de bibliothèque cliente pour CSS/JS.

```html
<sly data-sly-use.model="com.adobe.guides.aem.components.core.models.TableModel"
     data-sly-use.clientLib="/libs/granite/sightly/templates/clientlib.html">
</sly>
<sly data-sly-call="${clientLib.css @ categories='guides-components.table'}"></sly>
<sly data-sly-test="${wcmmode.edit && !model.hasContent}">
  <div class="cq-placeholder" data-emptytext="${component.title}"></div>
</sly>
<div data-sly-test="${model.hasContent}"
     class="gu-table-wrapper ${model.enableResponsive ? 'gu-table--responsive' : ''} gu-table--style-${model.tableStyle}"
     id="${model.componentId}">
  ${model.processedTableHtml @ context='unsafe'}
</div>
```

Le modèle renvoie un HTML complet avec une image principale déjà rendue, donc HTL l’imprime simplement.

**Ajouter le modèle Sling pour traiter HTML et effectuer le rendu de l’image principale**

Le modèle lit les champs de la boîte de dialogue, analyse le tableau HTML, recherche chaque `<img>` et le remplace par Core Image HTML via un service.

Voici quelques-uns des savoir-faire importants pour `TableModel` :

- Lit les `tableHtml`, les `enableResponsive` et les `tableStyle` à partir des propriétés des ressources.
- Utilise Jsoup pour analyser et modifier HTML en toute sécurité.
- Appelle `ImageComponentRenderer` pour effectuer le rendu de l’image principale et capturer HTML.
- Préserve les classes et le style CSS du `<img>` d’origine.
- Normalise les chemins d’accès DAM (supprime les `/jcr:content/renditions/*`).

```java
@Model(adaptables = {Resource.class, SlingHttpServletRequest.class},
       defaultInjectionStrategy = DefaultInjectionStrategy.OPTIONAL)
public class TableModel {
  @ValueMapValue private String tableHtml;
  @ValueMapValue private boolean enableResponsive;
  @ValueMapValue private String tableStyle;
  @OSGiService private ImageComponentRenderer imageRenderer;
  // ...
  @PostConstruct
  protected void init() {
    // parse HTML, for each <img> build image props (fileReference, alt, title)
    // call imageRenderer.renderImageComponent(...)
    // replace <img> with returned Core Image HTML
  }
  public String getProcessedTableHtml() { /* return final HTML */ }
}
```

Cela centralise la logique sur le serveur et réutilise le comportement de l’image principale.

**Rendu d’image principale via un service (inclusion côté serveur)**

`ImageComponentRenderer` effectue le rendu du composant Image principal et capture la sortie. It

- enveloppe une ressource qui force la `core/wcm/components/image/v2/image`.
- utilise `RequestDispatcher#include` pour effectuer le rendu.
- capture la réponse sous forme de chaîne.

```java
@Component(service = ImageComponentRenderer.class)
public class ImageComponentRenderer {
  private static final String IMAGE_RESOURCE_TYPE = "core/wcm/components/image/v2/image";
  public String renderImageComponent(Resource base, Map<String,Object> props,
                                     SlingHttpServletRequest req, SlingHttpServletResponse resp) {
    // create wrapped resource with IMAGE_RESOURCE_TYPE and props
    // dispatcher.include(...) with a response wrapper to capture HTML
    // return captured HTML
  }
}
```

Vous pouvez ainsi **déposer** l’image principale où vous en avez besoin, et pas seulement en tant que composant enfant.

**Bibliothèques clientes**

Créez une bibliothèque cliente pour les petits styles ou les futurs JS. Le HTL ci-dessus charge la catégorie `guides-components.table` .

```java
clientlibs/css.txt
  #base=css
  table.css
clientlibs/js.txt
  #base=js
  table.js
  
```

Cela permet de conserver la modularité et la visibilité des styles/scripts.

**Champs de boîte de dialogue (entrées Auteur)**

Ajoutez une boîte de dialogue avec au moins les propriétés suivantes :

- **Table HTML** : `./tableHtml` (textarea) ; HTML de la table.
- **Activer le responsive** : `./enableResponsive` (case à cocher) ; active/désactive une classe wrapper responsive.
- **Style de tableau** : `./tableStyle` (sélectionner) ; applique une classe de modificateur de style.

Ils mappent 1:1 aux propriétés du modèle Sling et contrôlent le rendu.

**Autoriser le composant sur les modèles**

Dans l’éditeur de modèles, modifiez la stratégie du conteneur de mises en page > Composants autorisés > activez votre composant Tableau sous **Guides - Personnalisés**.

Les auteurs ne peuvent pas ajouter de composants tant que les politiques ne les autorisent pas.

## Conseils de création

- Collez une HTML valide pour le tableau. Le modèle assainit et ajuste les URL des images.
- Utilisez des chemins d’accès aux ressources DAM pour les images ; les rendus sont normalisés au chemin d’accès aux ressources d’origine.
- Dans la mesure du possible, fournissez du texte secondaire dans HTML. Dans le cas contraire, les images sont marquées comme décoratives.

## Contraintes

- Le service force Core Image v2. Pour changer de version, mettez à jour `IMAGE_RESOURCE_TYPE`.
- Pour le rendu synthétique, le modèle remplace les URL `.coreimg.` générées par Core Image par des chemins d’accès directs à la gestion des ressources numériques et supprime les `srcset` pour éviter les URL rompues.
- Tous les rendus s’effectuent une seule fois sur le serveur ; JavaScript est facultatif.

## Référence rapide (implémentation)

- HTML : `ui.apps/.../components/table/table.html`
- Clientlibs : `ui.apps/.../components/table/clientlibs/`
- Modèle : `core/.../models/TableModel.java`
- Service : `core/.../services/ImageComponentRenderer.java`

Ce modèle montre comment composer un composant personnalisé avec un composant principal côté serveur, en conservant vos balises tout en réutilisant la logique Core.
