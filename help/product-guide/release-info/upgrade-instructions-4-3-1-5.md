---
title: Notes de mise à jour | Instructions de mise à niveau pour la version Adobe Experience Manager Guides 4.3.1.5
description: Découvrez comment mettre à niveau vers 4.3.1.5 version d’Adobe Experience Manager Guides
role: Leader
exl-id: 856970ef-9f50-4452-b589-ba1f5ee73322
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 2%

---

# Instructions de mise à niveau pour la version 4.3.1.5

Cet article couvre les instructions de mise à niveau et la matrice de compatibilité pour 4.3.1.5 version d’Adobe Experience Manager Guides.


Pour obtenir la liste des problèmes qui ont été résolus dans cette version, voir [Problèmes résolus dans la version 4.3.1.5](../release-info/fixed-issues-4-3-1-5.md).




## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par la version Experience Manager Guides 4.3.1.5.

### Adobe Experience Manager

**4.3.1.5non-UUID**
Version 6.5 Service Pack 18, 17, 16, 15, 14

**4.3.1.5UUID**
Version 6.5 Service Pack 18, 17, 16, 15, 14

Pour plus d’informations, consultez la section *Exigences techniques* dans le Guide de configuration et d’installation On-Premise .

### FrameMaker et FrameMaker Publishing Server

| Version | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.3.1.5 (non-UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.3 ou version ultérieure |
| 4.3.1.5 (UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.4 ou version ultérieure |
| | | | | |

*La ligne de base et les conditions créées dans AEM sont prises en charge dans les versions FMPS à compter de 2020.2.

### Connecteur D&#39;Oxygène

| Version | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.3.1.5 (non-UUID) | 2.3-standard-5 | 2.3-standard-5 | 1,6 | 1,6 |
| 4.3.1.5 (UUID) | 3.2-uuid-5 | 3.2-uuid-5 | 2,3 | 2,3 |
|  |  |   | | |



### Version du modèle de la base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu de composants Experience Manager Guides pour Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |



## Mise à niveau vers la version 4.3.1.5 de Experience Manager Guides


Vous pouvez facilement mettre à niveau votre version actuelle des guides vers la version 4.3.1.5. Avant de poursuivre la mise à niveau vers la version 4.3.1.5 de Experience Manager Guides, tenez compte des points suivants :


- Si vous utilisez la version 4.3.1 ou 4.3.1.x, vous pouvez directement effectuer la mise à niveau vers la version 4.3.1.5.
- Si vous utilisez la version 4.3.0 ou 4.2 (correctif 4.2.1.3), vous devez effectuer la mise à niveau vers la version 4.3.1 avant d’effectuer la mise à niveau vers la version 4.3.1.5.

- Si vous utilisez la version 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers la version 4.3.1 avant de passer à la version 4.3.1.5.


- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant d’effectuer la mise à niveau vers la version 4.3.x.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à la version 3.8.5, reportez-vous à la section Mise à niveau de Experience Manager Guides dans le guide d’installation spécifique au produit disponible sur [l’archive PDF d’aide d’Adobe Experience Manager Guides](https://helpx.adobe.com/fr/xml-documentation-for-experience-manager/archive.html).



>[!NOTE]
>
>Vous devez installer le pack de services AEM avant de mettre à niveau la version de Experience Manager Guides.

Pour plus d’informations, consultez les [instructions de mise à niveau pour les versions On-premise](../install-guide/upgrade-xml-documentation.md) de Experience Manager Guides.
