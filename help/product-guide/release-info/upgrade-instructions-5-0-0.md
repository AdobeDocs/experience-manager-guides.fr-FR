---
title: Notes de mise à jour | Instructions de mise à niveau pour la version 5.0.0 d’Adobe Experience Manager Guides
description: Découvrez la matrice de compatibilité et comment effectuer une mise à niveau vers la version 5.0.0 d’Adobe Experience Manager Guides.
exl-id: 763db247-133e-40c0-807a-2f965b1ddb2f
source-git-commit: ef8de789f8d6cf0cabc55f4d12c72b164619231c
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 6%

---

# Instructions de mise à niveau pour la version 5.0.0 (mars 2025)

Cet article couvre les instructions de mise à niveau et la matrice de compatibilité pour la version 5.0.0 d’Adobe Experience Manager Guides.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 5.0.0](../release-info/whats-new-5-0-0.md).

Pour obtenir la liste des problèmes qui ont été résolus dans cette version, voir [Problèmes résolus dans la version 5.0.0](../release-info/fixed-issues-5-0-0.md).

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par Experience Manager Guides version 5.0.0.

### Adobe Experience Manager

**5.0.0 UUID**

Version 6.5 Service Pack 22, Service Pack 21 et Service Pack 20

Pour plus d&#39;informations, consultez la section [Exigences techniques](../install-guide/download-install-technical-requirements.md) dans le Guide d&#39;installation et de configuration On-Premise.

### FrameMaker et FrameMaker Publishing Server

| Version | FMPS | FM |
| --- | --- | --- |
| 5.0.0 (UUID) | Pris en charge | 2022 ou version ultérieure |

### Connecteur D&#39;Oxygène

| Version | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 5.0.0 (UUID) | 3.7-uuid.2 | 3.7-uuid.2 | 2,3 | 2,3 |

### Version du modèle de la base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu de composants Experience Manager Guides pour Cloud Service | dxml-components.all-1.3.0 | aem-site-template-dxml.all-1.0.4 |

### Nouvelle version du modèle de site AEM


| Version des composants | Version du site |
|---|---|
| guides-components.all-1.3.0 | aemg-docs.all-1.2.0 |


## Mise à niveau vers la version 5.0.0 de Experience Manager Guides

Vous pouvez facilement mettre à niveau votre version actuelle de Guides vers la version 5.0.0. Avant de procéder à la mise à niveau vers la version 5.0.0 de Experience Manager Guides, vous devez tenir compte des points suivants :

- Si vous utilisez la version 4.6.3, 4.6.1, 4.6 ou 4.4, vous pouvez directement effectuer la mise à niveau vers la version 5.0.0.
- Si vous utilisez la version 4.3.x, 4.2, 4.2.1 (correctif 4.2.1.3), 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers la version 4.4 avant d’effectuer la mise à niveau vers la version 5.0.0.
- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant d’effectuer la mise à niveau vers la version 4.3.x.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à la version 3.8.5, reportez-vous à la section Mise à niveau de Experience Manager Guides dans le guide d’installation spécifique au produit disponible sur [l’archive PDF d’aide d’Adobe Experience Manager Guides](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
>Vous devez installer le pack de services AEM avant de mettre à niveau la version de Experience Manager Guides.

Pour plus d’informations, consultez les [instructions de mise à niveau pour les versions On-premise](../install-guide/upgrade-xml-documentation.md) de Experience Manager Guides.
