---
title: Notes de mise à jour | Adobe Experience Manager Guides as a Cloud Service, version d’août 2022
description: Version d’août des Guides Adobe Experience Manager as a Cloud Service
exl-id: a01bfe8a-4715-438c-bb94-aa1d31f6662d
feature: Release Notes
role: Leader
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1169'
ht-degree: 0%

---

# Version d’août des Guides Adobe Experience Manager as a Cloud Service

## Mise à niveau vers la version d’août

Mettez à niveau vos guides Adobe Experience Manager actuels as a Cloud Service (plus tard appelés *AEM Guides as a Cloud Service*) en procédant comme suit :
1. Extrayez le code Git des Cloud Service et passez à la branche configurée dans le pipeline Cloud Service correspondant à l’environnement que vous souhaitez mettre à niveau.
1. Mettre à jour `<dox.version>` dans `/dox/dox.installer/pom.xml` du code Git Cloud Service vers la version 2022.8.167.
1. Validez les modifications et exécutez le pipeline Cloud Service pour effectuer la mise à niveau vers la version d’août d’AEM Guides as a Cloud Service.

## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par AEM Guides as a Cloud Service août 2022.

### FrameMaker et FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Non compatible | Mise à jour 4 et ultérieure 2020 |
| | |

*Les conditions de base et créées dans AEM sont prises en charge dans les versions FMPS à partir de 2020.2.

### Connecteur Oxygen

| AEM Guides as a Cloud | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen |
| --- | --- | --- |
| 2022.8.0 | 2,7,5 | 2,7,5 |
|  |  |  |


## Nouvelles fonctionnalités et améliorations

AEM Guides as a Cloud Service comporte de nombreuses améliorations et nouvelles fonctionnalités dans la version d’août :

### Mode Mise en page dans l’éditeur de mappage

Vous pouvez désormais afficher la mise en page complète d’un mappage DITA dans l’éditeur de cartes. Lorsque vous ouvrez une carte en vue de la modifier, elle ouvre la variable **Disposition** vue de l’éditeur de cartes. Dans cette vue, vous pouvez voir la hiérarchie des mappages dans une arborescence et organiser ou structurer les rubriques dans une carte.

![vue de mise en page](assets/layout-view-map.png)

La vue Disposition contient une barre d’outils distincte qui vous aide à effectuer de nombreuses tâches sur les rubriques présentes dans une carte.
Vous pouvez insérer des références de rubrique, un groupe de rubriques, des définitions de clés dans un mappage. Vous pouvez réorganiser les rubriques présentes dans une carte en les déplaçant vers le haut, le bas, la gauche ou la droite. Vous pouvez également faire glisser et déposer les rubriques pour les déplacer dans une carte. L’éditeur de mappage fournit également les icônes permettant de verrouiller ou de déverrouiller des fichiers, de vérifier l’historique des versions et d’effectuer une gestion des libellés de version.


La vue Disposition fournit également le **Options d’affichage** pour afficher ou masquer le numéro de ligne, afficher ou masquer une case à cocher ou afficher le nom ou le titre du fichier pour les rubriques dans une carte.


![view-options](assets/view-options.png)

Vous pouvez également afficher les rubriques en fonction des filtres conditionnels qui leur sont appliqués.

Outre l’organisation des rubriques dans le fichier de mappage, vous pouvez également ajouter, déplacer, copier, coller ou supprimer des références à l’aide de la variable **Options** pour un élément en mode Mise en page. Vous pouvez également faire glisser une rubrique ou un mappage depuis le panneau du référentiel vers le mappage ouvert dans l’éditeur de mappage.

Le panneau de droite affiche les propriétés du contenu et les propriétés de mappage dans la vue Disposition de l’éditeur de cartes. Les attributs intégrés définis pour la rubrique sélectionnée sont affichés par rapport à la rubrique dans la vue Disposition. Par exemple, vous pouvez rapidement trouver toutes les rubriques pour lesquelles l’attribut platform est défini comme `IOS`.

Vous pouvez désormais également définir les informations de métadonnées pour les rubriques ou la carte. Vous pouvez définir le titre de navigation, le texte du lien, la description courte et les mots-clés pour la rubrique ou le mappage sélectionné.

![panneau droit du mode Disposition](assets/layout-inline-attributes.png)

Pour plus d’informations, voir *Mode Mise en page* dans Utilisation des guides Adobe Experience Manager as a Cloud Service.

### Attributs intégrés dans les paramètres de l’éditeur

