---
title: Traduire les rubriques modifiées
description: Learn how to re-translate a modified topic in AEM Guides.
feature: Translation
role: User
hide: true
exl-id: b623b109-8695-40e5-9e28-78f78cf57ad6
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 0%

---

# Traduire les rubriques modifiées {#id16A5A0B6072}

If you make changes in some of the topics, then those topics require re-translation. You can keep track of modified topics from DITA map. From the source language copy folder, click the DITA map file and click the Translation tab. You can see the status of each topic whether it requires re-translation or not.

Perform the following steps to send a modified topic for re-translation:

1. Click the DITA map file from the source language copy folder.

1. Cliquez sur l’onglet **Traduction**.

1. In the **Filter** panel on the left, select the **Translate Languages** that you want to check the status for and click **Done**.

   You can see the translation status for each topic. The topics that have another revision of topic available than what was sent for translation, show an **Out of Date** status.

   >[!NOTE]
   >
   > The translation workflow compares the last saved revision of the topic file in the source language folder with the translated version.

   If you click the arrow to see further details. you can see the particular language copy that is out of date.

   ![](images/out-of-sync-uuid.png){width="800" align="left"}

1. Click the check box to select the topics that you want to send for re-translation.

   When you select an out of sync date, the **Create/Update Language Copies** option appears in the References panel and the **Dismiss Out of Sync Status** button above the **Filter** icon.

   You can use the **Dismiss Out of Sync** button to override the Out of Date status for the topics in the DITA map. For example, if you made some changes in the English version of the topic that does not need translation, you can use this button and change the Out of Date status for the selected topic.

   >[!NOTE]
   >
   > If you click the **Dismiss Out of Sync Status** button, it sets the topic status to Up to Date for the selected Out of Date topics.

1. Click **Update Language Copies** and configure the translation job.

1. You can choose to create a new translation project or add topics to an existing translation project. Provide the required details to configure the translation project.

1. Cliquez sur **Démarrer**.

   A confirmation message is displayed showing that the topic has been sent for translation.

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


**Rubrique parente :**[ Traduire le contenu](translation.md)
