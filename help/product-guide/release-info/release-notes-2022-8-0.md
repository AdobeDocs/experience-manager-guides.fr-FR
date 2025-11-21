---
title: Notes de mise à jour | Adobe Experience Manager Guides as a Cloud Service, version d’août 2022
description: Version d’août d’Adobe Experience Manager Guides as a Cloud Service
exl-id: a01bfe8a-4715-438c-bb94-aa1d31f6662d
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1169'
ht-degree: 0%

---

# Version d’août d’Adobe Experience Manager Guides as a Cloud Service

## Mise à niveau vers la version d’août

Mettez à niveau votre configuration Adobe Experience Manager Guides as a Cloud Service actuelle (ultérieurement appelée *AEM Guides as a Cloud Service*) en procédant comme suit :
1. Consultez le code Git des services cloud et passez à la branche configurée dans le pipeline des services cloud correspondant à l’environnement à mettre à niveau.
1. Mettez à jour `<dox.version>` propriété dans `/dox/dox.installer/pom.xml` fichier de votre code Git Cloud Services vers la version 2022.8.167.
1. Validez les modifications et exécutez le pipeline Cloud Services pour effectuer la mise à niveau vers la version d’août d’AEM Guides as a Cloud Service.

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par la version d’août 2022 d’AEM Guides as a Cloud Service.

### FrameMaker et FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Non compatible | Mise à jour 2020 4 et versions ultérieures |
| | |

*La ligne de base et les conditions créées dans AEM sont prises en charge dans les versions FMPS à compter de 2020.2.

### Connecteur D&#39;Oxygène

| Version d’AEM Guides as a Cloud | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène |
| --- | --- | --- |
| 2022.8.0 | 2,7,5 | 2,7,5 |
|  |  |  |


## Nouvelles fonctionnalités et améliorations

AEM Guides as a Cloud Service offre de nombreuses améliorations et nouvelles fonctionnalités dans la version d’août :

### Mode Disposition dans l’éditeur de cartes

Vous pouvez maintenant afficher la disposition complète d&#39;un plan DITA dans l&#39;éditeur de plans. Lorsque vous ouvrez une carte pour la modifier, la vue **Disposition** de l’éditeur de cartes s’affiche. Dans cette vue, vous pouvez voir la hiérarchie des cartes dans une arborescence et également organiser ou structurer les rubriques dans une carte.

![mode mise en page](assets/layout-view-map.png)

Le mode Mise en page contient une barre d’outils distincte qui vous permet d’effectuer de nombreuses tâches sur les rubriques présentes dans une carte.
Vous pouvez insérer des références de rubrique, un groupe de rubriques, des définitions de clés dans un mappage. Vous pouvez réorganiser les rubriques présentes dans une carte en les déplaçant vers le haut, le bas, la gauche ou la droite. Vous pouvez également faire glisser et déposer les rubriques pour les déplacer dans un mappage. L’éditeur de carte fournit également les icônes pour verrouiller ou déverrouiller les fichiers, vérifier l’historique des versions et gérer les libellés de version.


Le mode Mise en page fournit également la **Options d&#39;affichage** pour afficher ou masquer le numéro de ligne, afficher ou masquer la case à cocher ou afficher le nom de fichier ou le titre des rubriques dans un mappage.


![view-options](assets/view-options.png)

Vous pouvez également afficher les rubriques en fonction des filtres conditionnels qui leur sont appliqués.

En plus d&#39;organiser les rubriques dans le fichier map, vous pouvez également ajouter, déplacer, copier, coller ou supprimer des références à l&#39;aide du menu **Options** disponible pour un élément en mode Mise en page. Vous pouvez également faire glisser une rubrique ou une carte du panneau du référentiel vers la carte ouverte dans l’éditeur de cartes.

Le panneau de droite affiche les propriétés de contenu et les propriétés de carte en mode Mise en page de l’éditeur de cartes. Les attributs intégrés définis pour la rubrique sélectionnée s’affichent en regard de la rubrique en mode Mise en page. Par exemple, vous pouvez rechercher rapidement toutes les rubriques dont l’attribut de plateforme est défini sur `IOS`.

Vous pouvez désormais également définir les informations de métadonnées pour les rubriques ou la carte. Vous pouvez définir le Titre de navigation, le Texte du lien, la Description courte et les Mots-clés pour la rubrique ou le mappage sélectionné.

![panneau droit du mode disposition](assets/layout-inline-attributes.png)

Pour plus d’informations, consultez la section *Mode Mise en page* dans Utilisation d’Adobe Experience Manager Guides as a Cloud Service.

### Attributs intégrés dans les paramètres de l’éditeur

