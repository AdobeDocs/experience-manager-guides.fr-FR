---
title: Utilisation de l’éditeur de cartes de base
description: Découvrez comment utiliser l’éditeur de cartes de base dans AEM Guides. Découvrez les fonctionnalités de l’éditeur de mappage de base au niveau de la carte et de la rubrique. Créez et modifiez des tableaux de relation dans un mappage DITA.
exl-id: 13da729d-e8f7-46ae-873a-1bfc32da974f
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1408'
ht-degree: 0%

---

# Utilisation de l’éditeur de cartes de base {#id1942CM005Y4}

L’éditeur de mappage de base (Basic Map Editor) offre une fonctionnalité de glisser-déposer simple pour ajouter des rubriques à partir de votre référentiel AEM afin de créer le mappage ou le signet DITA. Vous pouvez ajouter des rubriques imbriquées, des tables de relations \(reltable\), des informations d’attributs et de métadonnées, et également valider le mappage pour vérifier son exactitude.

>[!NOTE]
>
> Si votre administrateur a activé l’option Éditeur de cartes avancé, vous n’aurez pas accès à l’Éditeur de cartes de base. Par défaut, tous les fichiers de mappage s’ouvrent dans l’éditeur de mappage avancé.

Les sections suivantes décrivent les différentes fonctions disponibles dans l’éditeur de cartes de base.

## Ajout de rubriques à un fichier map {#id193CBL0505Z}

Une fois un fichier map créé, vous devez ajouter des rubriques au fichier map. À l’aide de l’éditeur de mappage de base, vous pouvez ajouter des rubriques, des tableaux de relation ou d’autres fichiers de mappage.

Effectuez les étapes suivantes pour créer votre fichier map :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de mappage à modifier.

1. Pour obtenir un verrou exclusif sur le fichier map, sélectionnez le fichier map et cliquez sur **Extraire**.

   >[!NOTE]
   >
   > Une fois que vous disposez d’un verrou exclusif sur un fichier de carte, les autres utilisateurs ne peuvent plus modifier la carte. Cependant, ils pourraient travailler sur les rubriques du fichier de mappage.

1. Une fois le fichier map sélectionné, cliquez sur **Modifier**.

   Le fichier map est ouvert pour modification dans l’éditeur de cartes. À l’aide de l’éditeur de cartes, vous créez un mappage à l’aide des rubriques actuellement disponibles qui s’affichent dans le rail Références .

   ![](images/dita-map-01.png){width="800" align="left"}

1. En utilisant la variable **Références** , accédez au dossier contenant les rubriques ou sous-plans à ajouter.

   >[!NOTE]
   >
   > Vous pouvez ajouter des rubriques ou des sous-plans à partir de n’importe quel dossier du rail Références .

1. Pour ajouter la première rubrique au mappage, faites glisser la rubrique sur l’éditeur de mappage de base.

   >[!NOTE]
   >
   > Après avoir ajouté le premier lien, le lien Ajouter une nouvelle référence est disponible lorsque vous passez la souris sur une rubrique existante dans la carte.

1. Pour ajouter des rubriques ou une sous-map suivantes, faites glisser la rubrique ou la sous-map vers l’emplacement requis dans la carte.

   Si vous ajoutez une sous-map à votre mappage DITA, la sous-map s’affiche sous la forme d’un lien dans le mappage DITA. Pour visualiser toutes les rubriques de la sous-carte, cliquez sur le lien de la sous-carte. Le contenu du sous-mapping s&#39;affiche dans un nouvel onglet.

   >[!NOTE]
   >
   > Si vous déposez une nouvelle rubrique sur une rubrique existante dans le mappage, vous obtenez un message sur le remplacement de la rubrique. Cliquez sur Oui si vous souhaitez remplacer la rubrique, puis sur Non si vous ne souhaitez pas remplacer la rubrique. Vous pouvez utiliser les touches CTRL+Z et CTRL+Y pour annuler ou rétablir toute modification dans la carte.

1. Cliquez sur **Enregistrer**.


## Fonctionnalités disponibles dans la barre d’outils de l’éditeur de cartes de base

