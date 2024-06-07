---
title: Notes de mise à jour | Correction de problèmes dans les guides Adobe Experience Manager, version 2024.06.0
description: Découvrez les correctifs de bogues de la version 2024.06.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: dff625a841ea9fc758de83b1d830ddffa15646cd
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 3%

---


# Correction de problèmes dans la version 2024.06.0

Cet article couvre les bogues corrigés dans différentes zones de la version 2024.06.0 de Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2024.06.0](whats-new-2024-06-0.md).

En savoir plus [instructions de mise à niveau pour la version 2024.06.0](upgrade-instructions-2024-06-0.md).

## Création

- L’opération de copier-coller de rubriques supérieures à 15 Ko échoue avec une erreur inattendue. 17171
- La fonctionnalité permettant de modifier l’état du document à partir de la fonction  **Propriétés du fichier** ne fonctionne pas correctement et les modifications apportées au *Version préliminaire* état. 17088
- Lors de la modification des paramètres de l’éditeur XML à l’aide d’un profil de dossier personnalisé, la variable `ui_config.json` est mis à jour avec un fichier incorrect. (17011)
- Dans le **Référentiel** du panneau **Filtrer** search ne conserve pas la valeur de **Extraits par** lors de la réouverture du champ **Filtre avancé** de la boîte de dialogue (16935)
- Les images liées des rubriques ne s’affichent pas dans la ligne de base après la création de la version. 16931
- Les panneaux de contenu réutilisables ne répertorient pas les éléments lorsque la variable **Préférences utilisateur** sont définies pour afficher les fichiers par **Nom du fichier**. (16896)
- Le rendu des sous-éléments de l’élément de titre du tableau échoue dans la variable **Aperçu** mode des guides du Experience Manager. (16691)
- L’exécution du script de post-traitement échoue en raison de **FileNotFoundException** exception. (16517)
- Les vidéos Vimeo ne prennent pas en charge la fonctionnalité plein écran dans les guides du Experience Manager. (15996)
- Coller de longues séquences de texte préformatées dans `<pre>` ou `<codeblock>` mène au texte tronqué. 15859)
- La suppression de contenu est due à des GUID en double lorsque les modèles sont installés par le biais du code, mais restent non traités. (15858)
- Les guides du Experience Manager ne parviennent pas à respecter les **Rôle de traitement** dans **Aperçu** mode . (15787)
- L’éditeur supprime par intermittence le texte supplémentaire au-delà de la zone sélectionnée.  (15708)
- Impossible de copier et coller des tableaux volumineux à partir de documents Word ou de HTML dans l’éditeur Web. (15369)
- La variable **Copier** échoue pour les dossiers vides dans les guides de Experience Manager as a Cloud Service. 15353)
- Absence d’API ou d’événements pour capturer l’ajout d’attributs à un élément ou l’insertion d’un nouvel élément. 15351
- Impossible d’ajouter `<data>` balise dans `<ol>` dans l’éditeur Web. 15161)
- Lorsque le Shell unifié est activé, la variable **Gestion des étiquettes de version** boîte de dialogue s’affiche incorrectement **Contenu principal** pour les versions sans étiquettes. (15039)
- Les fichiers volumineux se chargent lentement dans l’éditeur web, avec un délai de quelques secondes. (14958)
- Appuyez sur **Entrée** Dans une cellule de tableau du texte, la clé ne fractionne pas le paragraphe comme prévu. 14251)
- Le guide DITA du Experience Manager ne parvient pas à déclencher la variable **Enregistrer** après avoir utilisé la fonction de retrait automatique. 16482
- Les rubriques de révision n’apparaissent pas dans l’ordre correct. (16319)
- Dans le **Auteur** , un problème de copier-coller se produit lors de l’utilisation d’espaces insécables et entraîne un débordement de texte. (15541)

- Dans `<othermeta>` element dans `<topicmeta>`, lors de l’ajout d’un `<conref>`sur un autre mappage DITA, l’ID de mappage est également ajouté avec l’ID de l’élément . (15226)
- La variable `<conref>` ne peut pas être mis à jour à partir du **Attributs** lors de la modification. 15209
- Lorsque vous sélectionnez une image dans une cellule de tableau, la cellule entière est sélectionnée. (15188)

## Publication


- La liaison croisée n’affiche pas toutes les cartes parentes dans les paramètres de contexte de publication pour un lien qui contient la variable `peer @scope`. (16700)
- Lors de l’ajout ou de la suppression d’attributs existants, les anciens attributs sont conservés dans la variable **Paramètres prédéfinis de condition**. (15890)
- Le contenu de la langue RTL n’est pas géré correctement dans la sortie de publication du PDF natif. 15709
- Le premier PDF n’est pas versionné lorsqu’une sortie de PDF natif est générée. (10305)
- Dans le PDF natif, les rubriques DITA imbriquées s’affichent incorrectement dans la table des matières. 16742
- Les miniatures générées à partir de Dynamic Media pour les fichiers vidéo ne sont pas conservées dans la sortie publiée. 15656)
- La génération de sortie échoue pour la publication de PDF natif sur un processeur ARM64. (16968)

## Gestion

- La modification d’une ligne de base existante et la sélection d’une version spécifique déclenchent des erreurs d’application. 14451)

## Traduction

- Les projets de traduction ne parviennent pas à ajouter de nouvelles tâches linguistiques à Adobe Experience Manager 6.5 SP18 avec la version d’octobre 2023 des Guides du Experience Manager. (15398)

## Cloud Service

- La navigation dans les outils Adobe Experience Manager ne répond pas. (17118)
- La phase de transformation de build dans le déploiement Cloud Service échoue avec des erreurs provenant du code base DITA. (14432)

## Rapports

- L&#39;inexact **Liste des rubriques** les décomptes dans l’interface utilisateur des guides de Experience Manager en raison de propriétés non corrigées lors de la copie de ressources DITA ont un impact sur les rapports générés pour une carte DTIA. (15529)
- Sujets contenant des références externes avec *%20* dans l’URL, les références de fichier rompues s’affichent. (15347)


## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 2024.06.0 :

- La publication du PDF natif échoue lorsque du contenu Vimeo est ajouté à la rubrique.
- La variable **Propriétés de la rubrique** ne s’affichent pas selon le format sélectionné dans les champs de métadonnées d’une mise en page.
- `xrefs` ne peuvent pas faire l’objet d’un clic dans le **Ressources** s’affiche lorsque Dynamic Media est activé.
