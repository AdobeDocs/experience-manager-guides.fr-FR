---
title: Notes de mise à jour | Adobe Experience Manager Guides as a Cloud Service, version d’avril 2023
description: Version d’avril 2023 des Guides Adobe Experience Manager as a Cloud Service
exl-id: 269e3a13-584d-4cff-a18a-d4fa89646a5a
feature: Release Notes
role: Leader
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# Nouveautés de la version d’avril 2023 des Guides Adobe Experience Manager as a Cloud Service

Cet article couvre les nouvelles fonctionnalités et les fonctionnalités améliorées de la version d’avril 2023 des Guides Adobe Experience Manager (ultérieurement appelée *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans cette version, voir la section [Notes de mise à jour](release-notes-2023.4.0.md) article.

## Prise en charge avancée des métadonnées dans la publication dans PDF

AEM Guides fournit désormais une prise en charge avancée des métadonnées mappées aux métadonnées dans la sortie de votre PDF. Les options de métadonnées incluent des informations sur le document et son contenu, telles que le nom de l’auteur, le titre du document, les mots-clés, les informations de copyright et d’autres champs de données.

<img src="assets/pdf-metadata.png" alt=" métadonnées pdf natives">

Vous pouvez importer un fichier XMP et AEM Guides peuvent sélectionner les informations du fichier. Vous avez également la possibilité de fournir les noms et valeurs des métadonnées à l’aide de la liste déroulante. Vous pouvez également ajouter des métadonnées personnalisées en saisissant directement dans le champ du nom.


## Panneau Aperçu amélioré

AEM Guides fournit un panneau d’affichage en ligne amélioré dans lequel vous obtenez une vue hiérarchique des éléments utilisés dans le document.

<img src="assets/select-element-content-outline-view_cs.png" alt=" métadonnées pdf natives">

La vue Plan comprend les améliorations suivantes :

* La liste déroulante Options d’affichage s’affiche en haut du panneau Vue synchrone. Si un élément comporte un identifiant, un attribut et du texte, vous pouvez les sélectionner dans la liste déroulante pour les afficher avec l’élément . Les attributs qui peuvent s’afficher dans le panneau Vue synchrone sont déterminés par les paramètres Attributs d’affichage configurés par votre administrateur dans la variable **Paramètres de l’éditeur**.

* La fonction de recherche vous permet de rechercher un élément par son nom, son identifiant, son texte ou sa valeur d’attribut.


## Publication basée sur un microservice pour AEM Guides as a Cloud Service

AEM Guides as a Cloud Service permet d’exécuter des charges de travail de publication volumineuses simultanément avec la publication basée sur un microservice et d’exploiter la plate-forme sans serveur Adobe I/O Runtime de pointe.

Dans la version d’avril, vous pouvez désormais exécuter plusieurs demandes de publication simultanément et générer des sorties de PDF en masse très efficacement à l’aide de la publication de PDF natif basée sur un microservice.
Pour plus d’informations, voir [Configuration de la nouvelle publication basée sur un microservice pour AEM Guides as a Cloud Service](../knowledge-base/publishing/configure-microservices.md).
