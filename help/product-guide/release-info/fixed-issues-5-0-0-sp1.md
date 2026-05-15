---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides 5.0.0 Service Pack 1
description: Découvrez les correctifs de bugs dans la version 5.0.0 Service Pack 1 d’Adobe Experience Manager Guides
role: Leader
exl-id: 1d0bc3d0-aedf-4f67-b6f7-2208facdee96
TQID: https://experienceleague.adobe.com/0qxye7ZUWt1iixHthjjTNJgtlOQX-C30jGi5zQlRJfA
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 288
ht-degree: 2%

---

# Correction de problèmes dans la version 5.0.0 Service Pack 1 (juin 2025)


Cet article couvre les bugs corrigés dans différentes zones de la version 5.0.0 Service Pack 1 d’Adobe Experience Manager Guides.

Découvrez les [instructions de mise à niveau pour la version 5.0.0 du pack de services 1](upgrade-instructions-5-0-0-sp1.md).

## Création

- Lorsque du contenu est collé dans une `codeblock` ou lorsque des espaces sont ajoutés dans la `codeblock` et que la vue est changée, l’espacement est perdu. (GUIDES-29347)
- Lorsqu&#39;un commentaire XML est ajouté dans un élément de la vue ****, les espaces de début et de fin autour du commentaire sont perdus lors du changement de vue. (GUIDES- 28188)

## Gestion des ressources

- Lors de l’ouverture d’une rubrique en mode **Auteur** après l’actualisation du navigateur, les balises précédemment appliquées dans le panneau **Propriétés du fichier** ne sont pas conservées et l’ajout de nouvelles balises remplace les balises existantes, en particulier lorsqu’un grand nombre de balises sont disponibles pour la sélection. (GUIDES-29078)
- Lors de la génération d&#39;un rapport de métadonnées pour un plan DITA contenant un grand nombre de ressources, le bouton **Gérer** ne répond plus ou présente une réponse retardée. (GUIDES-29778)

## Traduction

- Lors de l’envoi de ressources pour traduction à partir de Experience Manager Guides, les ressources ne sont pas ajoutées dans la tâche de traduction, ce qui empêche l’affichage du bouton **Démarrer** et vous empêche de lancer la tâche de traduction. (GUIDES-28237)

## Publication

- Lors de la modification des paramètres d&#39;un paramètre prédéfini de sortie dans le profil de dossier et de la sélection de **Appliquer les modifications de paramètre prédéfini**, les modifications ne sont pas propagées aux paramètres prédéfinis de sortie présents dans le plan DITA. (GUIDES-26694)

## Révision

- Les tentatives de création de tâches de révision par le biais du workflow AEM échouent systématiquement, car le nœud de révision n’est pas créé. (GUIDES-28214)
