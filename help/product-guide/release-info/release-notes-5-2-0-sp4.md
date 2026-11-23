---
title: Notes de mise à jour | Notes de mise à jour d’Adobe Experience Manager Guides 5.2.0 Service Pack 4
description: Découvrez le processus de mise à niveau et les correctifs de bugs dans la version 5.2.0 Service Pack 4 d’Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: ad78587f55ec7190443dbbce80f596821ec41f9f
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 2%
---
# Notes de mise à jour de la version 5.2.0 Service Pack 4 (novembre 2026)

Cet article fournit des informations sur les instructions de mise à niveau, la compatibilité Java SDK, les problèmes résolus et les problèmes connus de la version 5.2.0 Service Pack 4 d’Adobe Experience Manager Guides.

## Ressources Java SDK

Utilisez les ressources suivantes lors du développement de modules externes Java personnalisés ou d’intégrations avec Experience Manager Guides. Assurez-vous que la version de SDK correspond à la version de Experience Manager Guides que vous avez installée.

| Version | Version de Java SDK | Maven Central | Référence de l’API Java |
|---|---|---|----|
| 5.2.0 Service Pack 4 (UUID) | 5.2.2 | [API AEM Guides SDK 5.2.2](https://central.sonatype.com/artifact/com.adobe.aem/aem-guides-sdk-api/5.2.2/) | [Javadoc 5.2.2](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html) |

Pour plus d’informations, consultez [Configurer et utiliser le fichier JAR de l’API à partir du référentiel central Maven](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/api-reference/introduction).

## Mise à niveau vers la version 5.2.0 Service Pack 4 de Experience Manager Guides

Découvrez comment installer le pack de services 4 de Experience Manager Guides 5.2.0.

>[!NOTE]
>
>Cette version est disponible uniquement pour AEM 6.5 LTS. Le pack de services pris en charge est le pack de services 2 d’AEM 6.5 LTS.

### Conditions préalables

Avant de commencer le processus de mise à niveau du pack de services 4 de Experience Manager Guides 5.2.0, assurez-vous d’utiliser la version 5.2.0 du pack de services 1.

### Processus de mise à niveau vers la version 5.2.0 du pack de services 4

1. Téléchargez le package Experience Manager Guides version 5.2.0 Service Pack 4.
1. Chargez le package vers votre instance à l’aide du gestionnaire de packages (`/crx/packmgr`).
1. Installez le package . Vérifiez ensuite que les lots `fmdita` sont revenus à l’état **Actif**. Vous pouvez vérifier l’état du lot à `/system/console/bundles`.
1. Effacez la mémoire cache de votre navigateur.

## Problèmes résolus

Les bogues corrigés dans différentes zones sont répertoriés ci-dessous :

### Création

- Lorsque vous faites glisser une ressource dans un mappage à partir du panneau Explorateur qui n’a pas été actualisé après qu’un autre auteur a déplacé cette ressource, une référence rompue est ajoutée au mappage. (GUIDES-57869)

### Gestion des ressources numériques

- Lorsque vous remplacez une ressource non DITA existante, telle qu&#39;une image, à l&#39;aide de l&#39;option **Remplacer les fichiers existants**, la nouvelle version de l&#39;image chargée n&#39;est pas créée. Par conséquent, la sortie générée à l’aide de la ligne de base contient l’ancienne ressource. (GUIDES-59287)

- Lorsqu&#39;une ressource non DITA, telle qu&#39;une image, qui a été migrée d&#39;une configuration non-UUID vers une configuration UUID est rétablie ou branchée sur une autre version, son UUID change. Les références existantes à la ressource ne sont plus résolues et l’image apparaît endommagée dans les rubriques qui y font référence. (GUIDES-58414)

### Publication

- Lors de la publication d’une carte pendant l’exportation d’autres cartes, la sortie utilise par intermittence un format d’image de qualité inférieure au lieu de l’image vectorielle d’origine. (GUIDES-55221)

## Problèmes connus

Adobe a identifié le problème connu suivant dans la version 5.2.0 Service Pack 4 :

- Lorsque vous faites glisser et déposez un élément à un emplacement non valide, l’éditeur le déplace à l’emplacement valide le plus proche, pendant lequel la référence peut conserver son chemin de référentiel. De même, lorsque vous remplacez par glisser-déposer une référence existante dans un plan DITA, la nouvelle référence peut conserver son chemin d&#39;accès au référentiel. (GUIDES-60688)