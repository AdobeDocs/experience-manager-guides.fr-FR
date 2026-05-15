---
title: Notes de mise à jour | Nouveautés de la version Adobe Experience Manager Guides 2025.11.0
description: Découvrez les fonctionnalités nouvelles et améliorées de la version 2025.11.0 d’Adobe Experience Manager Guides
role: Leader
exl-id: 270a5faa-a16f-4939-900e-3c6c54660d2c
TQID: https://experienceleague.adobe.com/IuRSYXzBeHanuEsfc3-dPZuIGW3r67zPMeBILR34FvA
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 512
ht-degree: 3%

---

# Nouveautés de la version 2025.11.0 (novembre 2025)

Cet article présente les nouvelles fonctionnalités améliorées introduites dans la version 2025.11.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour connaître la liste des problèmes résolus dans cette version, voir la section [Problèmes résolus dans la version 2025.11.0](fixed-issues-2025-11-0.md).

Découvrez les [instructions de mise à niveau pour la version 2025.11.0](../release-info/upgrade-instructions-2025-11-0.md).


## Présentation du nouveau référentiel sur la page d’accueil et de l’expérience de recherche améliorée

Le référentiel, désormais accessible directement à partir de la page d’accueil, sert d’espace centralisé pour améliorer la visibilité des dossiers et des fichiers. Il comprend un **panneau de navigation Dossier** dédié et une vue personnalisable **tabulaire du référentiel**. La nouvelle expérience de recherche et de filtrage facilite considérablement la recherche et la localisation des fichiers. Pour plus d’informations, consultez la section [Connaître l’interface du référentiel](../user-guide/home-page-repository-view.md).

![](assets/repository-view-home.png)

Dans l’éditeur, l’expérience de recherche et de filtrage des fichiers est désormais cohérente avec la page d’accueil d’. Un nouveau [panneau de recherche](../user-guide/search-panel-explorer.md) situé au bas de l’interface de l’éditeur, permet d’afficher les résultats de la recherche. En outre, le référentiel est désormais renommé **Explorateur** dans l’éditeur, ce qui vous permet de parcourir les dossiers et les fichiers comme auparavant.

![](assets/search-panel-explorer.png)


## Indexation améliorée pour les suggestions intelligentes dans l’assistant AI

Vous pouvez désormais facilement suivre l’état de chaque tentative d’indexation pour les suggestions intelligentes dans l’assistant AI à l’aide de nouveaux indicateurs de statut : indexation terminée, Non synchronisée, En cours et L’indexation a échoué. La dernière date et heure d’indexation est désormais enregistrée au niveau du profil de dossier pour une meilleure traçabilité. En outre, les restrictions de dossier parent-enfant sont appliquées lors de la spécification d’un chemin de dossier ou de fichier pour l’indexation.

Pour plus d’informations, consultez [Configuration de l’assistant AI pour l’aide intelligente et la création](../cs-install-guide/conf-folder-level.md#configure-ai-assistant-for-smart-help-and-authoring).

## Améliorations des performances

### Nettoyage automatisé de l’arborescence B pour des performances optimales

Pour maintenir l’efficacité du système et prévenir la congestion des ressources, un nouveau processus de fond nettoie régulièrement les arbres B au niveau du système. Cela permet de s’assurer que les ressources qui n’existent plus ou qui ont été ajoutées temporairement n’occupent pas d’espace inutile.

Le système identifie intelligemment les candidats au nettoyage et effectue une suppression automatisée. De plus, cette fonctionnalité est configurable, ce qui permet aux administrateurs et administratrices de contrôler son comportement en fonction des besoins opérationnels.

Pour plus d’informations, consultez la section [Configurer le nettoyage de l’arborescence B](../cs-install-guide/configure-btree-cleanup-cs.md).

### Amélioration de la gestion des plans DITA avec un grand nombre de clés

Vous pouvez désormais travailler en toute simplicité avec les plans DITA qui contiennent un grand nombre de clés. Cette amélioration accélère le chargement et améliore les performances, ce qui facilite la gestion des cartes complexes sans interruptions.

Après la mise à niveau de la build, le système peut subir une augmentation temporaire de la charge, ce qui peut entraîner un retard dans le post-traitement des données nouvellement chargées. Cela est dû à l’exécution d’un script unique automatisé (OTS) en arrière-plan. Une fois le script terminé, les performances du système reviendront à la normale.

### Amélioration du traitement des ressources

Un processus automatisé est introduit pour maintenir à jour les ressources du `/content/dam`. Le système déclenche le retraitement des ressources toutes les 15 minutes. Au cours de chaque cycle, les ressources qui ont été ajoutées récemment ou qui n’ont pas été traitées au cours des 15 dernières minutes sont récupérées et retraitées, ce qui améliore l’efficacité et la cohérence de votre référentiel de contenu.

Pour plus d’informations, consultez la section [Traitement des ressources](../user-guide/asset-processor.md).
