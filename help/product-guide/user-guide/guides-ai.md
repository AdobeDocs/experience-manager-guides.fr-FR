---
title: Guides AI pour la fonctionnalité de balisage intelligent
description: Découvrez comment utiliser l’IA dédiée aux guides pour la fonctionnalité de balisage intelligent des rubriques et des cartes en une seule opération.
source-git-commit: b866964c30a565eab0f6f9aec4b3fc9013f15f75
workflow-type: tm+mt
source-wordcount: '1276'
ht-degree: 0%

---


# Prise en main de l’IA dédiée aux guides

>[!NOTE]
>
> L’IA dédiée aux guides est disponible dans Experience Manager Guides as a Cloud Service à partir de la version 2026.08.0. Contactez votre équipe du succès client pour activer cette fonctionnalité.

L’IA dédiée aux guides accélère, facilite et uniformise le balisage de votre contenu. Grâce aux compétences de balisage intelligent dynamique d’Adobe CX Enterprise Coworker, Guides AI analyse votre contenu et recommande des balises pertinentes en fonction de la taxonomie de votre entreprise, au lieu de lire manuellement le contenu pour décider quelles balises s’appliquent. Gardez le contrôle en examinant les balises suggérées et en choisissant de les appliquer ou de les rejeter avant de confirmer votre sélection, ce qui réduit considérablement les efforts manuels, améliore la précision des balises et garantit la cohérence des métadonnées dans l’ensemble de votre documentation.

## Panneau IA dédiée aux guides

Le panneau d’IA de Guides fournit tous les outils dont vous avez besoin pour générer, réviser et appliquer les balises suggérées par l’IA.

![Panneau d’IA pour Guides](images/guides-ai-panel.png){width="650"}

Les composants suivants de l’IA dédiée aux guides vous aident à ajouter des fichiers, configurer des recommandations de balises et gérer votre workflow de balisage intelligent :

- **(A)** Historique des conversations : affichez et rouvrez les conversations précédentes pour consulter les recommandations et actions relatives aux balises précédentes.

  ![Guide l’historique des conversations du panneau d’IA](images/chat-history.png){width="350"}

- **(B)** Nouvelle conversation : démarrez une nouvelle session de balisage pour une autre rubrique, un autre mappage ou un autre ensemble de fichiers.
- **(C)** Espace de noms de balise : sélectionnez les espaces de noms de taxonomie à partir desquels l’IA dédiée aux guides doit générer des recommandations de balises. Seules les balises des espaces de noms sélectionnés sont prises en compte.

  ![Guide la taxonomie du panneau IA](images/taxononmy.png){width="350"}

- **(D)** Espace de réponse : passez en revue les recommandations de balises générées par l’IA et choisissez de les accepter, de les rejeter ou de les modifier avant d’appliquer les balises.
- **(E)** Espace d’invite : saisissez une demande d’invite pour générer des recommandations de balises pour le contenu sélectionné.
- **(F)** Joindre des fichiers ou ajouter du contexte : permet d’ajouter des rubriques, des cartes ou des fichiers externes à partir de votre système local pour fournir le contenu que Guides AI doit analyser pour les recommandations de balises.
- Modèle **(G)** : affiche le modèle d’IA utilisé pour analyser le contenu et générer des recommandations de balises. Plusieurs modèles OpenAI et Anthropic Claude peuvent être sélectionnés. Par défaut, l’option **Utiliser le manifeste par défaut** est sélectionnée, et utilise le modèle configuré pour l’assistant sélectionné.
- **(H)** Envoyer : envoyez votre invite et le contenu joint pour générer des recommandations de balises basées sur l’IA.

## Appliquer des balises à une ou plusieurs rubriques avec la compétence de balisage intelligent

Effectuez les étapes suivantes pour utiliser l’IA dédiée aux guides afin d’appliquer des balises à une ou plusieurs rubriques avec la compétence de balisage intelligent :

