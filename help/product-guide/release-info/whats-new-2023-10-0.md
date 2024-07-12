---
title: Notes de mise à jour | Nouveautés d’Adobe Experience Manager Guides, version d’octobre 2023
description: Découvrez les nouvelles fonctionnalités améliorées de la version d’octobre 2023 d’Adobe Experience Manager Guides as a Cloud Service.
exl-id: 41bfed0d-5901-4ada-b6d7-a5be93b25ba8
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Nouveautés de la version d’octobre 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cet article couvre les nouvelles fonctionnalités améliorées de la version d’octobre 2023 d’Adobe Experience Manager Guides (appelée ultérieurement *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans cette version, consultez les [Notes de mise à jour](release-notes-2023-10-0.md).


## Configurer un connecteur de source de données à partir de l’interface utilisateur

Experience Manager Guides fournit désormais un outil **Sources de données** qui vous aide à configurer des connecteurs prêts à l’emploi pour les sources de données. Vous pouvez facilement créer les connecteurs pour JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce et les bases de données Elasticsearch.

Vous pouvez également facilement modifier, reconnecter, dupliquer ou supprimer un connecteur de source de données. Découvrez comment [configurer facilement un connecteur de source de données à partir de l’interface utilisateur](../cs-install-guide/conf-data-source-connector-tools.md).

![Connecteurs de source de données répertoriés dans le panneau des sources de données](assets/data-sources-create-window.png){width="550" align="left"}

*Créez et affichez les connecteurs de source de données à partir du panneau des sources de données.*

## Afficher les journaux pour le générateur de rubrique

Vous pouvez désormais également afficher le fichier journal de génération du contenu. Ce fichier journal permet de vérifier les avertissements, les erreurs et les exceptions.  Découvrez comment les [options d’un générateur de rubriques](../user-guide/web-editor-content-snippet.md#options-for-a-topic-generator) vous aident à générer et gérer facilement les générateurs de rubriques.

## Prise en charge des outils Velocity dans les modèles de source de données

Vous pouvez désormais utiliser les outils Velocity dans les modèles Experience Manager Guides. Ces outils vous aident à appliquer diverses fonctions aux données que vous récupérez à partir des sources de données. Vous pouvez utiliser les modèles lors de la création d’un fragment de contenu ou d’une rubrique. Cette fonctionnalité vous permet de gagner du temps et vous permet d’appliquer manuellement la même fonction à chaque jeu de données.  Elle garantit également des résultats précis.
Par exemple, vous pouvez utiliser $mathTool pour exécuter des fonctions mathématiques.
Découvrez comment [utiliser les outils Velocity dans les modèles de source de données](../user-guide/web-editor-content-snippet.md#use-velocity-tools).


## Améliorations apportées aux PDF natifs

Les améliorations suivantes ont été apportées au PDF natif dans la version d’octobre 2023 :

### Réinitialisation du numéro de page de la première page d’une mise en page

Dans la sortie native du PDF, vous pouvez redémarrer les numéros de page et spécifier le numéro à partir duquel la numérotation commence. Vous pouvez désormais également commencer la numérotation uniquement pour la première occurrence d’une section.
Découvrez comment [utiliser les propriétés de page d’une mise en page](../native-pdf/design-page-layout.md#page-props-page-layout).


### Affichage des chapitres sans numéros automatiques dans la table des matières

Experience Manager Guides affiche les numéros de chapitre ainsi que les noms de chapitre dans la table des matières (table des matières). Vous pouvez désormais choisir de publier uniquement les noms des chapitres sans les numéros de chapitre. Pour plus d’informations sur la configuration des [paramètres avancés du PDF d’un modèle](../native-pdf/components-pdf-template.md#advanced-pdf-settings), consultez la page.

## Téléchargement d’une carte à partir de l’éditeur Web

Désormais, vous pouvez non seulement modifier une carte dans la vue map de l’éditeur web, mais aussi la télécharger. Vous pouvez choisir de télécharger la carte à l’aide d’une ligne de base spécifique. Vous avez également la possibilité d’aplatir la hiérarchie et d’enregistrer tous les fichiers et dossiers dans un seul dossier.

Pour plus d’informations, reportez-vous à la description de la fonctionnalité **Vue Carte** dans la section [Panneau de gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .

Menu ![options d’un fichier dans la vue de référentiel](assets/options-menu-repo-view-file-level-2310.png){width="550" align="left"}

*Sélectionnez un fichier dans la vue du référentiel et choisissez l’option permettant d’effectuer une action sur le fichier.*

## Modification d’un fichier dans le module externe du connecteur Oxygen

Experience Manager Guides vous permet désormais de sélectionner un fichier dans l’éditeur web, puis de choisir de modifier le fichier dans le module externe du connecteur Oxygen. Cette option n’est pas activée dans le cadre de la prise en charge prête à l’emploi.

Pour plus d’informations, reportez-vous à la description de la fonctionnalité **Options pour un fichier** dans la section [Panneau de gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .
