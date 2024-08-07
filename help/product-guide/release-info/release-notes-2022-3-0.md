---
title: Notes de mise à jour de la version de  [!DNL AEM Guides], mars 2022
description: Version de mars de [!DNL Adobe Experience Manager Guides] as a Cloud Service
exl-id: 885edbb5-dfe4-4bdc-bb66-0df64addb094
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 1%

---

# Version de mars de [!DNL Adobe Experience Manager Guides] as a Cloud Service

## Mise à niveau vers la version de mars

Mettez à niveau votre configuration actuelle [!DNL Adobe Experience Manager Guides] as a Cloud Service (plus tard appelée *[!DNL AEM Guides]as a Cloud Service*) en procédant comme suit :
1. Extrayez le code Git des Cloud Service et passez à la branche configurée dans le pipeline Cloud Service correspondant à l’environnement que vous souhaitez mettre à niveau.
1. Mettez à jour la propriété `<dox.version>` du fichier `/dox/dox.installer/pom.xml` de votre code Git Cloud Service vers la version 2022.3.123.
1. Validez les modifications et exécutez le pipeline Cloud Service pour effectuer la mise à niveau vers la version de mars de l’as a Cloud Service [!DNL AEM Guides].

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité des applications logicielles prises en charge par la version as a Cloud Service de [!DNL AEM Guides] de mars 2022.

### FrameMaker et FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Non compatible | Mise à jour 4 et ultérieure 2020 |
| | |


### Connecteur Oxygen

| [!DNL AEM Guides] Version cloud | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen |
| --- | --- | --- |
| 2022.3.0 | 2.4.0 | 2.4.0 |
|  |  |  |

*Les conditions de base et créées dans AEM sont prises en charge dans les versions FMPS à partir de 2020.2.

## Nouvelles fonctionnalités et améliorations

### Nouveau tableau de bord de ligne de base

[!DNL AEM Guides] La version de mars as a Cloud Service fournit la fonctionnalité de ligne de base intégrée dans l’éditeur web. Vous pouvez désormais créer des lignes de base à partir de l’éditeur Web et les utiliser pour publier ou traduire des rubriques de différentes versions.

Remarque : Pour le système mis à niveau, mettez à jour la dernière version de **ui_config.json** pour le profil de dossier.

Utilisez cette fonction pour créer une ligne de base avec une version spécifique des rubriques disponibles à une date et une heure spécifiques. En outre, vous obtenez la prise en charge de l’API pour créer ou mettre à jour une ligne de base avec un libellé défini pour une version de rubriques.

![Onglet de gestion de ligne de base](assets/baseline-manage.png)

Vous pouvez rechercher les fichiers en fonction de leur nom ou de leur emplacement. Vous pouvez également filtrer les rubriques à afficher dans la fenêtre d&#39;édition de ligne de base et les trier selon des colonnes spécifiques.

![Onglet de gestion de ligne de base](assets/baseline-filter.png)

Les performances du processus de création de ligne de base ont été améliorées. Le processus de création des lignes de base est asynchrone. Vous pouvez donc continuer à modifier d’autres fichiers dans l’éditeur web pendant la création de la ligne de base. Pour plus d’informations, voir *Création et gestion de lignes de base à partir de l’éditeur web* dans le Guide de l’utilisateur.

Remarque : l’onglet Ligne de base du tableau de bord de carte est masqué par défaut. Votre administrateur peut activer l’onglet Ligne de base dans le tableau de bord de mappage.

### Amélioration du comportement d’actualisation de l’éditeur web

Les améliorations suivantes sont désormais disponibles avec l’opération d’actualisation du navigateur dans l’éditeur web :

* Vous obtenez maintenant la prise en charge d’actualiser le navigateur pendant que vous modifiez votre
contenu dans l’éditeur Web. Si vous appuyez sur l’icône d’actualisation du navigateur pendant qu’un ou plusieurs fichiers contiennent
les modifications non enregistrées sont ouvertes pour modification. vous êtes invité à enregistrer vos fichiers ou à annuler l’action d’actualisation.

* Même lors de l’actualisation du navigateur, les vues du panneau de gauche et du panneau de droite sont conservées.

* La rubrique active ou le mappage DITA est rouvert dans la zone de modification du contenu.

### Améliorations apportées à la publication

Le processus de publication a été amélioré avec la version as a Cloud Service de [!DNL AEM Guides] de mars :

* Les lignes de base ont été respectées pour les métadonnées de la sortie AEM site. Vous pouvez également traiter les propriétés d’une version de ligne de base en tant que métadonnées. Si aucune ligne de base n’est définie, les propriétés de la dernière version sont traitées comme des métadonnées.

* Les options **Nom de fichier** et **Arguments de ligne de commande DITA-OT** ont été ajoutées pour les paramètres prédéfinis de sortie personnalisés, HTML5 et EPUB. Vous pouvez maintenant spécifier le nom de fichier avec lequel vous souhaitez enregistrer la sortie. Vous pouvez également spécifier les arguments supplémentaires que DITA-OT doit traiter lors de la génération de la sortie.

## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :

* Impossible d’ajouter de la matière frontale, des éléments de fond dans un plan de navigation à l’aide de la vue Auteur de l’éditeur web. (7652)
* Arborescence de référence après la suppression d’une rubrique et l’exécution d’une opération de déplacement. (8804)
* Une exception est reçue lors de l’affichage du contenu après le téléchargement d’une ressource. (3638)
* Une erreur se produit lorsque des fichiers dont le dossier parent contient des caractères spéciaux dans le nom du fichier sont ouverts dans Oxygen (à l’aide du bouton **Modifier dans Oxygen** ). (8918)
* L’option **Locate In Repository** ne localise pas et ne met pas en surbrillance le mappage DITA dans l’éditeur XML. (8796)
* Le filtrage n’affiche pas les résultats appropriés lorsque plusieurs attributs sont ajoutés au contenu dans l’éditeur XML. (8795)
* Une erreur se produit lors de l’ajout d’un utilisateur en tant qu’administrateur dans le profil de dossier lorsque l’ID utilisateur est numérique. (8908)

## Problèmes connus

Adobe a identifié le problème connu suivant dans la version de mars as a Cloud Service de [!DNL AEM Guides].

* La suppression des libellés sur les références directes supprime également les libellés des références indirectes.

* Impossible de refléter le titre de ligne de base mis à jour sans actualiser manuellement le panneau de ligne de base.

* La fonction d’aperçu de version du panneau Historique de version n’affiche pas l’aperçu d’une rubrique sélectionnée.