La barre d’outils principale de l’éditeur de cartes de base vous permet d’effectuer les tâches suivantes :

![](images/ditamap-toolbar-actions.png){width="800" align="left"}

**R : Recherche**

Vous pouvez rechercher et inclure les rubriques requises dans la gestion des ressources numériques. Cliquez sur cette icône pour afficher la boîte de dialogue Rechercher :

![](images/search-dita-map.png){width="800" align="left"}

Saisissez les mots-clés à rechercher, ils correspondent dans le nom de fichier, le contenu et même les valeurs d’attribut de la rubrique. Une fois les résultats de recherche disponibles, sélectionnez la rubrique souhaitée\(s\) et cliquez sur le bouton Cocher pour ajouter les fichiers sélectionnés à la fin de la structure de votre carte. Vous pouvez filtrer les résultats de la recherche en spécifiant les paramètres Modifier la date .

**B : Groupe**

Cochez la case à gauche des rubriques, puis cliquez sur Regrouper dans la barre d’outils pour regrouper les rubriques sélectionnées. Pour plus d’informations sur le regroupement de rubriques, voir [topicgroup](https://docs.oasis-open.org/dita/v1.0/langspec/topicgroup.html) documentation dans la Spécification du langage OASIS DITA.

**C : Supprimer**

Cochez la case à gauche d’une rubrique et cliquez sur Supprimer dans la barre d’outils pour supprimer les rubriques sélectionnées de la carte.

**D : Afficher les nombres/Masquer les nombres**

Afficher la numérotation \(ou masquer\) pour les rubriques dans la carte.

**E : Valider**

Vérifiez si la carte est valide ou comporte des erreurs.

**F : Mode par défaut/Mode XML**

Dans le **Mode par défaut**, un clic sur un lien de rubrique affiche l’aperçu de la rubrique dans un nouvel onglet. Cliquez sur le bouton **Mode par défaut** change de mode en **Mode XML**. Dans **Mode XML**, cliquer n’importe où sur une ligne de rubrique affiche le code XML sous-jacent des références de rubrique dans la rubrique. Dans la vue XML source, une **Retrait automatique** qui réorganise le code XML dans un format présentable et facile à lire. Si vous modifiez manuellement une carte, la vue source effectue également des vérifications de validation. Si votre XML contient des erreurs, celles-ci sont surlignées dans la variable **Mode XML** et vous n’êtes pas autorisé à enregistrer le fichier de mappage DITA. Si vous souhaitez afficher le code XML pour la carte entière, cliquez n’importe où en dehors de la limite de la rubrique.


**Remarque :** En mode par défaut, vous pouvez utiliser les raccourcis clavier pour annuler \(`Ctrl+z`\) ou rétablir \(`Ctrl+y`\) la dernière action.


![](images/dita-map-invalid-source.png){width="650" align="left"}

**G : Propriétés de la carte**

Affichez la boîte de dialogue Propriétés de la carte dans laquelle vous pouvez définir les attributs et les informations de métadonnées de la carte. Pour ajouter un attribut, cliquez sur le bouton **Ajouter** dans le coin inférieur gauche de la boîte de dialogue pour obtenir le **Attribut** liste déroulante. Dans la liste, sélectionnez l’attribut à ajouter. Si l’attribut sélectionné a des valeurs prédéfinies spécifiées dans la DTD, ces valeurs seront présentées dans une nouvelle liste déroulante. Vous pouvez sélectionner une valeur dans la liste déroulante. S’il n’existe pas de valeur prédéfinie, une zone de texte s’affiche pour vous permettre de saisir une valeur pour l’attribut sélectionné.

![](images/map-properties.png){width="300" align="left"}

## Fonctionnalités disponibles au niveau de la rubrique dans l’éditeur de carte de base

Lorsque vous placez le pointeur de la souris sur une rubrique ou un fichier de sous-map dans l’éditeur de cartes de base, vous pouvez effectuer les tâches suivantes :

![](images/ditamap-actions.png){width="650" align="left"}

**A : Déplacer à gauche ou Déplacer à droite**

Cliquez sur les icônes de flèche gauche ou droite pour déplacer la rubrique vers la gauche ou la droite. Le déplacement d’une rubrique de cette manière en fait un enfant \(imbriqué\) ou un frère \(supprimez l’imbrication\) par rapport à la rubrique ci-dessus.

**B : Propriétés**

Cliquez sur l’icône Propriétés pour ouvrir la boîte de dialogue Propriétés de la référence de rubrique. Cette boîte de dialogue vous permet de définir les attributs de rubrique et les informations de métadonnées. Pour plus d’informations sur les métadonnées et les attributs de rubrique standard, voir la section [topicref](https://docs.oasis-open.org/dita/v1.2/os/spec/langref/topicref.html) documentation dans la Spécification du langage OASIS DITA.


![](images/map-properties-metadata.png){width="350" align="left"}

**C : Ajouter une nouvelle référence**

Cliquez sur l’icône Ajouter une nouvelle référence pour ajouter une nouvelle référence en tant que frère de la rubrique actuelle.

**D : Ajouter une nouvelle définition de clé**

Cliquez sur l’icône Clé pour ajouter une nouvelle définition de clé. Toute clé remplacée ou clé déjà définie dans la carte s’affiche en rouge. Si vous cliquez sur l’icône Propriétés d’une définition de clé, la boîte de dialogue Propriétés de Keydef s’affiche.

## Utilisation des tableaux de relation dans l’éditeur de mappage de base {#id1944B0I0COB}

Les éditeurs de carte d’AEM Guides sont dotés d’une puissante fonctionnalité qui vous permet de créer et de modifier des tableaux de relation dans votre carte DITA.

Effectuez les étapes suivantes pour utiliser les tableaux de relation dans l’éditeur de mappage de base :

1. Dans l’interface utilisateur d’Assets, accédez au mappage DITA dans lequel vous souhaitez créer le tableau de relation.

1. Cliquez sur le mappage DITA pour l’ouvrir dans la console de mappage DITA.

1. Sélectionnez la variable **Sujets** pour afficher la liste des rubriques disponibles dans le mappage DITA.

   >[!TIP]
   >
   > L’onglet Rubriques vous permet de télécharger le fichier de mappage avec ses dépendances. Pour plus d’informations, voir [Exportation d’un fichier de mappage DITA](authoring-download-assets.md#id218UBA00IXA).

1. Dans la barre d’outils principale, cliquez sur **Modifier**.

   Le fichier de mappage est ouvert dans l’éditeur de mappage de base.

1. Sélectionner **Reltable** dans la barre d’outils.

   ![](images/reltable.png){width="650" align="left"}

1. Faites glisser des rubriques de la liste des rubriques vers l’éditeur de table des matières.

   >[!NOTE]
   >
   > Vous pouvez ajouter des rubriques à partir de n’importe quel dossier du rail Références .

   ![](images/create-reltable.png){width="550" align="left"}

1. Pour ajouter un en-tête à votre tableau de relation, cliquez sur **Ajouter Relheader**.

1. Pour ajouter une colonne à votre tableau de relation, cliquez sur **Ajouter une colonne**.

   ![](images/complete-reltable.png){width="550" align="left"}

1. Cliquez sur **Enregistrer**.


Vous pouvez également effectuer les actions suivantes à partir de l’éditeur de table de relation :

**Suppression de lignes ou de colonnes**

Si vous souhaitez supprimer une colonne du tableau, cochez la case dans l’en-tête de colonne et cliquez sur Supprimer. Si vous souhaitez supprimer une ligne du tableau, cochez la case dans la première colonne de la ligne correspondante, puis cliquez sur Supprimer.

**Suppression d’une rubrique**

Si vous souhaitez supprimer une rubrique de votre tableau, cliquez sur l’icône croix en regard de la rubrique.

**Suppression de la table des relations**

Si vous souhaitez supprimer le tableau de relation, cliquez n’importe où en dehors du tableau de relation, puis cliquez sur Supprimer.

**Rubrique parente :**[ Utilisation de l’éditeur de cartes](map-editor.md)
