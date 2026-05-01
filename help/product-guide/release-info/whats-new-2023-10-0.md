---
title: Notes de mise à jour | Nouveautés d’Adobe Experience Manager Guides, version d’octobre 2023
description: Découvrez les nouvelles fonctionnalités et les fonctionnalités améliorées de la version d’octobre 2023 d’Adobe Experience Manager Guides as a Cloud Service.
exl-id: 41bfed0d-5901-4ada-b6d7-a5be93b25ba8
feature: What's New
role: Leader
source-git-commit: 12ba7129255257970ddd7a0989149be664ce9803
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 0%

---

# Nouveautés de la version d’octobre 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cet article couvre les nouvelles fonctionnalités et les fonctionnalités améliorées de la version d’octobre 2023 d’Adobe Experience Manager Guides (plus tard appelée *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans cette version, voir [Notes de mise à jour](release-notes-2023-10-0.md).


## Configuration d’un connecteur de source de données à partir de l’interface utilisateur

Experience Manager Guides propose désormais un outil **Sources de données** qui vous permet de configurer des connecteurs prêts à l’emploi pour les sources de données. Vous pouvez facilement créer des connecteurs pour les bases de données JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), Adobe Commerce et Elasticsearch.

Vous pouvez également modifier, reconnecter, dupliquer ou supprimer facilement un connecteur de source de données. Découvrez comment [configurer facilement un connecteur de source de données à partir de l’interface utilisateur](../cs-install-guide/conf-data-source-connector-tools.md).

![connecteurs de sources de données répertoriés dans le panneau sources de données](assets/data-sources-create-window.png){width="550"}

*Créez et affichez les connecteurs de sources de données à partir du panneau des sources de données.*

## Afficher les journaux pour le générateur de rubriques

Vous pouvez désormais également afficher le fichier journal de génération de contenu. Ce fichier journal vous aide à vérifier les avertissements, les erreurs et les exceptions.  En savoir plus sur la manière dont les [options d’un générateur de rubriques](../user-guide/web-editor-content-snippet.md#options-for-a-topic-generator) vous aident à générer et gérer facilement les générateurs de rubriques.

## Prise en charge des outils Velocity dans les modèles de source de données

Vous pouvez désormais utiliser les outils Velocity dans les modèles Experience Manager Guides. Ces outils vous aident à appliquer diverses fonctions aux données que vous récupérez à partir des sources de données. Vous pouvez utiliser les modèles lors de la création d’un fragment de contenu ou d’une rubrique. Cette fonctionnalité vous permet de gagner du temps et d’économiser des efforts pour appliquer manuellement la même fonction à chaque jeu de données.  Il garantit également des résultats précis.
Par exemple, vous pouvez utiliser $mathTool pour exécuter des fonctions mathématiques.
Découvrez comment [utiliser les outils Velocity dans les modèles de source de données](../user-guide/web-editor-content-snippet.md#use-velocity-tools).


## Améliorations du PDF natif

Les améliorations du PDF natif suivantes ont été apportées à la version d’octobre 2023 :

### Réinitialiser le numéro de page de la première page d&#39;une mise en page

Dans la sortie PDF native, vous pouvez redémarrer les numéros de page et spécifier le numéro à partir duquel la numérotation commence. Vous pouvez également commencer la numérotation uniquement pour la première occurrence d’une section.
En savoir plus sur l’utilisation [ des propriétés de page d’une mise en page ](../native-pdf/design-page-layout.md#page-props-page-layout).


### Afficher les chapitres sans numéros automatiques dans la table des matières

Experience Manager Guides affiche les numéros de chapitres ainsi que les noms de chapitres dans la table des matières (table des matières). Vous pouvez maintenant choisir de publier uniquement les noms des chapitres sans les numéros de chapitres. Affichez plus de détails sur la configuration des [paramètres PDF avancés d’un modèle](../native-pdf/components-pdf-template.md#advanced-pdf-settings).

## Téléchargement d’une carte à partir de l’éditeur web

Désormais, vous pouvez non seulement modifier une carte dans la vue Carte de l’éditeur web, mais également la télécharger. Vous pouvez choisir de télécharger la carte à l’aide d’une ligne de base spécifique. Vous avez également la possibilité d’aplatir la hiérarchie et d’enregistrer tous les fichiers et dossiers dans un seul dossier.

Pour plus d’informations, reportez-vous à la description de la fonctionnalité **Vue Carte** dans la section [Panneau de gauche](../user-guide/web-editor-features.md#id2051EA0M0HS).

![menu options d’un fichier dans la vue du référentiel](assets/options-menu-repo-view-file-level-2310.png){width="550"}

*Sélectionnez un fichier dans la vue du référentiel et choisissez l’option permettant d’effectuer une action sur le fichier.*

## Modifiez un fichier dans le plug-in du connecteur Oxygen

Experience Manager Guides vous permet désormais de sélectionner un fichier dans l’éditeur web, puis de choisir de le modifier dans le plug-in du connecteur Oxygen. Cette option n’est pas activée dans le cadre de la prise en charge prête à l’emploi.

Pour plus d’informations, reportez-vous à la description des fonctionnalités **Options de fichier** dans la section [Panneau de gauche](../user-guide/web-editor-features.md#id2051EA0M0HS).
