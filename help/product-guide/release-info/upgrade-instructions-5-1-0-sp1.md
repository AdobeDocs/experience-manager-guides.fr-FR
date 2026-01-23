---
title: Notes de mise à jour | Instructions de mise à niveau vers Adobe Experience Manager Guides 5.1.0 Service Pack 1
description: Découvrez la matrice de compatibilité et comment effectuer une mise à niveau vers la version 5.1.0 Service Pack 1 d’Adobe Experience Manager Guides.
source-git-commit: 1df6b18aa441df33f96eb8298f4ef2799754cbcf
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 1%

---

# Instructions de mise à niveau vers la version 5.1.0 Service Pack 1 (octobre 2025)

Cet article contient les instructions de mise à niveau et la matrice de compatibilité pour la version 5.1.0 du Service Pack 1 d’Adobe Experience Manager Guides.

Pour obtenir la liste des problèmes qui ont été résolus dans cette version, voir [Problèmes résolus dans le pack de services 1 d’ 5.1.0](../release-info/fixed-issues-5-1-0-sp1.md).

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par Experience Manager Guides 5.1.0 Service Pack 1.

### Adobe Experience Manager

**5.1.0 Service Pack 1 UUID**

Version 6.5 Service Pack 23, Service Pack 22 et Service Pack 21

Pour plus d&#39;informations, consultez la section [Exigences techniques](../install-guide/download-install-technical-requirements.md) dans le Guide d&#39;installation et de configuration On-Premise.

### FrameMaker et FrameMaker Publishing Server

| Version | FMPS | FM |
| --- | --- | --- |
| 5.1.0 Service Pack 1 (UUID) | Pris en charge | 2022 ou version ultérieure |

### Connecteur D&#39;Oxygène

| Version | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 5.1.0 Service Pack 1 (UUID) | 3.8-uuid.1 | 3.8-uuid.1 | 2,3 | 2,3 |

### Version du modèle de la base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu de composants Experience Manager Guides pour Cloud Service | dxml-components.all-1.3.0 | aem-site-template-dxml.all-1.0.4 |

### Nouvelle version du modèle de site AEM


| Version des composants | Version du site |
|---|---|
| guides-components.all-1.4.0 | aemg-docs.all-1.2.0 |


## Mise à niveau vers la version 5.1.0 Service Pack 1 de Experience Manager Guides

Vous pouvez facilement mettre à niveau votre version actuelle de Guides vers la version 5.1.0 du Service Pack 1. Avant de procéder à la mise à niveau vers la version 5.1.0 Service Pack 1 de Experience Manager Guides, vous devez tenir compte des points suivants :

- Si vous utilisez la version 5.1.0, vous pouvez directement effectuer la mise à niveau vers la version 5.1.0 du Service Pack 1.
- Si vous utilisez la version 4.6.0, 4.6.x, 5.0.0 ou 5.0.x, vous devez effectuer la mise à niveau vers la version 5.1.0.
- Si vous utilisez la version 4.6.3, 4.6.1, 4.6 ou 4.4, vous devez effectuer la mise à niveau vers la version 5.0.0.
- Si vous utilisez la version 4.3.x, 4.2, 4.2.1 (correctif 4.2.1.3), 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers la version 4.4 avant d’effectuer la mise à niveau vers la version 5.0.0.
- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant d’effectuer la mise à niveau vers la version 4.3.x.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à la version 3.8.5, reportez-vous à la section Mise à niveau de Experience Manager Guides dans le guide d’installation spécifique au produit disponible sur [l’archive PDF d’aide d’Adobe Experience Manager Guides](https://helpx.adobe.com/fr/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
>Vous devez installer le pack de services AEM avant de mettre à niveau la version de Experience Manager Guides.

Pour plus d’informations, consultez les [instructions de mise à niveau pour les versions On-premise](../install-guide/upgrade-xml-documentation.md) de Experience Manager Guides.
