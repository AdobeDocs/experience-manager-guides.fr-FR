---
title: Ajouter et gérer des citations dans votre contenu
description: Ajoutez et gérez des citations dans AEM Guides. Découvrez comment appliquer, importer, filtrer, rechercher, modifier le style de la citation, modifier, prévisualiser, insérer, supprimer et générer une sortie de contenu avec des citations.
exl-id: 685d747d-e017-4350-a6bf-822fd55c76e8
feature: Authoring, Features of Web Editor
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '1887'
ht-degree: 0%

---

# Ajouter et gérer des citations dans votre contenu

Les citations sont des références à la source d’informations ajoutées à votre contenu. En utilisant des citations, vous pouvez créditer les auteurs des informations sources et aider les lecteurs à suivre les informations sources. Ajouter des citations rend votre contenu plus fiable et évite le plagiat. Ils permettent également d&#39;afficher du contenu bien documenté.

Dans AEM Guides, vous pouvez ajouter et importer des citations et les appliquer à votre contenu. Vous pouvez ajouter ces citations à partir de n’importe quelle source de livres, de sites web et de journaux.


AEM Guides vous aide à modifier, prévisualiser et trier vos citations. Après avoir ajouté vos citations dans le contenu, vous pouvez générer la sortie à l’aide du PDF natif. Vous pouvez également ajouter la bibliographie ou la page de références dans la sortie Native PDF.

AEM Guides prend en charge plusieurs styles de citations, comme Modern Language Association (MLA), American Psychological Association (APA), Chicago, Institute for Electric and Electronics Engineers (IEEE) et American Heart Association (AHA). Il est recommandé de les utiliser de manière claire et cohérente.


>[!NOTE]
>
>Actuellement, AEM Guides ne prend en charge que les PDF natifs pour les citations.


## Ajouter des citations

Pour ajouter des citations, procédez comme suit :

1. Sélectionnez la variable **Citations** ![icône citations](images/citations-icon.svg) dans le panneau de gauche.
La variable **Citations** s’ouvre.

   ![](images/citation-panel.png){width="300" align="left"}

1. Dans le **Citations** panneau, sélectionnez ![Icône Ajouter](images/Add_icon.svg). Dans la liste déroulante, vous pouvez choisir d’ajouter une nouvelle citation ou d’importer une citation.

1. Sélectionner **Nouvelle citation** pour ajouter une nouvelle citation.
La variable **Ajouter une citation** s’ouvre.

   ![panneau de citation dans l’éditeur web](images/citation-add.png) {width="300" align="left"}


