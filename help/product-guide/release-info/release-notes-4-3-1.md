---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans la version 4.3.1 d’Adobe Experience Manager Guides
description: Découvrez les correctifs et comment effectuer une mise à niveau vers la version 4.3.1 d’Adobe Experience Manager Guides
exl-id: 3fb6dc31-ec6e-40f5-ab3f-a6e591da315e
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 1%

---

# Version 4.3.1 d’Adobe Experience Manager Guides (octobre 2023)

Cette note de mise à jour couvre les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans la version 4.3.1 d’Adobe Experience Manager Guides (plus tard appelée *Experience Manager Guides*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version 4.3.1 d’Adobe Experience Manager Guides](./whats-new-4-3-1-release.md).

## Mise à niveau vers la version 4.3.1 de Experience Manager Guides


Vous pouvez facilement mettre à niveau votre version actuelle de Experience Manager Guides vers la version 4.3.1. Avant de procéder à la mise à niveau vers la version 4.3.1 de Experience Manager Guides, vous devez tenir compte des points suivants :
Vous pouvez mettre à niveau votre version actuelle de Experience Manager Guides vers la version 4.3.1


- Si vous utilisez la version 4.3.0, 4.2 ou 4.2.1, vous pouvez directement effectuer la mise à niveau vers la version 4.3.1.
- Si vous utilisez la version 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers la version 4.3.0, 4.2 ou 4.2.x avant de passer à la version 4.3.1.
- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant d’effectuer la mise à niveau vers la version 4.3.1.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à la version 3.8.5, reportez-vous à la section Mise à niveau de Experience Manager Guides dans le guide d’installation spécifique au produit.


>[!NOTE]
>
>Vous devez installer le pack de services AEM avant de mettre à niveau la version de Experience Manager Guides.

Pour plus d’informations, voir [Instructions de mise à niveau](../install-guide/upgrade-xml-documentation.md).

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par la version 4.3.1 de Experience Manager Guides.

### Adobe Experience Manager

**4.3.1 Non-UUID**
Version 6.5 Service Pack 18, 17, 16, 15 ou 14

**4.3.1 UUID**
Version 6.5 Service Pack 18, 17, 16, 15 ou 14

Pour plus d’informations, consultez la section *Exigences techniques* du guide Installation et configuration d’Adobe Experience Manager Guides .

### FrameMaker et FrameMaker Publishing Server

