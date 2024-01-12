---
title: Installation de packages pour la publication basée sur un article
description: Découvrez comment installer des packages pour la publication basée sur un article
exl-id: d83fc1a9-0822-47f0-8099-22a74b9ced2a
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Installation de packages pour la publication basée sur un article {#id21BNL02052Z}

AEM Guides offre une puissante fonctionnalité de publication basée sur des articles intégrée à l’éditeur web. Cette fonction vous permet de publier simultanément une ou plusieurs rubriques. Une fois que vous avez ouvert une carte dans l’éditeur de cartes, vous pouvez accéder à l’onglet Sorties pour créer un paramètre prédéfini, puis choisir une ou plusieurs rubriques pour générer la sortie. Vous pouvez utiliser la fonction de publication basée sur des articles pour générer de manière incrémentielle la sortie d’une ou de plusieurs rubriques ou publier votre contenu sur une plateforme de la base de connaissances de manière article par article. Pour plus d’informations, voir *Publication basée sur des articles à partir de la section Éditeur web* dans le guide de l’utilisateur.

Pour créer un site AEM pour publier une sortie basée sur un article, procédez comme suit :

1. Télécharger **Package de contenu des composants XML Documentation pour Cloud Service** de votre [Portail de distribution de logiciels Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. Ouvrez AEM Gestionnaire de modules. L’URL par défaut pour accéder au gestionnaire de packages est la suivante : `https://<hostname>/crx/packmgr/index.jsp`
1. Téléchargez le module de contenu des composants XML Documentation pour Cloud Service, puis installez-le.
1. Téléchargez la `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` à partir de [Portail de distribution de logiciels Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. Dans la navigation globale, sélectionnez **Sites**.
1. Dans l’interface utilisateur de Sites, cliquez sur **Créer** dans le coin supérieur droit.
1. Sélectionner **Site à partir du modèle** de la **Créer** menu déroulant.
1. Cliquez sur le bouton **Importer** puis sélectionnez l’option `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` téléchargé sur votre système. Une fois le modèle de site importé, il est répertorié en bas de la page.

   >[!NOTE]
   >
   > Vous ne devez importer le fichier ZIP que pour la première fois. Une fois importé, le modèle de site est disponible dans la liste.

   Sélectionner **Modèle de base de connaissances pour la publication basée sur un article** pour créer le site AEM et cliquez sur **Suivant** dans le coin supérieur droit.

1. Saisissez le **Titre du site** et la variable **Nom du site** et cliquez sur **Créer** dans le coin supérieur droit. Un site AEM est créé à l’aide du modèle de site Tragopan . \(Le site Tragopan est un exemple de base de connaissances AEM site avec des modèles pour une catégorie, une section et des pages d’article.\)

   >[!NOTE]
   >
   > Vous pouvez créer plusieurs sites d’AEM en utilisant le même modèle.


Vous pouvez utiliser le site AEM pour publier votre article à l’aide des paramètres prédéfinis de sortie de l’éditeur web.

**Rubrique parente :**[ Personnalisation de l’éditeur web](conf-web-editor.md)
