---
title: Installation de packages pour la publication basée sur des articles
description: Découvrez comment installer des packages pour la publication basée sur des articles
exl-id: d83fc1a9-0822-47f0-8099-22a74b9ced2a
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Installation de packages pour la publication basée sur des articles {#id21BNL02052Z}

AEM Guides offre une puissante fonctionnalité de publication d’articles intégrée à l’éditeur web. Grâce à cette fonctionnalité, vous pouvez publier une ou plusieurs rubriques simultanément. Une fois que vous avez ouvert une carte dans l’éditeur de cartes, vous pouvez accéder à l’onglet Sorties pour créer un paramètre prédéfini, puis choisir une ou plusieurs rubriques pour générer la sortie. Vous pouvez utiliser la fonction de publication d’article pour générer de manière incrémentielle la sortie d’un ou de plusieurs sujets ou publier votre contenu sur une plateforme de base de connaissances article par article. Pour plus d’informations, reportez-vous à la section *Publication d’articles à partir de l’éditeur web* du guide de l’utilisateur.

Pour créer un site AEM en vue de publier une sortie basée sur des articles, procédez comme suit :

1. Téléchargez le package de contenu de composants XML Documentation **pour Cloud Service** à partir de votre portail de distribution de logiciels Adobe [&#128279;](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. Ouvrez le gestionnaire de packages AEM. L’URL par défaut pour accéder au gestionnaire de packages est : `https://<hostname>/crx/packmgr/index.jsp`
1. Téléchargez le package de contenu des composants XML Documentation pour Cloud Service, puis installez-le.
1. Téléchargez le fichier `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` à partir du portail de distribution logicielle [Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. Dans la navigation globale, sélectionnez **Sites**.
1. Dans l’interface utilisateur de Sites, cliquez sur le bouton **Créer** dans le coin supérieur droit.
1. Sélectionnez **Site à partir d’un modèle** dans la liste déroulante **Créer**.
1. Cliquez sur le bouton **Importer**, puis sélectionnez le `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` téléchargé sur votre système. Une fois le modèle de site importé, il est répertorié en bas.

   >[!NOTE]
   >
   > Vous ne devez importer le fichier ZIP que pour la première fois. Une fois importé, le modèle de site est disponible dans la liste.

   Sélectionnez **Modèle de base de connaissances pour la publication d’articles** pour créer le site AEM, puis cliquez sur **Suivant** dans le coin supérieur droit.

1. Saisissez le **Titre du site** et le **Nom du site**, puis cliquez sur **Créer** dans le coin supérieur droit. Un site AEM est créé à l’aide du modèle de site Tragopan. \(Le site Tragopan est un exemple de site AEM de la base de connaissances avec des modèles pour une catégorie, une section et des pages d’article.\)

   >[!NOTE]
   >
   > Vous pouvez créer plusieurs sites AEM à partir du même modèle.


Vous pouvez utiliser le site AEM pour publier votre article à l’aide des paramètres prédéfinis de sortie de l’éditeur web.

**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur web](conf-web-editor.md)
