---
title: Charger des fichiers
description: Découvrez comment charger vos fichiers dans le référentiel AEM et gérer les erreurs. Découvrez l’interface utilisateur de la console de ressources, AEM l’appli de bureau, l’outil d’assimilation en masse de ressources et utilisez le FrameMaker pour le chargement en masse.
exl-id: b5430242-1122-43df-a0b2-275b1dea33f2
feature: Content Management
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 1%

---

# Charger des fichiers {#id176FF000JUI}

Il est probable que vous disposiez d’un référentiel de contenu DITA existant que vous souhaitez utiliser avec AEM Guides. Pour ce contenu existant, vous pouvez utiliser l’une des méthodes suivantes pour charger en masse votre contenu dans AEM référentiel :

>[!IMPORTANT]
>
> Voir [Ajout de ressources numériques à Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html) pour plus d’informations, voir les méthodes de chargement de contenu prises en charge dans AEM.

## Interface utilisateur de la console Assets

Vous pouvez sélectionner du contenu sur votre bureau et le faire glisser sur l’interface utilisateur d’AEM \(navigateur web\) vers le dossier de destination. Pour plus d’informations, voir [Chargement de ressources](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html#upload-assets) dans la documentation AEM.

## Application de bureau AEM

Utilisez AEM’appli de bureau si vous êtes un professionnel de la création et souhaitez gérer les ressources sur votre ordinateur local. Vous pouvez ouvrir et modifier ces ressources avec vos applications de bureau. Vous pouvez également conserver des versions et partager vos fichiers avec d’autres utilisateurs. Pour plus d’informations, voir [Application de bureau AEM](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html?lang=fr).

## Ingestion en masse de ressources

Si vous disposez de migrations à grande échelle et d’assimilations en masse occasionnelles, utilisez l’outil d’ingestion en masse des ressources pour charger votre contenu. Grâce à cet outil, vous pouvez charger du contenu en masse à partir de banques de données prises en charge telles qu’Azure ou S3. Pour plus d’informations, voir [Ingestion en masse de ressources](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=en#asset-bulk-ingestor).

## Utilisation du FrameMaker pour le téléchargement en masse

Adobe FrameMaker est fourni avec un puissant connecteur d’AEM qui vous permet de télécharger facilement votre DITA existant et d’autres documents de FrameMaker \(`.book` et `.fm`\) dans AEM. Vous pouvez utiliser différentes fonctionnalités de chargement de fichier, telles que le chargement d’un seul fichier, le chargement d’un dossier complet avec ou sans dépendances \(comme les références de contenu, les références croisées et les graphiques\).

Pour plus d’informations sur l’utilisation de la fonctionnalité de chargement en masse dans FrameMaker, reportez-vous à la section . *Création d’un dossier CRX et chargement de fichiers* dans le Guide de l’utilisateur de FrameMaker.

## Gestion des erreurs lors du chargement de contenu {#id201MI0I04Y4}

En cas d’échec du chargement d’un ou de plusieurs fichiers, une invite s’affiche à la fin du processus de chargement avec une liste des fichiers dont le chargement a échoué :

![](images/uuid-files-failed-to-upload_cs.png){width="650" align="center"}

Pour plus d’informations sur les différents scénarios de téléchargement de fichiers, voir [Chargement du contenu DITA](authoring-file-management.md#).

Si vous utilisez un outil tel que l’appli de bureau AEM ou l’outil d’assimilation en masse de ressources, l’action à effectuer sur un fichier en double est contrôlée par un paramètre du serveur AEM. Contactez votre administrateur système pour connaître cette configuration.

**Rubrique parente :**[ Gestion du contenu](authoring.md)
