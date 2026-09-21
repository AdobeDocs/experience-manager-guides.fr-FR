---
title: Notes de mise à jour | Instructions de mise à niveau pour Adobe Experience Manager Guides 5.2.0 Service Pack 1
description: Découvrez la matrice de compatibilité et comment effectuer une mise à niveau vers la version 5.2.0 Service Pack 1 d’Adobe Experience Manager Guides.
source-git-commit: b975fd2c2d79fb56f180484431af135d35eec750
workflow-type: tm+mt
source-wordcount: '885'
ht-degree: 4%
---
# Instructions de mise à niveau vers la version 5.2.0 Service Pack 1 (septembre 2026)

Cet article contient les instructions de mise à niveau et la matrice de compatibilité pour la version 5.2.0 du Service Pack 1 d’Adobe Experience Manager Guides.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version 5.2.0 du Service Pack 1](../release-info/whats-new-5-2-1.md).

Pour obtenir la liste des problèmes qui ont été résolus dans cette version, voir [Problèmes résolus dans le pack de services 1 d’ 5.2.0](../release-info/fixed-issues-5-2-0-sp1.md).

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par Experience Manager Guides 5.2.0 Service Pack 1.

| AEM Guides | Version d’AEM | Pack de services |
| --- | --- | --- |
| 5.2.0 Service Pack 1 (UUID) | 6.5 LTS | 2 |
| 5.2.0 Service Pack 1 (UUID) | 6.5 | 24, 23, 22 |

Pour plus d&#39;informations, consultez la section [Exigences techniques](../install-conf-guide/aemg-technical-requirements.md) dans le Guide d&#39;installation et de configuration On-Premise.


### Ressources Java SDK

Utilisez les ressources suivantes lors du développement de modules externes Java personnalisés ou d’intégrations avec Experience Manager Guides. Assurez-vous que la version de SDK correspond à la version de Experience Manager Guides que vous avez installée.

| Version | Version de Java SDK | Maven Central | Référence de l’API Java |
|---|---|---|----|
| 5.2.0 Service Pack 1 (UUID) | 5.2.2 | [API AEM Guides SDK 5.2.2](https://central.sonatype.com/artifact/com.adobe.aem/aem-guides-sdk-api/5.2.2/) | [Javadoc 5.2.2](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html) |

Pour plus d’informations, consultez [Configuration et utilisation du fichier JAR de l’API à partir du référentiel central Maven](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/api-reference/introduction).


### FrameMaker et FrameMaker Publishing Server

| Version | FMPS | FM |
| --- | --- | --- |
| 5.2.0 Service Pack 1 (UUID) | Pris en charge | 2026 ou version ultérieure |

### Connecteur D&#39;Oxygène

| Version | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 5.2.0 Service Pack 1 (UUID) | 3.8-uuid.1 | 3.8-uuid.1 | 2,3 | 2,3 |

### Version du modèle de la base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu de composants Experience Manager Guides pour Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |

### Nouvelle version du modèle de site AEM


| AEM Guides | Version d’AEM | Version des composants | Version du site |
|---|---|---| ---|
| 5.2.0 Service Pack 1 UUID | 6.5 LTS | guides-components.all-1.4.1 | S/O |
| 5.2.0 Service Pack 1 UUID | 6.5 | guides-components.all-1.4.0 | aemg-sites-template-1.3.0 |

## Prérequis

Avant de lancer le processus de mise à niveau du pack de services 1 de Experience Manager Guides 5.2.0, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 5.2.0.
1. (Facultatif) A fermé toutes les tâches de traduction.
1. Modification du niveau de journal en **INFO** pour `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` classe et ajout de ces journaux dans un nouveau fichier journal, par exemple, `logs/translation_upgrade.log`.

## Chemin de mise à niveau vers Experience Manager Guides 5.2.0 Service Pack 1

Vous pouvez facilement mettre à niveau votre version actuelle de Experience Manager Guides vers la version 5.2.0 Service Pack 1 sur **AEM 6.5** ou **AEM 6.5 LTS**.

>[!IMPORTANT]
>
> - **Pour AEM 6.5 LTS** : Experience Manager Guides 5.2.0 Service Pack 1 est pris en charge uniquement avec AEM 6.5 LTS Service Pack 2.
> - **Pour AEM 6.5** le pack de services 1 de Experience Manager Guides 5.2.0 est pris en charge uniquement avec les packs de services 24, 23 et 22 d’AEM 6.5.
> - Si vous utilisez actuellement AEM 6.5 et envisagez de passer à AEM 6.5 LTS, veillez à effectuer d’abord la mise à niveau d’AEM avant de poursuivre la mise à niveau vers Experience Manager Guides 5.2.0. Pour plus d’informations, consultez la section [Mise à niveau vers Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

Avant de procéder à la mise à niveau vers la version 5.2.0 Service Pack 1 de Experience Manager Guides, vous devez tenir compte des points suivants :

- Si vous utilisez la version 5.2.0, vous pouvez directement effectuer la mise à niveau vers la version 5.2.0 du Service Pack 1.
- Si vous utilisez la version 5.0.0, 5.0.3, 5.1.0, 5.1.3 ou 5.1.4, vous pouvez directement effectuer la mise à niveau vers la version 5.2.0.
- Si vous utilisez les versions 4.6.3, 4.6.4 et 5.0.x, vous pouvez directement effectuer la mise à niveau vers la version 5.1.0.
- Si vous utilisez la version 4.6.0 ou 4.6.1, vous devez effectuer la mise à niveau vers la version 4.6.3, 4.6.4 ou 5.0.0 avant d’effectuer la mise à niveau vers la version 5.1.0.
- Si vous utilisez la version 4.3.x, 4.2, 4.2.1 (correctif 4.2.1.3), 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers la version 4.4 avant d’effectuer la mise à niveau vers la version 5.1.0.
- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant d’effectuer la mise à niveau vers la version 4.3.x.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à la version 3.8.5, reportez-vous à la section Mise à niveau de Experience Manager Guides dans le guide d’installation spécifique au produit disponible sur [l’archive PDF d’aide d’Adobe Experience Manager Guides](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

## Processus de mise à niveau vers Experience Manager Guides 5.2.0 Service Pack 1

>[!IMPORTANT]
>
> Le post-traitement et l’indexation peuvent prendre quelques heures. Il est recommandé de démarrer le processus de mise à niveau pendant les heures creuses.

1. Téléchargez le package de la version 5.2.0 Service Pack 1 à partir du portail de distribution logicielle [](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package de version sur lequel vous souhaitez effectuer la mise à niveau et attendez que le bundle soit installé.
1. *(Facultatif)* Mettre à niveau le plug-in Oxygen Connector fourni avec la version vers laquelle vous effectuez la mise à niveau.
1. Effacez la mémoire cache du navigateur après l’installation du package.
1. Si vous avez activé le paramètre `Enable markup find and replace` pour accéder à la fonction Rechercher et remplacer dans la vue source du contenu précédemment capturé, vous devez réindexer l’index `guidesAssetLucene`. Pour plus d’informations, consultez [Réindexation pour la recherche et le remplacement](../install-conf-guide/custom-indexing-on-prem.md).







