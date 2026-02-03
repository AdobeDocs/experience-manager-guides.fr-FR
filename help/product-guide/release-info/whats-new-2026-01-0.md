---
title: Notes de mise à jour | Nouveautés de la version Adobe Experience Manager Guides 2026.01.0
description: Découvrez les fonctionnalités nouvelles et améliorées de la version 2026.01.0 d’Adobe Experience Manager Guides
role: Leader
source-git-commit: f0ba8dce38a6eef5dedc8a81107c8e31ea6b26b3
workflow-type: tm+mt
source-wordcount: '1542'
ht-degree: 1%

---

# Nouveautés de la version 2026.01.0 (février 2026)

Cet article présente les nouvelles fonctionnalités améliorées introduites dans la version 2026.01.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour connaître la liste des problèmes résolus dans cette version, voir la section [Problèmes résolus dans la version 2026.01.0](fixed-issues-2026-01-0.md).

Découvrez les [instructions de mise à niveau pour la version 2026.01.0](../release-info/upgrade-instructions-2026-01-0.md).


## Présentation de la recherche en mode Source dans Rechercher et remplacer

Experience Manager Guides a apporté plusieurs améliorations à la fonction Rechercher et remplacer disponible dans le panneau de gauche de l’interface de l’éditeur. Outre une interface utilisateur améliorée pour une meilleure convivialité, cette version introduit un nouveau bouton bascule **Utiliser le mode source** dans le panneau **Rechercher et remplacer**.

L’activation de ce mode vous permet d’effectuer une recherche globale non seulement sur le contenu visible, mais également sur le contenu source sous-jacent (structure XML, y compris les éléments, les balises et les valeurs d’attribut) pour la chaîne recherchée. Ce mode permet d’assurer une recherche complète sur l’ensemble du contenu.

![](assets/map-find-replace-with-source-mode.png){width="650" align="left"}

Dans ce mode, vous pouvez appliquer des filtres pour affiner votre recherche par type de fichier, état du document, date de dernière modification, etc. Vous avez également la possibilité de télécharger un rapport CSV détaillé après l’opération Remplacer tout , qui fournit un instantané de toutes les actions de remplacement effectuées ainsi que leur statut de réussite et d’échec.

