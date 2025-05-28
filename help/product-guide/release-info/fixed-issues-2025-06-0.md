---
title: Notes de mise à jour | Correction de problèmes dans la version 2025.06.0 d’Adobe Experience Manager Guides
description: Découvrez les correctifs de bugs de la version 2025.06.0 d’Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 78d8896982ff73e954de6d6daa9832faf30ed3b3
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 4%

---

# Correction de problèmes dans la version 2025.06.0

Cet article couvre les bugs corrigés dans différentes zones de la version 2025.06.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2025.06.0](whats-new-2025-06-0.md).

Découvrez les [instructions de mise à niveau pour la version 2025.06.0](upgrade-instructions-2025-06-0.md).

## Création

- Lors de l&#39;ouverture d&#39;un plan DITA avec Unified Shell activé, l&#39;éditeur s&#39;actualise par intermittence. (GUIDES-26919)
- Si vous ne fermez pas les connexions de session JCR lors de la mise à jour ou de la création de rubriques, des fuites de mémoire et des temps d’arrêt du service surviennent. (GUIDES-26282)
- Faire glisser les colonnes modifie leur largeur de pourcentage en valeurs en pixels, ce qui entraîne des distorsions ou des incohérences dans les tableaux.(GUIDES-23128)
- Lorsque du contenu est collé dans une `code block` ou lorsque des espaces sont ajoutés dans la `code block` et que la vue est changée, l’espacement est perdu. (GUIDES-27478)
- Lors de l’ajout d’un mappage au `bookmap`, il est stocké dans `fmditatopicrefs` au lieu de `fmditamaprefs`. (GUIDES-25480)
- La boîte de dialogue **Insérer une image** ne s’affiche pas correctement sur un écran haute résolution ou sur un écran agrandi, ce qui entraîne la disparition du titre de la figure et des champs de texte secondaire. (GUIDES-26459)


## Publication

- La publication native de PDF se poursuit indéfiniment si le contenu DITA comporte un lien web sans que la portée soit définie comme `external`. (GUIDES-26434)
- La publication des PDF natifs et des sites AEM est bloquée et mise en file d’attente en cas d’erreur dans le contenu. (GUIDES-26516)
- Lors de la création d&#39;une nouvelle ligne de base avec un grand nombre de libellés, cela empêche la récupération de tous les libellés. (GUIDES-16232)
- Lors de la génération de pages du site AEM avec des titres qui incluent plusieurs mots séparés par des espaces, le titre de la carte affiche des tirets au lieu des espaces. (GUIDES-27903)
- Pour le PDF natif, un nom de propriété de métadonnées non valide n’est pas résolu et s’affiche comme `unresolved property name` dans **propriétés du document**. (GUIDES-25680)
- Le texte multiligne dans `codeblock` entraîne des problèmes de débordement de texte lors de la génération de PDF. (GUIDES-15541)
- Lors de l’ajout de mappages à la collection de mappages, les ressources autres que les mappages (telles que les rubriques, etc.) s’affichent et les langues de mappage traduites ne sont pas correctement triées non plus.(GUIDES-25085)


## Révision

- La vue Document de l’interface utilisateur de révision n’inclut pas le contenu pour certaines tailles d’écran, ce qui oblige les utilisateurs à faire défiler l’écran vers la droite ou la gauche pour afficher l’intégralité du contenu. (GUIDES-25292)


## Problèmes connus

Adobe a identifié le problème connu suivant pour la version 2025.06.0 :

- Lors de l’utilisation de l’option Rechercher et remplacer , après l’application de l’opération Remplacer une seule occurrence sur un fichier, aucune autre action ne peut être effectuée dans le panneau Rechercher et remplacer . (GUIDES-28930)

- Dans un profil de dossier, lorsqu’une ressource déjà indexée est supprimée de l’interface utilisateur, le chemin d’accès indexé correspondant n’est pas supprimé et une tentative de réindexation échoue avec un message d’erreur. (GUIDES-29147) <br>**Solution :** vous devez supprimer le chemin obsolète qui n’existe plus avant de lancer la réindexation.

- Si une carte contient des dépendances cycliques et que vous ouvrez l’aperçu de la carte, les vues Source, Auteur et Disposition deviennent inaccessibles jusqu’à ce que la page soit actualisée. (GUIDES-28334) <br>**Solution :** vous devez actualiser la page pour rétablir l’accès à ces vues.
