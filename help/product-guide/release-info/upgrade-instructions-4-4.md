---
title: Notes de mise à jour | Instructions de mise à niveau de la version 4.4.0 d’Adobe Experience Manager Guides
description: Découvrez comment mettre à niveau vers la version 4.4.0 d’Adobe Experience Manager Guides
role: Leader
exl-id: 884178b6-7a72-471a-a6e3-238a543fb227
source-git-commit: 47c06dcc30b34780cbd26ded1ca400a5056a59ba
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 5%

---

# Instructions de mise à niveau de la version 4.4.0 (janvier 2024)

Cet article décrit les instructions de mise à niveau et la matrice de compatibilité de la version 4.4.0 d’Adobe Experience Manager Guides.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 4.4.0](../release-info/whats-new-4-4.md).

Pour obtenir la liste des problèmes qui ont été corrigés dans cette version, consultez la section [Problèmes résolus dans la version 4.4.0](../release-info/fixed-issues-4-4.md).




## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par la version 4.4.0 de Experience Manager Guides.

### Adobe Experience Manager

**4.4.0 Non-UUID**
Version 6.5 Service Pack 20, 19, 18 ou 17

**4.4.0 UUID**
Version 6.5 Service Pack 20, 19, 18 ou 17


Pour plus d’informations, consultez la section [Exigences techniques](../install-guide/download-install-technical-requirements.md) du Guide d’installation et de configuration On-Premise.

### FrameMaker et FrameMaker Publishing Server

| Version | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.4.0 (non UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.3 ou version ultérieure |
| 4.4.0 (UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.4 ou version ultérieure |
| | | | |

*Les conditions de base et créées dans AEM sont prises en charge dans les versions FMPS à partir de 2020.2.

### Connecteur Oxygen

| Version | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.4.0 (non UUID) | 2.7-normal-1 | 2.7-normal-1 | 1,6 | 1,6 |
| 4.4.0 (UUID) | 3.4-uuid-1 | 3.4-uuid-1 | 2,3 | 2,3 |
|  |  |   |



### Version du modèle de base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu des composants Experience Manager Guides pour Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |



## Mise à niveau vers la version 4.4.0 de Experience Manager Guides


Vous pouvez facilement mettre à niveau votre version actuelle des guides vers la version 4.4.0. Avant de procéder à la mise à niveau vers la version 4.4.0 de Experience Manager Guides, vous devez tenir compte des points suivants :


- Si vous utilisez la version 4.3.1, 4.3.0 ou 4.2.1 (correctif 4.2.1.3), vous pouvez directement effectuer la mise à niveau vers la version 4.4.0.
- Si vous utilisez les versions 4.2, 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers les versions 4.3.1, 4.3.0 ou 4.2.1 (correctif 4.2.1.3) avant de passer à la version 4.4.0.
- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant de passer à la version 4.3.x.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à 3.8.5, reportez-vous à la section Mise à niveau de Experience Manager Guides dans le guide d’installation spécifique au produit disponible sur l’ [archive du PDF d’aide Adobe Experience Manager Guides](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).



>[!NOTE]
>
>Vous devez installer AEM Service Pack avant de mettre à niveau la version de Experience Manager Guides.

Pour plus d&#39;informations, consultez les [instructions de mise à niveau pour les versions On-premise](../install-guide/upgrade-xml-documentation.md) de Experience Manager Guides.