Pour plus d’informations, consultez la section [Rechercher et remplacer](../user-guide/web-editor-left-panel.md#find-and-replace) dans _Panneau de gauche de l’éditeur_.

>[!NOTE]
>
> Pour la fonctionnalité **Utiliser le mode source** du panneau Rechercher et remplacer , un déploiement d’index personnalisé doit d’abord être terminé. Une fois l’indexation en place, contactez votre équipe du succès client pour activer cette fonctionnalité.

## Amélioration de l’expérience de navigation dans les fichiers et les dossiers

Cette version introduit une interface plus épurée et plus intuitive pour parcourir les fichiers et les chemins d’accès aux dossiers dans Experience Manager Guides.

Lors de la navigation dans les fichiers, la boîte de dialogue repensée **Sélectionner un fichier** comprend désormais une disposition à onglets avec deux vues : **Référentiel** pour parcourir l’ensemble du référentiel de contenu sous la forme d’un tableau et **Collections** pour accéder rapidement aux rubriques, cartes et images fréquemment utilisées.

![](assets/select-file.png){width="650" align="left"}

Les principales améliorations sont les suivantes :

- Vue tabulaire des fichiers et des dossiers pour une navigation organisée.
- Chemins de navigation et panneau de navigation des dossiers pour vous déplacer facilement parmi les dossiers.
- Prise en charge de la sélection multi-fichiers pour le contenu réutilisable, les références de rubrique, le schéma, les paramètres prédéfinis de sortie (à l’aide de DITAVAL) et Workfront.
- Prévisualisez les fichiers sélectionnés pour une révision plus facile. Pour plusieurs sélections, prévisualisez tous les fichiers et supprimez-en un dans le panneau Prévisualisation, si nécessaire.
- Options de recherche et de filtrage permettant de filtrer les résultats par nom, titre, type de fichier, état du document et balises.

La boîte de dialogue **Sélectionner le chemin d’accès** propose également une vue arborescente améliorée pour la navigation entre les dossiers, offrant ainsi un moyen plus organisé et plus efficace de sélectionner les chemins d’accès dans le référentiel de contenu.

![](assets/select-path-dialog-new.png){width="350" align="left"}

Pour plus d’informations, consultez la section [Parcourir les fichiers et les dossiers dans Experience Manager Guides](../user-guide/web-editor-other-features.md#browse-files-and-folders-in-experience-manager-guides) dans _Autres fonctionnalités de l’éditeur_.

## Améliorations de la recherche et du filtrage de référentiel

### Prise en charge du filtre d’état du document

Désormais, filtrez les résultats de la recherche dans le référentiel en fonction de l’état actuel du document des fichiers. Le nouveau filtre **État du document** vous permet d’affiner votre recherche à l’aide des valeurs de filtre disponibles définies dans le fichier `ui_config.json` de votre profil de dossier.

![](assets/document-state-filter-repository.png){align="left"}

Les valeurs de filtre par défaut disponibles pour l’état du document sont les suivantes : Brouillon, Modifier, En cours de révision, Approuvé, Révisé et Terminé. Pour plus d’informations sur la personnalisation des valeurs des filtres d’état de document par défaut, voir [Configurer des filtres d’état de document](../cs-install-guide/config-doc-state-filters.md).

>[!NOTE]
>
> Si vous utilisez des paramètres personnalisés pour `ui_config.json` assurez-vous d’en reprendre une copie avant la mise à niveau. Après la mise à jour, vérifiez et ajustez vos paramètres pour vous aligner sur les modifications introduites dans la dernière version.

### Icône de miniature pour le multimédia

Tous les fichiers multimédias s’affichent désormais avec des icônes de miniature, ce qui facilite l’identification et la localisation visuelles des images dans le **référentiel**. Cette amélioration s’applique également lors de la recherche de fichiers dans le panneau **Recherche**, ce qui vous permet de distinguer rapidement les ressources multimédias des autres types de fichiers.

![](assets/thumbnail-repository.png){align="left"}

## Améliorations de l’éditeur

Les améliorations suivantes ont été apportées à l’éditeur dans le cadre de cette version :

### Actualiser les rubriques ou le mappage en mode Aperçu

Présentation de la nouvelle fonctionnalité **Actualiser** pour les mappages déjà ouverts en mode Aperçu. Grâce à cette nouvelle fonctionnalité, vous pouvez facilement actualiser le contenu de la carte entière ou des rubriques individuelles présentes dans celle-ci.

- Pour actualiser l’ensemble de la carte (y compris toutes les rubriques), un nouveau bouton **Actualiser** est introduit dans le coin supérieur gauche de l’éditeur.

  ![](assets/refresh-map.png){width="600" align="left"}

- Pour actualiser le contenu de rubriques individuelles, une nouvelle option **Actualiser la rubrique** est introduite dans le menu contextuel.

  ![](assets/refresh-topic.png){width="600" align="left"}

Pour plus d’informations, consultez [Fonctionnalités de l’éditeur de cartes](../user-guide/map-editor-advanced-map-editor.md).

### Indicateur de copie de travail pour les modifications de métadonnées

Toute modification apportée aux champs de métadonnées disponibles sous **Propriétés du fichier** déclenche désormais l’indicateur de copie de travail. Une version de document est marquée comme _sale (*)_ chaque fois que vous ajoutez, supprimez ou modifiez des champs de métadonnées par défaut ou personnalisés. Cette amélioration garantit que toutes les modifications apportées aux métadonnées sont suivies avec précision, offrant ainsi une meilleure visibilité et un meilleur contrôle sur les versions des documents.

### Nombre de mots pour les rubriques et les cartes

Vous pouvez désormais suivre le nombre de mots présents dans un mappage ou un fichier de rubrique. Le nouveau champ **Nombre de mots** dans le panneau de droite affiche le nombre total de mots présents dans une rubrique (ou un mappage), où les mots séparés par des espaces sont comptabilisés comme des mots individuels. Il s’actualise automatiquement chaque fois que vous enregistrez des modifications. Pour les références croisées, seul le texte affiché est inclus, tandis que les clés sont exclues.

![](assets/file-properties-new.png){width="350" align="left"}

Pour plus d’informations, consultez [Panneau de droite dans l’éditeur](../user-guide/web-editor-right-panel.md#file-properties).

### Amélioration de la gestion des fichiers en lecture seule

La modification des propriétés de fichier est désormais limitée aux fichiers qui sont en mode **Lecture seule**. Si un fichier est verrouillé par un autre utilisateur (disponible en mode Lecture seule), vous ne pouvez pas modifier une propriété de métadonnées, que ce soit à partir du panneau [Droite](../user-guide/web-editor-right-panel.md#file-properties), de l’option **Propriétés** du menu [contextuel d’un fichier](../user-guide/web-editor-other-features.md#context-menu-functions-on-a-files-tab) ou du [Rapport de métadonnées](../user-guide/reports-web-editor.md#metadata-report). Cela permet d’éviter les modifications accidentelles des fichiers en lecture seule.

## Améliorations de la révision

### Ajouter ou supprimer des rubriques d’une tâche de révision en cours

Désormais, vous pouvez ajouter de nouvelles rubriques à une tâche de révision en cours (si elles n’ont pas été précédemment envoyées pour révision) ou supprimer des rubriques d’une tâche de révision en cours sans affecter le workflow de révision.

Sur la page **Détails de la tâche**, vous pouvez simplement sélectionner ou désélectionner des rubriques pour modifier la liste de rubriques. Les réviseurs et réviseuses sont avertis (par AEM et par e-mail) de toute modification apportée aux rubriques qui leur sont attribuées par le biais d’AEM et de notifications par e-mail. Pour plus d’informations, voir [Envoyer les rubriques pour révision](../user-guide/review-send-topics-for-review.md).

![](assets/modify-review-topics.png){width="650" align="left"}

## Améliorations apportées à la traduction

### Indicateur pour les ressources non versionnées envoyées pour traduction

Lors de la gestion des traductions, il est important de s’assurer que le contrôle de version de tout le contenu est effectué avant de l’envoyer pour traitement. Pour faciliter cette tâche, Experience Manager Guides fournit désormais un indicateur clair pour les rubriques qui ont enregistré des modifications, mais qui n’ont pas encore de version.

Si un fichier contient des modifications sans version (non enregistrées en tant que nouvelle version dans votre mappage), une icône _info_ s’affiche en regard du fichier, indiquant que des mises à jour existent. Pour vous concentrer rapidement sur ces fichiers, activez l’option **Afficher uniquement les ressources avec des modifications sans version** dans le panneau Filtres.

Pour plus d’informations, consultez la section [Traduire les documents à partir de la console Carte](../user-guide/translate-documents-web-editor.md).

![](assets/unversioned-changes-translation.png){width="650" align="left"}

## Améliorations de la publication

### Rendus d’image personnalisés pour des paramètres prédéfinis de sortie spécifiques

Vous pouvez désormais configurer différents rendus d’image pour les paramètres prédéfinis de sortie individuels sous le même type de sortie à l’aide de l’attribut `outputName` dans `renditionmapping.xml`. Cette amélioration vous offre une plus grande flexibilité lors de la publication de contenu qui nécessite différentes résolutions d’image selon les scénarios. Par exemple, vous pouvez souhaiter une image haute résolution pour votre sortie HTML5 principale tout en utilisant une miniature plus petite pour un paramètre prédéfini léger.

Pour plus d’informations, consultez la section [Gérer le rendu d’image dans la génération de sortie](../cs-install-guide/conf-output-generation.md#handle-image-rendition-during-output-generation).


### Télécharger les journaux pour la sortie générée

Lors de la génération d’une sortie via l’interface utilisateur d’Assets, un nouveau bouton **Télécharger les journaux** est désormais disponible. Il vous permet de télécharger le journal sur votre appareil local pour un accès et une révision plus faciles.


### Variables de langue pour les références croisées dans la sortie PDF native

Lors de la publication d’une sortie PDF native, vous pouvez utiliser des [variables de langue](../native-pdf/native-pdf-language-variables.md) pour traduire du texte de référence croisée statique comme _Voir dans le chapitre_ ou _Voir sur la page_. La variable utilise la langue définie dans la rubrique via l’attribut `xml:lang`.

Pour plus d’informations sur la configuration du paramètre prédéfini de sortie PDF natif et des paramètres de référence croisée, consultez la section [Paramètre prédéfini de sortie PDF natif](../web-editor/native-pdf-web-editor.md).


### Prise en charge du mappage de composants au niveau des éléments dans la publication de New AEM Sites (à l’aide du mappage de composants composites)

Experience Manager Guides prend désormais en charge le mappage de composants au niveau des éléments dans la sortie AEM Sites (à l’aide du mappage de composants composites), ce qui permet aux équipes de contrôler précisément la manière dont les éléments DITA s’affichent à l’aide de `componentmapping.json`. En mappant des `topicref`, des titres, des images, des tableaux et plus encore aux composants principaux d’AEM appropriés, vous obtenez une structure plus épurée au lieu de tout ce qui est par défaut le composant de texte. Cela se traduit par de meilleures performances et des expériences Sites plus riches et plus modernes.

## Améliorations du traitement des ressources

Cette version apporte les améliorations suivantes au traitement des ressources :

- Exécutez le traitement des ressources au niveau du dossier et des fichiers individuels.
- Filtrez les ressources en choisissant des types de ressources spécifiques, tels que des rubriques, des mappages, Markdown, HTML/CSS, DITAVAL ou d’autres fichiers pris en charge, afin de traiter uniquement les fichiers dont vous avez besoin.
- Appliquez des filtres basés sur la date pour limiter l’étendue du traitement pour une période spécifiée.
- Retraiter les ressources directement à l’aide de la nouvelle option (**Retraiter les ressources**) disponible dans le menu contextuel des fichiers et dossiers dans la vue Référentiel et le panneau Explorateur.

Pour plus d’informations sur le traitement des ressources, voir [Traitement des ressources](../user-guide/asset-processor.md).

## Améliorations de l’API

Les améliorations d’API suivantes ont été apportées dans le cadre de cette version :

- De nouvelles API sont introduites pour créer un projet de traduction et suivre leur statut. Ces API permettent d’automatiser le processus de traduction, de réduire les efforts manuels et d’améliorer l’efficacité. Pour plus d’informations, consultez [Créer un projet de traduction](../api-reference/translation-project.md)
- Amélioration des API de traitement des ressources avec une meilleure capacité de filtrage des fichiers et des dossiers. Pour plus d’informations, consultez [Traitement des ressources](../api-reference/bulk-assets-processing.md).
















