---
title: Notes de mise à jour | Nouveautés de la version de février 2026 du contenu Formation et apprentissage du produit
description: Découvrez les fonctionnalités nouvelles et améliorées de la version de février 2026 des contenus de formation et d’apprentissage du produit
role: Leader
hidefromtoc: true
source-git-commit: 16e7f12ddc9e72e4344bf98e65718c0f3681b348
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 0%

---

# Version de février 2026 du contenu de formation et d’apprentissage du produit

Cette note de mise à jour couvre les nouvelles améliorations apportées aux fonctionnalités et les nouveaux problèmes résolus dans la version de février 2026 du contenu de formation et d’apprentissage du produit.

## Améliorations des nouvelles fonctionnalités

Les fonctionnalités suivantes ont été introduites dans la version de février 2026 des contenus de formation et d’apprentissage du produit :

- **Prise en charge des sous-titres** : vous pouvez désormais ajouter des sous-titres à votre contenu d’apprentissage à l’aide de la nouvelle option **Ajouter un sous-titre** dans **Propriétés du fichier**. Cela améliore la clarté et la capacité de recherche dans le contenu du cours.

  Pour plus d’informations, consultez [Ajouter un titre et un sous-titre au contenu de formation](../learning-content/lc-basic-blocks.md#add-title-and-subtitle-to-learning-content).

  ![](assets/add-subtitles.png)

- **Activer ou désactiver le score négatif final** : lors de la configuration des propriétés du quiz, vous pouvez contrôler le score négatif à l’aide de l’option **Autoriser le score négatif final**. Lorsque cette option est activée, les élèves obtiennent un score final minimal de zéro, même si une notation négative est appliquée. Les élèves restent ainsi motivés, car les scores ne doivent jamais descendre en dessous de zéro.

  En savoir plus sur les [propriétés du quiz](../learning-content/quiz-properties.md).

  ![](assets/negative-scores-lc.png)

- **Supprimer les widgets par un clic droit** : en plus de supprimer les questions du quiz, vous pouvez désormais supprimer des widgets tels que les accordéons, les cartes retournées et d’autres widgets avec **Clic droit > Supprimer l’élément**. Cette amélioration étend la fonctionnalité existante *Supprimer la question* aux widgets, ce qui vous permet de les supprimer avec moins de clics et une navigation minimale.

  En savoir plus sur [Utilisation de widgets interactifs](../learning-content/lc-widgets.md).

  ![](assets/delete-widget-items.png)
- **Épingler les choix de réponses** : vous pouvez désormais épingler des choix de réponses spécifiques afin que leur position reste inchangée, même lorsque les réponses sont randomisées pendant la génération de la sortie SCORM. Cela s’avère particulièrement utile pour les options telles que *Tout ce qui précède* ou *Aucun ce qui précède*.

  En savoir plus sur les [Propriétés de la question](../learning-content/quiz-insert-questions.md#question-properties).

  ![](assets/pin-question.png)
- **Type de réponse courte** : le type de question à réponse courte permet aux élèves de répondre à l’aide de réponses alphanumériques brèves et descriptives au lieu de sélectionner des options prédéfinies. Ce type de question encourage les élèves à se rappeler et à articuler activement leur compréhension dans leurs propres mots, rendant les évaluations plus attrayantes pour les élèves.

  En savoir plus sur les [types de questions](../learning-content/quiz-insert-questions.md#question-types).


  ![](assets/short-answer.png)
- **Tentative séquentielle pour les questions du quiz** : vous pouvez désormais appliquer des tentatives séquentielles de quiz pour la sortie SCORM à l’aide de l’option **Les élèves doivent tenter chaque question pour continuer** dans le paramètre prédéfini de sortie SCORM. Lorsque cette option est activée, les élèves doivent répondre à chaque question avant de passer à la question suivante, avec une navigation limitée jusqu’à ce que la question actuelle soit terminée. Cela garantit un flux d’évaluation guidé et détaillé, ainsi qu’une expérience d’apprentissage cohérente.

  Pour plus d’informations, consultez [Configuration du paramètre prédéfini de sortie SCORM](../learning-content/config-scorm-preset.md).

  ![](assets/scorm-general-tab-v3.png)

## Problèmes résolus

Les problèmes suivants ont été corrigés dans la version de février 2026 du contenu Formation et apprentissage du produit :

- Lors de la publication de la sortie SCORM et de son déploiement sur ALM, le rapport de quiz L2 affiche un total et un maximum incorrects pour les quiz qui utilisent plusieurs tentatives et une sélection aléatoire de banques de questions. (GUIDES-38855)
- Lorsqu’un cours est généré sur le serveur cloud, un espace blanc involontaire s’affiche sous le pied de page de copyright en raison de la feuille de style `coralui3.css`, ce qui entraîne une incohérence de la mise en page. (GUIDES-38853)
- Lorsque vous naviguez dans le cours d’apprentissage avec un accordéon à l’aide du clavier, le signe + ou le titre de l’onglet n’est pas mis en surbrillance, ce qui empêche l’identification visuelle de l’élément actif. (GUIDES-38852)
- Pour les cours générés à l’aide du modèle carbone SCORM ou du modèle par défaut, lorsqu’ils sont accessibles sur un appareil mobile en mode paysage, la table des matières (menu du cours) n’affiche pas les liens du module, ce qui empêche la navigation. (GUIDES-38851)
- Lors de la réplication de la hiérarchie pour un cours dans Experience Manager Guides, la création d’un objet d’apprentissage nécessite d’abord de créer un groupe d’apprentissage, car les ajouts au niveau de l’objet ne sont pas pris en charge. (GUIDES-38849)
- Les tentatives d’accès aux options de liste déroulante dans Faire correspondre le type de question suivant à l’aide du clavier échouent, car les options ne répondent pas à la touche de tabulation ou de flèche empêchant la navigation. (GUIDES-38985)
- L’application d’un paramètre prédéfini de style d’en-tête entraîne la disparition du texte sélectionné, probablement en raison de la couleur blanche de la police, ce qui rend le texte non sélectionnable et non visible. (GUIDES-39981)
- Lors de l’utilisation de Experience Manager Guides sur Mozilla Firefox, la carte Retourner affiche le texte au recto et au verso après le retournement. (GUIDES-39983)
- Lorsque vous cliquez sur la Table des matières (table des matières) dans le volet de gauche du cours, le cours continue d’afficher l’état d’achèvement même si le quiz a échoué. (GUIDES-40398)
- Si vous tentez de faire correspondre le type de question suivant dans un quiz de manière incorrecte dans ALM, les options sélectionnées n’apparaissent pas dans le rapport. (GUIDES-38640)
- Lors de la génération de la sortie PDF, les styles de création appliqués ne sont pas conservés, ce qui entraîne des incohérences dans la conception. (GUIDES-38642)

