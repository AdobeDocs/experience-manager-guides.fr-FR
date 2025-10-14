---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides, version 2025.10.0
description: Découvrez les correctifs de bugs de la version 2025.10.0 d’Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: ff3cf777bd348edded29d780031df59bbb03035d
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 3%

---

# Correction de problèmes dans la version 2025.10.0

Cet article couvre les bugs corrigés dans différentes zones de la version 2025.10.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2025.10.0](whats-new-2025-10-0.md).

Découvrez les [instructions de mise à niveau pour la version 2025.10.0](upgrade-instructions-2025-10-0.md).

## Création

- Lorsque plusieurs plans ou rubriques DITA sont ouverts et que l&#39;une des rubriques est fermée, le bouton **>>** qui affiche tous les onglets ouverts est chevauché par les onglets ouverts restants dans la barre d&#39;onglets. (GUIDES-31421)
- Lorsque le **workflow d’approbation** est activé, le bouton **Démarrer une nouvelle version** n’est pas visible sur la barre d’outils de l’éditeur si le panneau de gauche et le panneau des propriétés de contenu sont ouverts. (GUIDES-29093)
- Lorsque les noms des fragments de code dépassent la largeur du panneau, ils sont renvoyés à la ligne suivante de manière incorrecte, ce qui entraîne un chevauchement avec les fragments de code adjacents et un impact sur la lisibilité. (GUIDES-22685)
- Lorsque vous ajoutez la même référence plusieurs fois à un plan DITA, la vue **Map** affiche le titre uniquement pour la dernière occurrence, tandis que les précédentes affichent l&#39;UUID de la référence. (GUIDES-9699)
- Les fichiers DITAVAL restent modifiables, même lorsqu’ils sont verrouillés par un autre utilisateur ou lorsque le serveur a activé **Désactiver l’édition sans verrouiller le fichier** et que le fichier est ouvert en mode lecture seule. (GUIDES-27754)
- Les journaux des nœuds manquants sont générés à partir de tâches de nettoyage interne qui ne sont pas requises et qui sont incorrectement marquées comme des erreurs, ce qui encombre les fichiers journaux. (GUIDES-31765)


## Publication

- Lors de la génération de PDF, les règles de filtrage d’un fichier DITAVAL sont ignorées si un nom de propriété contient un point. (GUIDES-33229)
- La publication Salesforce échoue avec une erreur d’application, lorsqu’une rubrique portant le même nom et la même URL existe déjà. (GUIDES- 32390)
- La publication Salesforce affiche un statut réussi dans l&#39;interface utilisateur même lorsqu&#39;un plan DITA contenant un élément `topichead` ne parvient pas à publier les rubriques qu&#39;il contient. (GUIDES-32143)
- Pour le paramètre prédéfini de sortie HTML5, la fonctionnalité de filtrage de recherche ne fonctionne pas dans AEM Assets pour le filtrage DITAVAL, car les fichiers correspondants ne s’affichent pas lorsque le filtre DITAVAL est sélectionné. (GUIDES-28231)
- Lors de la génération d&#39;un PDF natif pour un plan DITA avec plusieurs rubriques, si une rubrique contient un élément `fig` dans une `figgroup` avec un `title`, le titre du `figgroup` est incorrectement rendu en tant que titre de chapitre dans la table des matières. (GUIDES-23223)
- Lors de la duplication de modèles PDF à partir de l’interface utilisateur, l’UUID est également dupliqué, ce qui entraîne la suppression de fichiers de modèle et génère des sorties PDF incorrectes. (GUIDES-30456)
- Lors de la génération d&#39;un PDF natif pour un plan DITA, le titre de `example` élément est rendu `h1` niveau titre, ce qui entraîne une incohérence visuelle et une structure de table des matières incorrecte. (GUIDES-19958)

## Traduction

- Lors du zoom sur l’écran de l’interface utilisateur de traduction, le bouton **Envoyer pour traduction** se déplace sous les points de suspension et devient activé même si aucune ressource n’est sélectionnée. (GUIDES-33720)
- Lors de la sélection de fichiers avec le statut **Désynchronisé** dans l’interface utilisateur de traduction et lorsque la largeur d’écran est limitée en raison de l’ouverture des panneaux Gauche et Droite, le libellé **Envoyer pour traduction** est tronqué. (GUIDES-33692)

## Révision

- Lorsque le réviseur termine une tâche de révision ou que l&#39;initiateur met à jour la tâche de révision sans saisir de commentaires, l&#39;e-mail de notification envoyé affiche le commentaire précédent le plus récent. (GUIDES-33590)

## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 2025.10.0 :

- Lors de l&#39;ouverture d&#39;une URL avec une rubrique DITA précédemment ouverte ou de l&#39;actualisation d&#39;une rubrique DITA ouverte, la rubrique ne se trouve pas dans le référentiel, bien que le paramètre **Toujours localiser les fichiers dans le référentiel** soit activé dans les préférences utilisateur. (GUIDES-35565)<br>**Solution de contournement** : sélectionnez l’onglet de rubrique pour localiser le fichier dans le référentiel.

- Lors de la création d’un fichier en mode Auteur avec plusieurs fichiers déjà ouverts, l’actualisation du panneau de droite échoue et affiche des données incorrectes si le curseur est placé sur une balise d’élément dans un autre fichier. (GUIDES-35450)<br>**Solution de contournement** : basculez sur les onglets ou actualisez la page pour résoudre le problème.

- Lorsque vous passez à la vue Auteur à partir de la vue Source pour une rubrique nouvellement ouverte (qui est initialement ouverte en mode Source), le contenu de la rubrique devient vide. (GUIDES-35000)<br>**Solution de contournement** : actualisez la page ou rouvrez la rubrique pour résoudre le problème.

- Le bouton **Actualiser la navigation** s&#39;affiche pour les fichiers de rubrique DITA, alors qu&#39;il ne devrait être disponible que pour les plans DITA, les plans de livres et les schémas d&#39;objets. (GUIDES-35452)






