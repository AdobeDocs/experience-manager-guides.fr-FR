---
title: Notes de mise à jour | Nouveautés d’Adobe Experience Manager Guides, version de septembre 2023
description: Découvrez les fonctionnalités nouvelles et améliorées de la version de septembre 2023 d’Adobe Experience Manager Guides as a Cloud Service
exl-id: d185d27f-0cbb-4ec6-ac65-cb69f7572c3f
feature: What's New
role: Leader
source-git-commit: 12ba7129255257970ddd7a0989149be664ce9803
workflow-type: tm+mt
source-wordcount: '1691'
ht-degree: 0%

---

# Nouveautés de la version de septembre 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cet article présente les nouvelles fonctionnalités améliorées de la version de septembre 2023 d’Adobe Experience Manager Guides (plus tard appelée *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans cette version, voir [Notes de mise à jour](release-notes-2023-9-0.md).

## Se connecter à une source de données et insérer les rubriques

AEM Guides fournit des connecteurs prêts à l’emploi qui vous aident à vous connecter à vos sources de données, ce qui fait d’AEM Guides un véritable hub de contenu. Vous gagnez ainsi du temps et économisez des efforts qui auraient autrement été consacrés à l’ajout ou à la réplication manuels de données.

Outre les connecteurs prêts à l’emploi existants tels que JIRA et SQL (MySQL, PostgreSQL, SQL Server, SQLite), votre administrateur peut également configurer des connecteurs pour les bases de données MariaDB, H2DB, AdobeCommerce et Elasticsearch. Ils peuvent également ajouter d’autres connecteurs en étendant les interfaces par défaut.

Vous pouvez afficher les connecteurs configurés sous le panneau **Sources de données** dans l’éditeur web.

<img src="assets/data-sources.png" alt="Liste des sources de données dans le panneau" width="300">

*Afficher les sources de données connectées.*

Vous pouvez désormais également créer une rubrique à partir d’une source de données connectée. Une rubrique peut contenir des données dans différents formats, tels que des tableaux, des listes et des paragraphes. Il permet également de créer un plan DITA pour toutes les rubriques. Vous pouvez associer des métadonnées à la rubrique lors de l’extraction d’une source de données.

Pour plus d’informations, consultez la section [Utiliser les données de votre source de données](../user-guide/web-editor-content-snippet.md).

## Ajouter des citations à votre contenu

Les citations sont des références à la source d’informations ajoutée à votre contenu. Les citations vous aident à établir la crédibilité et à prévenir le plagiat. Les citations aident les lecteurs à localiser la source et à vérifier les informations présentées dans le texte.

Dans AEM Guides, vous pouvez ajouter des citations ou importer des citations et les appliquer à votre contenu. Vous pouvez ajouter ces citations à partir de n’importe quelle source de livres, de sites web et de revues.

Après avoir inséré vos citations dans vos rubriques, vous pouvez les prévisualiser dans l’éditeur web. Vous pouvez également publier du contenu avec des citations à l’aide du PDF natif.

![Citations répertoriées dans un panneau](assets/citation-panel.png){width="300"}

*Afficher la liste des citations dans le panneau Citations.*

Pour plus d’informations, consultez la section [ Ajouter et gérer des citations dans votre contenu ](../user-guide/web-editor-apply-citations.md).


## Publication sur un fragment de contenu

Les fragments de contenu sont des éléments de contenu distincts dans AEM. Il s’agit de contenu structuré basé sur un modèle de contenu. Les fragments de contenu sont du contenu pur sans informations de conception ou de mise en page. Ils peuvent être créés et gérés indépendamment des canaux pris en charge par AEM. La modularité et la réutilisation des fragments de contenu accroissent la flexibilité, la cohérence, l’efficacité et simplifient la gestion.

AEM Guides offre désormais la possibilité de publier une rubrique ou les éléments d’une rubrique dans un fragment de contenu. Vous pouvez créer un mappage basé sur JSON entre une rubrique et un modèle de fragment de contenu. Utilisez ce mappage pour publier le contenu présent dans certains éléments ou dans tous les éléments d’une rubrique vers un fragment de contenu.

Tirez parti de la puissance d’AEM Guides et des fragments de contenu et utilisez les fragments de contenu dans n’importe quel site AEM. Vous pouvez également extraire les détails par le biais d’API prises en charge par les fragments de contenu.

![option de publication de fragment de contenu](assets/content-fragment-publish.png){width="550"}

*Publication d’une rubrique dans un fragment de contenu.*

