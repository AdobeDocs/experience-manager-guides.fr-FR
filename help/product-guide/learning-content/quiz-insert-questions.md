---
title: Insérer des questions dans un quiz
description: Découvrez comment insérer des questions dans un quiz dans la formation et l’apprentissage du produit.
feature: Authoring
role: User
exl-id: dff38476-c078-4970-b967-05a902430015
source-git-commit: 41ea5e91b5ee096ede2eb06dae7a44f01e0c0571
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# Insérer des questions dans un quiz

Pour insérer des questions dans un quiz, procédez comme suit :

1. Sélectionnez le type de question souhaité dans le menu déroulant **Questions** de la barre d’outils. Selon vos besoins, vous pouvez ajouter des questions en utilisant l’un des quatre formats disponibles : Vrai ou Faux, Correction simple, Correction multiple et Correspondance comme illustré ci-dessous. Pour plus d’informations, consultez la section [Types de questions](#question-types).

   ![](assets/question-types.png){width="650" align="left"}

   Lors de l&#39;insertion d&#39;une question, si votre curseur se trouve sur un bloc de questions, la nouvelle question est ajoutée juste après par défaut.

   Pour insérer une question entre les deux questions existantes, commencez [insérez un paragraphe](#insert-paragraph-within-the-quiz), puis insérez des questions.

1. Une question est insérée dans le format sélectionné. Vous pouvez ensuite modifier la question en fonction de vos besoins.

1. Vous pouvez sélectionner n’importe quelle question et configurer ses propriétés à l’aide du panneau **Propriétés du contenu**. Par exemple, vous pouvez spécifier la bonne réponse, définir les notes à attribuer et définir toute pénalité en cas de réponses incorrectes.

   ![](assets/question-properties.png){width="650" align="left"}

1. Enregistrez toutes les modifications apportées au quiz.

## Insérer un paragraphe dans le quiz

Lorsque vous placez le curseur sur une question spécifique ou sur un espace vide entre les deux questions, une ligne horizontale bleue s&#39;affiche avec une flèche bleue dans le coin le plus à droite de l&#39;écran. En sélectionnant la flèche bleue, vous pouvez insérer un paragraphe dans l’interface de création de quiz.

![](assets/insert-paragraph-here-arrow.png){width="650" align="left"}

- Lorsqu’elle est utilisée dans une question, elle vous permet d’ajouter d’autres éléments tels que des images, un tableau, des éléments de texte, etc. dans la question.
- Lorsqu’elle est utilisée entre les questions, elle vous permet d’insérer une autre question ou d’ajouter d’autres éléments de création comme mentionné ci-dessus.

## Supprimer la question ou l’option

Pour supprimer une question ou une option spécifique d’un quiz, procédez comme suit :

1. Cliquez avec le bouton droit sur la question ou l’option à supprimer.
1. Dans le menu contextuel, sélectionnez **Supprimer la question** (pour supprimer la question entière) ou **Supprimer option** (pour supprimer uniquement l’option sélectionnée).

![](assets/delete-options-lc.png){width="650" align="left"}

## Types de questions

Les types de questions suivants sont pris en charge dans un quiz :

- **Correction unique** : question avec plusieurs options pour laquelle une seule réponse est correcte.

  ![](assets/single-correct.png){width="650" align="left"}

- **Vrai/Faux** : question basée sur des instructions où les élèves choisissent s’il s’agit de Vrai ou Faux.

  ![](assets/true-false.png){width="650" align="left"}


- **Correction multiple** : question avec plusieurs options pour laquelle plusieurs réponses peuvent être correctes.

  ![](assets/multi-correct.png){width="650" align="left"}

- **Correspondre aux éléments suivants** : permet aux élèves de faire correspondre des éléments de deux listes afin de former des paires correctes. Vous pouvez ajouter de nouveaux ensembles d’options à partir du panneau **Propriétés du contenu**. Pour augmenter la complexité, vous pouvez supprimer une option de la première liste et inclure une correspondance supplémentaire dans la colonne Correspondance . Cela crée un élément de difficulté en exigeant des élèves qu’ils réfléchissent de manière critique à l’option qui n’a pas de paire directe.

  ![](assets/match-the-following.png){width="650" align="left"}

  Dans la sortie publiée, la question **Faire correspondre le suivant** s’affiche avec un menu déroulant pour chaque élément, ce qui vous permet de sélectionner la correspondance appropriée parmi les options disponibles.

  ![](assets/question-type-publishing.png){width="650" align="left"}