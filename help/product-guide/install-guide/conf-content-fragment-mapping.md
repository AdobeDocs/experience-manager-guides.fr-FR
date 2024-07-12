---
title: Configurez le mappage basé sur JSON entre une rubrique et un modèle de fragment de contenu.
description: Découvrez comment configurer le mappage basé sur JSON entre une rubrique et un modèle de fragment de contenu.
exl-id: 21446bcb-e7df-4823-acc3-1fdc7473f0d1
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# Créer un mappage entre une rubrique et un fragment de contenu

AEM Guides fournit la fonctionnalité permettant de créer un mappage JSON entre une rubrique et un modèle de fragment de contenu. Vous pouvez utiliser ce mappage pour publier du contenu présent dans certains éléments ou tous les éléments d’une rubrique sur un fragment de contenu.

1. Pour télécharger le fichier *contentFragmentMapping.json*, connectez-vous à Adobe Experience Manager en tant qu’administrateur.
1. Sélectionnez le lien Adobe Experience Manager en haut et choisissez **Outils**.
1. Sélectionnez Guides dans la liste des outils et sélectionnez le **Profil de dossier**.
1. Sélectionnez la mosaïque **Profil global** .
1. Sélectionnez l’onglet **Configuration de l’éditeur XML** et sélectionnez l’icône **Modifier** en haut.
1. Sélectionnez l’icône **Télécharger** pour télécharger le fichier *contentFragmentMapping.json* sur votre système local. Vous pouvez ensuite apporter des modifications au fichier, puis charger le même fichier.

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

Vous pouvez publier la rubrique entière avec le mappage par défaut. Sélectionnez le mappage `Full Topic` dans la liste déroulante de la boîte de dialogue **Publish as Content Fragment** et indiquez que le champ &quot;topicData&quot; se trouve dans le modèle de fragment de contenu.
