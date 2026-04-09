---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans Adobe Experience Manager Guides version 2026.04.0
description: Découvrez la matrice de compatibilité et comment effectuer une mise à niveau vers la version 2026.04.0 d’Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: ce2c9da0d9beb05a15f7cefcf9483e0c93abbf37
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 11%

---

# Instructions de mise à niveau pour la version 2026.04.0

Cet article couvre les instructions de mise à niveau et la matrice de compatibilité pour la version 2026.04.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2026.04.0](whats-new-2026-04-0.md).

Pour connaître la liste des problèmes résolus dans cette version, voir la section [Problèmes résolus dans la version 2026.04.0](fixed-issues-2026-04-0.md).

## Matrice de compatibilité

Cette section présente la matrice de compatibilité pour les applications logicielles prises en charge par la version 2026.04.0 de Experience Manager Guides as a Cloud Service.

### FrameMaker et FrameMaker Publishing Server

| Version de Experience Manager Guides as a Cloud | FMPS | FrameMaker | Oxygen Author |
| --- | --- | --- | --- |
| 2026.04.0 | Non compatible | 2022 ou version ultérieure | 26,1 |


### Connecteur D&#39;Oxygène

| Version de Experience Manager Guides as a Cloud | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2026.04.0 | 3.8 -uuid 1 | 3.8 -uuid 1 | 2,3 | 2,3 |


### Version du modèle de site AEM

| Version des composants | Version du site |
|---|---|
| guides-components.all-1.4.0 | aemg-sites-template-1.3.0 |

### Version du modèle de la base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu de composants Experience Manager Guides pour Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |

## Mise à niveau vers la version 2026.04.0

Experience Manager Guides est automatiquement mis à niveau lors de la mise à niveau vers la dernière version d’Experience Manager as a Cloud Service.

>[!IMPORTANT]
>
> Cette version comprend des mises à jour des paramètres du profil de dossier (ui_config.json). Si vous utilisez des paramètres personnalisés, veillez à les sauvegarder avant de procéder à la mise à niveau. Après la mise à jour, vérifiez et ajustez vos paramètres pour vous aligner sur les modifications introduites dans la dernière version.

Passez en revue et validez vos configurations de configuration pour vérifier qu’elles sont correctement implémentées. Si vous avez apporté des modifications à la configuration personnalisée, consultez [Configuration supplémentaire pour la mise à niveau de Cloud Service](../cs-install-guide/additional-config-for-cloud-service.md) pour connaître les procédures supplémentaires applicables à la version à partir de laquelle vous effectuez la mise à niveau.
