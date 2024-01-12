---
title: Notes de mise à jour | Nouveautés des guides Adobe Experience Manager, version d’octobre 2023
description: Découvrez les nouvelles fonctionnalités et les fonctionnalités améliorées de la version d’octobre 2023 de Adobe Experience Manager Guides as a Cloud Service.
exl-id: 41bfed0d-5901-4ada-b6d7-a5be93b25ba8
feature: What's New
role: Leader
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Nouveautés de la version d’octobre 2023 des Guides Adobe Experience Manager as a Cloud Service

Cet article couvre les nouvelles fonctionnalités et les fonctionnalités améliorées de la version d’octobre 2023 des Guides Adobe Experience Manager (ultérieurement appelée *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans cette version, voir [Notes de mise à jour](release-notes-2023.10.0.md).


## Configurer un connecteur de source de données à partir de l’interface utilisateur

Les guides du Experience Manager fournissent désormais une **Sources de données** qui vous aide à configurer des connecteurs prêts à l’emploi pour les sources de données. Vous pouvez facilement créer les connecteurs pour JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce et les bases de données Elasticsearch.

Vous pouvez également facilement modifier, reconnecter, dupliquer ou supprimer un connecteur de source de données. Découvrez comment [configurer facilement un connecteur de source de données à partir de l’interface utilisateur](../cs-install-guide/conf-data-source-connector-tools.md).

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

## Modification d’un fichier dans le module externe du connecteur Oxygen

Les guides du Experience Manager vous permettent désormais de sélectionner un fichier dans l’éditeur web, puis de choisir de modifier le fichier dans le module externe du connecteur Oxygen. Cette option n’est pas activée dans le cadre de la prise en charge prête à l’emploi.

Pour plus d’informations, reportez-vous au **Options d’un fichier** description des fonctionnalités dans la section [Panneau gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .
