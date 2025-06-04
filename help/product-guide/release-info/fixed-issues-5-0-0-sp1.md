---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides 5.0.0 Service Pack 1
description: Découvrez les correctifs de bugs dans la version 5.0.0 Service Pack 1 d’Adobe Experience Manager Guides
role: Leader
source-git-commit: 083a8e16b9d3cd6c3894d7eaa2fee489b1dc0bb8
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---


# Correction de problèmes dans la version 5.0.0 Service Pack 1 (juin 2025)


Cet article couvre les bugs corrigés dans différentes zones de la version 5.0.0 Service Pack 1 d’Adobe Experience Manager Guides.

Découvrez les [instructions de mise à niveau pour la version 5.0.0 du pack de services 1](upgrade-instructions-5-0-0-sp1.md).

## Création

- Lorsque du contenu est collé dans une `codeblock` ou lorsque des espaces sont ajoutés dans la `codeblock` et que la vue est changée, l’espacement est perdu. (GUIDES-29347)
- Lorsqu&#39;un commentaire XML est ajouté dans un élément de la vue **Source**, les espaces de début et de fin autour du commentaire sont perdus lors du changement de vue. (GUIDES- 28188)

## Gestion des ressources

- Lors de l’ouverture d’une rubrique en mode **Auteur** après l’actualisation du navigateur, les balises précédemment appliquées dans le panneau **Propriétés du fichier** ne sont pas conservées et l’ajout de nouvelles balises remplace les balises existantes, en particulier lorsqu’un grand nombre de balises sont disponibles pour la sélection. (GUIDES-29078)
- Lors de la génération d&#39;un rapport de métadonnées pour un plan DITA contenant un grand nombre de ressources, le bouton **Gérer** ne répond plus ou présente une réponse retardée. (GUIDES-29778)

## Traduction

- Lors de l’envoi de ressources pour traduction à partir de Experience Manager Guides, les ressources ne sont pas ajoutées dans la tâche de traduction, ce qui empêche l’affichage du bouton **Démarrer** et vous empêche de lancer la tâche de traduction. (GUIDES-28237)

## Publication

- Lors de la modification des paramètres d&#39;un paramètre prédéfini de sortie dans le profil de dossier et de la sélection de **Appliquer les modifications de paramètre prédéfini**, les modifications ne sont pas propagées aux paramètres prédéfinis de sortie présents dans le plan DITA. (GUIDES-26694)

## Révision

- Les tentatives de création de tâches de révision par le biais du workflow AEM échouent systématiquement, car le nœud de révision n’est pas créé. (GUIDES-28214)
