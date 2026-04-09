---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides, version 2026.04.0
description: Découvrez les correctifs de bugs de la version 2026.04.0 d’Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: ce2c9da0d9beb05a15f7cefcf9483e0c93abbf37
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 3%

---

# Correction de problèmes dans la version 2026.04.0

Cet article couvre les bugs corrigés dans différentes zones de la version 2026.04.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2026.04.0](whats-new-2026-04-0.md).

Découvrez les [instructions de mise à niveau pour la version 2026.04.0](upgrade-instructions-2026-04-0.md).

## Création

- Lors de la modification d’un fichier Schematron (`*.sch`) et de l’utilisation de la fonction Rechercher et remplacer , le panneau Rechercher et remplacer s’affiche partiellement hors écran en bas, empêchant l’accès à ses champs et contrôles de saisie. (GUIDES-38412)

## Publication

- Lorsque la même rubrique est réutilisée sur plusieurs mappages avec différents paramètres prédéfinis conditionnels, la publication du dernier mappage sur Salesforce remplace le contenu de la rubrique, ce qui entraîne l’affichage de données incorrectes aux utilisateurs de mappages précédemment publiés. (GUIDES-37806)
- Lors de la publication d’un PDF natif pour un mappage qui inclut un traitement conditionnel ou certains mappages imbriqués, le `dc:title` défini dans le mappage ne s’affiche pas sur la couverture du PDF, ce qui entraîne l’absence du titre de la couverture. (GUIDES-37733)
- La génération de la sortie du site AEM (à l’aide du mappage des composants composites) pour un mappage échoue et entraîne une erreur lorsque la variable `map_title` est présente dans le chemin de sortie. (GUIDES-36968)
- Lorsqu’un chemin de sortie avec une barre oblique est spécifié dans le paramètre prédéfini de sortie Native PDF, l’interface utilisateur ajoute automatiquement une barre oblique supplémentaire, ce qui entraîne un double chemin d’accès qui entraîne l’échec du chargement PDF dans certains scénarios. (GUIDES-34932)
- La publication de pages AEM Sites générées à partir de contenu DITA par le biais de Publication rapide ou de Gérer la publication publie involontairement les ressources DITA associées. (GUIDES-27967)
- Lors de la publication d’un mappage dans AEM Sites (à l’aide du mappage des composants hérités), les références croisées (`xrefs`) avec les `scope = peer` qui ciblent des sous-éléments d’une rubrique (comme des paragraphes) dans un autre mappage ne se résolvent pas sur l’ID d’élément spécifique et se résolvent uniquement sur la rubrique parente, ce qui entraîne le chargement de la page au début de la rubrique plutôt que le défilement vers la section prévue. (GUIDES-21802)


## Traduction

- Lorsqu’une image initialement gérée en tant que ressource spécifique à la langue avec une version spécifique (par exemple, sous `/en/`) est déplacée vers un dossier global avec une version mise à jour et que l’exportation de la ligne de base est effectuée, la nouvelle ligne de base continue à référencer des versions obsolètes spécifiques à la langue de cette image, ce qui entraîne l’échec de l’exportation de la ligne de base. (GUIDES-39394)
- Lors du traitement de projets de traduction créés en dehors de Experience Manager Guides, plusieurs messages de journal d’erreurs sont générés indiquant que *`fmTarget`propriété est introuvable*. (GUIDES-37804)

## Ligne de base

- Lors de la création d’une ligne de base dynamique, l’éditeur ne répond parfois plus en raison de plusieurs requêtes d’API simultanées, ce qui interrompt toutes les autres opérations. (GUIDES-39054)

## Révision

- Lors de l’affectation d’un utilisateur à une tâche de révision, la liste déroulante répertorie tous les utilisateurs au lieu de seulement ceux associés aux projets sélectionnés, ce qui entraîne des options utilisateur non valides. (GUIDES-37781)

## Rapports

- L’ouverture d’un rapport pour une carte entraîne un retard dans le chargement du panneau Filtres (GUIDES-39385)

## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 2026.04.0 :

- Un écran vierge est chargé lors de la création d’un paramètre prédéfini de la base de connaissances ServiceNow en double. (GUIDES-42732)
- L’API de récupération de l’état du document renvoie une réponse nulle pour certains fichiers, ce qui entraîne l’affichage d’états de document incorrects dans l’interface utilisateur. (GUIDES-42561)
- Les personnalisations de l’interface utilisateur basées sur les noms d’onglets dans le tableau de bord des cartes ne sont pas appliquées. (GUIDES-42285)
- Lorsqu’un fichier est ouvert à la fois dans l’éditeur et dans le panneau de recherche, sa suppression dans le panneau de l’explorateur supprime le fichier et actualise la liste de l’explorateur, mais l’actualisation de la page continue d’afficher le fichier dans le panneau de recherche. (GUIDES-41935)
- Lors de la mise à jour d’une tâche de révision active, si une rubrique qui fait déjà partie de la révision est supprimée puis ajoutée à nouveau sans cliquer sur **Mettre à jour**, les informations du ou des réviseurs dans l’onglet Réviseurs sont perdues.   (GUIDES-38774)
- La sélection d’un sujet en mode Aperçu ne le met pas en surbrillance dans la vue Carte si le sujet se trouve à l’intérieur des balises de la bookmap (frontend, chapter, part ou backMATTER) ou s’il fait partie du contenu cyclique. (GUIDES-42416)
- Dans l’interface utilisateur d’Assets, le bouton **Déplacer** n’est pas activé à la première tentative lorsque plus de 2 fichiers ou dossiers sont sélectionnés. (GUIDES-42721) <br> **Solution** : après avoir sélectionné plus de deux fichiers ou dossiers, patientez quelques secondes avant de sélectionner le dossier de destination.
- Lorsque vous accédez à **Préférences utilisateur** à partir de l’éditeur et mettez à jour la carte racine lorsque le mode Aperçu est ouvert dans l’éditeur, l’aperçu de la carte se charge sous la forme d’un écran vide lorsque vous revenez à l’éditeur. (GUIDES-42412) <br> **Solution** : Actualiser l’aperçu à l’aide de l’icône **Actualiser** disponible en mode Aperçu résout le problème.
- Le fait de renommer un modèle existant ne met pas à jour le nom dans le panneau **Modèles de sortie** tant que la page n’est pas actualisée manuellement. (GUIDES-42528)<br> **Solution** : actualisez le navigateur pour afficher le nom du modèle mis à jour dans le panneau Modèles Output.
