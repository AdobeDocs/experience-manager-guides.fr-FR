---
title: Notes de mise à jour | Correction de problèmes dans la version 2024.2.0 d’Adobe Experience Manager Guides
description: Découvrez les correctifs de bogues de la version 2024.2.0 d’Adobe Experience Manager Guides as a Cloud Service.
exl-id: fae1ff07-6232-4e9a-a89e-5e760e807b9d
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 4%

---

# Correction de problèmes dans la version 2024.2.0

Cet article couvre les bogues corrigés dans différentes zones de la version 2024.2.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2024.2.0](whats-new-2024-2-0.md).

Découvrez les [instructions de mise à niveau pour la version 2024.2.0](upgrade-instructions-2024-2-0.md).



## Création

- La vérification orthographique dans l’éditeur n’autorise pas la sélection de suggestions. 15045
- Le bouton de navigation globale ne fonctionne pas et le tableau de bord ne se charge pas. (14968)
- Dans l’éditeur web, la fonction de mappage de téléchargement ne parvient pas à déclencher une notification contextuelle lorsqu’elle est prête à être téléchargée. 14626
- Dans l’éditeur web, la fonction de mappage de téléchargement ne parvient pas à télécharger un mappage avec la ligne de base. 14622
- Erreur DTD non valide dans la version d’octobre 2023 de Experience Manager Guides as a Cloud Service. (14482)
- Le fait de faire glisser une rubrique de glossaire du référentiel vers une carte de glossaire crée `topicref`. 10767
- L’écran d’aperçu des fragments de code est figé. (14840)
- Les libellés du fichier `labels.json` apparaissent dans l’ordre aléatoire dans l’éditeur web. 10508

## Publication

- Dans la publication avec des PDF natifs, les attributs personnalisés dans les paramètres prédéfinis de condition ne fonctionnent pas pour la publication avec des PDF natifs. (14943)
- Dans la publication avec des PDF natifs, les références clés ne sont pas résolues pour la version de décembre 2023 d’Adobe Experience Manager Guides. 15085
- La publication d’AEM Sites échoue et entraîne des erreurs d’étendue pour les fichiers dont le `xref` commence par &quot;HTTP&quot; dans le fichier DITA. 15154
- Impossible d’ajouter un modèle personnalisé à partir de l’onglet **Sorties** de l’éditeur. (14846)
- Le paramètre prédéfini **AEM Site** ne fonctionne pas en raison d’un chemin de modèle vide. (14804)
- La régénération AEM site échoue pour les mappages DITA avec des rubriques contenant des équations MathML. (14790)
- Dans la publication de PDF natif, la génération de PDF renvoie des erreurs lors de l’obtention des dépendances pour la publication `Node.js`. (14445)
- AEM paramètre prédéfini n’autorise pas la sélection d’un modèle en dehors de la hiérarchie `/content` dans l’éditeur web. (14260)
- Dans la sortie AEM Sites, le style ou les sauts de ligne ont été perdus pour l’élément `<lines>` ayant des sous-éléments. 12542
- Les métadonnées personnalisées ne sont pas disponibles dans la sortie finale. (12116)
- Dans la publication avec un PDF natif, les propriétés de métadonnées de mappage DITA ne peuvent pas être utilisées pour renseigner les métadonnées pour la sortie du fichier de PDF. 15159)



## Gestion

- Les fichiers **Filtre de ligne de base** ne fonctionnent pas avec le nom de fichier dans l’éditeur web. (13486)
- La désactivation de l’indexation du mappage DITA parent pour obtenir de meilleures performances peut avoir un impact sur les fonctionnalités de certaines fonctionnalités.(12213)


## Révision

- Le menu contextuel de clic droit ne fonctionne pas pour les modifications de suivi **Accept** ou **Rejeter**. (14607)
- Basculer pour fermer les rubriques DITA dans l’écran de révision ne fonctionne pas dans la version de décembre 2023 d’Adobe Experience Manager Guides. (14537)
- La personnalisation des modèles de courrier électronique pour le processus de révision ne fonctionne pas avec la superposition. (13954)

## Problème connu

Adobe a identifié le problème connu suivant pour la version 2024.2.0 :

- La version 1.0 ne s’affiche pas dans l’interface utilisateur pour le fichier DITA dupliqué.
- La propagation des métadonnées de ressources ne fonctionne pas pour la version 2024.2.0 avec microservice activé pour aucun paramètre prédéfini.
