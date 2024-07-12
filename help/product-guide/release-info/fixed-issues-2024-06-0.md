---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides, version 2024.06.0
description: Découvrez les correctifs de bogues de la version 2024.06.0 d’Adobe Experience Manager Guides as a Cloud Service.
exl-id: 608e5b2c-72af-4498-9b63-935e698231d4
source-git-commit: d525775afeeb89754762ff514126b1c3a3307b3f
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 3%

---

# Correction de problèmes dans la version 2024.06.0

Cet article couvre les bogues corrigés dans différentes zones de la version 2024.06.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2024.06.0](whats-new-2024-06-0.md).

Découvrez les [instructions de mise à niveau pour la version 2024.06.0](upgrade-instructions-2024-06-0.md).

## Création

- L’opération de copier-coller de rubriques supérieures à 15 Ko échoue avec une erreur inattendue. 17171
- La fonctionnalité permettant de modifier l’état du document à partir du panneau **Propriétés du fichier** ne fonctionne pas correctement et passe à l’état *Brouillon*. 17088
- Lors de la modification des paramètres de l’éditeur XML à l’aide d’un profil de dossier personnalisé, `ui_config.json` est mis à jour avec un fichier incorrect. (17011)
- Dans le panneau **Repository**, la recherche **Filter** ne conserve pas la valeur du champ **Checked out by** lors de la réouverture de la boîte de dialogue **Advanced filter**. (16935)
- Les images liées des rubriques ne s’affichent pas dans la ligne de base après la création de la version. 16931
- Les panneaux de contenu réutilisables ne répertorient pas les éléments lorsque les **préférences utilisateur** sont définies pour afficher les fichiers par **nom de fichier**. (16896)
- Le rendu des sous-éléments dans l’élément de titre de la table échoue dans le mode **Aperçu** de Experience Manager Guides. (16691)
- L’exécution du script de posttraitement échoue en raison de l’exception **FileNotFoundException**. (16517)
- Les vidéos Vimeo ne prennent pas en charge la fonctionnalité plein écran dans Experience Manager Guides. (15996)
- Le collage de longues séquences de texte préformatées dans des éléments `<pre>` ou `<codeblock>` entraîne la troncation de texte. 15859)
- La suppression de contenu est due à des GUID en double lorsque les modèles sont installés par le biais du code, mais restent non traités. (15858)
- Experience Manager Guides ne parvient pas à se conformer à l’attribut **Rôle de traitement** en mode **Aperçu**. (15787)
- L’éditeur supprime par intermittence le texte supplémentaire au-delà de la zone sélectionnée.  (15708)
- Impossible de copier et coller des tableaux volumineux à partir de documents Word ou d’un HTML dans l’éditeur Web. (15369)
- La fonction **Copy** échoue pour les dossiers vides de Experience Manager Guides as a Cloud Service. 15353)
- Absence d’API ou d’événements pour capturer l’ajout d’attributs à un élément ou l’insertion d’un nouvel élément. 15351
- Impossible d’ajouter la balise `<data>` dans la balise `<ol>` de l’éditeur web. 15161)
- Lorsque le Shell unifié est activé, la boîte de dialogue **Gestion des étiquettes de version** affiche incorrectement le **contenu principal** pour les versions sans étiquettes. (15039)
- Les fichiers volumineux se chargent lentement dans l’éditeur web, avec un délai de quelques secondes. (14958)
- Appuyez sur la touche **Entrée** d’une cellule de tableau dans le texte pour ne pas fractionner le paragraphe comme prévu. 14251)
- Le guide DITA Experience Manager ne parvient pas à déclencher la fonction **Save** après l’utilisation de la fonction de mise en retrait automatique. 16482
- Les rubriques de révision n’apparaissent pas dans l’ordre correct. (16319)
- Dans la vue **Auteur**, un problème de copier-coller se produit lors de l’utilisation d’espaces insécables et entraîne un débordement du texte. (15541)

- Dans l’élément `<othermeta>` dans `<topicmeta>`, lors de l’ajout d’un `<conref>` à un autre mappage DITA, l’ID de mappage est également ajouté avec l’ID de l’élément. (15226)
- `<conref>` ne peut pas être mis à jour à partir du panneau **Attributs** lors de l’apport de modifications. 15209
- Lorsque vous sélectionnez une image dans une cellule de tableau, la cellule entière est sélectionnée. (15188)

## Publication


- La liaison croisée n’affiche pas toutes les cartes parentes dans les paramètres de contexte de publication pour un lien qui contient le `peer @scope`. (16700)
- Lors de l’ajout ou de la suppression d’attributs nouveaux ou existants, les anciens attributs sont conservés dans les **paramètres de condition prédéfinis**. (15890)
- Le contenu de la langue RTL n’est pas géré correctement dans la sortie de publication du PDF natif. 15709
- Le premier PDF n’est pas versionné lorsqu’une sortie de PDF natif est générée. (10305)
- Dans le PDF natif, les rubriques DITA imbriquées s’affichent incorrectement dans la table des matières. 16742
- Les miniatures générées à partir de Dynamic Media pour les fichiers vidéo ne sont pas conservées dans la sortie publiée. 15656)
- La génération de sortie échoue pour la publication de PDF natif sur un processeur ARM64. (16968)

## Gestion

- La modification d’une ligne de base existante et la sélection d’une version spécifique déclenchent des erreurs d’application. 14451)

## Traduction

- Les projets de traduction ne parviennent pas à ajouter de nouvelles tâches linguistiques à Adobe Experience Manager 6.5 SP18 avec la version d’octobre 2023 de Experience Manager Guides. (15398)

## Cloud Service

- La navigation dans les outils Adobe Experience Manager ne répond pas. (17118)
- La phase de transformation de build dans le déploiement Cloud Service échoue avec des erreurs provenant du code base DITA. (14432)

## Rapports

- Le nombre inexact de **Topic List** dans l’interface utilisateur de Experience Manager Guides en raison de propriétés non corrigées lors de la copie de ressources DITA a un impact sur les rapports générés pour une carte DTIA. (15529)
- Les rubriques contenant des références externes avec *%20* dans l’URL affichent des références de fichier rompues. (15347)


## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 2024.06.0 :

- La publication du PDF natif échoue lorsque du contenu Vimeo est ajouté à la rubrique.
- Les **propriétés de la rubrique** ne sont pas affichées selon le format sélectionné dans les champs de métadonnées d’une mise en page.
- `xrefs` ne peuvent pas faire l’objet d’un clic dans la vue **Assets** lorsque Dynamic Media est activé.
