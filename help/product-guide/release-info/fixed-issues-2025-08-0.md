---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides, version 2025.08.0
description: Découvrez les correctifs de la version 2025.08.0 d’Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 5abe5c153d8cedc7b555d6ca82709557cc38d28f
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 3%

---

# Correction de problèmes dans la version 2025.08.0

Cet article couvre les bugs corrigés dans différentes zones de la version 2025.08.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2025.08.0](whats-new-2025-08-0.md).

Découvrez les [instructions de mise à niveau pour la version 2025.08.0](upgrade-instructions-2025-08-0.md).

## Création

- Les fichiers **CSS** et **Mise en page** dans les modèles PDF natifs présentent un comportement de verrouillage de fichier incohérent, ce qui permet d’apporter des modifications même lorsque les fichiers sont verrouillés. (GUIDES-26688)
- L’actualisation de la page après l’ajout de boutons personnalisés au panneau de gauche crée des onglets en double. (GUIDES-30899)
- Lorsque du contenu XML contenant des crochets angulaires (tel que &lt;/ ou />) est ajouté dans un élément `code block` dans une rubrique, l’élément de bloc de code apparaît vide dans la sortie finale. (GUIDES-31007)
- Les valeurs des variables globales `canCheckIn` et `canCheckOut` ne sont pas correctement définies lorsqu’un fichier est extrait et archivé à partir de la barre d’outils de l’éditeur.(GUIDES-29890)
- Lors de l&#39;ouverture d&#39;un plan DITA avec Unified Shell activé, l&#39;éditeur s&#39;actualise par intermittence.(GUIDES-26919)
- Lorsqu&#39;un plan DITA est sélectionné dans la vue Carte, le nombre de sélections est d&#39;abord affiché de manière incorrecte car les nœuds enfants du plan ne sont pas sélectionnés. Le nombre correct de sélections et l’inclusion de tous les nœuds enfants ne sont reflétés que lors de la sélection suivante. (GUIDES-25663)
- Les fichiers Markdown ne sont pas récupérés lors d’une recherche dans le panneau Référentiel à l’aide du filtre **Rubrique DITA**. En outre, les fonctions **Rechercher et remplacer** ne fonctionnent pas pour les fichiers Markdown et le contenu associé. (GUIDES-27133)
- Impossible de personnaliser la **liste déroulante du menu** de la barre d’outils de l’éditeur à l’aide du framework d’extension. Par conséquent, vous ne pouvez pas masquer ni afficher les boutons existants ni en ajouter de nouveaux dans la liste déroulante Menu . (GUIDES-28748)

## Gestion des ressources numériques

- La copie d’un dossier contenant un grand nombre de ressources à partir de l’interface utilisateur d’Assets entraîne un délai d’expiration de l’API. L’opération continue de s’exécuter sur le serveur principal et se termine au bout d’un certain temps, mais aucun message de réussite ou d’échec, ou de notification n’est affiché dans l’interface utilisateur. (GUIDES-30900)
- L’opération de copier-coller effectuée sur un dossier dans l’interface utilisateur d’Assets échoue en raison d’erreurs de post-traitement. (GUIDES-30840)
- L’opération de copier-coller échoue pour les dossiers contenant des ressources composites (ressources avec sous-ressources) dans l’interface utilisateur d’Assets. (28107)
- Les dossiers contenant un grand nombre de ressources ne se chargent pas correctement dans le référentiel. (GUIDES-32500)
- Les noms de nœud de dossier ne s’affichent pas correctement à la place des titres de dossier dans l’éditeur. (GUIDES-32402)
- Une erreur se produit lors du chargement de ressources dont les noms de fichier contiennent des caractères non pris en charge ou interdits . (GUIDES-28845)

## Publication

- Dans la sortie Native PDF, la liste des index (LOI) s’affiche dans un ordre non alphabétique et les termes d’index imbriqués ne sont pas correctement regroupés, ce qui rend l’index difficile à parcourir. (GUIDES-29090)
- La liste déroulante **Modèle de page de mappage** et **Modèle de page de rubrique** de la page du paramètre prédéfini de sortie de mappage des composants AEM Sites apparaît vide lorsque le chemin de destination contient une variable avec deux points. (GUIDES-28119)
- Lorsqu&#39;un plan DITA contient différents types de références de rubrique telles que Concept, Référence ou Tâche, et qu&#39;il est fusionné à l&#39;aide de l&#39;attribut `chunk=to-content` pour générer une sortie sur une seule page dans AEM Sites avec le mappage de composant, le contenu n&#39;est pas publié correctement en raison d&#39;erreurs de publication. (GUIDES-28118)

## Ligne de base

- La copie d&#39;un plan DITA à partir de l&#39;interface utilisateur d&#39;Assets copie également sa ligne de base associée dans le nouveau plan. (GUIDES-11227)

## Page d’accueil

- La page d’accueil devient vide lorsque l’un des fichiers répertoriés dans le widget **Fichiers récents** est basé sur un modèle dont le modèle source n’inclut pas de miniature. (GUIDES-31506)

## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 2025.08.0 :

- Lorsqu’un fichier ouvert dans l’éditeur est renommé ou déplacé, le passage d’un mode à l’autre (**Auteur**, **Aperçu**, etc.) met à jour le contenu de la zone d’édition, mais ne met pas visuellement en surbrillance le mode actif dans le coin inférieur droit. (GUIDES-32719) <br> **Solution** : actualisez la page pour résoudre le problème.
- Les images dont les noms de fichier contiennent des espaces ne s’affichent pas dans la sortie lorsqu’elles sont marquées à l’aide d’attributs conditionnels. (GUIDES-33858)
- Dans le panneau **Propriétés du contenu**, le champ Attributs se ferme automatiquement lorsque vous essayez de mettre à jour une référence à partir de la boîte de dialogue **Mettre à jour le lien**, empêchant ainsi la mise à jour du lien. (GUIDES-17767)



