---
title: Configurez le mappage basé sur JSON entre une rubrique et un modèle de fragment de contenu.
description: Découvrez comment configurer le mappage basé sur JSON entre une rubrique et un modèle de fragment de contenu.
exl-id: 438e2964-b9c7-462a-a68c-8031bd97911c
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 97d7776c81e7776d0248d6711ae5d05c46c44239
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 0%

---

# Créer un mappage entre une rubrique et un fragment de contenu



Adobe Experience Manager Guides vous permet de créer un mappage JSON entre une rubrique et un modèle de fragment de contenu. Vous pouvez utiliser le mappage basé sur JSON pour publier du contenu présent dans certains éléments ou tous les éléments d’une rubrique sur un fragment de contenu.

>[!NOTE]
> 
> Si vous utilisez des versions 4.6 ou ultérieures, vous n’avez pas besoin de créer ce mappage, vous pouvez faire glisser les éléments de rubrique vers les champs présents dans le modèle de fragment de contenu.
> Découvrez comment [publier des fragments de contenu](../user-guide/publish-content-fragment.md).


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

Vous pouvez publier la rubrique entière avec le mappage par défaut. Sélectionnez le mappage `Full Topic` dans la boîte de dialogue **Générer un fragment de contenu** et indiquez le champ &quot;topicData&quot; dans le modèle de fragment de contenu.
