---
title: Notes de mise à jour de  [!DNL AEM Guides] version de mars 2022
description: Version de mars d' [!DNL Adobe Experience Manager Guides] as a Cloud Service
exl-id: 885edbb5-dfe4-4bdc-bb66-0df64addb094
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 1%

---

# Version de mars d’[!DNL Adobe Experience Manager Guides] as a Cloud Service

## Mise à niveau vers la version de mars

Mettez à niveau votre configuration actuelle d’[!DNL Adobe Experience Manager Guides] as a Cloud Service (plus tard appelée *[!DNL AEM Guides]as a Cloud Service*) en procédant comme suit :
1. Consultez le code Git des services cloud et passez à la branche configurée dans le pipeline des services cloud correspondant à l’environnement à mettre à niveau.
1. Mettez à jour `<dox.version>` propriété dans `/dox/dox.installer/pom.xml` fichier de votre code Git Cloud Services vers la version 2022.3.123.
1. Validez les modifications et exécutez le pipeline Cloud Services pour effectuer la mise à niveau vers la version de mars d’[!DNL AEM Guides] as a Cloud Service.

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par [!DNL AEM Guides] version de mars 2022 d’as a Cloud Service.

### FrameMaker et FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Non compatible | Mise à jour 2020 4 et versions ultérieures |
| | |


### Connecteur D&#39;Oxygène

| Version d’[!DNL AEM Guides] Cloud | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène |
| --- | --- | --- |
| 2022.3.0 | 2.4.0 | 2.4.0 |
|  |  |  |

*La ligne de base et les conditions créées dans AEM sont prises en charge dans les versions FMPS à compter de 2020.2.

## Nouvelles fonctionnalités et améliorations

### Nouveau tableau de bord de référence

[!DNL AEM Guides] version de mars d’as a Cloud Service fournit la fonctionnalité de ligne de base intégrée à l’éditeur web. Vous pouvez désormais créer des lignes de base à partir de l&#39;éditeur Web et les utiliser pour publier ou traduire des rubriques de différentes versions.

Remarque : pour le système mis à niveau, veuillez mettre à jour la dernière version de **ui_config.json** pour le profil de dossier.

Utilisez cette fonctionnalité pour créer une ligne de base avec une version spécifique des rubriques disponibles à une date et une heure spécifiques. En outre, vous obtenez la prise en charge de l’API pour créer ou mettre à jour une ligne de base avec un libellé défini pour une version des rubriques.

![onglet gestion de base](assets/baseline-manage.png)

Vous pouvez rechercher les fichiers en fonction de leurs noms ou de leur emplacement. Vous pouvez également filtrer les rubriques à afficher dans la fenêtre d&#39;édition de la ligne de base et les trier en fonction de colonnes spécifiques.

![onglet gestion de base](assets/baseline-filter.png)

Les performances du processus de création de la ligne de base ont été améliorées. Le processus de création des lignes de base est asynchrone. Vous pouvez donc continuer à modifier d&#39;autres fichiers dans l&#39;éditeur Web pendant la création de la ligne de base. Pour plus d&#39;informations, voir *Créer et gérer des lignes de base à partir de l&#39;éditeur web* dans le guide de l&#39;utilisateur.

Remarque : l&#39;onglet Ligne de base du tableau de bord des cartes est masqué par défaut. Votre administrateur peut activer l’onglet Ligne de base dans le tableau de bord des cartes.

### Amélioration du comportement d’actualisation de l’éditeur web

Les améliorations suivantes sont désormais disponibles avec l’opération d’actualisation du navigateur dans l’éditeur web :

* Vous obtenez maintenant la prise en charge pour actualiser le navigateur pendant que vous modifiez votre
contenu dans l’éditeur web. Si vous appuyez sur l’icône d’actualisation du navigateur pendant qu’un ou plusieurs fichiers avec
si des modifications non enregistrées sont ouvertes pour modification, vous êtes invité à enregistrer vos fichiers ou à annuler l’action d’actualisation.

* Même lors de l’actualisation du navigateur, les vues du panneau de gauche et du panneau de droite sont conservées.

* La rubrique active ou le plan DITA est rouverte dans la zone d&#39;édition du contenu.

### Améliorations de la publication

Le processus de publication a été amélioré avec la version de mars d’[!DNL AEM Guides] as a Cloud Service :

* Les références ont été respectées pour les métadonnées de sortie du site AEM. Vous pouvez également traiter les propriétés d’une version de base en tant que métadonnées. Si aucune ligne de base n’est définie, les propriétés de la dernière version sont traitées en tant que métadonnées.

* Les options **Nom de fichier** et **Arguments de ligne de commande DITA-OT** ont été ajoutées pour les paramètres prédéfinis de sortie HTML5, EPUB et Personnalisé. Vous pouvez maintenant spécifier le nom du fichier avec lequel vous souhaitez enregistrer la sortie. Vous pouvez également spécifier les arguments supplémentaires que DITA-OT doit traiter lors de la génération de la sortie.

## Problèmes résolus

Les bogues corrigés dans différentes zones sont répertoriés ci-dessous :

* Impossible d’ajouter des éléments frontend, backMATTER dans un bookmap à l’aide de la vue Auteur de l’éditeur web. (7652)
* L’arborescence de référence se rompt après la suppression d’une rubrique et l’exécution d’une opération de déplacement. (8804)
* Une exception est reçue lors de l’affichage du contenu après le chargement d’une ressource. (3638)
* Une erreur se produit lorsque les fichiers dont le dossier parent contient des caractères spéciaux dans le nom de fichier sont ouverts dans Oxygen (à l’aide du bouton **Modifier dans Oxygen**). (8918)
* L&#39;option **Localiser dans le référentiel** ne localise pas et ne met pas en évidence le plan DITA dans l&#39;éditeur XML. (8796)
* Le filtrage n’affiche pas les résultats appropriés lorsque plusieurs attributs sont ajoutés au contenu dans l’éditeur XML. (8795)
* Une erreur se produit lors de l’ajout d’un utilisateur en tant qu’administrateur dans le profil de dossier lorsque l’ID utilisateur est numérique. (8908)

## Problèmes connus

Adobe a identifié le problème connu suivant dans la version [!DNL AEM Guides] d’as a Cloud Service de mars.

* La suppression des libellés des références directes supprime également les libellés des références indirectes.

* Impossible de refléter le titre de ligne de base mis à jour sans actualiser manuellement le panneau de ligne de base.

* La fonction Aperçu de version du panneau Historique des versions n’affiche pas l’aperçu d’une rubrique sélectionnée.
