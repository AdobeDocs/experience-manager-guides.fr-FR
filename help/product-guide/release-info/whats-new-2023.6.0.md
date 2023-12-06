---
title: Notes de mise à jour | Nouveautés des guides Adobe Experience Manager, version de juin 2023
description: Découvrez les nouvelles fonctionnalités et les fonctionnalités améliorées de la version de juin 2023 de Adobe Experience Manager Guides as a Cloud Service
exl-id: 625f9702-2b91-4622-9fec-282f47f1d7a6
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 0%

---

# Nouveautés de la version de juin 2023 des Guides Adobe Experience Manager as a Cloud Service

Cet article couvre les nouvelles fonctionnalités et les fonctionnalités améliorées de la version de juin 2023 des Guides Adobe Experience Manager (ultérieurement appelée *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans cette version, voir [Notes de mise à jour](release-notes-2023.6.0.md).

## Rapport Liens rompus dans l’éditeur web

AEM Guides vous permet de vérifier l’exhaustivité globale de vos documents techniques et de générer des rapports à partir de l’éditeur web. La version de juin 2023 d’AEM Guides vous offre désormais la fonctionnalité d’affichage et de correction des liens rompus. Il s’agit d’un rapport utile qui vous aide à gérer vos liens rompus. Vous pouvez facilement afficher les liens rompus présents dans votre carte DITA et les corriger.
![](assets/broken-link-report.png){width="800" align="left"}

Une fois un lien corrigé, il ne s’affiche pas sous la liste des liens rompus.

Pour plus d’informations, voir [Afficher et corriger les liens rompus](../user-guide/reports-web-editor.md#report-broken-links).

## Renommer et déplacer des fichiers dans la vue Repository

Vous pouvez désormais également renommer ou déplacer un fichier à partir du panneau du référentiel. Cette fonctionnalité est pratique et permet de gérer facilement vos fichiers à partir du panneau Référentiel . Vous pouvez sélectionner un fichier et le renommer ou le déplacer à l’aide de la fonction **Options** pour le fichier sélectionné. AEM Guides affiche un message de réussite lorsque vous déplacez ou renommez un fichier.

![](assets/rename-move-assets.png){width="650" align="left"}

Pour plus d’informations sur le menu Options d’un fichier, voir la section **Vue Repository** description des fonctionnalités dans la section [Panneau gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .

## Améliorations apportées aux PDF natifs

### Ajout d’un filigrane à la sortie PDF pour les documents de brouillon

Vous pouvez maintenant ajouter un filigrane à la sortie PDF du document qui n’a pas encore été approuvé. Ce filigrane n’apparaît pas si vous générez le PDF du document dans le docstate &quot;Approuvé&quot;. Par exemple, vous pouvez ajouter un brouillon de filigrane pour la sortie de votre PDF.

Pour plus d’informations, voir [Ajout d’un filigrane à la sortie du PDF pour les brouillons de documents](../native-pdf/use-javascript-content-style.md#watermark-draft-document).

### Prise en charge des variables de langue

AEM Guides prend en charge les variables de langue. Vous pouvez utiliser des variables de langue pour définir une version localisée des libellés prêts à l’emploi tels que Remarque, Attention et Avertissement ou texte statique dans la sortie du PDF.
Vous pouvez ajouter les variables de langue ou la version localisée des étiquettes aux sections appropriées dans la sortie de votre PDF et dans les modèles de sortie.

#### Variables de langue dans la sortie du PDF

Vous pouvez utiliser les variables de langue pour définir des libellés localisés pour des éléments tels que Remarque, Attention et Avertissement. Vous pouvez mettre à jour la valeur de ces variables dans une ou plusieurs langues, puis la valeur localisée est automatiquement sélectionnée dans la sortie du PDF.
Par exemple, vous pouvez présenter le libellé Remarque dans la sortie de votre PDF de la manière suivante :

* Anglais : Remarque
* Français : Remarque
* Allemand : Hinweis

#### Variables de langue dans les modèles de sortie

Si vous vouliez créer la sortie du PDF dans différentes langues, vous deviez créer différents modèles de PDF contenant du texte localisé pour chaque langue. Désormais, avec la fonction Variables de langue, vous n’avez besoin de créer le modèle qu’une seule fois. Ensuite, pour tout texte statique que vous devez localiser, vous pouvez créer les variables de langue correspondantes et les utiliser dans votre modèle.
Vous pouvez créer des variables de langue pour du texte plus long, comme une phrase entière ou même un paragraphe. Vous pouvez également appliquer des styles et utiliser des balises de HTML pour formater ces variables de langue.

Pour plus d’informations, voir [Prise en charge des variables de langue](../native-pdf/native-pdf-language-variables.md).

### Possibilité d’utiliser des métadonnées AEM dans des mises en page PDF

Les métadonnées sont la description ou la définition de votre contenu. Ces métadonnées sont stockées dans le contenu de votre mappage DITA source.

Désormais, dans AEM Guides, vous pouvez également sélectionner les propriétés de métadonnées de vos ressources et les ajouter à la mise en page. AEM Guides sélectionne ensuite ces propriétés de métadonnées de vos ressources et les publie dans la sortie PDF.


![](assets/native-pdf-metadata-asset.png){width="550" align="left"}

>[!NOTE]
>
> AEM Guides prend également en charge les propriétés de métadonnées pour vos mappages DITA.

Pour plus d’informations, voir [Ajout de champs et de métadonnées](../native-pdf/design-page-layout.md#add-fields-metadata).


## Améliorations des schémas

### Utilisation d’instructions de rapport pour vérifier les règles dans le schéma

AEM Guides prend désormais en charge les instructions de rapport avec le schéma. Une instruction de rapport génère un message lorsqu’une instruction de test est évaluée comme vraie. Par exemple, si vous souhaitez que la brève description soit inférieure ou égale à 150 caractères, vous pouvez définir une instruction de rapport afin de vérifier les rubriques dont la brève description comporte plus de 150 caractères.

Pour plus d’informations, voir [Utilisez des instructions d’insertion et de rapport pour rechercher des règles.](../user-guide/support-schematron-file.md#schematron-assert-report).

### Utilisation d’expressions Regex

Vous pouvez également utiliser des expressions Regex pour définir une règle avec la fonction matches(), puis effectuer la validation à l’aide du fichier de schéma.

Pour plus d’informations, voir [Utilisation d’expressions Regex](../user-guide/support-schematron-file.md#schematron-assert-report).


### Définition de modèles abstraits

AEM Guides prend également en charge les modèles abstraits dans Schematron. Vous pouvez définir des modèles abstraits génériques et réutiliser ces modèles abstraits. Les modèles abstraits peuvent simplifier votre schéma de schéma et vous aider à gérer et à mettre à jour votre logique de validation.


Pour plus d’informations, voir [Définition de modèles abstraits](../user-guide/support-schematron-file.md#schematron-abstract-patterns).

## Accédez à la page d’accueil d’AEM à partir de l’éditeur Web.

Vous pouvez désormais facilement accéder à la page d’accueil d’AEM à partir de l’éditeur Web.

![](assets/web-editor-launch-page.png){width="800" align="left"}

* Cliquez sur le bouton **Guides** icône (![](assets/aem-guides-icon.png) ), pour revenir à la page de navigation AEM.


Pour plus d’informations, voir [Page de navigation AEM](../user-guide/web-editor-launch-editor.md#id2056BG00RZJ).

## Gestion des définitions hiérarchiques des définitions de sujet et des énumérations

AEM Guides s’accompagne d’une puissante fonctionnalité permettant de créer des mappages de schéma d’objet qui sont une forme spécialisée de mappages DITA utilisés pour définir des sujets taxonomiques et des valeurs contrôlées. Désormais, AEM Guides vous permet également de définir la définition de l’objet dans un mappage et les définitions d’énumération dans un autre mappage. Vous pouvez ensuite ajouter la référence de carte et utiliser le schéma d’objet.
Les références de l’énumération objet sont résolues dans le même mappage ou le mappage référencé.

Pour plus d’informations sur la gestion des définitions hiérarchiques des définitions d’objet et des énumérations, voir la section **Modèle d’objet** description des fonctionnalités dans la section [Panneau gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .

## Prise en charge du format XLIFF en traduction

AEM Guides fournit également la prise en charge du format XLIFF (XML Localization Interchange File Format) en traduction. Vous pouvez également choisir de **Créer un projet de traduction XLIFF** pour convertir le contenu XML au format XLIFF.
Avec ce format, vous pouvez exporter le contenu au format XLIFF standard du secteur, puis fournir la même chose aux fournisseurs de traduction. Pour plus d’informations, voir [Création d’un projet de traduction](../user-guide/translate-documents-web-editor.md#create-translation-project).

![](assets/translation-project-types.png){width="350" align="left"}



## Panneau Favoris amélioré

AEM Guides vous aide à créer une collection ou une liste préférée de vos fichiers et dossiers et à les utiliser facilement. Maintenant **Options** est également disponible dans la **Favoris** du panneau. Vous pouvez renommer la collection sélectionnée ou la supprimer de l’onglet **Options** . Vous pouvez sélectionner la variable **Actualiser** pour obtenir une nouvelle liste de fichiers ou de dossiers du référentiel. Vous pouvez également afficher le contenu du dossier dans l’interface utilisateur d’Assets.

![](assets/favorites-options.png){width="650" align="left"}

>[!NOTE]
>
> Vous pouvez également actualiser la liste à l’aide du **Actualiser** en haut.

Pour plus d’informations sur la variable **Options** d’une collection Favoris, voir **Favoris** description des fonctionnalités dans la section [Panneau gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .

## Passer au thème du système

Vous pouvez également désormais utiliser le thème de l’appareil. En utilisant la variable **Préférences utilisateur**, vous pouvez configurer AEM Guides pour basculer automatiquement entre les thèmes clairs et sombres en fonction du thème de votre appareil.

![](assets/device-theme-user-preferences.png){width="550" align="left"}

Pour plus d’informations, voir **Préférences utilisateur** description des fonctionnalités dans la section [Barre d’outils principale](../user-guide/web-editor-features.md#id2051EA0G05Z) .
