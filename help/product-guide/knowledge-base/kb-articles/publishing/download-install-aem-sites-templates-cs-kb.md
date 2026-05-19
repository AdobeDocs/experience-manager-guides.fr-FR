---
title: Télécharger et installer des modèles AEM Sites pour les services cloud
description: Découvrez comment télécharger et installer des modèles AEM Sites pour les services cloud
feature: Installation
role: Admin
level: Experienced
exl-id: 67f7ff26-fbc7-426c-aa7d-9bf4debf05d8
TQID: https://experienceleague.adobe.com/fj9JDKmklfdc-3UHShHD3PqynCcnnH5cK8lQNqCLD2c
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 705
ht-degree: 1%

---

# Télécharger et installer des modèles AEM Sites (Cloud Services)

Ce guide fournit des instructions détaillées pour installer et configurer le dernier modèle AEM Guides pour générer des pages AEM Sites dans un environnement cloud. Pour installer les packages requis, créer et configurer des paramètres prédéfinis et générer AEM Sites, procédez comme suit.

## Conditions préalables

Avant de poursuivre la configuration, assurez-vous que les conditions préalables suivantes sont remplies :

- **Adobe Experience Manager (AEM) Cloud** : instance en cours d’exécution de **AEM as a Cloud Service** avec **AEM Guides 2502 ou versions ultérieures**.

- **Autorisations requises** : vous devez disposer des autorisations suivantes :

   - Accès à **&#x200B;**&#x200B;pour déployer des packages.
   - Accès au **référentiel Git** associé à votre environnement.
   - Les autorisations de création et de modification des paramètres prédéfinis dans AEM Guides.

- **Télécharger les packages** : téléchargez les packages suivants à partir du portail de distribution logicielle :

   - Package de composants : guides-components.all-1.x.0.zip
   - Modèle Sites : aemg-docs-1.x.0.zip

## Installation du package via le déploiement dans le cloud

Installez le **Package de composants (guides-components.all-1.x.x.zip)** puis effectuez les étapes suivantes

1. **Clonage du référentiel Git :**
   1. Accédez à **Référentiels** dans le panneau de gauche de Cloud Manager.
   2. Sélectionnez **Accéder aux informations sur le référentiel** et copiez la commande de clone Git.

      ![Sélectionnez Accéder aux informations sur le référentiel](/help/product-guide/knowledge-base/kb-articles/assets/publishing/access-repo.png){width="350"}

   3. Clonez le référentiel sur votre système local à l’aide du nom d’utilisateur et du mot de passe fournis (générez un mot de passe si nécessaire).
2. **Ajouter un package au lot Maven :**
   1. Dans votre référentiel cloné localement, créez un lot Maven ou ajoutez-le à un lot existant.
   2. Assurez-vous que la structure `/jcr_root/apps/fmdita/` installer existe dans le projet Maven.

      ![Structure dans un projet Maven](/help/product-guide/knowledge-base/kb-articles/assets/publishing/maven-structure.png){width="650"}


   3. Placez le fichier guides-components.all-1.x.x.zip téléchargé dans le dossier d’installation.

3. **Mettre à jour filters.xml:**

   1. Ouvrez le fichier filters.xml situé dans le dossier META-INF du répertoire de contenu parent.
   2. Ajoutez le filtre suivant : racine du filtre=`/apps/fmdita` mode=`merge`/


      ![Ajouter un filtre](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-filter-xml.png){width="650"}


4. **Configurer pom.xml :** mettez à jour le fichier pom.xml en fonction des exigences de votre environnement.
5. **Envoi des modifications et exécution du pipeline :**
   1. Envoyez les modifications au référentiel Git principal.
   2. Accédez à **Pipelines** dans Cloud Manager et exécutez le pipeline pour l’environnement souhaité.
6. **Vérifier l’installation :** une fois le déploiement terminé, le package de composants sera installé dans l’environnement AEM Cloud.

## Créer un site à l’aide de modèles installés

1. **Modèle d’importation de sites :**
   1. Accédez à la page AEM Sites (servername/sites.html/content).
   2. Sélectionnez **Créer** > **Site** à partir d’un modèle.
   3. Importez le modèle de sites aemg-docs-1.x.x.zip à l’aide de l’option **Importer**.
2. **Sélectionner le modèle :** sélectionnez **AEMG Docs 1.x.x** puis sélectionnez **Suivant**.
3. **Saisir les détails du site :** saisissez le **titre du site** et le **nom du site**.

   ![Créer un site](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-site.png){width="350"}

4. Sélectionnez **Créer**.

## Créer un paramètre prédéfini de site AEM

1. **Créer un nouveau paramètre prédéfini :**
   1. Ouvrez un plan DITA dans AEM Guides et accédez au panneau **Sortie**.
   2. Sélectionnez **Créer un paramètre prédéfini**.
   3. Sélectionnez le type comme **&#x200B;**.
   4. Saisissez le nom du paramètre prédéfini.
   5. Décochez le paramètre **Utiliser le mappage des composants hérités**.

      ![Créer un nouveau paramètre prédéfini de site AEM](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-new-output-preset.png){width="350"}

   6. Sélectionnez **Ajouter** pour créer le paramètre prédéfini.
2. **Configurer le paramètre prédéfini de site AEM :** il existe deux options pour configurer le site prêt à l’emploi :

   **Option 1 : utiliser la liste déroulante Site**

   1. Sélectionnez **Site** comme celui créé ci-dessus (par exemple, Site de documents AEMG).
   2. Vérifiez que les modèles **Chemin de publication** et **Page de rubrique** sont automatiquement définis sur :
      - Chemin de publication : `/content/AEMG-Docs-Site/en/docs/product`
      - Modèle de page de rubrique : Page de rubrique

      ![Utilisez la liste déroulante Site pour configurer le site AEM](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-dropdown-cs.png){width="350"}

   **Option 2 : utiliser le chemin du site**

   1. Définissez manuellement le **chemin d’accès au site** comme `/content/AEMG-Docs-Site/en/docs/product`.
   2. Vérifiez que le modèle **Page de rubrique** est automatiquement défini sur Page de rubrique.

      ![Utilisez le chemin du site pour configurer le site AEM](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-path-cs.png){width="650"}

3. **Enregistrer le paramètre prédéfini :** enregistrer les modifications apportées au paramètre prédéfini.

## Générer AEM Sites

1. **Générer le site :**
   1. Une fois le paramètre prédéfini configuré, générez le site AEM pour le plan DITA correspondant.
   2. Le site généré sera disponible au chemin d’accès suivant : `/content/AEMG-Docs-Site/en/docs/product`.
2. **Modifier le chemin de génération par défaut (facultatif) :** si vous souhaitez modifier le chemin par défaut pour la génération du site, procédez comme suit :
   1. Accédez à **&#x200B;**.
   2. Créez une page produit sous la structure de site prête à l’emploi.
   3. Accédez à **Documents AEMG** > **Français** > **Documents**.

      ![Création d’une page](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-page-cs.png){width="650"}

   4. Sélectionnez la mosaïque **Page d’accueil** puis sélectionnez **Suivant**.

      ![Sélectionnez la mosaïque Accueil](/help/product-guide/knowledge-base/kb-articles/assets/publishing/home-tile-cs.png){width="650"}

   5. Saisissez les **Titre** et **Nom** de la page.
   6. Sélectionnez **Créer**.

>[!NOTE]
>
> Assurez-vous que toutes les configurations sont testées dans un environnement hors production avant le déploiement en production. <br><br> Reportez-vous à la documentation officielle [Déploiement sur AEM as a Cloud Service](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/deploying/overview) pour plus d’informations.
