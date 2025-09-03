---
title: Demander une révision ou fermer une tâche de révision en tant qu’auteur
description: Découvrez le processus de fermeture d’une tâche de révision ou de nouvelle demande de révision en tant qu’auteur dans Experience Manager Guides.
feature: Reviewing
role: User
exl-id: d2119bbe-3a0c-4da3-b4f8-7872496fa61f
source-git-commit: 439be49e8f4c8cfacb16679257352f4197574365
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 0%

---

# Demander une révision ou fermer une tâche de révision en tant qu’auteur

>[!IMPORTANT]
>
> Les nouvelles fonctionnalités décrites dans cet article sont activées par défaut avec la version 2508 de Experience Manager Guides as a Cloud Services. Les révisions créées avant la migration ne sont pas affectées et continueront à utiliser le workflow précédent. Si vous préférez continuer à utiliser les fonctionnalités existantes sans ces mises à jour, contactez votre équipe du succès client pour que les nouvelles fonctionnalités soient désactivées.

Lorsqu’une tâche de révision est marquée comme terminée par un réviseur, une notification est déclenchée à l’initiateur de la tâche, lui permettant d’accéder à la tâche et de la réviser, ainsi qu’aux commentaires au niveau de la tâche associés.

En tant qu’initiateur de la tâche de révision, vous pouvez ensuite décider comment procéder en fonction des commentaires. Les options disponibles sont les suivantes :

- Demander une révision
- Fermer la tâche de révision

## Demander une révision ou fermer une tâche de révision

Effectuez les étapes suivantes pour demander une révision ou fermer une tâche de révision :

1. Ouvrez la tâche Révision dans l’éditeur.
2. Dans le panneau Révision, sélectionnez la tâche de révision dans la liste **Tâches actives**.

   >[!NOTE]
   >
   > Vous pouvez également ouvrir la tâche dans le tableau de bord de la tâche pour obtenir une vue plus complète. Pour ce faire, sélectionnez **Ouvrir dans le tableau de bord de la tâche** dans le menu Options d’une tâche de révision active. Les détails de la tâche s’ouvrent alors dans la console Projets.

   ![](images/task-dashboard-selection-author-view.png)
3. Sélectionnez la boîte de dialogue **Commentaires de la tâche** pour accéder aux commentaires au niveau de la tâche ajoutés par le réviseur ou la réviseuse et les réviser.

   ![](images/task-comments-selection-author-view.png).

   La boîte de dialogue **Commentaires de la tâche** s’affiche à droite.

   ![](images/task-comments-dialog-editor.png){width="350" align="left"}.
4. Sélectionnez **Mettre à jour la tâche** pour effectuer une action supplémentaire sur la tâche de révision sélectionnée.
5. Dans la boîte de dialogue **Mettre à jour la tâche**, choisissez l’une des actions suivantes :

   - **Demander un réexamen** : lance un autre cycle de révision. Vous pouvez sélectionner une autre version de la rubrique à réviser. Par défaut, la dernière version (ou la dernière version modifiée) du fichier de rubrique ou de mappage envoyé pour révision est sélectionnée. Vous pouvez également utiliser l&#39;option **Modifier les versions** pour définir la version des rubriques sélectionnées sur **Dernière version**, **Version activée** et **Ligne de base** selon vos besoins.  Les réviseurs et réviseuses qui ont terminé la révision précédente recevront une notification leur demandant de faire part de leurs commentaires sur la version mise à jour. Les autres réviseurs et réviseuses qui n’ont pas marqué la tâche de révision comme terminée sont avertis de la mise à jour de la rubrique.

   - **Fermer la révision** : ferme la tâche de révision. Le bouton **Mettre à jour la tâche** présent au bas du panneau de révision devient **Fermé** et une notification est envoyée à tous les utilisateurs impliqués dans la tâche de révision pour indiquer sa fermeture.

   Pour plus d’informations sur le déclenchement des notifications de révision, voir [Présentation des notifications de révision](./review-understanding-review-notifications.md).

   ![](images/update-task-dialog.png){width="350" align="left"}

   >[!NOTE]
   >
   > La boîte de dialogue **Mettre à jour la tâche** comprend également une colonne **État du document** pour indiquer l’état actuel des rubriques de révision répertoriées lors de l’utilisation de Experience Manager Guides as a Cloud Services.


6. Sélectionnez **Confirmer**.


En tant qu’auteur ou initiateur d’une tâche de révision, lorsque vous fermez la tâche, le bouton **Mettre à jour la tâche** présent au bas du panneau de révision est remplacé par **Fermé**, indiquant que la tâche n’est plus active.

![](images/review-task-status-closed-review-panel.png){width="350" align="left"}

En outre, le bouton **Mettre à jour la tâche** présent dans le panneau de révision reste désactivé pour les autres utilisateurs de la tâche de révision. Par exemple, en tant que personne effectuant la révision d’une tâche de révision, si vous ouvrez la tâche dans l’éditeur, le bouton Mettre à jour la tâche sera désactivé avec un message **Vous n’êtes pas autorisé à agir sur cette tâche**. Seul l’initiateur d’une tâche de révision est autorisé à mettre à jour la tâche à partir de l’éditeur.

![](images/update-task-button-disabled.png){width="350" align="left"}
