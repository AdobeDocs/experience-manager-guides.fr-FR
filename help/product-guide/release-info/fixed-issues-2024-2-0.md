---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides version 2024.2.0
description: Découvrez les correctifs de bugs de la version 2024.2.0 d’Adobe Experience Manager Guides as a Cloud Service.
exl-id: fae1ff07-6232-4e9a-a89e-5e760e807b9d
TQID: https://experienceleague.adobe.com/z-L0sZ2HH720nI3LyDjiIqujxSBP-QLdPqvEInNNRnE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 504
ht-degree: 8%

---

# Correction de problèmes dans la version 2024.2.0

Cet article couvre les bugs corrigés dans différentes zones de la version 2024.2.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2024.2.0](whats-new-2024-2-0.md).

Découvrez les [instructions de mise à niveau pour la version 2024.2.0](upgrade-instructions-2024-2-0.md).



## Création

- La vérification orthographique dans l’éditeur ne permet pas de sélectionner des suggestions. (15045)
- Le bouton de navigation globale ne fonctionne pas et le chargement du tableau de bord échoue. (14968)
- Dans l’éditeur web, la fonctionnalité de carte de téléchargement ne déclenche pas de notification pop-up lorsqu’elle est prête à être téléchargée. (14626)
- Dans l’éditeur web, la fonction de téléchargement de carte ne parvient pas à télécharger une carte avec une ligne de base. (14622)
- Erreur DTD non valide dans la version d’octobre 2023 de Experience Manager Guides as a Cloud Service. (14482)
- Faire glisser une rubrique de glossaire du référentiel vers un glossaire map crée des `topicref`. (10767)
- L’écran d’aperçu des fragments de code est figé. (14840)
- Les libellés du fichier `labels.json` s’affichent dans un ordre aléatoire dans l’éditeur web. (10508)

## Publication

- Dans la publication Native PDF, les attributs personnalisés contenus dans les paramètres prédéfinis de condition ne fonctionnent pas pour la publication Native PDF. (14943)
- Dans la publication Native PDF, les références clés ne sont pas résolues pour la version de décembre 2023 d’Adobe Experience Manager Guides. (15085)
- La publication d&#39;AEM Sites échoue et entraîne des erreurs d&#39;étendue pour les fichiers ayant `xref` au fichier DITA commençant par « HTTP ». (15154)
- Impossible d’ajouter un modèle personnalisé à partir de l’onglet **Sorties** dans l’éditeur. (14846)
- Le préréglage **Site** ne fonctionne pas en raison d’un chemin d’accès au modèle vide. (14804)
- La régénération du site AEM échoue pour les plans DITA avec des rubriques contenant des équations MathML. (14790)
- Dans la publication Native PDF, la génération de PDF renvoie des erreurs d’obtention des dépendances pour la publication `Node.js`. (14445)
- Le paramètre prédéfini d’AEM ne permet pas la sélection d’un modèle en dehors de la hiérarchie de `/content` dans l’éditeur web. (14260)
- Dans la sortie AEM Sites, le style ou les sauts de ligne ont été perdus pour l’élément `<lines>` comportant des sous-éléments . (12542)
- Les métadonnées personnalisées ne sont pas disponibles dans la sortie finale. (12116)
- Dans la publication native PDF, les propriétés de métadonnées de plan DITA ne peuvent pas être utilisées pour renseigner les métadonnées pour la sortie de fichier PDF. (15159)



## Gestion

- Les fichiers **Filtre de ligne de base** ne fonctionnent pas avec le nom de fichier dans l’éditeur web. (13486)
- La désactivation de l&#39;indexation du plan DITA parent pour obtenir de meilleures performances peut avoir un impact sur les fonctionnalités de certaines fonctionnalités.(12213)


## Révision

- Le menu contextuel contextuel ne fonctionne pas pour les modifications de suivi **Accepter** ou **Refuser**. (14607)
- Le bouton (bascule) permettant de fermer les rubriques DITA dans l’écran de révision ne fonctionne pas dans la version de décembre 2023 d’Adobe Experience Manager Guides. (14537)
- La personnalisation des modèles d’e-mail pour le workflow de révision ne fonctionne pas avec la superposition. (13954)

## Problème Connu

Adobe a identifié le problème connu suivant pour la version 2024.2.0 :

- La version 1.0 n&#39;est pas affichée dans l&#39;interface utilisateur pour le fichier DITA dupliqué.
- La propagation des métadonnées des ressources ne fonctionne pas pour la version 2024.2.0 avec le microservice activé pour tout paramètre prédéfini.
