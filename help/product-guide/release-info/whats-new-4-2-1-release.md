---
title: Notes de mise à jour | Nouveautés de la version 4.2.1 des guides Adobe Experience Manager
description: Découvrez les nouvelles fonctionnalités et les fonctionnalités améliorées des versions 4.2.1 des Guides Adobe Experience Manager
exl-id: 441aa7ec-d88c-42cb-83f0-d0f6e58bfa41
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 0%

---

# Nouveautés de la version 4.2.1 des guides Adobe Experience Manager (mai 2023)

Cet article couvre les nouvelles fonctionnalités et les fonctionnalités améliorées de la version 4.2.1 des Guides Adobe Experience Manager (ultérieurement appelées *Guides d’AEM*).

Pour plus d’informations sur les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans cette version, voir la section [Notes de mise à jour](release-notes-4-2-1.md) article.

## Accédez à la page d’accueil d’AEM à partir de l’éditeur Web.

Vous pouvez désormais facilement accéder à la page de navigation d’AEM à partir de l’éditeur Web.

![](assets/web-editor-launch-page.png){width="800" align="left"}

* Cliquez sur le bouton **Guides** icône (![](assets/aem-guides-icon.png) ), pour revenir à la page de navigation AEM.


Pour plus d’informations, voir [Page de navigation AEM](../user-guide/web-editor-launch-editor.md#id2056BG00RZJ).

## Prise en charge avancée des métadonnées dans la publication dans PDF

AEM Guides fournit désormais une prise en charge avancée des métadonnées mappées aux métadonnées dans la sortie de votre PDF. Les options de métadonnées incluent des informations sur le document et son contenu, telles que le nom de l’auteur, le titre du document, les mots-clés, les informations de copyright et d’autres champs de données.

<img src="assets/pdf-metadata.png" alt=" métadonnées pdf natives">

Vous pouvez importer un fichier XMP et AEM Guides peuvent sélectionner les informations du fichier. Vous avez également la possibilité de fournir les noms et valeurs des métadonnées à l’aide de la liste déroulante. Vous pouvez également ajouter des métadonnées personnalisées en saisissant directement dans le champ du nom.

Pour plus d’informations, voir **Métadonnées** description des fonctionnalités dans [Création d’un paramètre prédéfini de sortie PDF](../web-editor/native-pdf-web-editor.md).

### Panneau Aperçu amélioré

AEM Guides fournit un panneau d’affichage en ligne amélioré dans lequel vous obtenez une vue hiérarchique des éléments utilisés dans le document.

<img src="assets/select-element-content-outline-view_cs.png" alt=" métadonnées pdf natives">

La vue Plan comprend les améliorations suivantes :

* La liste déroulante Options d’affichage s’affiche en haut du panneau Vue synchrone. Si un élément comporte un identifiant, un attribut et du texte, vous pouvez les sélectionner dans la liste déroulante pour les afficher avec l’élément . Les attributs qui peuvent s’afficher dans le panneau Vue synchrone sont déterminés par les paramètres Attributs d’affichage configurés par votre administrateur dans la variable **Paramètres de l’éditeur**.

* La fonction de recherche vous permet de rechercher un élément par son nom, son identifiant, son texte ou sa valeur d’attribut.

Pour plus d’informations, reportez-vous à la description de la fonction de la vue Plan dans la section [Panneau gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .

## Génération du rapport Multimédia à partir de l’éditeur web

AEM Guides fournit la fonctionnalité de génération de rapports pour vos documents techniques.  Vous pouvez utiliser cette fonction pour afficher la liste des rubriques et gérer les métadonnées de vos documents. Vous pouvez également voir le fichier multimédia utilisé dans toutes les références pour la carte actuelle à partir de la **Rapports** dans l’éditeur Web.

Vous pouvez générer le rapport multimédia qui contient des informations détaillées sur le multimédia utilisé dans vos références dans la carte actuelle. Vous avez la possibilité de filtrer et de trier les fichiers multimédia répertoriés dans le rapport.
Vous pouvez également générer le fichier CSV pour télécharger l’instantané actuel du fichier multimédia utilisé dans la carte DITA.

<img src="assets/web-editor-reports-multimedia.png" alt="rapport multimédia" width="600">

Pour plus d’informations, reportez-vous à la description de la fonctionnalité Générer un rapport multimédia dans la section [Rapport de mappage DITA à partir de l’éditeur web](../user-guide/reports-web-editor.md) .

## PDF natif | Barre de modification pour indiquer les rubriques modifiées dans la table des matières

AEM Guides vous permet désormais d’identifier rapidement les rubriques modifiées dans la table des matières de la sortie du PDF.  Une barre de modification s’affiche à gauche des rubriques modifiées dans la table des matières. Vous pouvez cliquer sur la rubrique dans la table des matières et afficher les modifications détaillées.

<img src="assets/change-marker-toc.png" alt="Changement de marqueur dans la table des matières " width="500">

Pour plus d’informations, voir [Utilisation des styles de barres de modification personnalisés](../native-pdf/change-bar-style.md).



## PDF natif | Style du marqueur de page dans le composant de note de bas de page

Vous pouvez maintenant mettre en forme le marqueur de la page dans les notes de pied. Par exemple, vous pouvez ajouter des crochets ou modifier leur couleur. Ces styles permettent aux utilisateurs d’identifier facilement les marqueurs de page dans le document.

Pour plus d’informations, voir [Utilisation de styles personnalisés dans les notes de bas de page](../native-pdf/footnote-number-style.md).

## Ouverture et lecture de fichiers vidéo ou audio dans l’éditeur web

AEM Guides fournit désormais la fonctionnalité permettant d’ouvrir et de lire les fichiers audio ou vidéo dans l’éditeur web. Vous pouvez modifier le volume ou l’affichage de la vidéo. Dans le menu contextuel, vous avez également la possibilité de **Télécharger**, modifier **Lecture de la vitesse** ou afficher **Image dans l’image**.

<img src="assets/video-web-editor.png" alt="vidéo de lecture" width="600">

Pour plus d’informations, voir la description de la fonctionnalité Repository View dans la section [Panneau gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .
