---
title: Ajouter et gérer des citations dans votre contenu
description: Ajouter et gérer des citations dans AEM Guides. Découvrez comment appliquer, importer, filtrer, rechercher, modifier le style de citation, modifier, prévisualiser, insérer, supprimer et générer une sortie de contenu avec des citations.
exl-id: 685d747d-e017-4350-a6bf-822fd55c76e8
feature: Authoring, Features of Web Editor
role: User
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1890'
ht-degree: 0%

---

# Ajouter et gérer des citations dans votre contenu

Les citations sont des références à la source d’informations ajoutée à votre contenu. À l’aide de citations, vous pouvez créditer les auteurs des informations sources et aider les lecteurs à effectuer un suivi sur ces informations. L&#39;ajout de citations rend votre contenu plus fiable et empêche le plagiat. Ils vous permettent également d’afficher du contenu bien documenté.

Dans Adobe Experience Manager Guides, vous pouvez ajouter et importer des citations et les appliquer à votre contenu. Vous pouvez ajouter ces citations à partir de n’importe quelle source de livres, de sites web et de revues.


Experience Manager Guides vous aide à modifier, prévisualiser et trier vos citations. Après avoir ajouté vos citations dans le contenu, vous pouvez générer la sortie à l’aide du PDF natif. Vous pouvez également ajouter la page de bibliographie ou de références dans la sortie Native PDF.

Experience Manager Guides prend en charge plusieurs styles de citations, tels que Modern Language Association (MLA), American Psychological Association (APA), Chicago, Institute for Electrical and Electronics Engineers (IEEE) et American Heart Association (AHA). Il est recommandé de les utiliser de manière claire et cohérente.


>[!NOTE]
>
>Actuellement, Experience Manager Guides ne prend en charge que le PDF natif pour les citations.


## Ajouter des citations

Pour ajouter des citations, procédez comme suit :

1. Sélectionnez l’icône **Citations** ![icône de citations](images/citations-icon.svg) dans le panneau de gauche.

   Le panneau **Citations** s’ouvre.

   ![](images/citation-panel.png){width="350" align="left"}

1. Dans le panneau **Citations**, sélectionnez ![Ajouter une icône](images/Add_icon.svg). Dans la liste déroulante, vous pouvez choisir d’ajouter une nouvelle citation ou d’importer une citation.

1. Sélectionnez **Nouvelle citation** pour ajouter une nouvelle citation.

   La boîte de dialogue **Ajouter une citation** s’ouvre.

   ![Panneau de citation dans l’éditeur web](images/citation-add.png) {width="300" align="left"}


1. Renseignez les champs de la boîte de dialogue **Ajouter une citation**.

   >[!NOTE]
   >
   >Vous pouvez également ajouter l’ISBN ou l’ID DOI ou PubMed. AEM Guides renseigne automatiquement les autres champs.

   | Livre | Site Web | Journal |
   | --- | ---|---|
   | **Source** <br> Dans la liste déroulante, sélectionnez la source de la citation sous forme de livre. | **Source**<br> Dans la liste déroulante, sélectionnez la source de la citation en tant que site Web. | **Source** <br> Dans la liste déroulante, sélectionnez la source de la citation en tant que Journal. |
   | **Rechercher par** <br> Sélectionnez **ISBN** ou **DOI** dans la liste déroulante pour rechercher l’identifiant numérique associé à la citation.  <br> DOI : Identifiant d’objet numérique <br> ISBN : Identifiant de livre numérique unique | **Rechercher par** <br> Sélectionnez **DOI** dans la liste déroulante pour rechercher l’identifiant numérique associé à la citation. | **Rechercher par** <br> Sélectionnez **DOI** ou ID PubMed dans la liste déroulante pour rechercher l’ID numérique associé à la citation. <br>  <br> |
   | **Auteur** <br> ajoutez le prénom et le nom de l’auteur de la citation. Sélectionnez ![](images/Add_icon.svg) pour ajouter d’autres noms. | **Auteur** <br> ajoutez le prénom et le nom de l’auteur de la citation. Sélectionnez ![](images/Add_icon.svg) pour ajouter d’autres noms. | **Auteur** <br> ajoutez le prénom et le nom de l’auteur de la citation. Sélectionnez ![](images/Add_icon.svg) pour ajouter d’autres noms. |
   | **Titre** <br> ajoutez le titre du livre. | **Titre** <br> ajoutez le titre de la page web. | **Titre** <br> ajoutez le titre de l’article. |
   | **Éditeur** <br> Ajoutez l&#39;éditeur du livre. | **Nom du site web** <br> ajoutez le nom du site web. | **Titre du journal** <br> ajoutez le titre de l’œuvre dans laquelle se trouve l’article. |
   | **Edition** <br> Ajoutez l&#39;édition du livre. | **URL** <br> Ajoutez le lien web du site web pour parcourir le contenu. | **Année** <br> ajoutez l’année de publication de l’article. |
   | **Ville** <br> ajoutez la ville de la publication. | **Date d’accès**<br> Ajoutez la date d’accès au contenu du site Web. | **Volume** <br> ajoutez le volume du travail de la série. |
   | **Éditeur** <br> Ajoutez le nom de l&#39;éditeur du livre. | **Date de publication** <br> ajoutez la date de publication du contenu du site web. | **Numéro** <br> ajoutez le numéro du volume dans la série. |
   | **Année** <br> Indiquez l&#39;année de publication de l&#39;ouvrage. | **Date de mise à jour** <br> ajoutez la date à laquelle le contenu du site web est mis à jour. | **Pages** <br> ajoutez le numéro de page ou la plage de pages où se trouve l’article. |
   | **Version** <br> Ajoutez la version du livre. | **ID unique** <br> ajoutez un ID unique pour la citation. Un ID unique est un identifiant unique pour cette citation. | **URL** <br>Ajoutez le lien web au journal. |
   | **Série** <br>Ajoutez la série du livre. |  | **ID unique** <br> ajoutez un ID unique pour la citation. Un ID unique est un identifiant unique pour cette citation. |
   | **URL** <br> Ajoutez le lien web au livre. |  |  |
   | **ID unique** <br> ajoutez un ID unique pour la citation. Un ID unique est un identifiant unique pour cette citation. |  |  |

1. Sélectionnez **Terminé**.

   Une nouvelle citation est ajoutée au panneau Citation .

>[!NOTE]
>
> L’ajout d’un ID unique pour le champ de citation est obligatoire.  Vous ne pouvez pas modifier l’ID unique une fois la citation ajoutée.

## Importer les citations

Pour importer des citations, procédez comme suit :

1. Dans le panneau de gauche, sélectionnez **Citations** ![icône de citations](images/citations-icon.svg).

   Le panneau **Citations** s’ouvre.

1. Dans le panneau **Citations**, sélectionnez ![Ajouter une icône](images/Add_icon.svg), puis sélectionnez **Importer** dans la liste déroulante.
1. Parcourez un fichier .bib à partir de votre système et importez-le .

   >[!TIP]
   >
   > Une extension de fichier .bib est un fichier BibTeX Bibliographical Database. Il s’agit d’un fichier texte spécialement formaté qui répertorie les références à propos d’une source d’information particulière.

   Une fois le fichier importé, vous pouvez afficher les références dans le panneau des citations.

   >[!NOTE]
   > <ol><li> Experience Manager Guides importe uniquement les citations uniques qui ne sont pas déjà présentes.
   > &gt; <li> Experience Manager Guides peut importer des citations d’un livre, d’un journal ou d’un site web. Actuellement, il ne prend pas en charge les citations provenant d’autres sources.

## Gérer les citations

Les citations sont triées par ordre alphabétique dans le panneau de gauche. Recherchez les citations en fonction des sources à utiliser dans votre rubrique.

### Filtrer

Sélectionnez l’icône **&#x200B;**&#x200B;Filtrer![](images/filter-search-icon.svg) à côté de la barre de recherche et sélectionnez les options sources dans la liste déroulante pour filtrer la liste de citations. Il permet des sélections uniques et multiples.

* **Toutes les sources** : affiche une liste complète des citations, y compris toutes les sources.

* **Livre** : il affiche la liste des citations provenant de livres.

* **Site Web** : affiche la liste des citations provenant de sites Web.

