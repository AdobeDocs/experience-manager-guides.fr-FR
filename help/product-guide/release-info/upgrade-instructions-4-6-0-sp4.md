---
title: Notes de mise à jour | Instructions de mise à niveau pour Adobe Experience Manager Guides 4.6.0 Service Pack 4
description: Découvrez comment effectuer une mise à niveau vers la version 4.6.0 Service Pack 4 d’Adobe Experience Manager Guides
role: Leader
exl-id: d0914e8a-7c7f-47da-9655-697f95f7d4ff
TQID: https://experienceleague.adobe.com/VFnhu8AwMB-wIZzLC-vG9xHozFQnwQMqYH-YPnnIE2I
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: afb45297-4313-4f67-818e-bc0b03abe086
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 527
ht-degree: 1%

---

# Instructions de mise à niveau vers la version 4.6.0 Service Pack 4 (avril 2025)

Cet article contient les instructions de mise à niveau et la matrice de compatibilité pour la version 4.6.0 du Service Pack 4 d’Adobe Experience Manager Guides.

Pour obtenir la liste des problèmes qui ont été résolus dans cette version, voir [Problèmes résolus dans le pack de services 4.6.0 d’](fixed-issues-4-6-0-sp4.md).

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par Experience Manager Guides 4.6.0 Service Pack 4.

### Adobe Experience Manager

**4.6.0 Service Pack 4 Non-UUID**
Version 6.5 Service Pack 21, 20 et 19

**4.6.0 Service Pack 4 UUID**
Version 6.5 Service Pack 21, 20 et 19

Pour plus d&#39;informations, consultez la section [Exigences techniques](../install-guide/download-install-technical-requirements.md) dans le Guide d&#39;installation et de configuration On-Premise.

### FrameMaker et FrameMaker Publishing Server

| Version | FMPS 2022 | FMPS 2020 | FM 2022 | FM 2020 |
| --- | --- | --- | --- | --- |
| 4.6.0 Service Pack 4 (non-UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.3 ou version ultérieure |
| 4.6.0 Service Pack 4 (UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.4 ou version ultérieure |
| | | | | |

*La ligne de base et les conditions créées dans AEM sont prises en charge dans les versions FMPS à compter de 2020.2.

### Connecteur D&#39;Oxygène

| Version | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.6.0 Service Pack 4 (non-UUID) | 2.8-normal-10 | 2.8-normal-10 | 1,6 | 1,6 |
| 4.6.0 Service Pack 4 (UUID) | 3.6-uuid.9 | 3.6-uuid.9 | 2,3 | 2,3 |
|  |  |   |  |  |

### Version du modèle de la base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu de composants Experience Manager Guides pour Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

### Nouvelle version du modèle de site AEM

| Version des composants | Version du site |
|---|---|
| guides-components.all-1.0.0 | aemg-docs.all-1.0.0 |

## Mise à niveau vers la version 4.6.0 Service Pack 4 de Experience Manager Guides

Vous pouvez facilement mettre à niveau votre version actuelle de Guides vers le pack de services 4.6.0. Avant de procéder à la mise à niveau, vous devez tenir compte des points suivants :

- Si vous utilisez la version 4.6.0, 4.6.0 Service Pack 1 ou 4.6.0 Service Pack 3, vous pouvez directement effectuer la mise à niveau vers 4.6.0 Service Pack 4.
- Si vous utilisez la version 4.4, 4.3.1 ou 4.3.0 , vous devez effectuer une mise à niveau vers la version 4.6.0.
- Si vous utilisez la version 4.2, 4.2.1 (correctif 4.2.1.3), 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers la version 4.4 avant la mise à niveau vers la version 4.6.0.
- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant d’effectuer la mise à niveau vers la version 4.3.x.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à la version 3.8.5, reportez-vous à la section Mise à niveau de Experience Manager Guides dans le guide d’installation spécifique au produit disponible sur [l’archive PDF d’aide d’Adobe Experience Manager Guides](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
>Vous devez installer le pack de services AEM avant de mettre à niveau la version de Experience Manager Guides.

Le processus de mise à niveau vers le pack de services 4.6.0 d’ suit les mêmes étapes que pour la version 4.6.0 d’. Pour obtenir des instructions détaillées, consultez [Instructions de mise à niveau pour les versions On-Premise](../install-guide/upgrade-xml-documentation.md) de Experience Manager Guides.
