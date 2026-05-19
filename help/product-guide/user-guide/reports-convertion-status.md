---
title: Rapport sur le statut de la conversion
description: Convertissez des documents de différents formats en DITA dans AEM Guides. Découvrez comment ajouter des filtres et afficher un rapport de statut de conversion.
exl-id: 0a4699e5-865f-40e1-a17f-5e1a248ea955
feature: Report Generation
role: User
TQID: https://experienceleague.adobe.com/-Jgxys5YiwelOf7jQHYQ4Y9ARYzwLCZ8lNStdnT4oLI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: cdab8659-8d50-4417-b6fd-762f347c13ee
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 318
ht-degree: 0%

---

# Rapport sur le statut de la conversion {#id205BBA00WZZ}

Adobe Experience Manager Guides offre une fonctionnalité de conversion robuste pour convertir en DITA des documents de différents formats. Le rapport Statut de la conversion fournit une vue consolidée de toutes les tâches de conversion exécutées par Experience Manager Guides.

Pour afficher le rapport Statut de la conversion, procédez comme suit :

1. Sélectionnez le logo Adobe Experience Manager en haut et choisissez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils.

1. Sélectionnez la mosaïque **Rapport de statut de la conversion**.

   Le rapport Statut de la conversion s’affiche pour toutes les tâches de conversion exécutées sur le système.

   ![](images/conversion-status-report-new.png)

1. La page du rapport est divisée en deux parties :

   - **Filter:**

     Vous pouvez filtrer les données du rapport en fonction du type de fichier et du statut de conversion. Dans le type de fichier, vous pouvez choisir d’afficher les données de rapport pour les documents Word, HTML structurés, XML, DocBook et IDML. Dans le Statut, vous pouvez choisir d’afficher les données du rapport pour les tâches exécutées avec succès, en échec, actives ou en file d’attente.

     La capture d’écran suivante affiche les données de rapport pour les tâches de conversion dont le statut est défini sur Succès .

     ![](images/conversion-report-failed-active-queued-new.png)

   - **Données du rapport :**

     Les données du rapport contiennent les colonnes suivantes :

      - **Nom de fichier** : nom du fichier source sur lequel le processus de conversion a été exécuté. Lorsque vous sélectionnez le lien Nom de fichier, vous accédez à l’emplacement du document source.

      - **Type de fichier** : type du document source, qui peut être Word, HTML structuré, XML, IDML et DocBook.

      - **Ajouté par** : nom de l’utilisateur qui a exécuté la tâche de conversion.

      - **Date ajoutée** : date d’exécution de la tâche. Sélectionner sur le lien Date d’ajout télécharge le fichier journal.

      - **Chemin** : chemin complet du document source.

      - **Statut** : statut des tâches de conversion : Succès, Échec, Actif ou En file d’attente.

      - **Output** : chemin d’accès du document converti. Lorsque vous sélectionnez le lien Sortie , vous accédez à l’emplacement où la sortie est enregistrée.


**Rubrique parente :**&#x200B;[&#x200B; Présentation des rapports](reports-intro.md)
