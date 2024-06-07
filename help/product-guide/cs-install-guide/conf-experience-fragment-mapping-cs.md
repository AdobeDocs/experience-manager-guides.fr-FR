---
title: Configurez le mappage basé sur JSON entre une rubrique et un modèle de fragment d’expérience.
description: Découvrez comment configurer le mappage basé sur JSON entre une rubrique et un modèle de fragment d’expérience.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: f252537d15d7e8f8651dddb0ae635905705e4adf
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Création d’un mappage entre une rubrique et un fragment d’expérience

Adobe Experience Manager Guides permet de créer un mappage JSON entre une rubrique et un modèle de fragment d’expérience. Vous pouvez utiliser ce mappage pour publier du contenu présent dans certains éléments ou tous les éléments d’une rubrique sur un fragment d’expérience.

1. Pour télécharger le *experienceFragmentMapping.json*, connectez-vous à Adobe Experience Manager en tant qu’administrateur.
1. Sélectionnez le lien Adobe Experience Manager dans la partie supérieure et choisissez **Outils**.
1. Sélectionnez Guides dans la liste des outils, puis sélectionnez l’option **Profils de dossier**.
1. Sélectionnez la mosaïque de profil que vous souhaitez configurer. Vous pouvez configurer le mappage pour le profil global ou au niveau du dossier. Par exemple, sélectionnez la variable **Profil global** mosaïque.
1. Sélectionnez la variable **Configuration de l’éditeur XML** et sélectionnez l’option **Modifier** en haut.
1. Sélectionnez la variable **Télécharger** pour télécharger l’icône *experienceFragmentMapping.json*  sur votre système local. Vous pouvez ensuite apporter des modifications au fichier, puis charger le même fichier.

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

Les guides du Experience Manager convertissent la rubrique complète en HTML, qui peut ensuite être mappée aux composants principaux utilisés dans le fragment d’expérience. Par exemple, le contenu d’une `<p>` peut être mappée pour créer un composant de texte dans le fragment d’expérience.
* `name`: spécifiez l’élément de HTML. Par exemple, `<div>`, `<img>`.
* `class`: spécifiez la balise de l’élément DITA correspondant à l’élément de HTML. Par exemple : `<p>` `<image>`
* `resourceType`: spécifiez le type de ressource applicable pour le composant utilisé dans le fragment d’expérience. Par exemple : `wcm/foundation/components/text` est le type de ressource pour le wcm. `text` composant.
* `attributeMap`: fournissez des informations supplémentaires au composant, par exemple si un composant de texte doit être rendu comme `RichText` ou contient le paramètre `fileReference` d’un composant d’image.




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



Lors de la publication des fragments d’expérience à partir de l’éditeur web, sélectionnez la variable `Template` dans la liste déroulante du **Générer un fragment d’expérience** pour afficher le mappage disponible pour le modèle dans la **Mappage** champ . Si aucun mappage personnalisé n’est présent pour un modèle, le mappage par défaut est répertorié. Vous pouvez utiliser le mappage par défaut pour publier l’ensemble de la rubrique en tant que fragment d’expérience.

Pour plus d’informations, voir [Publication de fragments d’expérience](../user-guide/publish-experience-fragment.md).