* **Journal** : affiche la liste des citations provenant des journaux.

### Recherche

Recherchez la citation de votre contenu.

1. Dans le panneau de gauche, sélectionnez Citations.
Le panneau **Citations** s’ouvre.

1. Utilisez la barre de recherche pour rechercher la citation appropriée dans une longue liste.

### Modifier le style de citation {#change-citation-style}

Votre administrateur système peut modifier le style des citations à partir de la liste déroulante **Citations** de l’onglet **Général** dans les **Paramètres**.
Ces styles déterminent la manière dont les citations apparaissent dans le volet d’aperçu ou dans la sortie Native PDF.

Les options suivantes sont disponibles dans la liste déroulante :

| DÉPUTÉ PROVINCIAL | APA | Chicago | IEEE | AHA |
|---|---|---|---|---|
| <br> de style de l’association de langue moderne | Style de l&#39;American Psychological Association | Manuel de style de Chicago | Style de l&#39;Institut des ingénieurs en électricité et électronique | Style de l&#39;American Heart Association |
| Exemple : <br> Crawford, Claire, et al. *Emotional Content of Dark Memories*.Edité par Memory, vol 16, 2010, Amsterdam. | Exemple : <br> Crawford, C., J., &amp; , C. (2010). *Emotional Content of Dark Memories* (505-16 éd.). 10.1080/ 09658210902067289 | Exemple : <br> Crawford, Claire, et al. *Contenu émotionnel des souvenirs sombres*. 505-16, 2010. | Exemple : <br> C. Crawford, J. , et C. , *Contenu émotionnel des souvenirs sombres*. Amsterdam, 2010. | Exemple : <br> C. Crawford, J. , et C. , *Contenu émotionnel des souvenirs sombres*. Amsterdam, 2010. |


## Modifier une citation

Pour modifier la citation, procédez comme suit :

1. Survolez le nom de la citation dans la liste. Sélectionnez ![](images/options.svg) l’icône **Options**.

1. Sélectionnez **Modifier**.

La boîte de dialogue **Modifier la citation** s’ouvre.

1. Effectuez les modifications nécessaires. Sélectionnez **Terminé**.
La citation sélectionnée est modifiée.

>[!NOTE]
>
>Vous ne pouvez pas modifier l’ID unique une fois la citation ajoutée.

## Prévisualiser une citation

Pour prévisualiser une citation, procédez comme suit :

Survolez le nom de la citation dans la liste. Sélectionner     ![](images/options.svg) icône **Options**.

1. Sélectionnez **Aperçu**.
Vous pouvez prévisualiser le contenu et le format de la citation dans le volet de prévisualisation.

   >[!NOTE]
   >
   >L’aperçu est basé sur le style de citation sélectionné par votre administrateur dans les **Paramètres**.

1. Sélectionnez n’importe où sur l’écran pour fermer la zone d’aperçu.

   ![](images/citation-preview.png){width="550" align="left"}

>[!NOTE]
>
> Vous pouvez également prévisualiser une citation insérée dans une rubrique à partir de l’interface utilisateur d’Assets ou de l’onglet Aperçu de l’éditeur.

## Insérer des citations

Pour insérer des citations dans une rubrique, procédez comme suit :
1. Sélectionnez la rubrique dans le panneau Référentiel, puis double-cliquez pour l’ouvrir dans la fenêtre d’édition.
1. Placez le curseur à l&#39;emplacement du sujet où vous souhaitez ajouter la citation.



Vous pouvez insérer des citations sur le sujet à partir de la barre d’outils principale ou du panneau de gauche.

### Dans la barre d’outils principale

1. Sélectionnez l’icône **&#x200B;**&#x200B;Citations![&#x200B; &#x200B;](images/citations-icon.svg)citations dans la barre d’outils principale.
1. Dans la boîte de dialogue **Citations**, choisissez la citation. Vous pouvez également sélectionner plusieurs citations.
   ![boîte de dialogue de citation](images/citation-dialog-main-toolbar.png){width="300" align="left"}
1. Vous pouvez filtrer les citations en tapant les premiers caractères alphabétiques dans le panneau de recherche de la boîte de dialogue **Citation**.

