---
title: Notes de mise à jour | Instructions de mise à niveau pour Adobe Experience Manager Guides 5.2.0 Service Pack 3
description: Découvrez la matrice de compatibilité et comment effectuer une mise à niveau vers la version 5.2.0 Service Pack 3 d’Adobe Experience Manager Guides.
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: aa4de29e96d7e140730c6c36c925b906429944f8
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 3%
---
# Instructions de mise à niveau vers la version 5.2.0 Service Pack 3 (novembre 2026)

Cet article contient les instructions de mise à niveau et la matrice de compatibilité pour la version 5.2.0 du Service Pack 3 d’Adobe Experience Manager Guides.

Pour obtenir la liste des problèmes résolus dans cette version, consultez [Problèmes résolus dans le pack de services 3 d’ 5.2.0](../release-info/fixed-issues-5-2-0-sp3.md).

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par Experience Manager Guides 5.2.0 Service Pack 3.

| AEM Guides | Version d’AEM | Pack de services |
| --- | --- | --- |
| 5.2.0 Service Pack 3 (UUID) | 6.5 LTS | 2 |
| 5.2.0 Service Pack 3 (UUID) | 6.5 | 24, 23, 22 |

Pour plus d&#39;informations, consultez la section [Exigences techniques](../install-conf-guide/aemg-technical-requirements.md) du Guide d&#39;installation et de configuration On-Premise.


### Ressources Java SDK

Utilisez les ressources suivantes lors du développement de modules externes Java personnalisés ou d’intégrations avec Experience Manager Guides. Assurez-vous que la version de SDK correspond à la version de Experience Manager Guides que vous avez installée.

| Version | Version de Java SDK | Maven Central | Référence de l’API Java |
|---|---|---|----|
| 5.2.0 Service Pack 3 (UUID) | 5.2.2 | [API AEM Guides SDK 5.2.2](https://central.sonatype.com/artifact/com.adobe.aem/aem-guides-sdk-api/5.2.2/) | [Javadoc 5.2.2](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html) |

Pour plus d’informations, consultez [Configurer et utiliser le fichier JAR de l’API à partir du référentiel central Maven](https://experienceleague.adobe.com/fr/docs/experience-manager-guides/using/api-reference/introduction).


### FrameMaker et FrameMaker Publishing Server

| Version | FMPS | FM |
| --- | --- | --- |
| 5.2.0 Service Pack 3 (UUID) | Pris en charge | 2026 ou version ultérieure |

### Connecteur D&#39;Oxygène

| Version | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 5.2.0 Service Pack 3 (UUID) | 3.8-uuid.1 | 3.8-uuid.1 | 2,3 | 2,3 |

### Version du modèle de la base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu de composants Experience Manager Guides pour Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |

### Nouvelle version du modèle de site AEM


| AEM Guides | Version d’AEM | Version des composants | Version du site |
|---|---|---| ---|
| 5.2.0 Service Pack 3 UUID | 6.5 LTS | guides-components.all-1.4.1 | aemg-docs.all-1.2.0 |
| 5.2.0 Service Pack 3 UUID | 6.5 | guides-components.all-1.4.0 | aemg-docs.all-1.2.0 |

## Conditions préalables

Avant de lancer le processus de mise à niveau du pack de services 3 de Experience Manager Guides 5.2.0, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 5.2.0.
1. (Facultatif) A fermé toutes les tâches de traduction.
1. Modification du niveau de journal en **INFO** pour la classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` et ajout de ces journaux dans un nouveau fichier journal, par exemple `logs/translation_upgrade.log`.

## Chemin de mise à niveau pour Experience Manager Guides 5.2.0 Service Pack 3

Vous pouvez facilement mettre à niveau votre version actuelle de Experience Manager Guides vers la version 5.2.0 du Service Pack 3 sur **AEM 6.5** ou **AEM 6.5 LTS**.

>[!IMPORTANT]
>
> - **Pour AEM 6.5 LTS** : le pack de services 3 de Experience Manager Guides 5.2.0 est pris en charge uniquement avec le pack de services 2 d’AEM 6.5 LTS.
> - **Pour AEM 6.5** : le pack de services 3 de Experience Manager Guides 5.2.0 est pris en charge uniquement avec les packs de services 24, 23 et 22 d’AEM 6.5.
> - Si vous utilisez actuellement AEM 6.5 et envisagez de passer à AEM 6.5 LTS, veillez à effectuer d’abord la mise à niveau d’AEM avant de poursuivre la mise à niveau vers Experience Manager Guides 5.2.0. Pour plus d’informations, consultez [Mise à niveau vers Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/fr/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).
> - Si vous utilisez actuellement AEM 6.5 et envisagez de passer à AEM 6.5 Service Pack 24 ou une version ultérieure, veillez d’abord à effectuer la mise à niveau d’AEM. Une fois que vous avez terminé, réinstallez Experience Manager Guides 5.2.0. avant d’installer Experience Manager Guides 5.2.1.

Avant de procéder à la mise à niveau vers la version 5.2.0 Service Pack 3 de Experience Manager Guides, vous devez tenir compte des points suivants :

- Si vous utilisez la version 5.2.0 Service Pack 1 ou 5.2.0, vous pouvez directement mettre à niveau vers la version 5.2.0 Service Pack 3.
- Si vous utilisez la version 5.0.0, 5.0.3, 5.1.0, 5.1.3 ou 5.1.4, vous pouvez directement effectuer la mise à niveau vers la version 5.2.0.
- Si vous utilisez les versions 4.6.3, 4.6.4 et 5.0.x, vous pouvez directement effectuer la mise à niveau vers la version 5.1.0.
- Si vous utilisez la version 4.6.0 ou 4.6.1, vous devez effectuer la mise à niveau vers la version 4.6.3, 4.6.4 ou 5.0.0 avant d’effectuer la mise à niveau vers la version 5.1.0.
- Si vous utilisez la version 4.3.x, 4.2, 4.2.1 (correctif 4.2.1.3), 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers la version 4.4 avant la version 5.1.0.
- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant d’effectuer la mise à niveau vers la version 4.3.x.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à la version 3.8.5, reportez-vous à la section Mise à niveau de Experience Manager Guides dans le guide d’installation spécifique au produit disponible sur [l’archive PDF de l’aide d’Adobe Experience Manager Guides](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

## Processus de mise à niveau vers Experience Manager Guides 5.2.0 Service Pack 3

>[!IMPORTANT]
>
> Le post-traitement et l’indexation peuvent prendre quelques heures. Il est recommandé de démarrer le processus de mise à niveau pendant les heures creuses.

1. Téléchargez le package de la version 5.2.0 Service Pack 3 à partir du [Portail de distribution logicielle Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package de version sur lequel vous souhaitez effectuer la mise à niveau et attendez que le bundle soit installé.
1. *(Facultatif)* Mise à niveau Le plug-in Connecteur Oxygen est fourni avec la version vers laquelle vous effectuez la mise à niveau.
1. Effacez la mémoire cache du navigateur après l’installation du package.
1. Si vous avez activé le paramètre `Enable markup find and replace` pour accéder à la fonction Rechercher et remplacer dans la vue source du contenu précédemment capturé, vous devez réindexer l’index `guidesAssetLucene`. Pour plus d’informations, consultez [Réindexation pour Rechercher et remplacer](../install-conf-guide/custom-indexing-on-prem.md).