1. Renseignez les champs du **Ajouter une citation** de la boîte de dialogue

   >[!NOTE]
   >
   >Vous pouvez également ajouter l&#39;ISBN, le DOI ou le PubMed ID. AEM Guides renseigne automatiquement les autres champs.

   | Livre | Site Web | Journal |
   | --- | ---|---|
   | **Source** <br> Dans la liste déroulante, sélectionnez la source de la citation en tant que Livre. | **Source**<br> Dans la liste déroulante, sélectionnez la source de la citation en tant que site web. | **Source** <br> Dans la liste déroulante, sélectionnez la source de la citation en tant que Journal. |
   | **Rechercher par** <br> Sélectionner **ISBN** ou **DOI** dans la liste déroulante pour rechercher l’ID numérique associé à la citation.  <br> DOI : identifiant d’objet numérique <br> ISBN : identificateur unique de livre numérique | **Rechercher par** <br> Sélectionner **DOI** dans la liste déroulante pour rechercher l’ID numérique associé à la citation. | **Rechercher par** <br> Sélectionner **DOI** ou PubMed ID dans la liste déroulante pour rechercher l’ID numérique associé à la citation. <br>  <br> |
   | **Auteur** <br> Ajoutez le prénom et le nom de l’auteur de la citation. Sélectionner ![](images/Add_icon.svg) pour ajouter d’autres noms. | **Auteur** <br> Ajoutez le prénom et le nom de l’auteur de la citation. Sélectionner ![](images/Add_icon.svg)  pour ajouter d’autres noms. | **Auteur** <br> Ajoutez le prénom et le nom de l’auteur de la citation. Sélectionner ![](images/Add_icon.svg)pour ajouter d’autres noms. |
   | **Titre** <br> Ajoutez le titre du livre. | **Titre** <br> Ajoutez le titre de la page web. | **Titre** <br> Ajoutez le titre de l’article. |
   | **Éditeur** <br> Ajoutez l&#39;éditeur du livre. | **Nom du site Web** <br> Ajoutez le nom du site web. | **Titre du journal** <br> Ajoutez le titre du travail dans lequel se trouve l’article. |
   | **Edition** <br> Ajoutez l&#39;édition du livre. | **URL** <br> Ajoutez le lien web du site web pour parcourir le contenu. | **Année** <br> Ajoutez l’année de publication de l’article. |
   | **Ville** <br> Ajoutez la ville de la publication. | **Date d’accès**<br> Ajoutez la date d&#39;accès au contenu du site web. | **Volume** <br> Ajoutez le volume du travail dans la série. |
   | **Éditeur** <br> Ajoutez le nom de l’éditeur du livre. | **Date de publication** <br> Ajoutez la date de publication du contenu du site web. | **Nombre** <br> Ajoutez le numéro du volume dans la série. |
   | **Année** <br> Ajoutez l&#39;année de publication du livre. | **Date de mise à jour** <br> Ajoutez la date à laquelle le contenu du site web est mis à jour. | **Pages** <br> Ajoutez le numéro de page ou la plage de pages dans laquelle se trouve l’article. |
   | **Version** <br> Ajoutez la version du livre. | **Identifiant unique** <br> Ajoutez un identifiant unique pour la citation. Un identifiant unique est l’identifiant unique de cette citation. | **URL** <br>Ajoutez le lien Web au journal. |
   | **Série** <br>Ajoutez la série du livre. |  | **Identifiant unique** <br> Ajoutez un identifiant unique pour la citation. Un identifiant unique est un identifiant unique pour cette citation. |
   | **URL**  <br>  Ajoutez le lien Web au livre. |
   | **Identifiant unique** <br> Ajoutez un identifiant unique pour la citation. Un identifiant unique est l’identifiant unique de cette citation. |





1. Sélectionnez **Terminé**.

   Une nouvelle citation est ajoutée au panneau Citation .

>[!NOTE]
>
> L’ajout d’un identifiant unique pour le champ de citation est obligatoire.  Vous ne pouvez pas modifier l’identifiant unique une fois la citation ajoutée.

## Importer des citations

Pour importer des citations, procédez comme suit :

1. Dans le panneau de gauche, sélectionnez **Citations** ![icône citations](images/citations-icon.svg).

   La variable **Citations** s’ouvre.

1. Dans le **Citations** panneau, sélectionnez ![Icône Ajouter](images/Add_icon.svg), puis sélectionnez **Importer** dans la liste déroulante.
1. Parcourez un fichier .bib depuis votre système et importez-le .

   >[!TIP]
   >
   > Une extension de nom de fichier .bib est un fichier de base de données bibliographique BibTeX. Il s’agit d’un fichier texte spécialement formaté qui répertorie les références à une source d’information particulière.

   Une fois le fichier importé, vous pouvez afficher les références dans le panneau des citations.

   >[!NOTE]
   > <ol><li> AEM Guides importe uniquement les citations uniques qui ne sont pas déjà présentes.
    &gt; <li> AEM Guides peuvent importer des citations à partir d’un livre, d’un journal ou d’un site Web. Actuellement, il ne prend pas en charge les citations d’autres sources.

## Gestion des citations

Les citations sont triées par ordre alphabétique dans le panneau de gauche. Recherchez les citations en fonction des sources à utiliser dans votre rubrique.

### Filtrer

Sélectionnez la variable **Filtrer** ![](images/filter-search-icon.svg) en regard de la barre de recherche et sélectionnez les options de la source dans la liste déroulante pour filtrer la liste de citations. Il permet des sélections simples et multiples.

* **Sources toutes**: affiche une liste complète des citations, y compris toutes les sources.

* **Livre**: affiche la liste des citations provenant de livres.

* **Site Web**: affiche la liste des citations provenant de sites web.

