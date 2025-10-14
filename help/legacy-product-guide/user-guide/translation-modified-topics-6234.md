---
title: Traduire les rubriques modifiées
description: Découvrez comment retraduire une rubrique modifiée dans AEM Guides.
feature: Translation
role: User
hide: true
exl-id: b623b109-8695-40e5-9e28-78f78cf57ad6
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 0%

---

# Traduire les rubriques modifiées {#id16A5A0B6072}

Si vous apportez des modifications à certains sujets, alors ces sujets doivent être retraduits. Vous pouvez suivre les rubriques modifiées à partir du plan DITA. Dans le dossier de copie de la langue source, cliquez sur le fichier de mappage DITA, puis sur l&#39;onglet Traduction . Vous pouvez voir le statut de chaque rubrique, qu’elle nécessite une retraduction ou non.

Effectuez les étapes suivantes pour envoyer une rubrique modifiée pour retraduction :

1. Cliquez sur le fichier de mappage DITA dans le dossier de copie de la langue source.

1. Cliquez sur l’onglet **Traduction**.

1. Dans le panneau **Filtre** à gauche, sélectionnez les **Traduire les langues** dont vous souhaitez vérifier le statut, puis cliquez sur **Terminé**.

   Vous pouvez voir le statut de la traduction pour chaque rubrique. Les rubriques pour lesquelles une autre révision de rubrique est disponible que celle envoyée pour traduction affichent le statut **Obsolète**.

   >[!NOTE]
   >
   > Le workflow de traduction compare la dernière révision enregistrée du fichier de rubrique dans le dossier de langue source avec la version traduite.

   Si vous cliquez sur la flèche pour afficher plus de détails. vous pouvez voir la copie de langue spécifique qui est obsolète.

   ![](images/out-of-sync-uuid.png){width="800" align="left"}

1. Cochez la case pour sélectionner les rubriques à envoyer pour une nouvelle traduction.

   Lorsque vous sélectionnez une date désynchronisée, l’option **Créer/mettre à jour des copies de langue** s’affiche dans le panneau Références et le bouton **Ignorer le statut de désynchronisation** au-dessus de l’icône **Filtrer**.

   Vous pouvez utiliser le bouton **Ignorer la désynchronisation** pour remplacer le statut Obsolète pour les rubriques du plan DITA. Par exemple, si vous avez apporté des modifications à la version anglaise de la rubrique qui n’ont pas besoin d’être traduites, vous pouvez utiliser ce bouton et modifier le statut Obsolète pour la rubrique sélectionnée.

   >[!NOTE]
   >
   > Si vous cliquez sur le bouton **Ignorer le statut de désynchronisation**, il définit le statut de la rubrique sur À jour pour les rubriques obsolètes sélectionnées.

1. Cliquez sur **Mettre à jour des copies de langue** et configurez la tâche de traduction.

1. Vous pouvez choisir de créer un projet de traduction ou d’ajouter des rubriques à un projet de traduction existant. Fournissez les détails requis pour configurer le projet de traduction.

1. Cliquez sur **Démarrer**.

   Un message de confirmation s’affiche indiquant que la rubrique a été envoyée pour traduction.

1. Accédez au projet de traduction dans la console Projet. Une nouvelle carte de tâche de traduction est créée dans le dossier . Cliquez sur les points de suspension pour afficher les ressources du dossier.

   ![](images/incremental-job.PNG){width="300" align="left"}

1. Pour commencer la traduction, cliquez sur la flèche sur la carte Tâche de traduction et sélectionnez **Démarrer** dans la liste. Un message indique que le traitement a commencé.

   Vous pouvez également consulter le statut de la rubrique en cours de traduction lorsque vous cliquez sur les points de suspension en bas de la carte Tâche de traduction .

   >[!NOTE]
   >
   > Si vous utilisez le service de traduction humaine, vous devez exporter le contenu pour le traduire. Une fois que vous disposez du contenu traduit, vous devez le réimporter dans le projet de traduction.

1. Une fois la traduction terminée, le statut passe à **Prêt pour la révision**. Cliquez sur les points de suspension pour afficher les détails de la rubrique et effectuez l’une des opérations suivantes à partir de la barre d’outils :

   - Cliquez sur **Afficher dans Assets** pour afficher et vérifier la traduction.

   - Cliquez sur **Accepter la traduction** si vous pensez que les modifications ont été correctement traduites. Un message de confirmation s’affiche.

   - Cliquez sur **Rejeter la traduction** si vous pensez que la tâche doit être reeffectuée. Un message de rejet s’affiche.

   >[!NOTE]
   >
   > Il est important d’accepter ou de rejeter la ressource traduite, sinon le fichier reste à l’emplacement temporaire et n’est pas copié dans la gestion des ressources numériques.

1. Revenez au fichier de mappage DITA dans le dossier de langue source dans l’interface utilisateur d’Assets. Les rubriques retraduites sont désormais synchronisées.


**Rubrique parente :**&#x200B;[&#x200B; Traduire le contenu](translation.md)
