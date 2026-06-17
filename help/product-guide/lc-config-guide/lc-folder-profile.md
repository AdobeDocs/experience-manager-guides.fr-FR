---
title: Configuration des profils de dossier
description: Découvrez comment configurer des profils de dossier lors de l’utilisation du contenu de formation dans Experience Manager Guides.
feature: Authoring
role: Admin
level: Experienced
exl-id: dc26ae48-c953-492c-823a-5f65157b6902
TQID: https://experienceleague.adobe.com/jp7oUSIZlnTfGnx58E9rPn6Tk4zE2lp-oZSTdjblbZ0
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0eid: d90290ec-3e61-4ebd-8649-bcafe0836803id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0id: b89a36a9-95de-429b-adde-f901256d8f24id: f7774ebe-aec9-42b6-97e4-5002acdc712eid: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 9132140a0305eb0507598a7caf5f704861879a93
workflow-type: tm+mt
source-wordcount: 1960
ht-degree: 0%

---

# Configuration des profils de dossier

Un profil de dossiers est nécessaire pour séparer les configurations pour différents services ou produits de votre entreprise. Pour le contenu de formation et d’apprentissage, vous pouvez créer et configurer un profil au niveau du dossier pour gérer la création de modèles, de modèles de sortie, de paramètres prédéfinis de sortie et d’autres paramètres au niveau du dossier.

Découvrez les [bonnes pratiques pour configurer la structure de dossiers](best-practices-folder-structure.md).

Pour commencer à utiliser la configuration de profil de dossiers pour le contenu de formation, vous devez :

1. **Créez différents dossiers pour gérer les modèles de création et de sortie** : vous pouvez créer des dossiers pour les auteurs et les éditeurs travaillant dans différents services ou produits de votre entreprise. Ces dossiers peuvent être associés à des profils de dossier spécifiques, chacun configuré avec différents modèles de création et de sortie pour prendre en charge la création de cours d’apprentissage spécifiques au service et une administration décentralisée.

   Vous pouvez créer un dossier à partir du panneau Référentiel.

   ![](assets/create-new-folder.png){width="350"}
2. **Créer des dossiers de langue pour gérer la traduction** : si vous traduisez du contenu dans différentes langues, vous devez créer des dossiers correspondant à chaque langue. Chacun de ces dossiers de langue contient le contenu correspondant à cette langue.

3. **Création d’un dossier pour gérer Assets** : comme pour les dossiers, vous pouvez également créer différents dossiers Assets pour répondre aux besoins des différents services. Ainsi, vous vous assurez également que les auteurs et les éditeurs ont accès au CSS correct configuré dans leurs modèles, images et autres ressources.

   ![](assets/configure-assets-folder.png){width="350"}
