---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans la version 4.3.1 d’Adobe Experience Manager Guides
description: Découvrez les correctifs et comment mettre à niveau vers les versions 4.3.1 d’Adobe Experience Manager Guides
exl-id: 3fb6dc31-ec6e-40f5-ab3f-a6e591da315e
feature: Release Notes
role: Leader
source-git-commit: 1b25f1df67fa2442ab79830dc2ac5a6eabd0394c
workflow-type: tm+mt
source-wordcount: '1308'
ht-degree: 1%

---

# Version 4.3.1 d’Adobe Experience Manager Guides (octobre 2023)

Cette note de mise à jour traite des instructions de mise à niveau, de la matrice de compatibilité et des problèmes résolus dans la version 4.3.1 d’Adobe Experience Manager Guides (appelée ultérieurement *Experience Manager Guides*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version 4.3.1 d’Adobe Experience Manager Guides](./whats-new-4-3-1-release.md).

## Mise à niveau vers la version 4.3.1 de Experience Manager Guides


Vous pouvez facilement mettre à niveau votre version actuelle de Experience Manager Guides vers la version 4.3.1. Avant de procéder à la mise à niveau vers la version 4.3.1 de Experience Manager Guides, vous devez tenir compte des points suivants :
Vous pouvez mettre à niveau votre version actuelle de Experience Manager Guides vers la version 4.3.1.


- Si vous utilisez la version 4.3.0, 4.2 ou 4.2.1, vous pouvez directement effectuer la mise à niveau vers la version 4.3.1.
- Si vous utilisez la version 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers la version 4.3.0, 4.2 ou 4.2.x avant de passer à la version 4.3.1.
- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant de passer à la version 4.3.1.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à 3.8.5, reportez-vous à la section Mise à niveau de Experience Manager Guides du guide d’installation spécifique au produit.


>[!NOTE]
>
>Vous devez installer AEM Service Pack avant de mettre à niveau la version de Experience Manager Guides.

Pour plus d’informations, voir [Instructions de mise à niveau](../install-guide/upgrade-xml-documentation.md).

## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par la version 4.3.1 de Experience Manager Guides.

### Adobe Experience Manager

**4.3.1 Non-UUID**
Version 6.5 Service Pack 18, 17, 16, 15 ou 14

**4.3.1 UUID**
Version 6.5 Service Pack 18, 17, 16, 15 ou 14

Pour plus d’informations, voir la section *Exigences techniques* du guide Installation et configuration d’Adobe Experience Manager Guides.

### FrameMaker et FrameMaker Publishing Server

