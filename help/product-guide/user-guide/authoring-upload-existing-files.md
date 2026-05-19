---
title: Charger des fichiers
description: Découvrez comment charger vos fichiers dans le référentiel AEM et gérer les erreurs. Connaître l’interface utilisateur de la console Assets, l’application de bureau AEM, l’outil d’ingestion de ressources en masse et utiliser FrameMaker pour le chargement en masse.
exl-id: b5430242-1122-43df-a0b2-275b1dea33f2
feature: Content Management
role: User
TQID: https://experienceleague.adobe.com/GG5Bx2yyJz2GaQFmMsDZ6wq6xzb4XUAsSBxEkRNvEVE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 536
ht-degree: 3%

---

# Charger des fichiers {#id176FF000JUI}

Il est probable que vous disposiez d&#39;un référentiel de contenu DITA existant que vous souhaitez utiliser avec Adobe Experience Manager Guides. Pour ce type de contenu existant, vous pouvez utiliser l’une des approches suivantes pour charger en bloc votre contenu dans le référentiel Adobe Experience Manager.

>[!IMPORTANT]
>
> Consultez la section [Ajout de ressources numériques à Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html) pour plus d’informations sur les méthodes de chargement de contenu prises en charge dans Adobe Experience Manager.

## Interface utilisateur de la console Assets

Pour [ajouter des ressources numériques à Adobe Experience Manager as a Cloud Service Assets](#upload-assets) à l’aide de l’interface utilisateur de la console Assets, sélectionnez la ressource requise sur votre bureau et faites glisser l’interface utilisateur Adobe Experience Manager \(navigateur web\) vers le dossier de destination. Lors du chargement de ressources, veillez à ce que les noms de fichier ne contiennent aucun caractère non pris en charge ou interdit.

Pour plus d’informations, consultez la section [&#x200B; Gestion des noms de fichier et caractères interdits &#x200B;](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html#filename-handling) de la documentation Adobe Experience Manager.

## Appli de bureau Adobe Experience Manager

Utilisez l’application de bureau Adobe Experience Manager si vous êtes un professionnel de la création et que vous souhaitez gérer les ressources sur votre bureau local. Vous pouvez ouvrir et modifier ces ressources à l’aide de vos applications de bureau. Vous pouvez également gérer des versions et partager vos fichiers avec d’autres utilisateurs. Pour plus d’informations, consultez l’appli de bureau [&#128279;](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html?lang=fr).

## Ingérant en bloc des ressources

Si vous disposez de migrations à grande échelle et d’ingestions en bloc occasionnelles, utilisez l’outil d’ingestion en bloc des ressources pour charger votre contenu. Grâce à cet outil, vous pouvez charger du contenu en bloc à partir des magasins de données pris en charge, tels qu’Azure ou S3. Pour plus d’informations, consultez [Asset bulk ingestor](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=en#asset-bulk-ingestor).

## Utilisation de FrameMaker pour le chargement en masse

Adobe FrameMaker s’accompagne d’un puissant connecteur Adobe Experience Manager qui vous permet de charger facilement vos documents DITA et autres documents FrameMaker \(`.book` et `.fm`\) dans Adobe Experience Manager. Vous pouvez utiliser diverses fonctionnalités de chargement de fichier, telles que le chargement d’un seul fichier ou d’un dossier complet avec ou sans dépendances \(comme les références de contenu, les références croisées et les graphiques\).

Pour plus d’informations sur l’utilisation de la fonction de chargement en bloc dans FrameMaker, consultez la section *Création d’un dossier CRX et chargement de fichiers* dans le guide d’utilisation de FrameMaker.

## Gestion des erreurs lors du chargement du contenu {#id201MI0I04Y4}

En cas d’échec de chargement d’un ou de plusieurs fichiers, une invite s’affiche à la fin du processus de chargement avec une liste des fichiers qui n’ont pas été chargés, comme illustré dans le fragment de code ci-dessous.

![](images/uuid-files-failed-to-upload_cs.png){width="650" align="center"}

Pour plus d’informations sur le fonctionnement des différents scénarios de chargement de fichiers, consultez la section [Gérer les fichiers et les dossiers](authoring-file-management.md#).

Si vous utilisez un outil tel que l’application de bureau Adobe Experience Manager ou l’outil d’ingestion de ressources en bloc, l’action à effectuer sur un fichier en double est contrôlée par un paramètre dans le serveur Adobe Experience Manager. Contactez votre administrateur système pour en savoir plus sur cette configuration.

**Rubrique parente :**&#x200B;[&#x200B; Gérer le contenu](authoring.md)
