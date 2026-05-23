---
title: Notes de mise à jour | Instructions de mise à niveau pour Adobe Experience Manager Guides version 4.4.0
description: Découvrez comment mettre à niveau vers la version 4.4.0 d’Adobe Experience Manager Guides
role: Leader
exl-id: 884178b6-7a72-471a-a6e3-238a543fb227
TQID: https://experienceleague.adobe.com/bich0n61TfwxRPQLCrM-HVSZ8cfjyv6s3SjUf2vIjnQ
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: afb45297-4313-4f67-818e-bc0b03abe086
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: cda0baeb-996e-4aaa-92d1-41032e34fd68
  - id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 454
ht-degree: 5%

---

# Instructions de mise à niveau pour la version 4.4.0 (janvier 2024)

Cet article couvre les instructions de mise à niveau et la matrice de compatibilité pour la version 4.4.0 d’Adobe Experience Manager Guides.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 4.4.0](../release-info/whats-new-4-4.md).

Pour obtenir la liste des problèmes qui ont été résolus dans cette version, voir [Problèmes résolus dans la version 4.4.0](../release-info/fixed-issues-4-4.md).




## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par la version 4.4.0 de Experience Manager Guides.

### Adobe Experience Manager

**4.4.0 Non-UUID**
Version 6.5 Service Pack 20, 19, 18 ou 17

UUID **4.4.0**
Version 6.5 Service Pack 20, 19, 18 ou 17


Pour plus d&#39;informations, consultez la section [Exigences techniques](../install-guide/download-install-technical-requirements.md) dans le Guide d&#39;installation et de configuration On-Premise.

### FrameMaker et FrameMaker Publishing Server

| Version | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.4.0 (non-UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.3 ou version ultérieure |
| 4.4.0 (UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.4 ou version ultérieure |
| | | | | |

*La ligne de base et les conditions créées dans AEM sont prises en charge dans les versions FMPS à compter de 2020.2.

### Connecteur D&#39;Oxygène

| Version | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.4.0 (non-UUID) | 2.7-normal-1 | 2.7-normal-1 | 1,6 | 1,6 |
| 4.4.0 (UUID) | 3.4-uuid-1 | 3.4-uuid-1 | 2,3 | 2,3 |
|  |  |   | |  |



### Version du modèle de la base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu de composants Experience Manager Guides pour Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |



## Mise à niveau vers la version 4.4.0 de Experience Manager Guides


Vous pouvez facilement mettre à niveau votre version actuelle de Guides vers la version 4.4.0. Avant de procéder à la mise à niveau vers la version 4.4.0 de Experience Manager Guides, vous devez tenir compte des points suivants :


- Si vous utilisez la version 4.3.1, 4.3.0 ou 4.2.1 (correctif 4.2.1.3), vous pouvez directement effectuer la mise à niveau vers la version 4.4.0.
- Si vous utilisez la version 4.2, 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers la version 4.3.1, 4.3.0 ou 4.2.1 (correctif 4.2.1.3) avant de passer à la version 4.4.0.
- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant d’effectuer la mise à niveau vers la version 4.3.x.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à la version 3.8.5, reportez-vous à la section Mise à niveau de Experience Manager Guides dans le guide d’installation spécifique au produit disponible sur [l’archive PDF d’aide d’Adobe Experience Manager Guides](https://helpx.adobe.com/fr/xml-documentation-for-experience-manager/archive.html).



>[!NOTE]
>
>Vous devez installer le pack de services AEM avant de mettre à niveau la version de Experience Manager Guides.

Pour plus d’informations, consultez les [instructions de mise à niveau pour les versions On-premise](../install-guide/upgrade-xml-documentation.md) de Experience Manager Guides.