| Version | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.3.1 (Non-UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.3 ou version ultérieure |
| 4.3.1 (UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.4 ou version ultérieure |
| | | | | |

*La ligne de base et les conditions créées dans AEM sont prises en charge dans les versions FMPS à compter de 2020.2.

### Connecteur D&#39;Oxygène

| Version | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.3.1 (Non-UUID) | 2.3-standard-5 | 2.3-standard-5 | 1,6 | 1,6 |
| 4.3.1 (UUID) | 3.2-uuid-5 | 3.2-uuid-5 | 2,3 | 2,3 |
|  |  |   | | |



### Version du modèle de la base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu de composants Experience Manager Guides pour Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problèmes résolus

Les bogues corrigés dans différentes zones sont répertoriés ci-dessous :

### Création

- Les heures de l&#39;après-midi ne sont pas définies dans la **Date** pour la création des lignes de base. (12712)
- Impossible de coller le code JSON dans l’élément `<codeblock>` de l’éditeur web. (12326)
- Les modifications de version non enregistrées et les indicateurs correspondants ne s’affichent pas pour les fichiers volumineux. (11784)
- Lors de la modification en coréen, le premier caractère est remplacé par la valeur par défaut. (10049)

- Le préfixe est dupliqué dans le mode d’aperçu de l’éditeur web. (13133)
- `Choicetable` lignes ne sont pas affichées ou ne peuvent pas être sélectionnées. (12616)
- L’éditeur web renvoie des erreurs de validation dans des scénarios spécifiques lors de la création d’une rubrique à l’aide d’un schéma personnalisé. (12576)
- Les références au modèle de rubrique de dictionnaire ne créent pas de copie dans le dossier de contenu lors de la création d’un mappage à partir du modèle de mappage. (12150)

- La zone de recherche dans les plans DITA ne comporte pas de bouton Fermer. (11867)
- Lors de l’enregistrement de fichiers longs dans l’éditeur web, `DirtyChecker` renvoie une exception avec une longue trace de pile et remplit les fichiers journaux. (11860)
- La création de rubriques DITA requiert l&#39;autorisation Supprimer sur le nœud de dossier correspondant, bien que le mappage puisse être créé avec l&#39;autorisation Écriture. (11706)
- Web Editor affiche un titre incorrect en présence d’une barre oblique. (10949)

- Si le titre d’une rubrique contient une barre oblique « / », l’onglet de l’éditeur affiche uniquement les lettres qui suivent. (13455)
- L’aperçu de l’image ne disparaît pas après l’affichage de l’aperçu dans l’éditeur. (13454)
- Certaines versions existantes ou leurs libellés ne s’affichent pas dans l’historique des versions après la mise à niveau vers la version 4.x. (13247)
- Le panneau Historique des versions de l’interface utilisateur d’Assets affiche un horodatage incorrect pour le champ **Actuel**. (12624)
- La rubrique avec le titre conref n&#39;est pas résolue dans la vue Référentiel ou Carte.(13304)


### Publication

- PDF natif | L’ordre des rubriques n’est pas corrigé lors de la génération de la sortie PDF. (13157)
- PDF native| Aucune balise de style par défaut n’est disponible pour l’élément `<p>`. (12559)
- PDF natif | Les styles intégrés appliqués à la zone de contenu ne sont pas appliqués aux rubriques du sujet principal et du sujet arrière. (13510)
- L’attribut `DeliveryTarget` n’est pas propagé lors de la génération de la sortie du site AEM.  (13132)
- Le workflow **Publication** est bloqué lors de la génération de la sortie du site AEM pour le contenu présentant certaines erreurs. (12000)

- PDF natif | L’inclusion de plusieurs xréfs étend le texte au-delà de la largeur de colonne. (13004)
- PDF natif | Lorsque la rubrique et le titre ont le même ID, cela entraîne une génération incorrecte de la sortie PDF. (12644)
- PDF natif | Lors de l&#39;ajout d&#39;une classe outputclass à un élément `<topicref>` parent dans un plan DITA et de l&#39;application d&#39;un style personnalisé à la classe outputclass, le style est appliqué aux éléments du corps de la rubrique, y compris les titres de section. (12166)
- La publication incrémentielle ne fonctionne pas si un plan DITA comporte plusieurs variables DITA. (12117)
- Site AEM | Lors de la création d’une carte avec keydef pointant vers un topic en tant que variable et en ajoutant processing-role=resource-only, certaines pages sont inattendues. (12099)
- Si des ressources de la gestion des ressources numériques d’AEM sont utilisées dans une sortie autre que le site AEM, alors le « jcr :createdBy » des métadonnées ne reflète pas le nom de l’éditeur ou de l’utilisateur qui a effectué la dernière modification du plan ou de la rubrique DITA. (12090)
- AEM Sites | Un plan DITA avec topichead dans le titre de la navigation (avec des caractères non pris en charge) génère des URL de page incorrectes. (11978)
- PDF natif | Des problèmes se produisent à l’appui de topichead / topicmeta / navtitle dans FrontMATTER et BackMATTER. (11969)
- PDF natif | La génération de PDF pour les documents volumineux prend du temps. (11955)
- PDF natif | Le changement de nom d’un préréglage renvoie une exception NullPointerException lors de la génération d’une sortie PDF. (11889)
- Le contenu `<conref>` ne s’affiche pas dans la sortie PDF. (11131)
- Un espace supplémentaire est ajouté dans les éléments `<div>` lors du basculement entre la vue Auteur et Source dans l’éditeur de mise en page. (10750)
- Le contenu répliqué sur AEM Cloud Manager n’est pas visible sur l’instance de publication. (9564)


### Gestion

- L’historique des versions ne s’affiche pas même si la propriété `dc:format` n’est pas présente pour une ressource. (10463)
- La référence au contenu consiste à copier-coller des fichiers DITA rompus lorsque l&#39;ID de rubrique est différent du GUID. (12614)
- Dans les références dynamiques, la liste des libellés n&#39;est pas extraite des références directes de la copie de travail d&#39;un plan DITA. (11917)
- La ligne de base affiche un nombre incorrect de fichiers sur le tableau de bord Mapper lors de l’utilisation de la fonctionnalité Parcourir toutes les rubriques. (13265)
- Dans l&#39;éditeur Web, la ligne de base affiche le titre de la version précédente au lieu de la version sélectionnée du fichier DITA. (13444)

### Révision

- La révision d&#39;un sujet affiche des commentaires incorrects. (13453)
- Le bouton Fermer de la page Réviser de Experience Manager Guides permet d’accéder à la page d’accueil d’AEM. (13535)
- Les pièces jointes ne s’affichent pas dans le panneau de droite de l’éditeur pour une rubrique en cours de révision. (13011)



### Traduction

- La ligne de base exportée à partir du tableau de bord **Traduction** échoue et ne s’ouvre pas dans la langue cible. (13466)

- De nouveaux projets de traduction sont créés au lieu d’ajouter de nouvelles tâches aux projets de traduction existants sélectionnés.  (10214)
- Le titre du fichier traduit s’affiche à la place du titre du fichier source. (11630)
- L’approbation automatique ne fonctionne pas toujours et des exceptions se produisent si une valeur incorrecte est définie sur Statut de traduction. (13607)
- La ligne de base exportée à partir du tableau de bord de traduction échoue et ne s’ouvre pas dans la langue cible. (12993)
- Certains fichiers sont manquants lors de l’utilisation des références dans la traduction. (13021)