* **Journal**: affiche la liste des citations provenant des journaux.

### Recherche

Recherchez votre contenu dans la citation.

1. Dans le panneau de gauche, sélectionnez Citations.
La variable **Citations** s’ouvre.

1. Utilisez la barre de recherche pour rechercher la citation appropriée dans une liste longue.

### Changer le style de citation {#change-citation-style}

Votre administrateur système peut modifier le style des citations à partir de la fonction **Citations**  dans la liste déroulante **Paramètres généraux** dans le **Paramètres de l’éditeur**.
Ces styles déterminent la manière dont les citations apparaissent dans le volet d’aperçu ou dans la sortie du PDF natif.

Les options suivantes sont disponibles dans la liste déroulante :

| MLA | APA | Chicago | IEEE | AHA |
|---|---|---|---|---|
| Style d&#39;association de langues modernes <br> | Le style de l&#39;association psychologique américaine | Manuel de style de Chicago | Style de l&#39;Institut pour les ingénieurs électriques et électroniques | American Heartbeat Association Style |
| Exemple :<br> Crawford, Claire, et al. *Contenu émotionnel des souvenirs sombres*.Edité par Memory, vol 16, 2010, Amsterdam. | Exemple : <br> Crawford, C., J., &amp;, C. (2010). *Contenu émotionnel des souvenirs sombres* (505-16 éd.). 10.1080/09658210902067289 | Exemple : <br> Crawford, Claire, et al. *Contenu émotionnel des souvenirs sombres*. 505-16, 2010. | Exemple : <br> C. Crawford, J. et C. , *Contenu émotionnel des souvenirs sombres*. Amsterdam, 2010. | Exemple : <br> C. Crawford, J. et C. , *Contenu émotionnel des souvenirs sombres*. Amsterdam, 2010. |


## Modifier une citation

Pour éditer la citation, procédez comme suit :

1. Pointez sur le nom de la citation de la liste. Sélectionner  ![](images/options.svg) la valeur **Options** Icône

1. Sélectionner  **Modifier**.

La variable **Modifier la citation** s’ouvre.

1. Effectuez les modifications nécessaires. Sélectionner **Terminé**.
La citation sélectionnée est éditée.

>[!NOTE]
>
>Vous ne pouvez pas modifier l’identifiant unique une fois la citation ajoutée.

## Aperçu d’une citation

Pour prévisualiser une citation, procédez comme suit :

Pointez sur le nom de la citation de la liste. Sélectionner     ![](images/options.svg) **Options** Icône

1. Sélectionner **Aperçu**.
Vous pouvez prévisualiser le contenu et le format de la citation dans le volet d’aperçu.

   >[!NOTE]
   >
   >L’aperçu est basé sur le style de citation que votre administrateur a sélectionné dans le **Paramètres de l’éditeur**.

1. Cliquez n’importe où sur l’écran pour fermer la zone d’aperçu.

   ![](images/citation-preview.png){width="550" align="left"}

>[!NOTE]
>
> Vous pouvez également prévisualiser une citation insérée dans une rubrique à partir de l’interface utilisateur d’Assets ou de l’onglet Aperçu de l’éditeur web.

## Insérer des citations

Effectuez les étapes suivantes pour insérer des citations vers une rubrique :
1. Sélectionnez la rubrique dans le panneau du référentiel, puis double-cliquez pour l’ouvrir dans la fenêtre d’édition.
1. Placez le curseur à l’emplacement de la rubrique où vous souhaitez ajouter la citation.



Vous pouvez insérer des citations dans la rubrique à partir de la barre d’outils principale ou du panneau de gauche.

### Dans la barre d’outils principale

1. Sélectionnez la variable **Citations** ![icône citations ](images/citations-icon.svg) dans la barre d’outils principale.
1. Dans le **Citations** , sélectionnez la citation. Vous pouvez également sélectionner plusieurs citations.
   ![boîte de dialogue de citation](images/citation-dialog-main-toolbar.png){width="300" align="left"}
1. Vous pouvez filtrer les citations en saisissant les premiers alphabets dans le panneau de recherche du **Citation** de la boîte de dialogue

