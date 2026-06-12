---
title: Notes de mise à jour | Nouveautés d’Adobe Experience Manager Guides, version de juin 2023
description: Découvrez les fonctionnalités nouvelles et améliorées de la version de juin 2023 d’Adobe Experience Manager Guides as a Cloud Service
exl-id: 625f9702-2b91-4622-9fec-282f47f1d7a6
feature: What's New
role: Leader
TQID: https://experienceleague.adobe.com/fPOg5RioczOxug8ACT9X9seCvXgjZ84mpPMEBUD4yJs
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 910
ht-degree: 0%

---

# Nouveautés de la version de juin 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cet article couvre les nouvelles fonctionnalités et les fonctionnalités améliorées de la version de juin 2023 d’Adobe Experience Manager Guides (plus tard appelée *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans cette version, voir [Notes de mise à jour](release-notes-2023-6-0.md).

## Rapport Liens rompus dans l’éditeur web

AEM Guides vous permet de vérifier l’exhaustivité globale de vos documents techniques et de générer des rapports à partir de l’éditeur web. Désormais, dans la version de juin 2023, AEM Guides vous offre la possibilité d’afficher et de corriger les liens rompus. Il s’agit d’un rapport utile qui vous aide à gérer vos liens rompus. Vous pouvez facilement afficher les liens rompus présents dans votre plan DITA et également les corriger.
![](assets/broken-link-report.png){width="800"}

Une fois que vous avez corrigé un lien, il ne s’affiche pas sous la liste des liens rompus.

