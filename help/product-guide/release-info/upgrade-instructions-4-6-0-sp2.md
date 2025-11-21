---
title: Notes de mise à jour | Instructions de mise à niveau vers Adobe Experience Manager Guides 4.6.0 Service Pack 3
description: Découvrez comment effectuer une mise à niveau vers la version 4.6.0 Service Pack 3 d’Adobe Experience Manager Guides
role: Leader
exl-id: f0612eff-c18b-4667-a487-5f8809127d75
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 1%

---

# Instructions de mise à niveau vers la version 4.6.0 Service Pack 3 (janvier 2025)

Cet article contient les instructions de mise à niveau et la matrice de compatibilité pour la version 4.6.0 du Service Pack 3 d’Adobe Experience Manager Guides.

Pour obtenir la liste des problèmes qui ont été résolus dans cette version, voir [Problèmes résolus dans le pack de services 3 d’ 4.6.0](fixed-issues-4-6-0-sp2.md).

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par Experience Manager Guides 4.6.0 Service Pack 3.

### Adobe Experience Manager

**4.6.0 Service Pack 3 Non-UUID**
Version 6.5 Service Pack 21, 20 et 19

**4.6.0 Service Pack 3 UUID**
Version 6.5 Service Pack 21, 20 et 19

Pour plus d&#39;informations, consultez la section [Exigences techniques](../install-guide/download-install-technical-requirements.md) dans le Guide d&#39;installation et de configuration On-Premise.

### FrameMaker et FrameMaker Publishing Server

| Version | FMPS 2022 | FMPS 2020 | FM 2022 | FM 2020 |
| --- | --- | --- | --- | --- |
| 4.6.0 Service Pack 3 (Non-UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.3 ou version ultérieure |
| 4.6.0 Service Pack 3 (UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.4 ou version ultérieure |
| | | | | |

*La ligne de base et les conditions créées dans AEM sont prises en charge dans les versions FMPS à compter de 2020.2.

### Connecteur D&#39;Oxygène

| Version | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.6.0 Service Pack 3 (Non-UUID) | 2.8-normal-10 | 2.8-normal-10 | 1,6 | 1,6 |
| 4.6.0 Service Pack 3 (UUID) | 3.6-uuid.9 | 3.6-uuid.9 | 2,3 | 2,3 |
|  |  |   | |  |

### Version du modèle de la base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu de composants Experience Manager Guides pour Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

### Nouvelle version du modèle de site AEM

| Version des composants | Version du site |
|---|---|
| guides-components.all-1.0.0 | aemg-docs.all-1.0.0 |

## Mise à niveau vers la version 4.6.0 Service Pack 3 de Experience Manager Guides

Vous pouvez facilement mettre à niveau votre version actuelle de Guides vers le pack de services 3 d’ 4.6.0. Avant de procéder à la mise à niveau, vous devez tenir compte des points suivants :

- Si vous utilisez la version 4.6.0 ou 4.6.0 Service Pack 1, vous pouvez directement mettre à niveau vers 4.6.0 Service Pack 3.
- Si vous utilisez la version 4.4, 4.3.1 ou 4.3.0 , vous devez effectuer une mise à niveau vers la version 4.6.0.
- Si vous utilisez la version 4.2, 4.2.1 (correctif 4.2.1.3), 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers la version 4.4 avant la mise à niveau vers la version 4.6.0.
- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant d’effectuer la mise à niveau vers la version 4.3.x.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à la version 3.8.5, reportez-vous à la section Mise à niveau de Experience Manager Guides dans le guide d’installation spécifique au produit disponible sur [l’archive PDF d’aide d’Adobe Experience Manager Guides](https://helpx.adobe.com/fr/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
>Vous devez installer le pack de services AEM avant de mettre à niveau la version de Experience Manager Guides.

Le processus de mise à niveau vers le pack de services 3 version 4.6.0 suit les mêmes étapes que pour la version 4.6.0. Pour obtenir des instructions détaillées, consultez [Instructions de mise à niveau pour les versions On-Premise](../install-guide/upgrade-xml-documentation.md) de Experience Manager Guides.
