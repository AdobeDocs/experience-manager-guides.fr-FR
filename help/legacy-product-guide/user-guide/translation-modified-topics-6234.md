---
title: Traduire les rubriques modifiées
description: Découvrez comment retraduire une rubrique modifiée dans AEM Guides.
feature: Translation
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 0%

---

# Traduire les rubriques modifiées {#id16A5A0B6072}

Si vous apportez des modifications à certaines rubriques, ces rubriques doivent être retraduites. Vous pouvez effectuer le suivi des rubriques modifiées à partir du mappage DITA. Dans le dossier de copie de langue source, cliquez sur le fichier de mappage DITA et cliquez sur l’onglet Traduction . Vous pouvez voir l’état de chaque rubrique, qu’elle nécessite une retraduction ou non.

Effectuez les étapes suivantes pour envoyer une rubrique modifiée à retraduire :

1. Cliquez sur le fichier de mappage DITA dans le dossier de copie de langue source.

1. Cliquez sur l’onglet **Traduction** .

1. Dans le panneau **Filter** à gauche, sélectionnez le **Traduire les langues** dont vous souhaitez vérifier l’état, puis cliquez sur **Terminé**.

   Vous pouvez afficher l’état de traduction de chaque rubrique. Les rubriques pour lesquelles une autre révision de la rubrique est disponible que celle qui a été envoyée pour traduction affichent l’état **Out of Date** (Date d’expiration).

   >[!NOTE]
   >
   > Le processus de traduction compare la dernière révision enregistrée du fichier de rubrique dans le dossier de langue source avec la version traduite.

   Cliquez sur la flèche pour afficher plus de détails. vous pouvez voir la copie de langue spécifique qui est obsolète.

   ![](images/out-of-sync-uuid.png){width="800" align="left"}

1. Cochez la case pour sélectionner les rubriques que vous souhaitez envoyer pour retraduction.

   Lorsque vous sélectionnez une date désynchronisée, l’option **Créer/mettre à jour des copies de langue** apparaît dans le panneau Références et le bouton **Ignorer l’état de désynchronisation** situé au-dessus de l’icône **Filtrer**.

   Vous pouvez utiliser le bouton **Ignorer la désynchronisation** pour remplacer l’état &quot;obsolète&quot; pour les rubriques du mappage DITA. Par exemple, si vous avez apporté des modifications à la version en anglais de la rubrique qui n’a pas besoin d’être traduite, vous pouvez utiliser ce bouton et modifier l’état &quot;À jour&quot; de la rubrique sélectionnée.

   >[!NOTE]
   >
   > Si vous cliquez sur le bouton **Ignorer l’état de désynchronisation**, l’état de la rubrique est mis à jour pour les rubriques d’obsolescence sélectionnées.

1. Cliquez sur **Mettre à jour les copies de langue** et configurez la tâche de traduction.

1. Vous pouvez créer un projet de traduction ou ajouter des rubriques à un projet de traduction existant. Indiquez les informations requises pour configurer le projet de traduction.

1. Cliquez sur **Démarrer**.

   Un message de confirmation s’affiche, indiquant que la rubrique a été envoyée pour traduction.

1. Accédez au projet de traduction dans la console Projet. Une nouvelle carte de tâche de traduction est créée dans le dossier . Cliquez sur les points de suspension pour afficher les ressources du dossier.

   ![](images/incremental-job.PNG){width="300" align="left"}

1. Pour commencer la traduction, cliquez sur la flèche sur la carte de la tâche de traduction et sélectionnez **Démarrer** dans la liste. Un message indique que la tâche a commencé.

   Vous pouvez également afficher l’état de la rubrique en cours de traduction lorsque vous cliquez sur les points de suspension en bas de la carte de la tâche de traduction.

   >[!NOTE]
   >
   > Si vous utilisez le service de traduction humaine, vous devez exporter le contenu en vue de la traduction. Une fois que vous avez le contenu traduit, vous devez le réimporter dans le projet de traduction.

1. Une fois la traduction terminée, l’état passe à **Ready to Review**. Cliquez sur les points de suspension pour afficher les détails de la rubrique et effectuez l’une des opérations suivantes dans la barre d’outils :

   - Cliquez sur **Afficher dans Assets** pour afficher et vérifier la traduction.

   - Cliquez sur **Accepter la traduction** si vous pensez que les modifications ont été correctement traduites. Un message de confirmation s’affiche.

   - Cliquez sur **Rejeter la traduction** si vous pensez que la tâche doit être refaite. Un message de rejet s’affiche.

   >[!NOTE]
   >
   > Il est important d’accepter ou de rejeter la ressource traduite, sinon le fichier reste à l’emplacement temporaire et n’est pas copié dans la gestion des ressources numériques.

1. Revenez au fichier de mappage DITA dans le dossier de langue source dans l’interface utilisateur d’Assets. Les rubriques retraduites sont désormais synchronisées.


**Rubrique parente :**[ Traduire le contenu](translation.md)
