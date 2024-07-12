---
title: Configurez le mappage basé sur JSON entre une rubrique et un modèle de fragment d’expérience.
description: Découvrez comment configurer le mappage basé sur JSON entre une rubrique et un modèle de fragment d’expérience.
feature: Output Generation
role: Admin
level: Experienced
exl-id: 2b59db60-61b5-4a7e-bbf1-35cab8b89323
source-git-commit: d525775afeeb89754762ff514126b1c3a3307b3f
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Création d’un mappage entre une rubrique et un fragment d’expérience

Adobe Experience Manager Guides fournit la fonctionnalité permettant de créer un mappage JSON entre une rubrique et un modèle de fragment d’expérience. Vous pouvez utiliser ce mappage pour publier du contenu présent dans certains éléments ou tous les éléments d’une rubrique sur un fragment d’expérience.

1. Pour télécharger le fichier *experienceFragmentMapping.json*, connectez-vous à Adobe Experience Manager en tant qu’administrateur.
1. Sélectionnez le lien Adobe Experience Manager en haut et choisissez **Outils**.
1. Sélectionnez Guides dans la liste des outils et sélectionnez le **Profil de dossier**.
1. Sélectionnez la mosaïque de profil que vous souhaitez configurer. Vous pouvez configurer le mappage pour le profil global ou au niveau du dossier. Par exemple, sélectionnez la mosaïque **Profil global** .
1. Sélectionnez l’onglet **Configuration de l’éditeur XML** et sélectionnez l’icône **Modifier** en haut.
1. Sélectionnez l’icône **Télécharger** pour télécharger le fichier *experienceFragmentMapping.json* sur votre système local. Vous pouvez ensuite apporter des modifications au fichier, puis charger le même fichier.

1. Vous devez suivre les validations suivantes :

   1. Il doit s’agir d’un fichier JSON
   2. Il doit contenir un tableau contenant au moins un objet et chaque objet doit contenir les éléments suivants :


      `"template": string `

      `"mapping": array`

      Chaque objet de mappage doit contenir les éléments suivants :

      `"name": string`

      `"class": string`

      `"resourceType": string`

      `"attributeMap": array`


1. Enregistrez le fichier et téléchargez-le.

Experience Manager Guides convertit la rubrique complète en HTML qui peut ensuite être mappée aux composants principaux utilisés dans le fragment d’expérience. Par exemple, le contenu d’une balise `<p>` peut être mappé pour créer un composant de texte dans le fragment d’expérience.
* `name` : spécifiez l’élément HTML. Par exemple, `<div>`, `<img>`.
* `class` : spécifiez la balise de l’élément DITA correspondant à l’élément HTML. Par exemple, `<p>` `<image>`
* `resourceType` : spécifiez le type de ressource applicable pour le composant utilisé dans le fragment d’expérience. Par exemple, `wcm/foundation/components/text` est le resourceType du composant wcm `text`.
* `attributeMap` : fournissez des informations supplémentaires au composant, par exemple si un composant de texte doit être rendu en tant que `RichText` ou contient le `fileReference` d’un composant d’image.




Exemple de fichier :

```
[
  {
    "template": "default",
    "mapping": [
      {
        "name": "#element",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      }
    ]
  },
  {
    "template": "/conf/we-retail/settings/wcm/templates/experience-fragment-web-variation",
    "mapping": [
      {
        "name": "div",
        "class": "title",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "h1, h2, h3, h4, h5, h6",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "div",
        "class": "p",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "img",
        "class": "image",
        "resourceType": "wcm/foundation/components/image",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "fileReference"
          }
        ]
      },
      {
        "name": "#element",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      }
    ]
  }
]
```



Lors de la publication des fragments d’expérience à partir de l’éditeur web, sélectionnez `Template` dans la liste déroulante de la boîte de dialogue **Générer le fragment d’expérience** pour afficher le mappage disponible pour le modèle dans le champ **Mapping**. Si aucun mappage personnalisé n’est présent pour un modèle, le mappage par défaut est répertorié. Vous pouvez utiliser le mappage par défaut pour publier l’ensemble de la rubrique en tant que fragment d’expérience.

Pour plus d’informations, voir [Fragments d’expérience Publish](../user-guide/publish-experience-fragment.md).
