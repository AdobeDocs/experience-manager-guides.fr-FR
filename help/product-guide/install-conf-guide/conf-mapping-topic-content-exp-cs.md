---
title: Configurez le mappage basé sur JSON entre une rubrique et un modèle de fragment d’expérience.
description: Découvrez comment configurer le mappage JSON entre une rubrique et un modèle de fragment d’expérience.
feature: Output Generation
role: Admin
level: Experienced
exl-id: f37cd341-aa8b-4af0-9a40-1d034eea3be6
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 0%
---
# Créer un mappage entre une rubrique et un fragment d’expérience pour Cloud Service

Adobe Experience Manager Guides permet de créer un mappage basé sur JSON entre une rubrique et un modèle de fragment d’expérience. Vous pouvez utiliser ce mappage pour publier dans un fragment d’expérience du contenu présent dans certains éléments d’une rubrique ou dans tous ses éléments.

1. Pour télécharger le fichier *experienceFragmentMapping.json*, connectez-vous à Adobe Experience Manager en tant qu’administrateur.
1. Sélectionnez le lien Adobe Experience Manager en haut et choisissez **Outils**.
1. Sélectionnez Guides dans la liste d’outils, puis sélectionnez le **Profils de dossier**.
1. Sélectionnez la mosaïque de profil à configurer. Vous pouvez configurer le mappage pour le profil global ou au niveau d’un dossier. Par exemple, sélectionnez la mosaïque **Profil global**.
1. Sélectionnez l’onglet **Configuration de l’éditeur XML** et sélectionnez l’icône **Modifier** en haut.
1. Sélectionnez l’icône **Télécharger** pour télécharger le fichier *experienceFragmentMapping.json* sur votre système local. Vous pouvez ensuite apporter des modifications au fichier , puis le charger.

1. Vous devez suivre les validations suivantes :

   1. Il doit s’agir d’un fichier JSON
   2. Il doit contenir un tableau contenant au moins un objet , et chaque objet doit contenir les éléments suivants :


      `"template": string `

      `"mapping": array`

      Chaque objet de mappage doit contenir les éléments suivants :

      `"name": string`

      `"class": string`

      `"resourceType": string`

      `"attributeMap": array`


1. Enregistrez le fichier et chargez-le.

Experience Manager Guides convertit la rubrique complète en HTML qui peut ensuite être mappée aux composants principaux utilisés dans le fragment d’expérience. Par exemple, le contenu d’une balise `<p>` peut être mappé pour créer un composant de texte dans le fragment d’expérience.
* `name` : spécifiez l’élément HTML. Par exemple, `<div>`, `<img>`.
* `class` : spécifiez la balise d&#39;élément DITA correspondant à l&#39;élément HTML. Par exemple, `<p>` `<image>`
* `resourceType` : spécifiez le type de ressource applicable au composant utilisé dans le fragment d’expérience. Par exemple, `wcm/foundation/components/text` est le type de ressource pour le composant `text` de gestion de contenu web.
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



Lors de la publication des fragments d’expérience à partir de l’éditeur, sélectionnez le `Template` dans la liste déroulante de la boîte de dialogue **Générer un fragment d’expérience** pour afficher le mappage disponible pour le modèle dans le champ **Mappage**. Si aucun mappage personnalisé n’est présent pour un modèle, le mappage par défaut est répertorié. Vous pouvez utiliser le mappage par défaut pour publier la rubrique entière en tant que fragment d’expérience.

Pour plus d’informations, consultez [Publication de fragments d’expérience](../user-guide/publish-experience-fragment.md).