| Version | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.3.1 (non UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.3 ou version ultérieure |
| 4.3.1 (UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.4 ou version ultérieure |
| | | | |

*Les conditions de base et créées dans AEM sont prises en charge dans les versions FMPS à partir de 2020.2.

### Connecteur Oxygen

| Version | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.3.1 (non UUID) | 2.3-normal-5 | 2.3-normal-5 | 1,6 | 1,6 |
| 4.3.1 (UUID) | 3.2-uuid-5 | 3.2-uuid-5 | 2,3 | 2,3 |
|  |  |   |



### Version du modèle de base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu des composants Experience Manager Guides pour Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :

### Création

- Les heures de l’après-midi ne sont pas définies dans la **Date** pour la création de lignes de base. (12712)
- Impossible de coller le code JSON dans l’élément `<codeblock>` de l’éditeur web. (12326)
- Les modifications de version non enregistrées et les indicateurs associés ne sont pas affichés pour les fichiers volumineux. (11784)
- Lors de l’édition en coréen, le premier caractère est remplacé par défaut. (10049)

- Le préfixe est dupliqué en mode d’aperçu de l’éditeur web. (13133)
- `Choicetable` lignes ne sont pas affichées ou ne peuvent pas être sélectionnées. (12616)
- L’éditeur web renvoie des erreurs de validation dans des scénarios spécifiques lors de la création d’une rubrique à l’aide d’un schéma personnalisé. (12576)
- Les références du modèle de rubrique ditaval ne créent pas de copie dans le dossier de contenu lors de la création d’un mappage à partir du modèle de mappage. (12150)

- La zone de recherche dans les mappages DITA ne comporte pas de bouton de fermeture. (11867)
- Lors de l’enregistrement des fichiers longs dans l’éditeur Web, `DirtyChecker` renvoie une exception avec une longue trace de pile et remplit les fichiers journaux. (11860)
- La création de rubriques DITA nécessite l’autorisation Supprimer sur le noeud de dossier correspondant, bien que le mappage puisse être créé avec l’autorisation En écriture. (11706)
- L’éditeur web affiche un titre incorrect lorsqu’une barre oblique est présente. (10949)

- Si le titre d’une rubrique contient une barre oblique &quot;/&quot;, l’onglet de l’éditeur n’affiche que les lettres qui lui succèdent. (13455)
- L’aperçu de l’image ne disparaît pas après l’affichage de l’aperçu dans l’éditeur. (13454)
- Certaines des versions existantes ou leurs libellés ne s’affichent pas dans l’ historique des versions après la mise à niveau vers la version 4.x. (13247)
- Le panneau Historique de version de l’interface utilisateur d’Assets affiche un horodatage incorrect pour le champ **Actuel**. 12624
- La rubrique avec le titre de référence n’est pas résolue en mode Référentiel ou Carte.(13304)


### Publication

- PDF natif | L’ordre des rubriques n’est pas fixe lors de la génération de la sortie du PDF. (13157)
- PDF natif| Aucune balise de style par défaut n’est disponible pour l’élément `<p>`. (12559)
- PDF natif | Les styles intégrés appliqués à la région de contenu ne sont pas appliqués aux rubriques en premier et en arrière. (13510)
- L’attribut `DeliveryTarget` n’est pas propagé lors de la génération de la sortie AEM Site.  (13132)
- Le workflow **Publish** est bloqué lors de la génération de la sortie AEM Site pour le contenu avec certaines erreurs. (12000)

- PDF natif | L’inclusion de plusieurs expressions étend le texte au-delà de la largeur de colonne. 13004
- PDF natif | Lorsque la rubrique et le titre ont le même ID, cela entraîne une génération incorrecte de la sortie du PDF. 12644
- PDF natif | Lors de l’ajout d’une classe de sortie à un élément `<topicref>` parent dans un mappage DITA et de l’application d’un style personnalisé à la classe de sortie, le style est appliqué aux éléments dans le corps de la rubrique, y compris les titres des sections. (12166)
- La publication incrémentielle ne fonctionne pas si un mappage DITA comporte plusieurs attributs ditavalrefs. (12117)
- AEM site | Lors de la création d’un mappage avec keydef pointant vers une rubrique en tant que variable, l’ajout de processing-role=resource-only crée des pages inattendues. (12099)
- Si des ressources provenant de la gestion des actifs numériques AEM sont utilisées dans une sortie autre que le site AEM, les métadonnées &quot;jcr:createdBy&quot; ne reflètent pas le nom de l’éditeur ou le nom de l’utilisateur qui a modifié la dernière fois le mappage ou la rubrique DITA. (12090)
- AEM Sites | Le mappage DITA avec le titre de la topique dans le titre de navigation (avec des caractères non pris en charge) entraîne des URL de page incorrectes. (1978)
- PDF natif | Des problèmes se produisent pour la prise en charge de topichead/topicmeta/navtitle dans les sections Frontmatter et Backmatter. (1969)
- PDF natif | La génération de PDF pour les documents volumineux prend du temps. (11955)
- PDF natif | Le changement de nom d’un paramètre prédéfini renvoie une exception NullPointerException lors de la génération d’une sortie de PDF. (11889)
- Le contenu `<conref>` n’est pas affiché dans la sortie du PDF. (11131)
- Un espace supplémentaire est ajouté à l’intérieur des éléments `<div>` lors du basculement entre la vue Auteur et Source dans l’éditeur de mise en page. 10750
- Le contenu répliqué sur AEM Cloud Manager n’est pas visible sur l’instance Publish. (9564)


### Gestion

- L’historique de version ne s’affiche pas même si la propriété `dc:format` n’est pas présente pour une ressource. 10463
- La référence au contenu est un fichier DITA copié-collé rompu lorsque l’ID de rubrique n’est pas identique au GUID. (12614)
- Dans les lignes de base dynamiques, la liste des libellés n’est pas extraite des références directes de la copie de travail d’un mappage DITA. (1917)
- La ligne de base affiche le nombre incorrect de fichiers sur le tableau de bord des cartes lors de l’utilisation de la fonctionnalité Parcourir toutes les rubriques. (13265)
- Dans l’éditeur Web, la ligne de base affiche le titre de la version précédente au lieu de la version sélectionnée du fichier DITA. (13444)

### Révision

- La révision d’une rubrique affiche des commentaires incorrects. (13453)
- Le bouton Fermer de la page Révision de Experience Manager Guides permet d’accéder à la page d’accueil d’AEM. 13535)
- Les pièces jointes ne s’affichent pas dans le panneau de droite de l’éditeur pour une rubrique In-review. (13011)



### Traduction

- La ligne de base exportée à partir du tableau de bord **Traduction** échoue et ne s’ouvre pas dans la langue cible. (13466)

- De nouveaux projets de traduction sont créés au lieu d’ajouter de nouvelles tâches aux projets de traduction existants sélectionnés.  (10214)
- Le titre du fichier traduit est affiché à la place du titre du fichier source. (11630)
- L’approbation automatique ne fonctionne pas parfois et des exceptions se produisent si une valeur incorrecte est définie sur le statut de traduction. (13607)
- La ligne de base exportée à partir du tableau de bord Traduction échoue et ne s’ouvre pas dans la langue cible. (12993)
- Certains fichiers sont manquants lors de l’utilisation des lignes de base en traduction. (13021)
