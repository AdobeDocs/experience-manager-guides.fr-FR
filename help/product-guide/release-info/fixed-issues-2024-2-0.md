---
title: Notes de mise à jour | Correction de problèmes dans les guides Adobe Experience Manager, version 2024.2.0
description: Découvrez les correctifs de bogues de la version 2024.2.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 3da78dd90bd219809d0a47bcdc2775b2c5ba29e1
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 0%

---

# Correction de problèmes dans la version 2024.2.0

Cet article couvre les bogues corrigés dans différentes zones de la version 2024.2.0 de Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version 2024.2.0](whats-new-2024-2-0.md).

En savoir plus [instructions de mise à niveau pour la version 2024.2.0](upgrade-instructions-2024-2-0.md).



## Création

- La vérification orthographique dans l’éditeur n’autorise pas la sélection de suggestions. 15045
- Le bouton de navigation globale ne fonctionne pas et le tableau de bord ne se charge pas. (14968)
- Dans l’éditeur web, la fonction de mappage de téléchargement ne parvient pas à déclencher une notification contextuelle lorsqu’elle est prête à être téléchargée. 14626
- Dans l’éditeur web, la fonction de mappage de téléchargement ne parvient pas à télécharger un mappage avec la ligne de base. 14622
- Erreur DTD non valide dans la version d’octobre 2023 des Guides de Experience Manager as a Cloud Service. (14482)
- Le fait de faire glisser une rubrique de glossaire du référentiel vers un mappage de glossaire crée `topicref`. 10767
- L’écran d’aperçu des fragments de code est figé. (14840)
- Étiquettes des `labels.json` s’affichent dans un ordre aléatoire dans l’éditeur Web. 10508

## Publication

- Dans la publication avec des PDF natifs, les attributs personnalisés dans les paramètres prédéfinis de condition ne fonctionnent pas pour la publication avec des PDF natifs. (14943)
- Dans la publication avec les PDF natifs, les références clés ne sont pas résolues pour la version de décembre 2023 des Guides Adobe Experience Manager. 15085
- La publication d’AEM Sites échoue et entraîne des erreurs de portée pour les fichiers comportant `xref` au fichier DITA commençant par &quot;HTTP&quot;. 15154
- Impossible d’ajouter un modèle personnalisé à partir du **Sorties** dans l’éditeur. (14846)
- **AEM site** ne fonctionne pas en raison d’un chemin de modèle vide. (14804)
- La régénération AEM site échoue pour les mappages DITA avec des rubriques contenant des équations MathML. (14790)
- Dans la publication de PDF natifs, la génération de PDF génère des erreurs lors de l’obtention des dépendances pour `Node.js` publication. (14445)
- AEM paramètre prédéfini n’autorise pas la sélection d’un modèle en dehors de la fonction `/content` hiérarchie dans l’éditeur web. (14260)
- Dans la sortie AEM Sites, le style ou les sauts de ligne ont été perdus pour le `<lines>` ayant des sous-éléments. 12542
- Les métadonnées personnalisées ne sont pas disponibles dans la sortie finale. (12116)
- Dans la publication avec un PDF natif, les propriétés de métadonnées de mappage DITA ne peuvent pas être utilisées pour renseigner les métadonnées pour la sortie du fichier de PDF. 15159)



## Gestion

- **Filtre de ligne de base** Les fichiers ne fonctionnent pas avec le nom de fichier dans l’éditeur web. (13486)
- La désactivation de l’indexation du mappage DITA parent pour obtenir de meilleures performances peut avoir un impact sur les fonctionnalités de certaines fonctionnalités.(12213)


## Révision

- Le menu contextuel du clic droit ne fonctionne pas pour **Accepter** ou **Rejeter** effectuer le suivi des modifications. (14607)
- Basculer pour fermer les rubriques DITA dans l’écran de révision ne fonctionne pas dans la version de décembre 2023 des Guides Adobe Experience Manager. (14537)
- La personnalisation des modèles de courrier électronique pour le processus de révision ne fonctionne pas avec la superposition. (13954)

## Problème connu

Adobe a identifié le problème connu suivant pour la version 2024.2.0 :

- La version 1.0 ne s’affiche pas dans l’interface utilisateur pour le fichier DITA dupliqué.
- La propagation des métadonnées de ressources ne fonctionne pas pour la version 2024.2.0 avec microservice activé pour aucun paramètre prédéfini.