1. Connectez-vous à Experience Manager Guides.
1. Sur la page d’accueil, sélectionnez **Guides AI** dans la barre de navigation. Assurez-vous que la fonctionnalité Guides AI est activée par votre administrateur.
1. Ajoutez la rubrique pour laquelle vous souhaitez générer des recommandations de balises à l’aide de l’une des méthodes suivantes :

   - **Utilisation d’invites suggérées** : pour la première conversation de la zone Réponse, sélectionnez **Suggérer des balises pour une invite de fichier**. L’invite est automatiquement ajoutée à l’espace Invite . Sélectionnez `[file]`, puis choisissez la rubrique dans le référentiel ou dans une collection de la boîte de dialogue **Sélectionner un fichier**. Vous pouvez sélectionner une rubrique dans la boîte de dialogue **Sélectionner un fichier**.

     ![Panneau IA Access Guides à l’aide des invites suggérées](images/suggested-prompts.png){width="650"}

   - **Utilisation d’un raccourci** : saisissez `/` dans le champ Invite, puis choisissez **Ajouter une référence au référentiel** pour choisir une rubrique dans le référentiel (ou **Ajouter des fichiers à partir de l’appareil** pour charger une rubrique à partir de votre ordinateur) et saisissez l’invite suggérée *Suggérer des balises pour un fichier*.

   - **Glisser-déposer** : faites glisser et déposez une ou plusieurs rubriques dans l’espace Invite, puis saisissez l’invite *Suggérer des balises pour un fichier*.

     ![accédez au panneau d’IA de Guides en faisant glisser et en déposant une rubrique ou un plan](images/dragging-prompts.png){width="650"}

   - **Spécifier les chemins d’accès aux rubriques** : saisissez `@` suivis des chemins séparés par des virgules pour plusieurs rubriques de la même carte ou de cartes différentes, puis saisissez l’invite : *Suggérer des balises pour un fichier*.

     ![Ajout de rubriques en bloc dans le panneau IA dédiée aux guides](images/topics-path-add.png){width="650"}

1. Sélectionnez **Envoyer**.

1. Guides AI analyse le contenu de la rubrique et génère des recommandations de balises.

   ![Interface du panneau Guides AI lors de l’analyse et de la réflexion](images/guides-ai-analysis.png){width="650"}

1. Examinez les balises suggérées comme suit :

   >[!NOTE]
   >
   > Pour les rubriques qui contiennent déjà des balises, l’IA dédiée aux guides affiche les balises existantes. Ces balises sont en lecture seule et ne peuvent pas être modifiées ni supprimées.

   - Pour un seul sujet, vous pouvez simplement **Accepter** les recommandations pour les appliquer ou **Rejeter** si elles ne sont pas nécessaires.

     ![Guide la réponse du panneau de l’IA après analyse du contenu](images/guides-ai-tags-review.png){width="650"}

   - Pour plusieurs rubriques :
     1. Sélectionnez **Aperçu** pour consulter les recommandations de balises générées par l’IA.

        ![Aperçu de l’analyse en bloc du panneau de l’IA Guides](images/topics-tag-preview.png){width="650"}

     1. Passez en revue les balises suggérées pour chaque rubrique, puis choisissez l’une des actions suivantes :
        - **Accepter tout** pour appliquer toutes les balises suggérées à toutes les rubriques.
        - **Rejeter tout** pour ignorer toutes les balises suggérées pour toutes les rubriques.
        - **Effacer toutes les suggestions** pour supprimer toutes les balises suggérées pour une rubrique spécifique.
        - Sélectionnez l’icône **X** en regard d’une balise pour supprimer une suggestion de balise individuelle.

          ![Boîte de dialogue d’aperçu de l’analyse en bloc du panneau Guides AI](images/topics-tag-preview-dialog.png){width="650"}

1. Lorsque vous acceptez les balises suggérées, la compétence Balisage intelligent ajoute les balises générées par l’IA aux balises déjà appliquées au contenu.

Une fois la révision terminée, l’IA dédiée aux guides affiche un résumé des balises appliquées à la rubrique et des recommandations de balises rejetées.

![Résumé des réponses du panneau de l’IA dédiée aux guides](images/topic-tag-summary.png){width="650"}

## Appliquer des balises à plusieurs rubriques d’une carte à l’aide des compétences de balisage intelligent

Effectuez les étapes suivantes pour utiliser l’IA dédiée aux guides afin d’appliquer des balises à plusieurs rubriques d’une carte avec les compétences de balisage intelligent :

