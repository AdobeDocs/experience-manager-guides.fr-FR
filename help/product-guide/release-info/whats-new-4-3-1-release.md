---
title: Notes de mise à jour | Nouveautés de la version 4.3.1 des guides Adobe Experience Manager
description: Découvrez les fonctionnalités nouvelles et améliorées des versions 4.3.1 des Guides Adobe Experience Manager
exl-id: 14db7453-ccc1-4709-903f-677f55c263b2
feature: What's New
role: Leader
source-git-commit: 5a444e88b0adba7fa3d498437df39b729b10b5eb
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 0%

---

# Nouveautés de la version 4.3.1 des guides Adobe Experience Manager (octobre 2023)

Cet article couvre les nouvelles fonctionnalités et les fonctionnalités améliorées de la version 4.3.1 des Guides Adobe Experience Manager (ultérieurement appelées *Guides du Experience Manager*).

Pour plus d’informations sur les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans cette version, voir [Notes de mise à jour](./release-notes-4-3-1.md).

## Connexion à une source de données et insertion des rubriques

Experience Manager Guides fournit des connecteurs prêts à l’emploi qui vous aident à vous connecter à vos sources de données, ce qui fait de Experience Manager Guides un véritable centre de contenu. Cela vous permet de gagner du temps et de vous consacrer à l’ajout ou à la réplication manuels de données.

Outre les connecteurs prêts à l’emploi tels que JIRA et SQL (MySQL, PostgreSQL, SQL Server, SQLite), votre administrateur peut également configurer des connecteurs pour les bases de données MariaDB, H2DB, AdobeCommerce et Elasticsearch. Ils peuvent également ajouter d’autres connecteurs en étendant les interfaces par défaut.

Vous pouvez afficher les connecteurs configurés sous le **Sources de données** dans l’éditeur Web.

<img src="assets/data-sources.png" alt="Liste des sources de données dans le panneau" width="300">

*Afficher les sources de données connectées.*

Vous pouvez désormais créer une rubrique à partir d’une source de données connectée. Une rubrique peut contenir des données dans divers formats, tels que des tableaux, des listes et des paragraphes. Il vous permet également de créer un mappage DITA pour toutes les rubriques. Vous pouvez associer des métadonnées à la rubrique lors de l’extraction d’une source de données.

Pour plus d’informations, voir [Utiliser les données de votre source de données](../user-guide/web-editor-content-snippet.md).

## Configurer un connecteur de source de données à partir de l’interface utilisateur

Les guides du Experience Manager fournissent désormais une **Sources de données** qui vous aide à configurer des connecteurs prêts à l’emploi pour les sources de données. Vous pouvez facilement créer les connecteurs pour JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce et les bases de données Elasticsearch.

Vous pouvez également facilement modifier, reconnecter, dupliquer ou supprimer un connecteur de source de données. En savoir plus sur la manière de procéder [configurer facilement un connecteur de source de données à partir de l’interface utilisateur](../install-guide/conf-data-source-connector-tools.md).

![connecteurs de source de données répertoriés dans le panneau des sources de données](assets/data-sources-create-window.png){width="550" align="left"}

*Créez et affichez les connecteurs de source de données à partir du panneau des sources de données.*

## Afficher les journaux pour le générateur de rubrique

