---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides, version 2026.01.0
description: Découvrez les correctifs de bugs de la version 2026.01.0 d’Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 8a9a82e79c757e403141e853aafbc64e1618c30a
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 3%

---

# Correction de problèmes dans la version 2026.01.0

Cet article couvre les bugs corrigés dans différentes zones de la version 2026.01.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2026.01.0](whats-new-2026-01-0.md).

Découvrez les [instructions de mise à niveau pour la version 2026.01.0](upgrade-instructions-2026-01-0.md).

## Création

- Lors de la mise à jour d’une équation de MathML intégrée à l’aide de l’option Modifier le MathML du menu contextuel, la valeur mise à jour n’est pas reflétée tant que la page n’est pas actualisée. (GUIDES-38198)
- Lorsqu’une rubrique contient de nombreux éléments réutilisables (ceux avec des ID) ajoutés dans le panneau Réutilisable , certains éléments peuvent ne pas être accessibles en raison de la hauteur fixe du conteneur. (GUIDES-37220)
- Lors de l&#39;insertion d&#39;une référence croisée à un fichier, les icônes des cartes et des rubriques sont identiques.(GUIDES-36662)
- Lors de la modification d’une carte, les symboles spéciaux de la `navtitle` ne s’affichent pas pour `topichead` dans la vue de création. (GUIDES-35435)
- Impossible d’ajouter plusieurs libellés de version à une rubrique dans la boîte de dialogue **Enregistrer en tant que nouvelle version**. (GUIDES-32716)

## Gestion des ressources numériques

- Impossible de supprimer les libellés de version du panneau Historique des versions dans l’interface utilisateur Assets. (GUIDES-38276)
- Lors du chargement de ressources dont le nom de fichier contient des caractères non valides, la ressource ne charge pas et affiche un message incorrect **Le fichier est verrouillé par un autre utilisateur** même si la ressource est déverrouillée. (GUIDES-32680)
- Dans la recherche Assets, les sous-ressources et les nœuds de métadonnées (tels que les images et les fichiers PDF) sont incorrectement inclus dans les résultats. En outre, pour un paramètre prédéfini de sortie lorsque des filtres DITAVAL sont appliqués, la recherche renvoie des fichiers DITAVAL générés en interne et créés à partir de paramètres prédéfinis de condition. (GUIDES-35418)

## Publication

- Lors de la génération de la sortie AEM Sites, les titres de carte contenant des mots-clés et des titres de rubrique avec `<ph>` élément ne sont pas inclus dans la sortie publiée. (GUIDES-36641)
- Lors de la publication à l’aide d’un paramètre prédéfini personnalisé avec du contenu contenant des liens vers des fichiers PDF sans portée définie comme externe, le processus ne se termine pas. (GUIDES-21708)
- Lors de l’activation en bloc, la création de package ajoute des filtres pour tous les chemins répertoriés sous la propriété `fileReference` d’une page, y compris les chemins externes et d’homologue. (GUIDES-24887)
- Dans la sortie PDF native, l’élément `abbreviated-form` affiche le `glossterm` au lieu du `glossSurfaceForm` ou du `glossAcronym` désigné. (GUIDES-26393)
- Pour la sortie Native PDF, l’élément `<alt>` pour les images est ignoré, ce qui empêche l’application de texte secondaire pour des raisons d’accessibilité. (GUIDES-29087)
- Lors du téléchargement de fichiers temporaires pour un mappage avec une ligne de base lors de la publication d’un paramètre prédéfini, le fichier `metadata.xml` référence incorrectement le `versionPath` plutôt que le `dampath`.(GUIDES-29815)
- Lors de la création ou de la modification d’une rubrique qui inclut une citation, si le champ Auteur n’est pas ajouté à la boîte de dialogue de citation, le PDF n’est pas généré. (GUIDES-37934)
- Le fichier CSS (`rhdefault.css`) est incorrectement appliqué au modèle PDF bien qu’aucun fichier CSS ne soit référencé, ce qui entraîne l’absence de journaux d’erreurs de fichier CSS.(GUIDES-31752)

## Plateforme

- Lors de la tentative d’enregistrement d’une rubrique ou d’un mappage, l’opération peut échouer par intermittence avec une erreur **Échec de l’enregistrement du fichier**, en particulier lors de tâches de traitement intensif des ressources ou de workflows de traduction exécutés en arrière-plan. (GUIDES-37837)
- L’utilisation de `scope="external"` pour une référence au contenu de gestion des ressources numériques dans une rubrique ou un mappage entraîne la substitution du chemin relatif de la ressource par un GUID. (GUIDES-38783)

## Rapports

- Le rapport Liste interrompue inclut incorrectement des liens externes, des `keyrefs` valides et des mots-clés qui sont correctement résolus dans la portée du mappage actuel. (GUIDES-27774)

## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 2026.01.0 :

- Lorsqu’une rubrique de révision en cours est supprimée d’une tâche de révision en cours, son état de document reste **En révision**, même si la rubrique ne fait plus partie d’une tâche de révision. (GUIDES-38709)<br>**Solution de contournement** : remplacez le statut du document de la rubrique **En cours de révision** par le statut approprié à partir de la page Propriétés ou du panneau Propriétés du fichier.
- Lors de l’exécution d’une recherche à l’aide de **Rechercher et remplacer**, si vous ouvrez un fichier à partir des résultats de la recherche, le fermez, puis tentez de le rouvrir en sélectionnant le résultat répertorié, la réouverture du fichier échoue. (GUIDES-39050)<br>**Solution** : ouvrez d’abord un autre fichier à partir des résultats de la recherche, puis rouvrez le fichier précédemment fermé dans la liste pour résoudre le problème.
- Lors de l’utilisation de Guides avec le serveur de base de données, pour le contenu qui inclut des auto-références, le rapport Liste de rubriques affiche des entrées non valides pour chaque auto-référence, ce qui entraîne un nombre de fichiers inexact. (GUIDES-39420)












