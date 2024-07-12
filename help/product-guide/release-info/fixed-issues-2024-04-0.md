---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides version 2024.4.0
description: Découvrez les correctifs de bogues de la version 2024.04.0 d’Adobe Experience Manager Guides as a Cloud Service.
exl-id: 35351d71-7739-4ad3-a063-67adf64906bf
source-git-commit: 5d99274da8fdacbd255d426fa4913b5773ca45f8
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 3%

---

# Correction de problèmes dans la version 2024.04.0

Cet article couvre les bogues corrigés dans différentes zones de la version 2024.04.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2024.04.0](whats-new-2024-04-0.md).

Découvrez les [instructions de mise à niveau pour la version 2024.04.0](upgrade-instructions-2024-04-0.md).

## Création

- La fonction **Copy** ne parvient pas à dupliquer les dossiers vides dans Adobe Experience Manager as a Cloud Service. 15353)
- L’éditeur web ne peut pas télécharger de fichiers .pptx. (14837)
- Lors de la recherche d’un texte dans l’éditeur web, le curseur revient à la première occurrence du texte recherché, en appuyant sur la touche Entrée. (14820)
- L’enregistrement automatique entraîne plusieurs problèmes, repositionne le curseur et nécessite des clics manuels dans le document. (14253)
- Les résultats de la recherche sont désactivés après l’ouverture d’un fichier trouvé par l’intermédiaire de la méthode globale **Chercher et Remplacer**. (12142)
- Dans la vue source, `</conbody>` est parfois inséré à des emplacements incorrects. (11305)
- Dans l’éditeur XML, la fonction d’info-bulle ne parvient pas à mettre à jour le champ Source. (15847)
- La fonction **Partager le lien UUID** ne fonctionne pas pour les images dans Adobe Experience Manager. (15598)
- Des problèmes de chevauchement de texte se produisent dans les balises `<reltable>` et `<fig>`. 15238
- Des problèmes de scintillement se produisent dans le panneau **Attributs**. (15237)
- Lors de la suppression d’un caractère ou d’un mot dans le contenu, le curseur passe entre les éléments du bloc. 15224
- Le panneau **Attributs** ne s’affiche pas dans la vue Source de l’éditeur web. (14387)
- Des espaces indésirables insécables sont ajoutés lors de la modification à la fin d’une balise dans l’éditeur web. (11786)
- Le contenu est supprimé lors de la correction des erreurs d’orthographe dans les fichiers DITA. (11610)


## Publication

- La génération AEM sortie du site échoue lorsque l’option **Supprimer le site orpheline** est activée. (15896)
- La fonctionnalité de modification ne fonctionne pas lors de l’ajout de fichiers à la collection de cartes. (15813)
- Dans la sortie JSON, les métadonnées du mappage DITA ou des rubriques ne se propagent pas aux fichiers de sortie JSON. (15713)
- La publication du PDF natif échoue lors du changement de nom du paramètre prédéfini. (15662)
- La propriété **sourcePath** est incorrecte sur la sortie publiée AEM site. (15502)
- La sélection et la personnalisation des variables de langue ne fonctionnent pas correctement dans le paramètre prédéfini de sortie du PDF natif. (15399)
- La génération d’un PDF natif échoue lors de l’utilisation d’un modèle avec une feuille de style ou une mise en page volumineuse. 15344
- Le contenu n’est pas rendu correctement dans la sortie publiée si `<conref>` est utilisé avec un chemin d’accès absolu.
- Le raccourcissement des URL AEM Sites ne fonctionne pas en raison de conflits entre `fmdita rewriter` et `ResourceResolver`. (14793)
- Les attributs **processing-role=&quot;resource-only&quot;**, **search=&quot;no&quot;** et **chunk=&quot;to-content&quot;** apparaissent respectivement dans la sortie AEM Sites. (14442)
- Si un dossier contenant des mappages 2k est défini dans le chemin du dossier dans un profil de dossier, les modifications appliquées au paramètre prédéfini de sortie échouent.14852

## Gestion

- Les **Resource Resolvers** non fermés provoquent une augmentation du nombre de sessions et des erreurs PathNotFoundException après la version d’octobre 2023 de Experience Manager Guides as a Cloud Service. 15604
- L’indicateur de fonctionnalité **fmdita.useapproval** ne fonctionne pas comme prévu. (15310)
- La création d’une ligne de base à l’aide de l’API Java ne fonctionne pas avec la version de juin 2023 d’Experience Manager Guides as a Cloud Service. (14787)
- L’API `/bin/fmdita/import` reste bloquée indéfiniment dans la requête en attente lorsque les ressources de chargement dépassent 500 Mo. (14743)

## Révision

- La suppression de noeuds de révision perturbe la possibilité d’ouvrir et d’afficher des commentaires dans Adobe Experience Manager Guides. 15366
- Dans l’éditeur web, le panneau Révision se charge lentement. (14680)

## Traduction

- **Accepter la traduction** ne parvient pas à terminer la traduction des fichiers temporaires. (14665)