AEM Guides permet désormais à votre administrateur de configurer les **attributs intégrés** à partir des **paramètres de l’éditeur**. Vous pouvez également ajouter de nouveaux attributs intégrés ou supprimer les attributs existants à partir de l’onglet **Attributs intégrés** dans les paramètres de l’éditeur.
Les attributs intégrés configurés définis pour une rubrique s’affichent par rapport à la rubrique en mode Mise en page.

![Paramètres de l’éditeur](assets/editor-settings-inline-attributes.png)


### Filtres supplémentaires dans la vue Référentiel

Désormais, la recherche de filtres dans la vue du référentiel est plus puissante. Deux nouveaux critères de recherche, **Dernière modification** et **Balises** ont été ajoutés pour filtrer les fichiers et affiner votre recherche dans le référentiel AEM :
* **Dernière modification** : vous pouvez rechercher les fichiers qui ont été modifiés pour la dernière fois après une date sélectionnée, mais avant une date sélectionnée. Vous avez également la possibilité d’utiliser les critères prédéfinis et de rechercher les fichiers qui ont été modifiés pour la dernière fois au cours des 2 dernières heures, de la semaine dernière, du mois dernier ou de l’année dernière.
* **Balises** : vous pouvez également rechercher les fichiers sur lesquels des balises spécifiques sont appliquées. Vous pouvez saisir la balise ou la sélectionner dans la liste déroulante.

![Filtres d’affichage du référentiel](assets/repo-filter-search.png)


## Problèmes résolus

Les bogues corrigés dans différentes zones sont répertoriés ci-dessous :

* L’index Lucene obsolète est utilisé dans /core/article-publish/src/main/java/com/adobe/dxml/article/publish/util/DoxUtils.java (9291).
* Node.js mis à jour n’est pas utilisé pour la publication. (9835)
* La rubrique DITA n&#39;est pas mise à jour automatiquement avec les modifications effectuées sur la page **Propriétés**. (8745)
* L&#39;élément FrontMATTER ajouté à un bookmap DITA ne fonctionne pas correctement. (9507)
* PDF natif | Un PDF vierge est généré lors de l’utilisation de **Génération rapide** pour plusieurs fichiers lorsqu’un élément vide est sélectionné. (9822)
* PDF natif | L’annexe est publiée sous la forme d’un chapitre dans la sortie PDF. (9829)
* PDF natif | Lorsqu’une image SVG est modifiée, elle n’est pas affichée mise à jour dans la mise en page. (9069)
* Un trait d&#39;union normal est inséré lorsqu&#39;un caractère `Nonbreaking Hyphen` est inséré à l&#39;aide de la boîte de dialogue **Insérer un caractère spécial**. (8919)
* L’éditeur XML n’affiche pas les images mises à jour dans les rubriques si elles ont été modifiées. (9500)
* Lors de la publication de la sortie via l’éditeur, les paramètres prédéfinis ne peuvent pas être supprimés de l’onglet **Sortie**. (9100)
* Les sous-zones d&#39;un plan DITA ne sont pas extraites à l&#39;aide de l&#39;option **Tout sélectionner** du menu représentant des points de suspension. (9814)
* Impossible de glisser-déposer les modèles de carte ou de rubrique du menu **Modèles** vers le modèle de carte personnalisé dans l’éditeur Web. (9846)
* Impossible de créer une nouvelle rubrique ou un nouveau modèle de rubrique dans le sous-dossier d&#39;une rubrique ou d&#39;un modèle de rubrique. (9888)
* Aucune option n’est présente pour parcourir les rubriques ou les cartes présentes dans les sous-dossiers d’une carte ou d’un modèle de rubrique. (9889)
* Lorsqu&#39;un fichier Schematron est mis à jour et enregistré avec le fichier DITA, le panneau de droite n&#39;est pas affiché (si le fichier DITA rompt les validations présentes dans le fichier Schematron). (9986)
* Un nouveau paramètre prédéfini de sortie en double peut être créé si son nom est identique à celui d’un paramètre prédéfini existant. (9997)
* Les images SVG sont corrompues et ne sont pas publiées correctement lors de la génération de la sortie HTML. (9949)


## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version d’août 2022 d’AEM Guides as a Cloud Service.

### Problèmes connus liés à la solution de contournement

Utilisez la solution donnée pour les problèmes connus suivants :

* Le mode Mise en page n’est pas visible dans l’éditeur de cartes.

  **Solution** : mettez à jour le fichier ui_config.json dans le profil de dossiers.

* Symbols.json est remplacé de sorte que le problème 8919 se produit.

  **Solution** : le fichier symbols.json mis à jour doit être fusionné avec le fichier symbols.json remplacé.

### Autres problèmes connus

* Si plusieurs fichiers sont sélectionnés dans la section de résultats affichée lors de l’exécution d’une recherche sur le référentiel, puis font glisser et sont déposés dans la vue de création, un seul fichier est ajouté.