AEM Guides permet désormais de configurer les **Attributs intégrés** par votre administrateur depuis le **Paramètres de l’éditeur**. Vous pouvez également ajouter de nouveaux attributs intégrés ou supprimer les attributs existants du **Attributs intégrés** dans les paramètres de l’éditeur.
Les attributs intégrés configurés définis pour une rubrique sont affichés par rapport à la rubrique dans la vue Disposition.

![Paramètres de l’éditeur](assets/editor-settings-inline-attributes.png)


### Filtres supplémentaires dans la vue Repository

Désormais, la recherche de filtre dans la vue du référentiel a été rendue plus puissante. Deux nouveaux critères de recherche, **Dernière modification** et **Balises** ont été ajoutés pour filtrer les fichiers et pour affiner votre recherche dans le référentiel AEM :
* **Dernière modification**: vous pouvez rechercher les fichiers qui ont été modifiés pour la dernière fois après une date sélectionnée, mais avant une date sélectionnée. Vous avez également la possibilité d’utiliser les critères prédéfinis et de rechercher les fichiers qui ont été modifiés pour la dernière fois au cours des deux dernières heures, de la semaine dernière, du mois dernier ou de l’année dernière.
* **Balises**: vous pouvez également rechercher des fichiers auxquels des balises spécifiques sont appliquées. Vous pouvez saisir la balise ou la sélectionner dans la liste déroulante.

![Filtres d’affichage du référentiel](assets/repo-filter-search.png)


## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :

* L’index Lucene obsolète est utilisé dans /core/article-publish/src/main/java/com/adobe/dxml/article/publish/util/DoxUtils.java (9291)
* Le fichier Node.js mis à jour n’est pas utilisé pour la publication. (9835)
* La rubrique DITA n’est pas mise à jour automatiquement avec les modifications effectuées sur la **Propriétés** page. (8745)
* Lorsqu’il est ajouté à un mappage d’applet DITA, l’élément de structure de contenu ne fonctionne pas correctement. (9507)
* PDF natif | Un PDF vierge est généré lors de l’utilisation de **Génération rapide** pour plusieurs fichiers lorsqu’un élément vide est sélectionné. (9822)
* PDF natif | L’annexe est publiée sous forme de chapitre dans la sortie du PDF. (9829)
* PDF natif | Lorsqu’une image de SVG est modifiée, elle n’est pas affichée dans la mise en page. (9069)
* Un trait d’union normal est inséré lorsqu’un `Nonbreaking Hyphen` est inséré à l’aide du **Insérer un caractère spécial** boîte de dialogue. (8919)
* L’éditeur XML n’affiche pas les images mises à jour dans les rubriques si elles ont été modifiées. (9500)
* Lors de la publication de la sortie via l’éditeur, les paramètres prédéfinis ne peuvent pas être supprimés de la variable **Sortie** . (9100)
* Les sous-cartes d’un mappage DITA ne sont pas extraites à l’aide de la variable **Tout sélectionner** dans le menu représentant des points de suspension. (9814)
* Impossible de faire glisser et de déposer le mappage ou les modèles de rubrique depuis le **Modèles** au modèle de mappage personnalisé dans l’éditeur web. (9846)
* Impossible de créer une nouvelle rubrique ou un nouveau modèle de mappage dans le sous-dossier d’un mappage ou d’un modèle de rubrique. (9888)
* Aucune option n’est présente pour parcourir les rubriques ou les cartes présentes dans les sous-dossiers d’une carte ou d’un modèle de rubrique. (9889)
* Lorsqu’un fichier de schéma est mis à jour et enregistré avec le fichier DITA, le panneau de droite n’est pas affiché (si le fichier DITA rompt les validations présentes dans le fichier de schéma). (9986)
* Un nouveau paramètre prédéfini de sortie en double peut être créé si son nom est identique à un paramètre prédéfini existant. (9997)
* Les images du SVG sont corrompues et ne sont pas publiées correctement lors de la génération de la sortie du HTML. (9949)


## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version as a Cloud Service d’août 2022 d’AEM Guides.

### Problèmes connus liés à la solution

Utilisez la solution donnée pour les problèmes connus suivants :

* La vue Disposition n’est pas visible dans l’éditeur de cartes.

  **Solution**: mettez à jour le fichier ui_config.json dans le profil du dossier.

* Le fichier Symbols.json est remplacé, donc le problème 8919 se produit.

  **Solution**: la mise à jour de la bibliothèque de symboles.json doit être fusionnée avec la bibliothèque de symboles.json remplacée.

### Autres problèmes connus

* Si plusieurs fichiers sont sélectionnés à partir de la section de résultat affichée lors de l’exécution d’une recherche dans le référentiel, puis que vous effectuez un glisser-déposer dans la vue de création, un seul fichier est ajouté.
