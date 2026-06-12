---
title: Configurez le mappage basé sur JSON entre une rubrique et un modèle de fragment de contenu.
description: Découvrez comment configurer le mappage basé sur JSON entre une rubrique et un modèle de fragment de contenu.
exl-id: 438e2964-b9c7-462a-a68c-8031bd97911c
feature: Output Generation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/w1XQiP79ta2-huLRGIdevylhP7VCYvmmOQVpQgI7w4w
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0id: d6596f3f-92a7-43ec-b444-237db6adad05id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 267
ht-degree: 0%

---

# Créer un mappage entre une rubrique et un fragment de contenu



Adobe Experience Manager Guides vous permet de créer un mappage basé sur JSON entre une rubrique et un modèle de fragment de contenu. Vous pouvez utiliser le mappage basé sur JSON pour publier du contenu présent dans certains éléments d’une rubrique ou dans tous ses éléments dans un fragment de contenu.

>[!NOTE]
> 
> Si vous utilisez la version 4.6 ou une version ultérieure, vous n’avez pas besoin de créer ce mappage. Vous pouvez faire glisser les éléments de la rubrique vers les champs présents dans le modèle de fragment de contenu.
> En savoir plus sur la [publication de fragments de contenu](../user-guide/publish-content-fragment.md).


1. Pour télécharger le fichier *contentFragmentMapping.json*, connectez-vous à Adobe Experience Manager en tant qu’administrateur.
1. Sélectionnez le lien Adobe Experience Manager en haut et choisissez **Outils**.
1. Sélectionnez Guides dans la liste d’outils, puis sélectionnez le **Profils de dossier**.
1. Sélectionnez la mosaïque **Profil global**.
1. Sélectionnez l’onglet **Configuration de l’éditeur XML** et sélectionnez l’icône **Modifier** en haut.
1. Sélectionnez l’icône **Télécharger** pour télécharger le fichier *contentFragmentMapping.json* sur votre système local. Vous pouvez ensuite apporter des modifications au fichier , puis le charger.

1. Vous devez suivre les validations suivantes :

   1. Il doit s’agir d’un fichier JSON
   2. Il doit contenir un tableau contenant au moins un objet , et chaque objet doit contenir les éléments suivants :


      `"name": string `

      `"mapping": array`

      Chaque objet de mappage doit contenir les éléments suivants :

      `"modelField": string`

      `"xpath": string`

      `"outputType": string`
1. Enregistrez le fichier et chargez-le.

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

Vous pouvez publier la rubrique entière avec le mappage par défaut. Sélectionnez le mappage de `Full Topic` dans la liste déroulante **boîte de dialogue Générer un fragment de contenu** et disposez du champ « topicData » dans le modèle de fragment de contenu.