Pour plus d’informations, consultez la section [Publier sur un fragment de contenu](../user-guide//publish-content-fragment.md).

## Améliorations de la révision

AEM Guides offre désormais une fonctionnalité de révision améliorée avec les fonctionnalités suivantes :

### Rechercher des rubriques de révision

La réalisation de révisions est une fonctionnalité essentielle d’AEM Guides. Il permet aux réviseurs de passer en revue les documents qui leur sont affectés .
Vous pouvez désormais rechercher une rubrique en saisissant une partie du texte du titre ou du chemin de fichier dans la barre de recherche de l’affichage des rubriques du panneau de révision. Vous pouvez également choisir d’afficher toutes les rubriques ou d’afficher les rubriques avec des commentaires. Par défaut, vous pouvez afficher toutes les rubriques présentes dans la tâche de révision. Pour plus d’informations, voir [Rubriques de révision](../user-guide/review-topics.md).

![Rechercher dans un panneau de rubriques de révision](assets/review-search-topic.png){width="800"}

*Rechercher une rubrique de révision dans le panneau de révision.*



## Framework d’extension Guides

Créez des packages personnalisés en plus d’AEM Guides pour offrir une extensibilité à l’aide du framework d’extension AEM Guides. Ces packages sont utiles pour les développeurs et les consultants et leur donnent l’extensibilité aux composants dans l’éditeur. Ils peuvent cibler des boutons, des boîtes de dialogue et des listes déroulantes, et ajouter des JavaScript personnalisées qui peuvent facilement interagir avec l’interface utilisateur d’AEM Guides.



## Améliorations du PDF natif

Les améliorations apportées à Native PDF dans la version de septembre 2023 ont permis de rendre AEM Guides plus robuste :



### Classer les pages dans la sortie PDF

Vous pouvez afficher ou masquer les sections suivantes dans votre PDF et organiser l’ordre dans lequel elles doivent apparaître dans votre sortie PDF finale :

* Table des matières
* Chapitres et sujets
* Liste des figures
* Liste des tables
* Index
* Glossaire
* Citation
* Mises en page

Si vous ne souhaitez pas afficher une section particulière dans votre sortie PDF, vous pouvez la masquer en désactivant le bouton bascule.

Pour plus d’informations, voir [Ordre des pages](../native-pdf/components-pdf-template.md#page-order).

### Fusion de pages

Dans une sortie PDF native par défaut, toutes les sections commencent sur une nouvelle page. Vous pouvez maintenant fusionner une section à sa page précédente ou à la page suivante. Cette action publie la section en continuant avec la page sélectionnée dans la sortie PDF. Aucune saut de page n’est effectué entre les deux.

Pour plus d’informations, reportez-vous à la description des fonctionnalités de la section **Fusion de pages** dans [Ordre des pages](../native-pdf/components-pdf-template.md#page-order).

### Démarrer un chapitre à partir de la page active

Vous pouvez définir les paramètres de configuration de base pour démarrer un chapitre à partir d’une page paire ou impaire, la structure de la table des matières et définir le format de ligne de repère pour les entrées de la table des matières.

Vous pouvez également commencer un chapitre à partir de la page active. Si vous choisissez de le faire, tous les chapitres sont publiés en continu, sans sauts de page. Par exemple, si un chapitre se termine au milieu de la page 15, le chapitre suivant commence également à partir de la 15e page elle-même.

Pour plus d’informations, consultez la description de l’onglet **Général** dans [Paramètres PDF avancés](../native-pdf/components-pdf-template.md#advanced-pdf-settings-advanced-pdf-settings).

### Pages statiques

Vous pouvez également créer des mises en page personnalisées et les publier en tant que pages statiques dans la sortie PDF. Cela vous permet d’ajouter du contenu statique, tel que des notes ou des pages vierges.

Pour plus d’informations, consultez la description des fonctionnalités de la **Pages statiques** dans la section [Ordre des pages](../native-pdf/components-pdf-template.md#page-order).


### Variables dans les références croisées

Vous pouvez utiliser des variables pour définir une référence croisée. Lorsque vous utilisez une variable, sa valeur est sélectionnée dans les propriétés.

Vous pouvez désormais également utiliser {figure} et {table}.
Utilisez {figure}pour ajouter une référence croisée au numéro de la figure. Il sélectionne le numéro de figure parmi les styles de numéros automatiques que vous avez définis pour la légende.

Utilisez {table} pour ajouter une référence croisée au numéro de la table. Il sélectionne le numéro du tableau parmi les styles de numéros automatiques que vous avez définis pour les légendes.

Pour plus d’informations, voir [Références croisées](../native-pdf/components-pdf-template.md##cross-references).



### Refonte de l’éditeur CSS

L’éditeur CSS est maintenant repensé pour une meilleure expérience utilisateur avec des sélecteurs et des propriétés de style.

#### Amélioration de la boîte de dialogue Ajouter un style

Vous pouvez désormais utiliser des sélecteurs personnalisés pour ajouter des styles complexes. Le nouveau champ Sélecteur vous permet d’ajouter des sélecteurs personnalisés en plus de la combinaison Classe, Balise et Pseudo-Classe . Par exemple, vous pouvez créer `table a.link` style pour tous les liens hypertexte d’un tableau.

![ajout de styles dans les modèles pdf natifs](assets/add-styles-native-pdf.png){width="300"}

*Ajoutez les détails du nouveau style.*

#### Personnalisation des propriétés du style

AEM Guides vous présente désormais un nouveau panneau de propriétés sous la section d’aperçu pour les styles. Vous pouvez modifier les propriétés des styles plus efficacement et plus rapidement à partir du panneau des propriétés.


## Prise en charge de plusieurs définitions d’objet dans une seule définition d’énumération

Vous pouvez maintenant définir une ou plusieurs définitions d’objet dans un mappage et les définitions d’énumération dans un autre mappage, puis ajouter la référence de mappage. Les références d’énumération d’objet sont résolues dans le même mappage ou le mappage référencé.

Vous pouvez désormais également définir des conditions et les appliquer à certains éléments spécifiques d&#39;une rubrique.  Les conditions ne sont visibles que pour ces éléments spécifiques et non pour tous les autres éléments.

Pour plus d&#39;informations sur la gestion des définitions hiérarchiques des objets et des énumérations, consultez la description de la fonctionnalité Schéma d&#39;objet dans la section [Panneau de gauche](../user-guide/web-editor-features.md#id2051EA0M0HS).





## Sélection de tous les paramètres prédéfinis d’une collection de cartes

Vous pouvez non seulement activer un paramètre prédéfini individuel et tous les paramètres prédéfinis de profil de dossier, mais également activer tous les paramètres prédéfinis d&#39;un plan DITA en une seule fois.
![modifier une collection de cartes](assets/edit-map-collection-cs.png){width="800"}\
*Sélection de tous les paramètres prédéfinis d’une collection de cartes.*

Pour plus d’informations, consultez [Utilisation de la collecte de mappages pour la génération de sortie](../user-guide/generate-output-use-map-collection-output-generation.md).


## Prise en charge native de PDF dans le tableau de bord de publication en bloc


Grâce à la fonction d’activation en bloc d’AEM Guides, vous pouvez activer rapidement et facilement votre contenu, de la création à la publication. Dans la carte Activation en bloc, vous pouvez inclure le paramètre prédéfini de sortie Native PDF, le site AEM, PDF, HTML5, personnalisé et la sortie JSON.
Pour plus d’informations, consultez la section [ Activation en bloc du contenu publié ](../user-guide/conf-bulk-activation.md).

## Outil de déplacement en bloc amélioré

Désormais, en tant qu’administrateur, vous pouvez utiliser l’outil de déplacement en bloc amélioré pour déplacer des dossiers contenant de nombreux fichiers d’un emplacement à un autre.
Vous pouvez utiliser la boîte de dialogue Parcourir le fichier pour sélectionner les dossiers sources à déplacer. Vous pouvez également accéder à l’emplacement de destination pour déplacer les dossiers sources. Sélectionnez ![icône d’information](assets/info-icon.svg) {width="25"} près d’un champ pour afficher plus d’informations à son sujet.

Pour plus d’informations, consultez la section [ Déplacer des fichiers en bloc ](../user-guide/authoring-file-management.md#move-files-bulk).


## Expérience d’aperçu améliorée à partir du menu contextuel

Utilisez le menu contextuel pour prévisualiser rapidement le fichier (.dita, .xml, audio, vidéo ou image) sans l’ouvrir. Vous pouvez désormais redimensionner le volet d’aperçu. Si le contenu contient un lien de référence, vous pouvez le sélectionner pour l’ouvrir dans un nouvel onglet.

](assets/quick-preview_cs.png){width="800"} du volet d’aperçu![

*Prévisualisez le fichier dans le volet.*

Pour plus d’informations sur le menu contextuel, reportez-vous à la description de la fonction **Options de fichier** dans la section [Panneau de gauche](../user-guide/web-editor-features.md#id2051EA0M0HS).


## Utilisez des variables pour la date et l’heure actuelles dans les options Chemin de destination, Nom du site ou Nom de fichier

Lors de la génération de sorties dans des fichiers PDF ou de site AEM, vous pouvez utiliser des variables pour définir les options **Chemin de destination**, **Nom du site** ou **Nom du fichier**. Vous pouvez désormais également utiliser les variables `${system_date}` et `${system_time}`. Ces variables vous aident à ajouter la date et l’heure actuelles à ces options.

Découvrez comment [utiliser des variables pour définir les options Chemin de destination, Nom du site ou Nom de fichier](../user-guide/generate-output-use-variables.md).
