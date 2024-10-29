---
title: Notes de mise à jour | Instructions de mise à niveau de la version 4.6.1 d’Adobe Experience Manager Guides
description: Découvrez comment mettre à niveau vers la version 4.6.1 d’Adobe Experience Manager Guides
role: Leader
source-git-commit: 3547eb43977f31dae297ca5cb1f1ab53f7f2b067
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 1%

---

# Instructions de mise à niveau de la version 4.6.1 (octobre 2024)

Cet article décrit les instructions de mise à niveau et la matrice de compatibilité de la version 4.6.1 d’Adobe Experience Manager Guides.

Pour obtenir la liste des problèmes qui ont été corrigés dans cette version, consultez la section [Problèmes résolus dans la version 4.6.1](fixed-issues-4-6-1.md).

## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par la version 4.6.1 de Experience Manager Guides.

### Adobe Experience Manager

**4.6.1 Non-UUID**
Version 6.5 Service Pack 21, 20 et 19

**4.6.1 UUID**
Version 6.5 Service Pack 21, 20 et 19

Pour plus d’informations, consultez la section [Exigences techniques](../install-guide/download-install-technical-requirements.md) du Guide d’installation et de configuration On-Premise.

### FrameMaker et FrameMaker Publishing Server

| Version | FMPS 2022 | FMPS 2020 | FM 2022 | FM 2020 |
| --- | --- | --- | --- | --- |
| 4.6.1 (non UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.3 ou version ultérieure |
| 4.6.1 (UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.4 ou version ultérieure |
| | | | |

*Les conditions de base et créées dans AEM sont prises en charge dans les versions FMPS à partir de 2020.2.

### Connecteur Oxygen

| Version | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.6.1 (non UUID) | 2.8-normal-10 | 2.8-normal-10 | 1,6 | 1,6 |
| 4.6.1 (UUID) | 3.6-uuid.9 | 3.6-uuid.9 | 2,3 | 2,3 |
|  |  |   |

### Version du modèle de base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu des composants Experience Manager Guides pour Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

### Nouvelle version du modèle de site AEM


| Version des composants | Version du site |
|---|---|
| guides-components.all-1.0.0 | aemg-docs.all-1.0.0 |

## Mise à niveau vers la version 4.6.1 de Experience Manager Guides

Vous pouvez facilement mettre à niveau votre version actuelle des guides vers la version 4.6.1. Avant de procéder à la mise à niveau vers la version 4.6.1 de Experience Manager Guides, vous devez tenir compte des points suivants :

- Si vous utilisez la version 4.6.0, vous pouvez directement effectuer la mise à niveau vers la version 4.6.1.
- Si vous utilisez la version 4.4, 4.3.1 ou 4.3.0 , vous devez effectuer la mise à niveau vers la version 4.6.0 avant de passer à la version 4.6.1.
- Si vous utilisez les versions 4.2, 4.2.1 (correctif 4.2.1.3), 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers la version 4.4 avant de passer à la version 4.6.0.
- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant de passer à la version 4.3.x.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à 3.8.5, reportez-vous à la section Mise à niveau de Experience Manager Guides dans le guide d’installation spécifique au produit disponible sur l’ [archive du PDF d’aide Adobe Experience Manager Guides](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
>Vous devez installer AEM Service Pack avant de mettre à niveau la version de Experience Manager Guides.

Le processus de mise à niveau de la version 4.6.1 suit les mêmes étapes que la version 4.6.0. Pour obtenir des instructions détaillées, consultez les [instructions de mise à niveau pour les versions On-premise](../install-guide/upgrade-xml-documentation.md) de Experience Manager Guides.