1. Sélectionnez **Terminé**.
La citation sélectionnée est ajoutée à l&#39;emplacement du curseur dans votre rubrique.


### Dans le panneau de gauche

>[!NOTE]
> 
>Pour afficher l’icône **Citations** dans le panneau de gauche, votre administrateur système doit activer l’option **Citations** dans l’onglet **Panneaux** dans **Paramètres**.

1. Sélectionnez **Citations** ![icône de &#x200B;](images/citations-icon.svg) de citations dans le panneau de gauche.
1. Faites glisser la citation à partir du panneau **Citations** et déposez-la à l’emplacement approprié dans la rubrique.

   Vous pouvez également sélectionner **Insérer** dans ![](images/options.svg) **Options** pour insérer une citation.

   ![insérer des citations](images/citation-panel-insert.png)
1. Pour sélectionner plusieurs citations, cliquez avec le bouton droit de la souris sur une citation dans le sujet et sélectionnez **Modifier la citation** dans le menu contextuel.
1. Sélectionnez les citations à insérer dans la boîte de dialogue **Citation**.
1. Sélectionnez **Terminé** pour les ajouter à la rubrique.

Une fois que vous avez inséré des citations dans la rubrique, vous pouvez les prévisualiser dans l’éditeur web. Vous pouvez également publier du contenu avec des citations à l’aide du PDF natif.



## Supprimer une citation

Vous pouvez supprimer une citation du panneau Citations ou d&#39;une rubrique dans laquelle vous l&#39;avez insérée.

### Supprimer une citation du panneau Citations

Pour supprimer une citation du panneau Citations, procédez comme suit :

1. Survolez le nom de la citation dans la liste.
1. Sélectionnez l’icône ![](images/options.svg) **Options**.
1. Sélectionner le   **Supprimer** ![](images/Delete_icon.svg).
La boîte de dialogue de confirmation s’ouvre.
1. Sélectionnez **Oui**.
La citation sélectionnée est supprimée du panneau des citations.



### Supprimer une citation d’une rubrique

Pour supprimer une citation déjà utilisée dans la rubrique, procédez comme suit :

Dans la rubrique, placez le curseur à la fin de la citation.

1. Faites un clic droit sur une citation dans le sujet et sélectionnez **Modifier la citation** dans le menu contextuel. La boîte de dialogue Citation s’ouvre.
   ![menu contextuel d’une citation](./images/modify-citation.png)

1. Vous pouvez choisir les citations à insérer dans le document.

   >[!NOTE]
   >
   >Les citations déjà utilisées dans la rubrique sont remplacées par celles que vous sélectionnez dans la boîte de dialogue.


1. Sélectionnez **Terminé**.

## Générer la sortie du contenu avec des citations

Une fois que vous avez inséré des citations dans la rubrique, vous pouvez publier du contenu avec des citations à l’aide du PDF natif.

Dans la sortie Native PDF, les citations apparaissent à l’endroit où vous les avez insérées. Vous pouvez également créer une page de bibliographie. Lorsque vous sélectionnez une citation, vous êtes redirigé vers la page de bibliographie.

Créez une mise en page **Citations** dans les modèles PDF et incluez-la dans votre document. Toutes les citations utilisées dans le livre sont répertoriées sur une page qui apparaît dans la sortie PDF. Pour en savoir plus sur la création d’une mise en page, voir [Créer une mise en page](../native-pdf/components-pdf-template.md#create-page-layout).


Pour modifier l’affichage et la convivialité de la page de citation, consultez [Personnaliser les modèles PDF](../native-pdf/pdf-template.md).


### Appliquer un style de contenu à une citation

Appliquer une mise en forme à la citation lorsqu&#39;elle est ajoutée à la rubrique.

1. Sélectionnez **Feuilles de style** dans le panneau **Modèles** d’un paramètre prédéfini de sortie PDF natif.   Cela ouvre le panneau **STYLES** qui contient toutes les options de style.

1. Dans le panneau de recherche, recherchez `<cite>`.

Pour en savoir plus sur les styles, consultez la vue [Utiliser les styles de contenu courants](../native-pdf/stylesheet.md).
