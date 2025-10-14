---
title: Notes de mise à jour | Nouveautés de la version Adobe Experience Manager Guides 2025.10.0
description: Découvrez les fonctionnalités nouvelles et améliorées de la version 2025.10.0 d’Adobe Experience Manager Guides
role: Leader
source-git-commit: f9b879d6d374334a08a1d3b0a47b0cb419f02140
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 3%

---

# Nouveautés de la version 2025.10.0 (octobre 2025)

Cet article présente les nouvelles fonctionnalités améliorées introduites dans la version 2025.10.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour connaître la liste des problèmes résolus dans cette version, voir la section [Problèmes résolus dans la version 2025.10.0](fixed-issues-2025-10-0.md).

Découvrez les [instructions de mise à niveau pour la version 2025.10.0](../release-info/upgrade-instructions-2025-10-0.md).


## Les paramètres de l’éditeur sont désormais renommés paramètres Workspace et accessibles à partir de la page d’accueil

Pour améliorer la navigation et la convivialité, les améliorations suivantes ont été apportées :

- **Paramètres de l’éditeur** dans Experience Manager Guides a été renommé **Paramètres de Workspace**.
- Le menu **Autres actions** (menu sous forme de trois points), auparavant disponible uniquement dans l’interface de la console Éditeur et mappage , est désormais accessible à partir de la [Page d’accueil](../user-guide/intro-home-page.md).

  ![](assets/workspace-settings.png)

## Identifiez et corrigez facilement les identifiants en double dans les rubriques et les mappages de la vue de création

Experience Manager Guides comprend désormais un bouton **Dupliquer les identifiants** dans l’éditeur pour vous aider à identifier et à corriger rapidement les identifiants en double présents dans une seule rubrique ou carte. Lorsque des identifiants en double sont détectés, ce bouton s’affiche dans le coin inférieur gauche de l’interface de l’éditeur dans la vue **Auteur**. Lorsque vous sélectionnez le bouton, une liste de toutes les instances avec des ID en double s’affiche dans une fenêtre contextuelle. La sélection d’une instance met en surbrillance le contenu correspondant dans la rubrique ou le mappage, ce qui vous permet de localiser et de corriger les identifiants en double à partir du panneau de droite.

Pour plus d’informations, consultez la section [Fonctionnalités supplémentaires dans l’éditeur](../user-guide/web-editor-other-features.md).

![](assets/duplicate-element-IDs.png){width="350" align="left"}

## Améliorations apportées aux filtres Référentiel et Rapports

Le filtre **Verrouillé par** sous Filtres avancés dans le référentiel et le filtre **Auteur** dans les rapports DITA map chargent désormais les listes d&#39;utilisateurs progressivement au fur et à mesure que vous faites défiler l&#39;écran, plutôt que de les charger toutes en même temps. Ce chargement paginé améliore la vitesse et rend l’utilisation de jeux de données utilisateur volumineux plus efficace et plus transparente.

## Accès au statut des tâches de révision directement à partir du panneau de révision

En tant qu’initiateur ou initiatrice d’une tâche de révision, vous pouvez désormais vérifier le statut de votre tâche de révision directement depuis le panneau de révision. Grâce aux dernières améliorations, la boîte de dialogue **Mettre à jour la tâche** du panneau de révision comprend une nouvelle option **Vérifier le statut de la révision**. La sélection de cette option vous permet d’accéder directement au tableau de bord de révision, où vous pouvez afficher l’état de la tâche pour chaque réviseur ou réviseuse, ce qui vous permet d’accéder plus rapidement à la progression de la tâche sans avoir à changer de contexte.

Pour plus d’informations, consultez [Demander une révision ou fermer une tâche de révision en tant qu’auteur](../user-guide/review-close-review-task.md).

![](assets/check-review-status-icon.png){width="350" align="left"}



## API de suivi du statut de post-traitement des dossiers ou des ressources

Une nouvelle API est désormais disponible pour effectuer le suivi du statut de post-traitement des ressources et dossiers individuels. Cela s’avère particulièrement utile pour les équipes qui utilisent des workflows automatisés, où la publication ne doit se produire qu’une fois le contenu entièrement traité. L’API offre un moyen fiable de confirmer la préparation, ce qui réduit le risque d’échecs de publication causés par un traitement incomplet.

Pour plus d’informations, consultez [API pour suivre le statut de post-traitement des dossiers ou des ressources](../api-reference/track-post-processing-status.md).

