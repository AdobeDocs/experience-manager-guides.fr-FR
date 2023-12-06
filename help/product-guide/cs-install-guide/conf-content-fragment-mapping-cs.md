---
title: Configurez le mappage basé sur JSON entre une rubrique et un modèle de fragment de contenu.
description: Découvrez comment configurer le mappage basé sur JSON entre une rubrique et un modèle de fragment de contenu.
exl-id: 438e2964-b9c7-462a-a68c-8031bd97911c
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# Créer un mappage entre une rubrique et un fragment de contenu

AEM Guides fournit la fonctionnalité permettant de créer un mappage JSON entre une rubrique et un modèle de fragment de contenu. Vous pouvez utiliser ce mappage pour publier du contenu présent dans certains éléments ou tous les éléments d’une rubrique sur un fragment de contenu.

1. Pour télécharger le *contentFragmentMapping.json*, connectez-vous à Adobe Experience Manager en tant qu’administrateur.
1. Sélectionnez le lien Adobe Experience Manager dans la partie supérieure et choisissez **Outils**.
1. Sélectionnez Guides dans la liste des outils, puis sélectionnez l’option **Profils de dossier**.
1. Sélectionnez la variable **Profil global** mosaïque.
1. Sélectionnez la variable **Configuration de l’éditeur XML** et sélectionnez l’option **Modifier** en haut.
1. Sélectionnez la variable **Télécharger** pour télécharger l’icône *contentFragmentMapping.json*  sur votre système local. Vous pouvez ensuite apporter des modifications au fichier, puis charger le même fichier.

1. Vous devez suivre les validations suivantes :

   1. Il doit s’agir d’un fichier JSON
   2. Il doit contenir un tableau contenant au moins un objet et chaque objet doit contenir les éléments suivants :


      `"name": string `

      `"mapping": array`

      Chaque objet de mappage doit contenir les éléments suivants :

      `"modelField": string`

      `"xpath": string`

      `"outputType": string`
1. Enregistrez le fichier et téléchargez-le.

Exemple de fichier :

```
[
  {
    "mapping": [
      {
        "modelField": "title",
        "xpath": "/topic[1]/title[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "shortdesc",
        "xpath": "/topic[1]/shortdesc[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "topicData",
        "xpath": "/topic[1]/body[1]",
        "outputType": "outerHTML"
      }
    ],
    "name": "Full Topic"
  },
  {
    "mapping": [
      {
        "modelField": "title",
        "xpath": "/topic[1]/title[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "shortdesc",
        "xpath": "/topic[1]/shortdesc[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "heroImage",
        "xpath": "/topic[1]/body[1]/p[1]/image[1]",
        "outputType": "outerHTML"
      },
      {
        "modelField": "dataTable",
        "xpath": "/topic[1]/body[1]/table[1]",
        "outputType": "outerHTML"
      }
    ],
    "name": "Sample Example with XPath"
  }
]
```

Vous pouvez publier la rubrique entière avec le mappage par défaut. Sélectionnez la variable `Full Topic` mappage à partir de la liste déroulante dans la variable **Publier en tant que fragment de contenu** et disposer du champ &quot;topicData&quot; dans le modèle de fragment de contenu.