Vous pouvez désormais également afficher le fichier journal de génération du contenu. Ce fichier journal permet de vérifier les avertissements, les erreurs et les exceptions.  En savoir plus sur la manière dont la variable [options d’un générateur de rubrique](../user-guide/web-editor-content-snippet.md#options-for-a-topic-generator) vous aide à générer et gérer facilement les générateurs de rubriques.

## Prise en charge des outils Velocity dans les modèles de source de données

Vous pouvez désormais utiliser les outils Velocity dans les modèles de guides du Experience Manager. Ces outils vous aident à appliquer diverses fonctions aux données que vous récupérez à partir des sources de données. Vous pouvez utiliser les modèles lors de la création d’un fragment de contenu ou d’une rubrique. Cette fonctionnalité vous permet de gagner du temps et vous permet d’appliquer manuellement la même fonction à chaque jeu de données.  Elle garantit également des résultats précis.
Par exemple, vous pouvez utiliser $mathTool pour exécuter des fonctions mathématiques.
En savoir plus sur la manière de procéder [utiliser les outils Velocity dans les modèles de source de données ;](../user-guide/web-editor-content-snippet.md#use-velocity-tools).


## Améliorations apportées aux PDF natifs

Les améliorations suivantes ont été apportées au PDF natif dans la version d’octobre 2023 :

### Réinitialisation du numéro de page de la première page d’une mise en page

Dans la sortie native du PDF, vous pouvez redémarrer les numéros de page et spécifier le numéro à partir duquel la numérotation commence. Vous pouvez désormais également commencer la numérotation uniquement pour la première occurrence d’une section.
En savoir plus sur la manière de procéder [Utilisation des propriétés de page d’une mise en page](../native-pdf/design-page-layout.md#page-props-page-layout).


### Affichage des chapitres sans numéros automatiques dans la table des matières

Les guides du Experience Manager affichent les numéros de chapitre avec les noms de chapitre dans la table des matières (table des matières). Vous pouvez désormais choisir de publier uniquement les noms des chapitres sans les numéros de chapitre. Pour en savoir plus sur la configuration de la variable [paramètres de PDF avancés d’un modèle](../native-pdf/components-pdf-template.md#advanced-pdf-settings).

## Téléchargement d’une carte à partir de l’éditeur Web

Désormais, vous pouvez non seulement modifier une carte dans la vue map de l’éditeur web, mais aussi la télécharger. Vous pouvez choisir de télécharger la carte à l’aide d’une ligne de base spécifique. Vous avez également la possibilité d’aplatir la hiérarchie et d’enregistrer tous les fichiers et dossiers dans un seul dossier.

Pour plus d’informations, reportez-vous au **Vue Carte** description des fonctionnalités dans la section [Panneau gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .

![menu d’options d’un fichier dans la vue du référentiel](assets/options-menu-repo-view-file-level-2310.png){width="550" align="left"}

*Sélectionnez un fichier en mode Référentiel et choisissez l’option permettant d’effectuer une action sur le fichier.*


## Prise en charge de plusieurs définitions de sujet dans une seule définition d’énumération

Vous pouvez maintenant définir une ou plusieurs définitions de sujet dans un mappage et les définitions d’énumération dans un autre mappage, puis ajouter la référence de mappage. Les références de l’énumération objet sont résolues dans le même mappage ou le mappage référencé.

Vous pouvez désormais également définir des conditions et les appliquer à certains éléments spécifiques d’une rubrique.  Les conditions ne sont visibles que pour ces éléments spécifiques et non pour tous les autres éléments.

Pour plus d’informations sur la gestion des définitions hiérarchiques des définitions d’objet et des énumérations, consultez la description de la fonction Modèle d’objet dans la section [Panneau gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .




## Amélioration de l’expérience d’aperçu à partir du menu contextuel

Utilisez le menu contextuel pour prévisualiser rapidement le fichier (fichier .dita, .xml, audio, vidéo ou image) sans l’ouvrir. Vous pouvez désormais redimensionner le volet d’aperçu. Si le contenu contient un lien de référence, vous pouvez le sélectionner pour l’ouvrir dans un nouvel onglet.

![Volet Aperçu ](assets/quick-preview_cs.png){width="800" align="left"}

*Prévisualisez le fichier dans le volet.*

Pour plus d’informations sur le menu contextuel, voir **Options d’un fichier** description des fonctionnalités dans la section [Panneau gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .

## Modification d’un fichier dans le module externe du connecteur Oxygen

Les guides du Experience Manager vous permettent désormais de sélectionner un fichier dans l’éditeur web, puis de choisir de modifier le fichier dans le module externe du connecteur Oxygen. Cette option n’est pas activée dans le cadre de la prise en charge prête à l’emploi.

Pour plus d’informations, reportez-vous au **Options d’un fichier** description des fonctionnalités dans la section [Panneau gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .

## Utilisez des variables pour la date et l’heure actuelles dans les options Chemin de destination, Nom du site ou Nom de fichier .

Lors de la génération de sorties dans AEM site ou les PDF, vous pouvez utiliser des variables pour définir la variable **Chemin de destination**, **Nom du site**, ou **Nom du fichier** options. Vous pouvez désormais également utiliser la variable `${system_date}`et `${system_time}` . Ces variables vous aident à ajouter la date et l’heure actuelles à ces options.

Découvrez comment [utiliser des variables pour définir le chemin de destination, le nom du site ou le nom de fichier ;](../user-guide/generate-output-use-variables.md).


## Raccourcis clavier pour déplacer le curseur dans l’éditeur web

Les guides du Experience Manager vous permettent désormais d’utiliser des raccourcis clavier pour déplacer le curseur dans l’éditeur web. Vous pouvez utiliser les raccourcis clavier pour déplacer rapidement un mot vers la gauche ou la droite. Vous pouvez également passer au début ou à la fin de la ligne à l’aide des raccourcis clavier.

En savoir plus sur les [raccourcis clavier dans l’éditeur web](../user-guide/web-editor-keyboard-shortcuts.md).
