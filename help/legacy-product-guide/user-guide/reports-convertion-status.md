---
title: Rapport sur le statut de la conversion
description: Convertissez des documents de différents formats en DITA dans AEM Guides. Découvrez comment ajouter des filtres et afficher un rapport de statut de conversion.
feature: Report Generation
role: User
hide: true
exl-id: f6bf1033-9c2f-42c7-9ad5-e1060e2c9770
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# Rapport sur le statut de la conversion {#id205BBA00WZZ}

AEM Guides offre une fonctionnalité de conversion robuste pour convertir en DITA des documents de différents formats. Le rapport Statut de la conversion fournit une vue consolidée de toutes les tâches de conversion exécutées par AEM Guides.

Pour afficher le rapport Statut de la conversion, procédez comme suit :

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils.

1. Cliquez sur la mosaïque **Rapport de statut de la conversion**.

   Le rapport Statut de la conversion s’affiche pour toutes les tâches de conversion exécutées sur le système.

   ![](images/conversion-status-report.png){width="800" align="left"}

1. La page du rapport est divisée en deux parties :

   - **Filter:**

     Vous pouvez filtrer les données du rapport en fonction du type de fichier et du statut de conversion. Dans le type de fichier, vous pouvez choisir d’afficher les données de rapport pour les documents Word, HTML structuré, XML et DocBook. Dans le Statut, vous pouvez choisir d’afficher les données du rapport pour les tâches exécutées avec succès, en échec, actives ou en file d’attente.

     La capture d’écran suivante affiche les données du rapport pour les tâches de conversion dont le statut est En échec, Actif et En file d’attente.

     ![](images/conversion-report-failed-active-queued.png){width="800" align="left"}

   - **Données du rapport :**

     Les données du rapport contiennent les colonnes suivantes :

      - **Nom de fichier** : nom du fichier source sur lequel le processus de conversion a été exécuté. Cliquez sur le lien Nom du fichier pour accéder à l’emplacement du document source.

      - **Type de fichier** : type du document source, qui peut être Word, HTML structuré, XML ou DocBook.

      - **Ajouté par** : nom de l’utilisateur qui a exécuté la tâche de conversion.

      - **Date ajoutée** : date d’exécution de la tâche. Cliquez sur le lien Date d’ajout pour télécharger le fichier journal.

      - **Chemin** : chemin complet du document source.

      - **Statut** : statut des tâches de conversion : Succès, Échec, Actif ou En file d’attente.

      - **Output** : chemin d’accès du document converti. Cliquez sur le lien Sortie pour accéder à l’emplacement d’enregistrement de la sortie.


**Rubrique parente :**&#x200B;[ Rapports](reports-intro.md)
