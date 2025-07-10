---
title: Notes de mise à jour | Correction de problèmes dans la version 2025.07.0 d’Adobe Experience Manager Guides
description: Découvrez les correctifs de la version 2025.07.0 d’Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: bf8b295444a1e21fc19bfbc04efaa20fe78f71bb
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 4%

---

# Correction de problèmes dans la version 2025.07.0

Cet article couvre les bugs corrigés dans différentes zones de la version 2025.07.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2025.07.0](whats-new-2025-07-0.md).

Découvrez les [instructions de mise à niveau pour la version 2025.07.0](upgrade-instructions-2025-07-0.md).

## Création

- Lorsqu’un commentaire XML est ajouté à l’intérieur d’un élément dans la vue Source, les espaces de début et de fin autour du commentaire sont perdus lors du changement de vue. (GUIDES-29781)
- Les options multimédias ne fonctionnent pas lorsqu’elles sont présentes dans l’icône représentant des points de suspension (menu **Plus**) de la barre d’outils. (GUIDES-29583)
- Lors de la création d’une rubrique dans l’interface utilisateur ou l’éditeur d’Assets, la rubrique ne s’ouvre pas automatiquement dans l’éditeur si le paramètre `xmleditor.uniquefilenames` est défini sur true dans `XMLEditorConfig`. (GUIDES-28171)
- Les espaces ajoutés dans une équation MathML dans la vue Source ne sont pas conservés lors du changement de vue de l’éditeur. (GUIDES-26111)

## Gestion des ressources numériques

- Lors de l’ouverture d’une rubrique dans la vue Auteur après l’actualisation du navigateur, les balises précédemment appliquées dans le panneau Propriétés du fichier ne sont pas conservées et l’ajout de nouvelles balises remplace les balises existantes, en particulier lorsqu’un grand nombre de balises sont disponibles pour la sélection. (GUIDES-29078)
- Lors de la génération d&#39;un rapport de métadonnées pour un plan DITA contenant un grand nombre de ressources, le bouton **Gérer** ne répond plus ou affiche une réponse retardée. (GUIDES-28443)

## Révision

- Les tentatives de création de tâches de révision par le biais du workflow AEM échouent systématiquement, car le nœud de révision n’est pas créé. (GUIDES-28214)

## Publication

- Une erreur de qualité du code se produit lors du déploiement du package de publication AEM Sites `guides-components.all-1.3.0.zip` via Cloud Manager. (GUIDES-28873)
- La publication d&#39;un plan DITA avec `chunk=to-content` attribut crée des nœuds JCR en double dans la nouvelle sortie AEM Sites, ce qui entraîne une structure de contenu redondante dans AEM Sites. (GUIDES-28104)
- Lors de la publication d&#39;un plan DITA à l&#39;aide de la nouvelle sortie AEM Sites, si une rubrique possède l&#39;attribut `chunk =to-content` et que la sortie est définie pour utiliser les titres de rubrique comme noms de page, le nom de page généré affiche incorrectement le mot **chunk** au lieu de conserver le nom de rubrique d&#39;origine. (GUIDES-28102)
- La propriété `cq:template` définie dans le modèle de rubrique AEM Guides pour la nouvelle publication AEM Sites affiche une valeur incorrecte, ce qui affecte la structure du modèle et le rendu du contenu. (GUIDES-27789)


## Plateforme

- Des problèmes de performances tels que des temps de chargement plus longs et des délais d’expiration intermittents sont observés lors de l’utilisation de collections volumineuses. (GUIDES-29065, GUIDES-28793)
- Vulnérabilités liées à l’utilisation de la bibliothèque Guava obsolète dans les composants AEM Guides chargés sur Experience Manager Guides.(GUIDES-27402)

## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 2025.07.0 :

- Lorsque vous travaillez avec des rubriques Markdown, un bouton **Référence de rubrique** s’affiche dans la barre d’outils de l’éditeur, mais il ne fonctionne pas. (GUIDES-31038)
- Lorsque des dossiers dont les noms sont en majuscules sont chargés à l’aide de l’application de bureau Adobe Experience Manager, la casse n’est pas conservée et les noms apparaissent en minuscules dans l’éditeur. (GUIDES-30909)
- Dans la boîte de dialogue **Fusionner**, la liste déroulante s’affiche incorrectement **Contenu principal** au lieu d’afficher les versions disponibles de la rubrique sélectionnée. (GUIDES-30820)
- Lors de l&#39;ouverture d&#39;un plan DITA avec Unified Shell activé, l&#39;éditeur s&#39;actualise par intermittence.(GUIDES-26919)