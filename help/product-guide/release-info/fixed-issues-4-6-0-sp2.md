---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides 4.6.0 Service Pack 3
description: Découvrez les correctifs de bugs dans la version 4.6.0 Service Pack 3 d’Adobe Experience Manager Guides
role: Leader
source-git-commit: d60fea16831af458c479df24c877ef7095b2fd15
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# Correction de problèmes dans la version 4.6.0 Service Pack 3 (janvier 2025)


Cet article couvre les bugs corrigés dans différentes zones de la version 4.6.0 Service Pack 3 d’Adobe Experience Manager Guides.

Découvrez les [instructions de mise à niveau pour la version 4.6.0 du pack de services 3](upgrade-instructions-4-6-0-sp2.md).

## Création

- Tous les groupes de conditions sont perdus et les conditions sont aplaties lors de la mise à jour des conditions à partir du profil de dossier. (23526)
- La modification de la valeur des lignes d’en-tête d’un tableau dans le panneau **Propriétés du contenu** n’applique pas la valeur mise à jour. (23213)
- Lors de l&#39;ajout de nouvelles références de rubrique dans un plan DITA à l&#39;aide de la boîte de dialogue d&#39;élément **Référence de rubrique** en mode Mise en page, les références ajoutées s&#39;affichent sous la forme d&#39;un lien rompu. (22859)
- Lors de l&#39;ajout de rubriques dans un plan DITA à l&#39;aide de la boîte de dialogue d&#39;élément **Référence de rubrique** en mode création, les rubriques sélectionnées sont insérées dans l&#39;ordre inverse de la sélection. (22858)
- Lors de la copie d’une image à partir d’un produit externe (par exemple, MS PowerPoint) et de son collage dans Guides, la fonctionnalité permettant de charger la ressource à la volée pour l’utiliser dans les fichiers est interrompue. (24983)
- Lors de la recherche de fichiers dans le référentiel à l’aide de la fonctionnalité **Rechercher et filtrer**, plusieurs fichiers ne peuvent pas être sélectionnés. (25104)

## Publication

- La publication sur Salesforce échoue lorsque le contenu contient des espaces insécables. (23664)
- Pour les rubriques comportant des erreurs telles que des liens rompus, la publication de Salesforce échoue et la barre de progression s’affiche indéfiniment. (22985)
- Pour les mappages comportant des liens rompus, la publication du Salesforce échoue et la barre de progression s’affiche indéfiniment. (24963)
- Si un lien externe contient un UUID, il passe en post-traitement et convertit le lien externe en lien UUID, rompant ainsi le lien dans l’éditeur web ainsi que sur les sites de publication. (22574)
- Le `xref` est converti en lien relatif même lorsque la **portée** du lien est définie sur **externe**. (23059)
- La génération native du PDF échoue pour le contenu avec l’attribut **chunk** défini sur **to-content**. (21772)
- La boîte de dialogue **Modifier les propriétés** d&#39;une ligne de base n&#39;affiche pas les critères précédemment enregistrés pour la ligne de base dynamique. (23964)


## Traduction

- Pour une traduction non héritée (pour les traductions non UUID), le déplacement d’une rubrique dans le chemin d’accès source vers un autre dossier entraîne des ruptures de référence dans le paramètre régional cible. (24152)
