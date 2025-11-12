---
title: Télécharger et installer des modèles AEM Sites pour les services On-Premise
description: Découvrez comment télécharger et installer des modèles AEM Sites pour sur les services Prem
feature: Installation
role: Admin
level: Experienced
exl-id: aa843a72-ff0d-4c9a-a87d-48d099087b5e
source-git-commit: 4c564a0ffaa8f287bcaf012634d49dbf1e0682b4
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 0%

---

# Télécharger et installer des modèles AEM Sites (services On-Premise)

Ce guide fournit des instructions détaillées pour installer et configurer le dernier modèle AEM Guides pour générer AEM Sites. Pour installer les packages requis, créer et configurer des paramètres prédéfinis et générer AEM Sites, procédez comme suit.

## Conditions préalables

Avant de poursuivre la configuration, assurez-vous que les conditions préalables suivantes sont remplies :

- **Adobe Experience Manager (AEM) :** une instance en cours d’exécution de **AEM 6.5** avec **Service Pack** 21, 20 et 19 et **AEM Guides 4.6.0**, ou des versions ultérieures installées.

- **Autorisations requises** : assurez-vous de disposer des autorisations suivantes :

   - Accès au **Portail de distribution logicielle** pour télécharger les packages requis
   - Accès au **gestionnaire de packages CRX** pour installer des packages dans AEM.
   - Les autorisations de création et de modification des paramètres prédéfinis dans AEM Guides.

- **Télécharger les packages** : téléchargez les packages suivants à partir du **Portail de distribution logicielle** :

   - Package de composants : on-prem-guides-components.all-1.x.0.zip
   - Package Sites : aemg-docs.all-1.x.0.zip

## Installation de packages à l’aide du gestionnaire de packages CRX

1. **Installez le package de composants :**
   1. Accédez au [**Gestionnaire de packages CRX**](http://&lt;your-aem-instance>/crx/packmgr).
   2. Téléchargez et installez le package on-prem-guides-components.all-1.x.0.zip .

2. **Installation du package Sites :** téléchargez et installez le package aemg-docs.all-1.x.0.zip à l’aide du gestionnaire de packages CRX.


## Création et configuration d’un paramètre prédéfini de site AEM

1. **Créer un nouveau paramètre prédéfini :**
   1. Ouvrez un plan DITA dans AEM Guides et accédez au panneau **Sortie**.
   2. Sélectionnez **Créer un paramètre prédéfini**.
   3. Sélectionnez le type comme **AEM Sites**.
   4. Saisissez le nom du paramètre prédéfini.
   5. Décochez le paramètre **Utiliser le mappage des composants hérités**.
   6. Sélectionnez **Ajouter** pour créer le paramètre prédéfini.

      ![&#x200B; Boîte de dialogue Nouveau paramètre prédéfini de sortie &#x200B;](/help/product-guide/knowledge-base/kb-articles/assets/publishing/new-output-preset.png){width="350" align="left"}


2. **Configurer le paramètre prédéfini de site AEM :** il existe deux options pour configurer le site prêt à l’emploi :

   **Option 1 : utiliser la liste déroulante Site**

   1. Sélectionnez **Site** comme **Documents AEMG**.
   2. Vérifiez que les paramètres **Chemin de publication** et **Modèle de page Rubrique** sont automatiquement définis sur :
      - Chemin de publication : `aemg-docs/en/docs/product1`
      - Modèle de page de rubrique : Page de rubrique.

      ![Utiliser le menu déroulant du site](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-dropdown.png){width="350" align="left"}

   **Option 2 : utiliser le chemin du site**

   1. Définissez manuellement le **chemin d’accès au site** comme `/content/aemg-docs/en/docs/product1`.
   2. Vérifiez que le **modèle de page Rubrique** est automatiquement défini sur Page Rubrique.

      ![Utiliser le chemin du site](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-path.png){width="350" align="left"}

3. **Enregistrer le paramètre prédéfini :** enregistrer les modifications apportées au paramètre prédéfini.

## Générer AEM Sites

1. **Générer le site :**
   1. Une fois le paramètre prédéfini configuré, vous pouvez générer le site AEM pour le plan DITA correspondant.
   2. Le site généré sera disponible au chemin d’accès suivant : `/content/aemg-docs/en/docs/product1`.
2. **Modifier le chemin de génération par défaut (facultatif) :** si vous souhaitez modifier le chemin par défaut pour la génération du site, procédez comme suit :

   1. Accédez à **AEM Sites**.
   2. Créez une page produit sous la structure de site prête à l’emploi.
   3. Accédez à **Documents AEMG** > **Français** > **Documents**.

      ![Création d’une page dans la structure de site AEM &#x200B;](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-new-page.png){width="350" align="left"}

   4. Sélectionnez la mosaïque **Page d’accueil** puis sélectionnez **Suivant**.

      ![Sélectionnez la mosaïque de la page d’accueil](/help/product-guide/knowledge-base/kb-articles/assets/publishing/home-page-tile.png){width="350" align="left"}

   5. Saisissez les **Titre** et **Nom** de la page.
   6. Sélectionnez **Créer**.