1. Connectez-vous à Experience Manager Guides.
1. Sur la page d’accueil, sélectionnez **Guides AI** dans la barre de navigation. Assurez-vous que la fonctionnalité Guides AI est activée par votre administrateur.
1. Ajoutez le mappage pour lequel vous souhaitez générer des recommandations de balises à l’aide de l’une des méthodes suivantes, comme indiqué pour les rubriques :

   - **Utilisation d’invites suggérées** : pour la première conversation de la zone Réponse, sélectionnez **Suggérer des balises pour une invite de fichier**. L’invite est automatiquement ajoutée à l’espace Invite . Sélectionnez `[file]`, puis choisissez le mappage dans le référentiel ou dans une collection de la boîte de dialogue **Sélectionner un fichier**.

   - **Glisser-déposer** : faites glisser et déposez un mappage dans l’espace Invite, puis saisissez l’invite *Suggérer des balises pour un fichier*.

   - **À l’aide d’un raccourci** : saisissez `/` dans le champ Invite, puis choisissez **Ajouter une référence au référentiel** pour choisir une carte dans le référentiel (ou **Ajouter des fichiers à partir de l’appareil** pour charger une carte à partir de votre ordinateur) et saisissez l’invite suggérée *Suggérer des balises pour un fichier*.

     ![Balisage en bloc de l’IA dédiée aux guides](images/ai-map-selection.png){width="650"}

1. Sélectionnez **Envoyer**.
Un message indique que la carte sélectionnée contient plusieurs rubriques. Sélectionnez **Sélectionner les rubriques** pour choisir les rubriques pour lesquelles vous souhaitez obtenir des recommandations de balises.

   ![Guide le balisage en bloc de l’IA lors de la sélection de rubriques](images/ai-select-topics.png){width="650"}

1. Dans la boîte de dialogue **Sélectionner les rubriques**, sélectionnez les rubriques pour lesquelles vous souhaitez des recommandations de balises.\
   La boîte de dialogue **Sélectionner les rubriques** fournit les informations suivantes :

   - **Liste Rubriques :** affiche toutes les rubriques de la carte sélectionnée. Sélectionnez les rubriques pour lesquelles vous souhaitez générer des recommandations de balises.
   - **Volet Aperçu :** affiche un aperçu de la rubrique sélectionnée avec ses balises existantes.
   - **Filtrer :** filtrez les rubriques pour n’afficher que celles contenant **Balises ajoutées** ou **Aucune balise ajoutée**.

     ![Sélection de la boîte de dialogue des rubriques lors de l’application de balises](images/select-dialog.png){width="650"}

1. Sélectionnez **Confirmer**. L’IA dédiée aux guides analyse les rubriques sélectionnées et affiche le nombre de recommandations de balises générées pour chaque rubrique.
1. Sélectionnez **Aperçu** pour consulter les recommandations de balises générées par l’IA.
1. Passez en revue les balises suggérées pour chaque rubrique, puis choisissez l’une des actions suivantes :
   - **Accepter tout** pour appliquer toutes les balises suggérées à toutes les rubriques.
   - **Rejeter tout** pour ignorer toutes les balises suggérées pour toutes les rubriques.
   - **Effacer toutes les suggestions** pour supprimer toutes les balises suggérées pour une rubrique spécifique.
   - Sélectionnez l’icône **X** en regard d’une balise pour supprimer une suggestion de balise individuelle.

     >[!NOTE]
     >
     > Pour les rubriques qui contiennent déjà des balises, l’IA dédiée aux guides affiche les balises existantes. Ces balises sont en lecture seule et ne peuvent pas être modifiées ni supprimées.

   ![Boîte de dialogue d’aperçu du balisage en bloc de Guides AI](images/preview-dialog.png){width="650"}

1. Lorsque vous acceptez les balises suggérées, les compétences de balisage intelligent ajoutent les balises générées par l’IA aux balises déjà appliquées au contenu.

Une fois la révision terminée, l’IA dédiée aux guides affiche un résumé des balises appliquées à chaque rubrique et toute recommandation de balise rejetée.

