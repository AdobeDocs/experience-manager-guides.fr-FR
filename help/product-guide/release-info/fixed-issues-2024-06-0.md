---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides, version 2024.06.0
description: Découvrez les correctifs de bugs de la version 2024.06.0 d’Adobe Experience Manager Guides as a Cloud Service.
exl-id: 608e5b2c-72af-4498-9b63-935e698231d4
TQID: https://experienceleague.adobe.com/PWXSeB-BhL9Gc104XoVpfqdWqywq7T6bphx8im92C4c
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 781
ht-degree: 8%

---

# Correction de problèmes dans la version 2024.06.0

Cet article couvre les bugs corrigés dans différentes zones de la version 2024.06.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2024.06.0](whats-new-2024-06-0.md).

Découvrez les [instructions de mise à niveau pour la version 2024.06.0](upgrade-instructions-2024-06-0.md).

## Création

- L’opération de copier-coller de rubriques dépassant 15 Ko échoue avec une erreur inattendue. (17171)
- La fonctionnalité de modification de l’état du document à partir du panneau **Propriétés du fichier** ne fonctionne pas correctement et passe à l’état *Brouillon*. (17088)
- Lors de la modification des paramètres de l’éditeur XML à l’aide d’un profil de dossier personnalisé, le `ui_config.json` est mis à jour avec un fichier incorrect. (17011)
- Dans le panneau **Référentiel**, la recherche **Filtre** ne conserve pas la valeur du champ **Extrait par** lors de la réouverture de la boîte de dialogue **Filtre avancé**. (16935)
- Les images liées des rubriques ne s’affichent pas dans la ligne de base après la création de la version. (16931)
- Les panneaux de contenu réutilisables ne répertorient pas les éléments lorsque les **Préférences utilisateur** sont définies pour afficher les fichiers par **Nom de fichier**. (16896)
- Le rendu des sous-éléments dans l’élément de titre du tableau échoue dans le mode **Aperçu** de Experience Manager Guides. (16691)
- L&#39;exécution du script de post-processus échoue en raison de l&#39;exception **FileNotFoundException**. (16517)
- Les vidéos Vimeo ne prennent pas en charge la fonctionnalité plein écran dans Experience Manager Guides. (15996)
- Le collage de longues séquences de texte préformaté dans des éléments `<pre>` ou `<codeblock>` entraîne la troncature du texte. (15859)
- La suppression de contenu se produit en raison de GUID en double lorsque des modèles sont installés via le code, mais restent non traités. (15858)
- Experience Manager Guides ne parvient pas à se conformer à l’attribut **Rôle de traitement** en mode **Aperçu**. (15787)
- L’éditeur supprime par intermittence le texte supplémentaire au-delà de la zone sélectionnée.  (15708)
- Impossible de copier et coller des tableaux volumineux à partir de documents Word ou HTML dans l’éditeur web. (15369)
- La fonction **Copy** échoue pour les dossiers vides dans Experience Manager Guides as a Cloud Service. (15353)
- Manque d’API ou d’événements pour capturer l’ajout d’attribut à un élément ou l’insertion d’un nouvel élément. (15351)
- Impossible d’ajouter `<data>` balise dans `<ol>` balise dans l’éditeur web. (15161)
- Lorsque Unified Shell est activé, la boîte de dialogue **Gestion des libellés de version** s’affiche incorrectement **Contenu principal** pour les versions sans libellés. (15039)
- Les fichiers volumineux se chargent lentement dans l’éditeur web, avec un délai de quelques secondes. (14958)
- Appuyez sur la touche **Entrée** dans une cellule de tableau pour fractionner le paragraphe de la manière prévue. (14251)
- Le guide Experience Manager DITA ne parvient pas à déclencher la fonction **Enregistrer** après avoir utilisé la fonction de retrait automatique. (16482)
- Les rubriques de révision n’apparaissent pas dans le bon ordre. (16319)
- Dans la vue **Auteur**, un problème de copier-coller se produit lors de l’utilisation d’espaces insécables et entraîne un débordement du texte. (15541)

- Dans `<othermeta>` élément de `<topicmeta>`, lors de l&#39;ajout d&#39;un `<conref>`à un autre plan DITA, l&#39;ID de plan est également ajouté avec l&#39;ID de l&#39;élément. (15226)
- Le `<conref>` ne peut pas être mis à jour à partir du panneau **Attributs** lors de l’application de modifications. (15209)
- Lors de la sélection d’une image dans une cellule de tableau, la cellule entière est sélectionnée. (15188)

## Publication


- La liaison de plans d&#39;intersection ne parvient pas à afficher tous les plans parents dans les paramètres de contexte de publication pour un lien qui possède le `peer @scope`. (16700)
- Lors de l’ajout de nouveaux attributs ou de la suppression d’attributs existants, les anciens attributs sont conservés dans les **Paramètres prédéfinis de condition**. (15890)
- Le contenu en langue RTL n’est pas correctement géré dans la sortie de publication Native PDF. (15709)
- Le premier PDF n’est pas versionné lorsqu’une sortie PDF native est générée. (10305)
- Dans Native PDF, les rubriques DITA imbriquées ne s&#39;affichent pas correctement dans la table des matières. (16742)
- Les miniatures générées à partir de Dynamic Media pour les fichiers vidéo ne sont pas conservées dans la sortie publiée. (15656)
- La génération de sortie échoue pour la publication native PDF sur un processeur ARM64. (16968)

## Gestion

- La modification d&#39;une ligne de base existante et la sélection d&#39;une version spécifique déclenchent des erreurs d&#39;application. (14451)

## Traduction

- Les projets de traduction ne parviennent pas à ajouter de nouvelles tâches linguistiques au pack de services 18 de Adobe Experience Manager 6.5 avec la version d’octobre 2023 de Experience Manager Guides. (15398)

## Cloud Service

- La navigation dans les outils Adobe Experience Manager ne répond pas. (17118)
- La phase de transformation de build dans le déploiement Cloud Services échoue avec des erreurs provenant de la base de code DITA. (14432)

## Rapports

- Le décompte inexact **Liste de rubriques** dans l&#39;interface utilisateur de Experience Manager Guides en raison de propriétés non corrigées lors de la copie de ressources DITA a un impact sur les rapports générés pour un mappage DITA. (15529)
- Les rubriques contenant des références externes avec *%20* dans l&#39;URL affichent des références de fichier endommagées. (15347)


## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 2024.06.0 :

- La publication native de PDF échoue lorsque du contenu Vimeo est ajouté à la rubrique.
- Les **propriétés de rubrique** ne s’affichent pas selon le format sélectionné dans les champs de métadonnées d’une mise en page.
- `xrefs` ne sont pas cliquables dans la vue **Assets** lorsque Dynamic Media est activé.
