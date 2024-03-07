---
title: Notes de mise à jour | Instructions de mise à niveau pour la version 4.3.1.5 des guides Adobe Experience Manager
description: Découvrez comment mettre à niveau vers la version 4.3.1.5 des Guides Adobe Experience Manager
role: Leader
source-git-commit: 296bbea301df8828c00436db2b3c8b46dd235e64
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 2%

---


# Instructions de mise à niveau de la version 4.3.1.5

Cet article décrit les instructions de mise à niveau et la matrice de compatibilité de la version 4.3.1.5 des Guides Adobe Experience Manager.


Pour obtenir la liste des problèmes résolus dans cette version, consultez [Correction de problèmes dans la version 4.3.1.5](../release-info/fixed-issues-4-3-1-5.md).




## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par la version 4.3.1.5 de Experience Manager Guides.

### Adobe Experience Manager

**4.3.1.5 Non UUID**
Version 6.5 Service Pack 18, 17, 16, 15, 14

**4.3.1.5 UUID**
Version 6.5 Service Pack 18, 17, 16, 15, 14

Pour plus d’informations, voir la *Exigences techniques* dans le Guide d&#39;installation et de configuration On-Premise .

### FrameMaker et FrameMaker Publishing Server

| Version | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.3.1.5 (non UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.3 ou version ultérieure |
| 4.3.1.5 (UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.4 ou version ultérieure |
| | | | |

*Les conditions de base et créées dans AEM sont prises en charge dans les versions FMPS à partir de 2020.2.

### Connecteur Oxygen

| Version | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.3.1.5 (non UUID) | 2.3-normal-5 | 2.3-normal-5 | 1,6 | 1,6 |
| 4.3.1.5 (UUID) | 3.2-uuid-5 | 3.2-uuid-5 | 2,3 | 2,3 |
|  |  |   |



### Version du modèle de base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Module de contenu des composants des guides du Experience Manager pour Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |



## Mise à niveau vers la version 4.3.1.5 des guides du Experience Manager


Vous pouvez facilement mettre à niveau votre version actuelle des guides vers la version 4.3.1.5. Avant de procéder à la mise à niveau vers la version 4.3.1.5 des Guides du Experience Manager, vous devez tenir compte des points suivants :


- Si vous utilisez la version 4.3.1 ou 4.3.1.x, vous pouvez directement effectuer la mise à niveau vers la version 4.3.1.5.
- Si vous utilisez la version 4.3.0 ou 4.2 (correctif 4.2.1.3), vous devez effectuer la mise à niveau vers la version 4.3.1 avant de passer à la version 4.3.1.5.

- Si vous utilisez la version 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers la version 4.3.1 avant de passer à la version 4.3.1.5.


- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant de passer à la version 4.3.x.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à 3.8.5, reportez-vous à la section Guides du Experience Manager de mise à niveau du guide d’installation spécifique au produit disponible dans la section [Archive du PDF d’aide de Adobe Experience Manager Guides](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).



>[!NOTE]
>
>Vous devez installer AEM Service Pack avant de mettre à niveau la version des guides du Experience Manager.

Pour plus d’informations, voir [Instructions de mise à niveau pour les versions On-premise](../install-guide/upgrade-xml-documentation.md) de guides Experience Manager.

