---
title: Rapport d’état de conversion
description: Convertissez des documents de différents formats en DITA dans AEM Guides. Découvrez comment ajouter des filtres et afficher un rapport d’état de conversion.
exl-id: 0a4699e5-865f-40e1-a17f-5e1a248ea955
feature: Report Generation
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# Rapport d’état de conversion {#id205BBA00WZZ}

AEM Guides offre une fonctionnalité de conversion performante pour convertir des documents de divers formats en DITA. Le rapport État de conversion fournit une vue consolidée de toutes les tâches de conversion exécutées par AEM Guides.

Pour afficher le rapport d’état de conversion, procédez comme suit :

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et sélectionnez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils.

1. Cliquez sur la mosaïque **Rapport d’état de conversion** .

   Le rapport d’état de conversion s’affiche pour toutes les tâches de conversion exécutées sur le système.

   ![](images/conversion-status-report.png){width="800" align="left"}

1. La page du rapport se divise en deux parties :

   - **Filtre :**

     Vous pouvez filtrer les données du rapport en fonction du type de fichier et de l’état de conversion. Dans le type de fichier, vous pouvez choisir d’afficher les données du rapport pour le document Word, l’HTML structuré, XML et le type DocBook des documents. Dans l’état, vous pouvez choisir d’afficher les données du rapport pour les tâches qui ont été exécutées avec succès, Échec, Actif ou En file d’attente.

     La capture d’écran suivante présente les données du rapport pour les tâches de conversion ayant l’état En échec, Actif et En file d’attente.

     ![](images/conversion-report-failed-active-queued.png){width="800" align="left"}

   - **Données du rapport :**

     Les données du rapport contiennent les colonnes suivantes :

      - **Nom de fichier** : nom du fichier source sur lequel le processus de conversion a été exécuté. Cliquez sur le lien Nom du fichier pour accéder à l’emplacement du document source.

      - **Type de fichier** : type du document source, qui peut être Word, HTML structuré, XML et DocBook.

      - **Ajouté par** : nom de l’utilisateur qui a exécuté la tâche de conversion.

      - **Date d’ajout** : date d’exécution de la tâche. Cliquez sur le lien Date d’ajout pour télécharger le fichier journal.

      - **Path** : chemin d’accès complet au document source.

      - **État** : état des tâches de conversion - Réussite, Échec, Actif ou En file d’attente.

      - **Output** : chemin du document converti avec succès. Cliquez sur le lien Sortie pour accéder à l’emplacement d’enregistrement de la sortie.


**Rubrique parente :**[ Rapports](reports-intro.md)