4. [Créez un profil de dossier](../cs-install-guide/conf-folder-level.md#create-and-configure-a-folder-level-profile) pour mapper différents dossiers.
5. **Sélectionner le profil de dossier à configurer** : une fois le profil de dossier créé, vous devez sélectionner le profil de dossier sur la page [Préférences utilisateur](../user-guide/intro-home-page.md#user-preferences) pour vous assurer que les auteurs et les éditeurs ont accès aux modèles appropriés.

   ![](assets/folder-profile.png){width="650"}

6. **Configurer les paramètres de profil de dossier** : pour le contenu d’apprentissage et de formation, les paramètres suivants peuvent être configurés au niveau d’un dossier :
   - [Général](#general)
   - [Panneaux](#configure-panels)
   - [Modèles de contenu](#configure-content-templates)
   - [Paramètres prédéfinis de sortie](#configure-output-presets)
   - [éditeur ](#html-editor-settings)
   - [Publication de profils](#manage-publish-profiles)

Pour accéder à ces paramètres, basculez vers la vue Éditeur et sélectionnez **Paramètres** dans le menu **Options** comme illustré ci-dessous :

![](assets/access-editor-settings.png)

## Général

Dans l’onglet Général , vous pouvez configurer les paramètres suivants qui sont spécifiques à la fonctionnalité de contenu Formation et apprentissage du produit :

![](assets/lc-config-settings-general.png){width="350"}

- **Contenu d’apprentissage** : utilisez le bouton (bascule) **Activer le contenu d’apprentissage** pour activer ou désactiver la fonctionnalité au niveau du profil du dossier.
- **Éditeur HTML** : ce paramètre vous permet de configurer l’éditeur pour la création basée sur HTML. Les principales options de configuration de ce paramètre sont les suivantes :

   - **Masquer le style intégré** : activez cette option pour empêcher les auteurs d’appliquer un formatage en ligne au contenu du cours. Lorsqu’elles sont activées, toutes les options de style intégrées telles que Polices, Bordure, Disposition, Arrière-plan et Colonnes présentes dans le panneau de droite de l’éditeur restent masquées pour les auteurs. Cependant, les créateurs peuvent toujours utiliser les options de style globales basées sur les classes disponibles dans le panneau **Styles**. Cela permet de maintenir la cohérence avec les directives de style de votre organisation.
   - **Masquer la vue Source pour les auteurs** : activez cette option pour restreindre l’accès au code source HTML. Cela s’avère utile si vous souhaitez simplifier l’expérience de modification ou éviter des modifications accidentelles du code sous-jacent.

## Configuration des panneaux

Ce paramètre contrôle les panneaux qui s’affichent dans les panneaux de gauche et de droite de la **Éditeur** et de la **Console Carte** dans Experience Manager Guides. Vous pouvez activer/désactiver le bouton pour afficher ou masquer le panneau souhaité.

Pour le contenu de formation théorique et pratique, assurez-vous que seules les fonctionnalités suivantes sont activées pour l’éditeur et la console de mappage.

![](assets/panels-settings.png){width="350"}


### Éditeur

**Panneau de gauche**

- **Collections** : permet d’organiser et d’enregistrer les fichiers fréquemment utilisés ou d’accéder rapidement aux fichiers partagés.
- **Explorateur** : permet d’afficher toutes les cartes, rubriques, images et autres ressources stockées dans le référentiel de contenu, et d’y accéder.
- **Responsable de cours** : fournit un espace de travail dédié à la création et à la gestion des cours.
- **Map** : fournit une vue cartographique du fichier de mappage actuellement ouvert.
- **Plan** : affiche la hiérarchie structurelle de la rubrique ou de la carte actuellement ouverte, ce qui permet une navigation rapide et un accès au niveau de l’élément.
- **** : permet d’accéder à des fonctionnalités de gestion de projet fiables en plus des fonctionnalités de base du système de gestion de contenu par composant (CCMS) de Experience Manager Guides.
- **Contenu réutilisable** : permet de gérer et d’insérer des éléments ou des rubriques réutilisables pour garantir la cohérence et réduire la duplication du contenu.
- **Glossaire** : permet de créer et de gérer des termes de glossaire et de les inclure dans les rubriques afin de conserver une terminologie cohérente.
- **Fragments de code** : permet de créer et de réutiliser de petits fragments de contenu dans divers sujets de vos cours.
- **Conditions** : permet de configurer des attributs conditionnels au niveau global et du dossier.
- **Modèles** : permet de créer et de gérer des modèles de cours.
- **Citations** : permet d’ajouter et de gérer des citations dans le contenu à l’aide des styles de citations pris en charge.
- **Variables de langue** : permet de définir des variables de langue pour la sortie publiée.
- **Variables** : permet de créer et de gérer des variables à utiliser dans votre contenu de formation.
- **Modèles de sortie** : permet de créer et de gérer des modèles de sortie pour générer une sortie dans différents formats.
- **Rechercher et remplacer** : propose des options permettant de rechercher et de remplacer du texte dans les fichiers d’un mappage ou d’un dossier du référentiel. 
- **Sources de données** : permet de connecter des sources de données externes et de réutiliser des données dans votre contenu.
- **Révision** : permet de créer et de gérer des workflows de révision dans Experience Manager Guides.
- **Rapports système** : permet de créer et de gérer des rapports.

**Panneau droit**

- **Propriétés du contenu** : contient des informations sur le type et les attributs de l’élément actuellement sélectionné dans l’éditeur.
- **Propriétés du fichier** : permet d’afficher et de gérer les propriétés du fichier sélectionné.
- **Styles** : affichez les options de style globales basées sur les classes à utiliser dans votre contenu d’apprentissage.
- **Filtres** : permet de filtrer le contenu en fonction des conditions appliquées dans le mode Prévisualisation d’une rubrique.

### Console Carte

**Panneau de gauche**

- **Paramètres prédéfinis** : permet de configurer des paramètres prédéfinis de sortie pour publier le cours de formation.
- **Traduction** : propose des options pour traduire votre contenu dans plusieurs langues.
- **Rapports** : permet de générer et de gérer des rapports afin d’obtenir une insight utile dans l’intégrité globale du contenu de votre cours.
- **Paramètres prédéfinis de condition** : fournit des options pour configurer des paramètres prédéfinis de sortie basés sur des conditions pour différentes audiences, différents services, etc.

**Panneau droit**

- **Filtres** : permet d’utiliser des filtres lors de l’utilisation de rapports et de la traduction.

## Configurer des modèles de contenu

>[!NOTE]
>
> Ce paramètre est disponible uniquement lorsque la fonction de contenu de formation est activée dans les paramètres **** > **Général**.

Ce paramètre vous permet de gérer les modèles de création et de publication présents dans le panneau [Gauche) de l’éditeur](../user-guide/web-editor-left-panel.md). Vous pouvez ajouter, supprimer ou réorganiser des modèles de création et de sortie, qui seront ensuite accessibles aux auteurs et aux éditeurs.

![](assets/templates-settings.png){width="350"}

Les modèles de création sont disponibles dans quatre catégories : cours d’apprentissage, contenu d’apprentissage, quiz et banque de questions. Si des modèles prédéfinis sont configurés dans votre instance, ils s’affichent par défaut.

![](assets/templates-list.png){width="350"}

### Ajouter des modèles

Pour ajouter un nouveau modèle, procédez comme suit :

1. Accédez à la catégorie de modèles dans laquelle vous souhaitez ajouter un modèle et sélectionnez **Ajouter**.
2. Dans la boîte de dialogue Sélectionner le chemin d’accès, sélectionnez le modèle souhaité.
3. Choisissez **Sélectionner**.

   ![](assets/add-templates.png){width="350"}

Le modèle est ajouté dans la catégorie correspondante dans le panneau Paramètres .

De même, vous pouvez ajouter les autres modèles Création et Sortie . Une fois ajoutés, ces modèles sont mis à la disposition des auteurs et des éditeurs dans leurs boîtes de dialogue de cours respectives. Par exemple, le modèle de cours d’apprentissage ajouté par l’administrateur sera disponible pour les auteurs lorsqu’ils créeront un nouveau cours.

![](assets/templates-added-course.png){width="350"}

### Utiliser de nouveaux modèles de création et de sortie

Pour utiliser un modèle différent de ceux affichés dans la boîte de dialogue **Sélectionner le chemin d’accès**, créez un modèle de création ou de sortie personnalisé.

**Création de modèles**

Pour utiliser un autre mappage ou modèle de rubrique, créez un modèle de création à partir du panneau Modèles dans l’éditeur. Utilisez des modèles de carte pour créer des cours d’apprentissage et des modèles de sujet pour le contenu d’apprentissage, le quiz ou le résumé d’apprentissage.

Pour plus d’informations, consultez la section [Créer des modèles personnalisés à partir de l’éditeur](../user-guide/create-maps-customized-templates.md).

![](assets/authoring-templates-editor.png){width="350"}

**Créer des modèles de sortie**

Pour créer un modèle de sortie pour le contenu d’apprentissage et de formation, procédez comme suit :

1. Dans le panneau de gauche de l’éditeur, sélectionnez **Plus** > **Modèles de sortie**.

   Le panneau Modèles de sortie s’affiche.

   ![](assets/output-templates-editor.png){width="350" height=""}
2. Dans le panneau Modèles de sortie , sélectionnez (+) pour créer un modèle de sortie.

   ![](assets/create-new-output-template.png){width="350"}
3. Sélectionnez un modèle de sortie dans le menu déroulant.


   ![](assets/output-template-types.png){width="650"}
4. En fonction du type de modèle de sortie sélectionné, une boîte de dialogue s’affiche dans laquelle vous pouvez créer un modèle basé sur les modèles disponibles.

   ![](assets/new-scorm-template-dialog.png){width="350"}

5. Sélectionnez **Créer**.

   Un nouveau modèle de sortie est créé.

6. Pour accéder au modèle de sortie pour les éditeurs et l’ajouter, accédez à **Paramètres** > **Modèles** > **Modèles de sortie** et sélectionnez **Ajouter**.

   ![](assets/add-output-template-settings-panel.png){width="350"}

   Le modèle de sortie s’affiche dans la boîte de dialogue Sélectionner le chemin d’accès .
7. Sélectionnez le modèle et choisissez **Confirmer**.

   ![](assets/select-scorm-template-dialog.png){width="350"}

   Le modèle de sortie sélectionné est maintenant ajouté au panneau Paramètres.

   ![](assets/scorm-template-added.png){width="350"}

### Configuration des mises en page pour les modèles de sortie SCORM

Les modèles de sortie SCORM vous permettent d’affecter différentes mises en page à différents types de sujets au sein d’un cours. Cela vous permet de personnaliser la présentation des leçons, des quiz, des pages de présentation et d’autres types de contenu dans le package SCORM généré.

Par exemple, une page de leçon peut utiliser une mise en page qui comprend un en-tête, une zone de contenu et un pied de page, tandis qu’une page de quiz peut utiliser une mise en page simplifiée sans pied de page. Vous pouvez également créer des mises en page dédiées pour les pages d’aperçu ou tout autre type de rubrique et les mapper en conséquence.

Les affectations de disposition sont configurées au niveau du **modèle de sortie**. Tout paramètre prédéfini SCORM qui utilise le modèle de sortie configuré appliquera les mappages de disposition sélectionnés lors de la génération des cours.
Pour configurer la mise en page des modèles, procédez comme suit :

1. Accédez à **Modèles de sortie** et ouvrez le **modèle de sortie SCORM** requis.

2. Sélectionnez l’onglet **Paramètres**.

3. Dans la fenêtre **Mises en page**, recherchez les types de rubriques disponibles.

   ![](assets/page-layout-scorm.png){width="650"}

4. Pour chaque type de sujet, sélectionnez la mise en page à utiliser lors de la génération du cours.

   **Exemple :**
   - **Mise En Page Par Défaut** : Leçon
   - **Quiz** : Quiz
   - **Aperçu** : Leçon

5. Pour utiliser une nouvelle mise en page, créez la mise en page requise dans le modèle de sortie à l’aide de l’option **Nouvelle mise en page** du menu contextuel du panneau **Modèles de sortie**.

   ![](assets/new-page-layout-scorm.png){width="650"}

6. Revenez à l’onglet **Paramètres** et affectez la nouvelle disposition au type de rubrique approprié.

7. Enregistrez la mise en page du modèle de sortie à l’aide de l’icône Enregistrer située dans le coin droit de la barre d’onglets .


Lorsqu’un cours est généré à l’aide d’un paramètre prédéfini SCORM qui utilise le modèle de sortie configuré, chaque sujet est rendu selon la mise en page affectée à son type de sujet. Cela permet à différents types de contenu d’un même cours d’avoir des structures de page et une présentation visuelle personnalisées.

### Supprimer ou réorganiser des modèles

Une fois ajoutés, vous pouvez supprimer ou réorganiser les modèles du panneau Paramètres.

Pour supprimer un modèle, sélectionnez l’icône **Supprimer** située en regard de celui-ci.

![](assets/remove-teamplates.png){width="350"}

Vous pouvez également définir l’ordre d’affichage des modèles présents dans une catégorie. Pour modifier l’ordre d’affichage des modèles, sélectionnez les barres en pointillés et faites glisser un modèle à l’emplacement souhaité.

![](assets/reorder-templates.png){width="350"}


## Configuration des paramètres prédéfinis de sortie

>[!NOTE]
>
> Ce paramètre est disponible uniquement lorsque la fonction de contenu de formation est activée dans les paramètres **** > **Général**.

L’onglet Paramètres prédéfinis de sortie vous permet de définir les formats de sortie disponibles pour publier un cours. Il contient deux sections : **Types de paramètres prédéfinis de sortie autorisés** et **Paramètres prédéfinis de sortie courants**.

![](assets/configure-course-output-presets.png){width="350"}

- **Types de paramètres prédéfinis de sortie autorisés** : cette section répertorie tous les paramètres prédéfinis de sortie pris en charge dans l’instance Experience Manager Guides. Pour la publication de cours, seuls les formats **SCORM** et **PDF** sont applicables. Vous pouvez sélectionner une ou les deux options. Les paramètres prédéfinis sélectionnés seront disponibles pour les éditeurs lors de la génération de la sortie du cours.

  ![](assets/allowed-output-presets.png){width="350"}

- **Paramètres prédéfinis de sortie courants** : cette section affiche les paramètres prédéfinis de sortie généralement créés et ajoutés par les éditeurs à un profil de dossier spécifique. Vous pouvez également supprimer tout paramètre prédéfini qui n’est plus nécessaire.

  ![](assets/common-output-presets.png){width="350"}

## Gestion des profils de publication

Cette section vous permet d’afficher, de créer et de gérer des profils de publication utilisés pour publier des cours dans SCORM Cloud ou Adobe Learning Manager (ALM). Chaque profil définit les paramètres de connexion et les détails de configuration requis pour publier un cours de formation sur un serveur de publication sélectionné.

Vous pouvez créer plusieurs profils pour publier du contenu sur différents comptes SCORM Cloud ou instances ALM, ce qui vous offre davantage de flexibilité et de contrôle sur votre workflow de publication.

Pour configurer un profil de publication, sélectionnez le serveur de publication de votre choix (SCORM Cloud ou Adobe Learning Manager) et fournissez les détails de connexion requis. Pour SCORM Cloud, saisissez les informations sur le serveur, ainsi que l’ID client et le secret client de l’application SCORM Cloud associée. Pour Adobe Learning Manager, fournissez les détails de serveur et d’authentification correspondants requis pour votre environnement ALM.

![](assets/configure-publish-profiles.png){width="350"}
