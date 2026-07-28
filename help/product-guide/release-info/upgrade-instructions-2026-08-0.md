---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans Adobe Experience Manager Guides version 2026.08.0
description: Découvrez la matrice de compatibilité et comment effectuer une mise à niveau vers la version 2026.08.0 d’Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 0de22d4883096f6a9f3b2ca8acfad4a10992f5e7
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 1%

---

# Instructions de mise à niveau pour la version 2026.08.0

Cet article couvre les instructions de mise à niveau et la matrice de compatibilité pour la version 2026.08.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, consultez [Nouveautés de la version 2026.08.0](whats-new-2026-08-0.md).

Pour obtenir la liste des problèmes résolus dans cette version, voir [Problèmes résolus dans la version 2026.08.0](fixed-issues-2026-08-0.md).

## Matrice de compatibilité

Cette section présente la matrice de compatibilité pour les applications logicielles prises en charge par la version 2026.08.0 de Experience Manager Guides as a Cloud Service.

### Ressources Java SDK

Utilisez les ressources suivantes lors du développement de modules externes Java personnalisés ou d’intégrations avec Experience Manager Guides. Assurez-vous que la version de SDK correspond à la version de Experience Manager Guides que vous avez installée.

| Version | Version de Java SDK | Maven Central | Référence de l’API Java |
|---|---|---|----|
| 2026.08.0 | 2026.8.0 | [API AEM Guides SDK 2026.8.0](https://central.sonatype.com/artifact/com.adobe.aem/aem-dox-sdk-api/2026.8.0) | [Javadoc 2026.8.0](https://javadoc.io/doc/com.adobe.aem/aem-dox-sdk-api/latest/index.html) |

Pour plus d’informations, consultez [Configuration et utilisation du fichier JAR de l’API à partir du référentiel central Maven](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/api-reference/introduction).

### FrameMaker et FrameMaker Publishing Server

| Version de Experience Manager Guides as a Cloud | FMPS | FrameMaker | Oxygen Author |
| --- | --- | --- | --- |
| 2026.08.0 | Non compatible | 2022 ou version ultérieure | 26.1 |


### Connecteur D&#39;Oxygène

| Version de Experience Manager Guides as a Cloud | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2026.08.0 | 3.8 -uuid 1 | 3.8 -uuid 1 | 2,3 | 2,3 |


### Version du modèle de site AEM

| Version des composants | Version du site |
|---|---|
| guides-components.all-1.5.1 | aemg-sites-template-1.3.0 |

### Version du modèle de la base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu de composants Experience Manager Guides pour Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |

## Mise à niveau vers la version 2026.08.0

Experience Manager Guides est automatiquement mis à niveau lors de la mise à niveau vers la dernière version d’Experience Manager as a Cloud Service.

>[!IMPORTANT]
>
> Cette version comprend des mises à jour des paramètres du profil de dossier (ui_config.json). Si vous utilisez des paramètres personnalisés, veillez à les sauvegarder avant de procéder à la mise à niveau. Après la mise à jour, vérifiez et ajustez vos paramètres pour vous aligner sur les modifications introduites dans la dernière version.

Passez en revue et validez vos configurations de configuration pour vérifier qu’elles sont correctement implémentées. Si vous avez apporté des modifications à la configuration personnalisée, consultez [Configuration supplémentaire pour la mise à niveau de Cloud Service](../install-conf-guide/additional-config-for-upgrade.md) pour connaître les procédures supplémentaires applicables à la version à partir de laquelle vous effectuez la mise à niveau.
