---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides version 2024.4.0
description: Découvrez les correctifs de bugs de la version 2024.04.0 d’Adobe Experience Manager Guides as a Cloud Service.
exl-id: 35351d71-7739-4ad3-a063-67adf64906bf
TQID: https://experienceleague.adobe.com/cHKuFCElWbjxik0EHgoTrtlq2t3I62LQ5zUArzBoMqk
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
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 577
ht-degree: 8%

---

# Correction de problèmes dans la version 2024.04.0

Cet article couvre les bugs corrigés dans différentes zones de la version 2024.04.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2024.04.0](whats-new-2024-04-0.md).

Découvrez les [instructions de mise à niveau pour la version 2024.04.0](upgrade-instructions-2024-04-0.md).

## Création

- La fonction **Copy** ne parvient pas à dupliquer les dossiers vides dans Adobe Experience Manager as a Cloud Service. (15353)
- L’éditeur Web ne peut pas charger les fichiers .pptx. (14837)
- Lors de la recherche d’un texte dans l’éditeur web, le curseur revient à la première occurrence du texte recherché, lorsque vous appuyez sur la touche Entrée. (14820)
- L’enregistrement automatique entraîne plusieurs problèmes, repositionne le curseur et nécessite des clics manuels dans le document. (14253)
- Les résultats de la recherche sont désactivés après l’ouverture d’un fichier trouvé par le biais du **Rechercher et remplacer** global. (12142)
- Dans la vue source, `</conbody>` est parfois inséré à des emplacements incorrects. (11305)
- Dans l’éditeur XML, la fonction d’info-bulle ne parvient pas à mettre à jour le champ Source. (15847)
- La fonction **Partager le lien UUID** ne fonctionne pas pour les images dans Adobe Experience Manager. (15598)
- Des problèmes de chevauchement de texte se produisent dans les balises `<reltable>` et `<fig>`. (15238)
- Le panneau **Attributs** génère des problèmes de scintillement. (15237)
- Lors de la suppression d’un caractère ou d’un mot dans le contenu, le curseur passe d’un élément du bloc à l’autre. (15224)
- Le panneau **Attributs** ne s’affiche pas dans la vue Source de l’éditeur web. (14387)
- Des espaces superflus sont ajoutés lors de la modification à la fin d’une balise dans l’éditeur web. (11786)
- Le contenu est supprimé lors de la correction des fautes d&#39;orthographe dans les fichiers DITA. (11610)


## Publication

- La génération de la sortie du site AEM échoue lorsque l’option **Supprimer le site orphelin** est activée. (15896)
- La fonctionnalité de modification ne fonctionne pas lors de l’ajout de fichiers à la collection Map. (15813)
- Dans la sortie JSON, les métadonnées du plan ou des rubriques DITA ne se propagent pas aux fichiers de sortie JSON. (15713)
- La publication native de PDF échoue lors du changement du nom du préréglage. (15662)
- La propriété **sourcePath** est incorrecte sur la sortie de site AEM publiée. (15502)
- La sélection et la personnalisation des variables de langue ne fonctionnent pas correctement dans le paramètre prédéfini de sortie PDF natif. (15399)
- La génération native de PDF échoue lors de l’utilisation d’un modèle avec une feuille de style ou une mise en page volumineuse. (15344)
- Le contenu n’est pas rendu correctement dans la sortie publiée si `<conref>` est utilisé avec un chemin d’accès absolu.
- Le raccourcissement des URL d’AEM Sites ne fonctionne pas en raison de conflits entre le `fmdita rewriter` et le `ResourceResolver`. (14793)
- Les attributs **processing-role=« resource-only »**, **search=« no »** et **chunk=« to-content »** apparaissent indépendamment dans la sortie AEM Sites. (14442)
- Si un dossier contenant 2 000 mappages est défini dans le chemin du dossier à l’intérieur d’un profil de dossier, les modifications appliquées au paramètre prédéfini de sortie échouent.(14852)

## Gestion

- La non-fermeture de **Resource Resolvers** entraîne une augmentation du nombre de sessions et des erreurs PathNotFoundException après la version d’octobre 2023 d’Experience Manager Guides as a Cloud Service. (15604)
- L’indicateur de fonctionnalité **fmdita.useapproval** ne fonctionne pas comme prévu. (15310)
- La création d’une ligne de base à l’aide de l’API Java ne fonctionne pas avec la version de juin 2023 de Experience Manager Guides as a Cloud Service. (14787)
- L’API `/bin/fmdita/import` reste bloquée indéfiniment dans la requête en attente lorsque le chargement des ressources dépasse 500 Mo. (14743)

## Révision

- La suppression des nœuds de révision interrompt la possibilité d’ouvrir et d’afficher des commentaires dans Adobe Experience Manager Guides. (15366)
- Dans l’éditeur web, le panneau Révision se charge lentement. (14680)

## Traduction

- **Accepter la traduction** ne parvient pas à terminer la traduction des fichiers temporaires. (14665)
