---
title: Panneau droit dans l’éditeur
description: Découvrez le panneau Droit dans l’éditeur. Découvrez l’interface et les fonctionnalités de l’éditeur dans Adobe Experience Manager Guides.
feature: Authoring, Features of Web Editor
role: User
exl-id: 6a0f4ed2-6eca-4b3c-bd3a-3f72f6919b36
source-git-commit: ffc9a9e15f11e7059822b7cf6d4707b83d15a4f4
workflow-type: tm+mt
source-wordcount: '965'
ht-degree: 1%

---

# Panneau droit dans l’éditeur

Le panneau de droite contient des informations sur le document sélectionné.

>[!NOTE]
>
> Le panneau de droite est redimensionnable. Pour redimensionner le panneau, placez le curseur sur la limite du panneau, le curseur se transforme en flèche à deux pointes, sélectionnez et faites glisser pour redimensionner la largeur du panneau.

Le panneau de droite vous donne accès aux fonctionnalités suivantes :

- [Propriétés du contenu](#content-properties)
- [Propriétés du fichier](#file-properties)
- [Révision](#review)
- [Suivi des modifications](#track-changes)
- [Schematron](#schematron)

## Propriétés du contenu

Vous pouvez accéder à la fonction **Propriétés du contenu** en sélectionnant l’icône **Propriétés du contenu** dans le panneau de droite. Le panneau **Propriétés du contenu** contient des informations sur le type d’élément actuellement sélectionné dans le document et ses attributs.

**Type** : vous pouvez afficher et sélectionner les balises de la hiérarchie complète pour la balise active dans la liste déroulante.

**Attributs** : le panneau déroulant **Attributs** est disponible en vues Disposition, Auteur et Source. Vous pouvez facilement ajouter, modifier ou supprimer les attributs.

<details>
    <summary> Étapes d’ajout d’attributs </summary>


1. Sélectionnez **Ajouter**.

   ![attributs dans les propriétés du contenu](images/properties-tab-attributes_cs.png){width="300" align="left"}

1. Dans le panneau déroulant **Attribut**, sélectionnez l’attribut dans la liste déroulante et spécifiez une valeur d’attribut.  Sélectionnez ensuite **Ajouter**.

   ![panneau attributs avec plusieurs attributs ](images/attributes-multiple-properties.png){width="300" align="left"}

1. Pour modifier l’attribut, passez la souris dessus et sélectionnez **Modifier** ![icône-d’édition](images/edit_pencil_icon.svg).

1. Pour supprimer l’attribut, passez la souris dessus et sélectionnez **Supprimer** ![icône-de-suppression](images/Delete_icon.svg).

</details>


>[!NOTE]
>
> Même si votre rubrique contient du contenu référencé, vous pouvez y ajouter des attributs à l’aide du panneau des propriétés.

Si votre administrateur a créé un profil pour les attributs, vous obtiendrez ces attributs ainsi que leurs valeurs configurées. À l’aide du panneau Propriétés du contenu , vous pouvez choisir ces attributs et les affecter au contenu approprié dans votre rubrique. Vous pouvez ainsi également créer du contenu conditionnel, qui peut ensuite être utilisé pour créer une sortie conditionnelle. Pour plus d’informations sur la génération d’une sortie à l’aide de paramètres prédéfinis conditionnels, voir [Utiliser des paramètres prédéfinis de condition](generate-output-use-condition-presets.md#).



## Propriétés du fichier

Affichez les propriétés du fichier sélectionné en sélectionnant l’icône Propriétés du fichier dans le panneau de droite. La fonction Propriétés du fichier est disponible dans les quatre modes ou vues : Disposition, Auteur, Source et Aperçu.

Les propriétés du fichier comportent les deux sections suivantes :

**Général**

La section Général vous donne accès aux fonctionnalités suivantes :

![file-properties](images/file-properties-general.png){width="300" align="left"}

- **Nom de fichier** : affiche le nom de fichier de la rubrique sélectionnée. Le nom du fichier est lié par un lien hypertexte à la page des propriétés du fichier sélectionné.
- **ID** : affiche l’ID de la rubrique sélectionnée.
- **Balises** : il s’agit des balises de métadonnées de la rubrique. Elles sont définies dans le champ de balises de la page de propriétés. Vous pouvez les saisir ou les sélectionner dans la liste déroulante.  Les balises s’affichent sous la liste déroulante. Pour supprimer une balise, sélectionnez l’icône en forme de croix en regard de la balise.
- **Modifier plus de propriétés** : vous pouvez modifier d’autres propriétés à partir de la page des propriétés du fichier.
- **Langue** : affiche la langue de la rubrique. Elle est définie à partir du champ langue de la page des propriétés.
- **Créé le** : affiche la date et l’heure de création de la rubrique.
- **Modifié le** : affiche la date et l’heure de modification de la rubrique.
- **Verrouillé par** : affiche l’utilisateur qui a verrouillé la rubrique.
- **État du document** : vous pouvez sélectionner et mettre à jour l’état du document de la rubrique actuellement ouverte. Pour plus d’informations, voir [État du document](web-editor-document-states.md#).

>[!NOTE]
>
> Vous pouvez copier dans le presse-papiers les valeurs d’attribut des différents champs des propriétés du fichier.

**Références**

La section Références vous donne accès aux fonctionnalités suivantes :

![](images/file-properties-references.png){width="300" align="left"}

- **Utilisé dans** : le champ Utilisé dans les références répertorie les documents dans lesquels le fichier actuel est référencé ou utilisé.
- **Liens sortants :** les liens sortants répertorient les documents auxquels il est fait référence dans le document actif.

Par défaut, vous pouvez afficher les fichiers par titres. Pointez sur un fichier pour afficher le titre du fichier et son chemin d’accès sous forme d’info-bulle.

>[!NOTE]
>
> En tant qu’administrateur, vous pouvez également choisir d’afficher la liste des fichiers par nom de fichier dans l’éditeur. Sélectionnez l’option **Nom de fichier** de la section **Configuration de l’affichage des fichiers de l’éditeur** dans **Préférences utilisateur**.

>[!NOTE]
>
> Toutes les références Utilisé(e) dans et Sortant renvoient vers les documents via un lien hypertexte. Vous pouvez facilement ouvrir et modifier les documents liés.

Outre l’ouverture de fichiers, vous pouvez également effectuer de nombreuses actions à l’aide du menu **Options** dans la section Références . Vous pouvez effectuer entre autres les actions suivantes : Modifier, Prévisualiser, Copier l’UUID, Copier le chemin d’accès, Ajouter aux collections et Propriétés.

## Révision

Lorsque vous sélectionnez l’icône Réviser , vous ouvrez le panneau de révision dans lequel vous pouvez sélectionner une tâche de révision pour le document actuellement ouvert et afficher les commentaires.

![](images/review-panel-before-opening.png){width="300" align="left"}

Si vous avez créé plusieurs projets de révision, vous pouvez en sélectionner un dans la liste déroulante et accéder aux commentaires de révision.

Grâce au panneau de révision, vous pouvez afficher et publier les réponses aux commentaires donnés sur le sujet. Vous pouvez accepter ou rejeter les commentaires un par un.

>[!NOTE]
>
> La zone de commentaire et la zone de réponse prennent en charge les entrées multilignes et permettent aux utilisateurs de les développer selon leurs besoins pour fournir des commentaires complets ainsi qu’une réponse détaillée aux commentaires. Vous pouvez utiliser **Maj** + **Entrée** pour accéder à la ligne suivante lors de la rédaction des commentaires ou des réponses.

Pour plus d’informations, voir [Commentaires de révision d’adresse](review-address-review-comments.md#).

## Suivi des modifications

Grâce à la fonction Modifications suivies du panneau de droite, vous pouvez afficher les informations de toutes les mises à jour effectuées dans un document. Vous pouvez également rechercher les mises à jour spécifiques apportées au document.

>[!NOTE]
>
> La fonction Suivi des modifications affiche toutes les mises à jour qui ont été suivies à l’aide de la fonction Activer/désactiver le suivi des modifications de la [barre d’onglets](./web-editor-tab-bar.md).

## Schematron

« Schéma » fait référence à un langage de validation basé sur des règles utilisé pour définir des tests pour un fichier XML. L’éditeur prend en charge les fichiers Schematron. Vous pouvez importer les fichiers Schematron et les modifier également dans l&#39;éditeur. À l&#39;aide d&#39;un fichier Schematron, vous pouvez définir certaines règles, puis les valider pour une rubrique DITA ou une carte.

Découvrez comment utiliser les fichiers Schematron dans Experience Manager Guides. Pour plus d&#39;informations, consultez la section [Prise en charge des fichiers Schematron](./support-schematron-file.md).



**Rubrique parente :**&#x200B;[ Présentation de l’éditeur](web-editor.md)
