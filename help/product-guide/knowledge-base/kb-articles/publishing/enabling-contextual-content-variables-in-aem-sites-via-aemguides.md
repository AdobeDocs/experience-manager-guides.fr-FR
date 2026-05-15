---
title: Activation des variables de contenu contextuel (CCVAR) dans les pages AEM Sites générées à partir d’AEM Guides
description: Utilisation des variables de contenu contextuel (CCVAR) dans les pages AEM Sites générées à partir d’AEM Guides
feature: Web Editor
role: User, Admin
exl-id: f9adbb3f-6c1c-4d6f-b55d-1fb45acca91a
TQID: https://experienceleague.adobe.com/ehW4uJQaj3XqejwquxVwFo4vFx6q7qCsVIm6MowolZE
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 497
ht-degree: 3%

---

# Activation des variables de contenu contextuel (CCVAR) dans les pages AEM Sites générées à partir d’AEM Guides

Les variables de contenu contextuel (CCVAR) sont une fonctionnalité d’ACS Commons qui permet aux auteurs d’utiliser des variables de contenu dynamique directement dans leur texte créé. Bien que CCVAR soit couramment utilisé dans AEM Sites, cet article explique comment obtenir des fonctionnalités similaires par le biais de pages générées à partir de contenu créé dans **AEM Guides** *principalement à l&#39;aide de mots-clés définis dans le plan DITA*.


## Que sont les variables de contenu contextuel (CCVAR) ?

La CVAR permet aux créateurs et créatrices d’insérer des variables dynamiques dans leur contenu, qui sont résolues au moment de l’exécution en fonction du contexte. Par exemple, des variables telles que `((page_properties.pageTitle))` peuvent extraire dynamiquement le titre de la page pendant le rendu du contenu.


## Comment activer la fonction CCVAR dans les pages AEM Sites générées à partir d’AEM Guides ?

Étant donné qu’AEM Guides est utilisé comme source de tout le contenu (y compris AEM Sites, PDF ou HTML5), pour activer les CCVAR sur les pages générées à partir d’AEM Guides, vous devez utiliser des mots-clés pour définir le nom de la CCVAR. Pour ce faire dans les guides, définissez **mots-clés** dans votre plan DITA à l&#39;aide d&#39;éléments `<keydef>`. Ces mots-clés peuvent correspondre à des valeurs dynamiques (ou à des noms de CVAR), ce qui vous permet de les référencer dans vos rubriques DITA.


## Conditions préalables

Avant de poursuivre, vérifiez que les conditions préalables suivantes sont remplies :

1. **AEM ACS Commons Installé** :
   - Vérifiez qu’**ACS AEM Commons** est installé sur votre instance AEM. Obligatoire pour l’utilisation de la CCVAR.

2. **Configuration des variables de contenu contextuel** :
   - Terminez la configuration de la **Variables de contenu contextuel** dans AEM à l’aide de la [documentation officielle](https://adobe-consulting-services.github.io/acs-aem-commons/features/contextual-content-variables/index.html). Cela comprend :
      - Activation de l’**agrégation des propriétés**.
      - Configuration de la **réécriture** (si vous utilisez la sortie HTML).
      - Configuration de la **réécriture JSON** (si vous utilisez la sortie JSON).



## Procédure d’activation de la CCVAR dans AEM Guides

### &#x200B;1. Définir des mots-clés dans le plan DITA

- Dans AEM Guides, définissez des mots-clés à l’aide des éléments `<keydef>` dans le plan DITA pour correspondre à la variable CCVAR.
- Par exemple :

```xml
  <keydef keys="product">
    <topicmeta>
      <keywords>
        <keyword>((page_properties.pageTitle))</keyword>
      </keywords>
    </topicmeta>
  </keydef>
```

- L&#39;attribut `keys` (`product` dans cet exemple) sera utilisé pour référencer cette variable dans vos rubriques DITA.


## &#x200B;2. Utiliser des mots-clés dans les rubriques DITA

- Dans la rubrique , utilisez le mot-clé à l’endroit où la CCVar doit être utilisée.
- Par exemple :

```xml
  <p>This is the title of the product: <keyword keyref="product"/> </p>
```

- L’attribut `keyref` pointe vers la valeur `keys` définie dans l’élément `<keydef>` (`product` dans ce cas).
- Lors de la génération de la sortie, le mot-clé est remplacé par la valeur CCVar correspondante.


## &#x200B;3. Générer une sortie

- Lorsque vous générez une sortie pour AEM Sites, les références aux mots-clés sont résolues sur les valeurs dynamiques correspondantes.
- Par exemple :
   - Si `((page_properties.pageTitle))` correspond à `My Product`, la sortie affiche :

```xml
   This is the title of the product: My Product.
```


## Exemple de cas d’utilisation

Supposons que vous souhaitiez insérer de manière dynamique la langue de la page dans vos rubriques DITA. Pour ce faire, procédez comme suit :

**Définissez le mot-clé dans le plan DITA** :

```xml
   <keydef keys="pageLanguage">
     <topicmeta>
       <keywords>
         <keyword>((inherited_page_properties.jcr:language))</keyword>
       </keywords>
     </topicmeta>
   </keydef>
```

**Référencer le mot-clé dans une rubrique DITA** :

```xml
   <p>The title of this page is: <keyword keyref="pageLanguage"/>.</p>
```

**Sortie générée** :

Si `((inherited_page_properties.jcr:language))` correspond à `en`, la sortie affiche :

```
     The language of this page is: en.
```


### Ressources

Pour plus d’informations sur **les variables de contenu contextuelles**, consultez la documentation officielle :\
[Variables de contenu contextuelles dans AEM Commons](https://adobe-consulting-services.github.io/acs-aem-commons/features/contextual-content-variables/index.html)