1. Cliquez sur **Terminé**.
La citation sélectionnée est ajoutée à l’emplacement du curseur dans votre rubrique.


### Dans le panneau de gauche

>[!NOTE]
> 
>Pour afficher la variable **Citations** dans le panneau de gauche, votre administrateur système doit sélectionner la variable **Citations** dans le **Panneaux** dans **Paramètres de l’éditeur**.

1. Sélectionner **Citations** ![icône citations ](images/citations-icon.svg) dans le panneau de gauche.
1. Faites glisser la citation depuis le **Citations** et déposez-le à l’emplacement approprié dans la rubrique.

   Vous pouvez également sélectionner **Insérer** de  ![](images/options.svg) **Options** pour insérer une citation.

   ![insérer des citations](images/citation-panel-insert.png)
1. Pour sélectionner plusieurs citations, cliquez avec le bouton droit sur une citation dans la rubrique et sélectionnez **Modifier la citation** dans le menu contextuel.
1. Sélectionnez les citations à insérer dans le **Citation** boîte de dialogue.
1. Sélectionner **Terminé** pour les ajouter à la rubrique.

Une fois que vous avez inséré des citations dans la rubrique, vous pouvez les prévisualiser dans l’éditeur web. Vous pouvez également publier du contenu avec des citations à l’aide du PDF natif.



## Supprimer une citation

Vous pouvez supprimer des citations à partir du panneau Destinations ou d’une rubrique dans laquelle vous avez inséré le lien.

### Suppression d’une citation du panneau Citations

Pour supprimer une citation du panneau Citations, procédez comme suit :

1. Pointez sur le nom de la citation de la liste.
1. Sélectionnez la variable ![](images/options.svg) **Options** Icône
1. Sélectionnez la variable   **Supprimer** ![](images/Delete_icon.svg).
La boîte de dialogue de confirmation s’ouvre.
1. Sélectionner **Oui**.
La citation sélectionnée est supprimée du panneau des citations.



### Suppression d’une citation d’une rubrique

Pour supprimer une citation déjà utilisée dans la rubrique, procédez comme suit :

Dans la rubrique , placez le curseur à la fin de la citation.

1. Cliquez avec le bouton droit sur une citation dans la rubrique et sélectionnez **Modifier la citation** dans le menu contextuel. La boîte de dialogue Citation s’ouvre.
   ![menu contextuel d’une citation](./images/modify-citation.png)

1. Vous pouvez choisir les citations à insérer dans le document.

   >[!NOTE]
   >
   >Les citations déjà utilisées dans la rubrique sont remplacées par les citations que vous sélectionnez dans la boîte de dialogue.


1. Sélectionnez **Terminé**.

## Générer la sortie du contenu avec les citations

Une fois que vous avez inséré des citations dans la rubrique, vous pouvez publier du contenu avec des citations à l’aide du PDF natif.

Dans la sortie du PDF natif, les citations apparaissent dans le contenu dans lequel vous les avez insérées. Vous pouvez également créer une page de bibliographie. Lorsque vous cliquez sur une citation, vous êtes redirigé vers la page de bibliographie.

Créez un **Citations** mise en page dans les modèles de PDF et incluez-la dans votre document. Toutes les citations utilisées dans le livre sont répertoriées sur une page qui apparaît dans la sortie du PDF. Pour en savoir plus sur la création d’une mise en page, voir [Création d’une mise en page](../native-pdf/components-pdf-template.md#create-page-layout).


Pour modifier l’affichage et l’aspect de la page de référence, voir [Personnalisation des modèles de PDF](../native-pdf/pdf-template.md).



### Appliquer le style de contenu à une citation

Appliquez la mise en forme à la citation lorsqu’elle est ajoutée à la rubrique.

1. Sélectionner **Feuilles de style** dans le **Modèles** d’un paramètre prédéfini de sortie du PDF natif.   Elle ouvre la fenêtre **STYLES** qui contient toutes les options de style.

1. Dans le panneau Rechercher, recherchez `<cite>`.

Pour en savoir plus sur les styles, voir [Utilisation des styles de contenu communs](../native-pdf/stylesheet.md).