Pour plus d’informations, voir [Affichage et correction des liens rompus](../user-guide/reports-web-editor.md#report-broken-links).

## Renommer et déplacer des fichiers dans la vue Référentiel

Vous pouvez désormais également renommer ou déplacer un fichier à partir du panneau du référentiel. Cette fonctionnalité est pratique et permet de gérer facilement vos fichiers à partir du panneau Référentiel. Vous pouvez sélectionner un fichier et le renommer ou le déplacer à l&#39;aide du menu **Options** du fichier sélectionné. AEM Guides affiche un message de réussite lorsque vous déplacez ou renommez un fichier.

![](assets/rename-move-assets.png){width="650"}

Pour plus d’informations sur le menu Options d’un fichier, reportez-vous à la description de la fonction **Vue du référentiel** dans la section [Panneau de gauche](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Améliorations du PDF natif

### Ajouter un filigrane à la sortie PDF pour les brouillons de documents

Vous pouvez maintenant ajouter un filigrane à la sortie PDF du document qui n’a pas encore été approuvé. Ce filigrane n’apparaît pas si vous générez le PDF du document au statut docstate « Approuvé ». Par exemple, vous pouvez ajouter un filigrane Brouillon à votre sortie PDF.

Pour plus d’informations, voir [Ajouter un filigrane à la sortie PDF pour les brouillons de documents](../native-pdf/use-javascript-content-style.md#watermark-draft-document).

### Prise en charge des variables de langue

AEM Guides prend en charge les variables de langue. Vous pouvez utiliser des variables de langue pour définir une version localisée des libellés d’usine tels que Note, Attention et Avertissement ou du texte statique dans la sortie PDF.
Vous pouvez ajouter les variables de langue ou la version localisée des libellés aux sections appropriées dans votre sortie PDF et dans les modèles de sortie.

#### Variables linguistiques dans la sortie PDF

Vous pouvez utiliser les variables de langue pour définir des libellés localisés pour des éléments tels que Note, Attention et Avertissement. Vous pouvez mettre à jour la valeur de ces variables dans une ou plusieurs langues, puis la valeur localisée est automatiquement sélectionnée dans la sortie PDF.
Par exemple, vous pouvez présenter l’étiquette Remarque dans votre sortie PDF des manières suivantes :

* Anglais : Remarque
* Français : Remarque
* Allemand : Hinweis

#### Variables linguistiques dans les modèles de sortie

Pour créer la sortie PDF dans différentes langues, vous deviez créer différents modèles PDF contenant du texte localisé pour chaque langue. Désormais, avec la fonctionnalité des variables de langue, il vous suffit de créer le modèle une seule fois. Ensuite, pour tout texte statique que vous devez localiser, vous pouvez créer des variables de langue correspondantes et les utiliser dans votre modèle.
Vous pouvez créer des variables de langue pour un texte plus long, comme une phrase entière ou même un paragraphe. Vous pouvez également appliquer des styles et utiliser les balises HTML pour formater ces variables de langue.

Pour plus d’informations, consultez [Prise en charge des variables de langue](../native-pdf/native-pdf-language-variables.md).

### Possibilité d’utiliser des métadonnées AEM dans des mises en page PDF

Les métadonnées sont la description ou la définition de votre contenu. Ces métadonnées sont stockées dans le contenu de votre plan DITA source.

Désormais, dans AEM Guides, vous pouvez également sélectionner les propriétés de métadonnées de vos ressources et les ajouter à la mise en page. AEM Guides sélectionne ensuite les propriétés de métadonnées de vos ressources et les publie dans votre sortie PDF.


![](assets/native-pdf-metadata-asset.png){width="550"}

>[!NOTE]
>
> AEM Guides prend également en charge les propriétés de métadonnées de vos plans DITA.

Pour plus d’informations, voir [Ajouter des champs et des métadonnées](../native-pdf/design-page-layout.md#add-fields-metadata).


## Améliorations du schéma

### Utilisez des instructions de rapport pour vérifier les règles dans Schematron.

AEM Guides prend également désormais en charge les instructions de rapport avec le Schematron. Une instruction de rapport génère un message lorsqu’une instruction de test est évaluée comme vraie. Par exemple, si vous souhaitez que la description courte comporte moins de 150 caractères ou qu’elle soit égale à 1, vous pouvez définir une instruction de rapport pour vérifier les rubriques dont la description courte comporte plus de 150 caractères.

Pour plus d’informations, consultez [Utilisation des instructions d’assertion et de rapport pour vérifier les règles](../user-guide/support-schematron-file.md#schematron-assert-report).

### Utilisation d’expressions Regex

Vous pouvez également utiliser des expressions Regex pour définir une règle avec la fonction matches() , puis effectuer la validation à l’aide du fichier Schematron.

Pour plus d’informations, voir [Utilisation d’expressions Regex](../user-guide/support-schematron-file.md#schematron-assert-report).


### Définition de modèles abstraits

AEM Guides prend également en charge les modèles abstraits dans Schematron. Vous pouvez définir des modèles abstraits génériques et les réutiliser. Les modèles abstraits peuvent simplifier votre schéma Schematron et vous aider également à gérer et à mettre à jour votre logique de validation.


Pour plus d’informations, voir [&#x200B; Définition de modèles abstraits &#x200B;](../user-guide/support-schematron-file.md#schematron-abstract-patterns).

## Naviguez de l’éditeur web vers la page d’accueil d’AEM.

Vous pouvez désormais facilement accéder à la page d’accueil d’AEM à partir de l’éditeur web.

![](assets/web-editor-launch-page.png){width="800"}

* Cliquez sur l’icône **Guides** (![](assets/aem-guides-icon.png) ) pour revenir à la page de navigation d’AEM.


Pour plus d’informations, consultez la page Navigation dans AEM [&#128279;](../user-guide/web-editor-launch-editor.md#id2056BG00RZJ).

## Gestion des définitions hiérarchiques des objets et des énumérations

AEM Guides est doté d&#39;une puissante fonctionnalité permettant de créer des cartes de schéma d&#39;objets, qui sont une forme spéciale de cartes DITA utilisées pour définir des objets taxonomiques et des valeurs contrôlées. Désormais, AEM Guides vous permet également de définir la définition de l’objet dans un mappage et les définitions de l’énumération dans un autre mappage. Vous pouvez ensuite ajouter la référence de mappage et utiliser le schéma d’objet.
Les références d’énumération d’objet sont résolues dans le même mappage ou le mappage référencé.

Pour plus d’informations sur la gestion des définitions hiérarchiques des objets et des énumérations, reportez-vous à la description des fonctionnalités du **Schéma d’objet** dans la section [Panneau de gauche](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Prise en charge du format XLIFF dans la traduction

AEM Guides prend également en charge le format XLIFF (XML Localization Interchange File Format) pour la traduction. Vous pouvez également choisir de **Créer un projet de traduction XLIFF** pour convertir le contenu XML au format XLIFF.
Ce format vous permet d’exporter le contenu au format XLIFF standard, puis de le fournir aux fournisseurs de services de traduction. Pour plus d’informations, consultez la section [Créer un projet de traduction](../user-guide/translate-documents-web-editor.md#create-translation-project).

![](assets/translation-project-types.png){width="350"}



## Panneau Favoris amélioré

AEM Guides vous aide à créer une collection ou une liste de favoris de vos fichiers et dossiers et à les utiliser facilement. Le menu **Options** est désormais également disponible dans le panneau **Favoris**. Vous pouvez renommer la collection sélectionnée ou la supprimer du menu **Options**. Vous pouvez sélectionner l’option **Actualiser** pour obtenir une nouvelle liste de fichiers ou de dossiers du référentiel. Vous pouvez également afficher le contenu du dossier dans l’interface utilisateur d’Assets.

![](assets/favorites-options.png){width="650"}

>[!NOTE]
>
> Vous pouvez également actualiser la liste à l’aide de l’icône **Actualiser** située en haut.

Pour plus d’informations sur le menu **Options** d’une collection Favoris, consultez la description de la fonctionnalité **Favoris** dans la section [Panneau de gauche](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Passer au thème du système

Vous pouvez également utiliser désormais le thème de l’appareil. À l’aide des **Préférences utilisateur**, vous pouvez configurer AEM Guides pour basculer automatiquement entre les thèmes clairs et sombres en fonction du thème de votre appareil.

![](assets/device-theme-user-preferences.png){width="550"}

Pour plus d’informations, reportez-vous à la description de la fonctionnalité **Préférences utilisateur** dans la section [Barre d’outils principale](../user-guide/web-editor-features.md#id2051EA0G05Z).
