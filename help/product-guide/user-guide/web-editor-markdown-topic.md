---
title: Créer des documents Markdown
description: Créez des documents Markdown à partir de l’éditeur. Découvrez comment créer, créer et prévisualiser une rubrique Markdown dans AEM Guides.
exl-id: def14e35-27c5-4b90-bc3d-eef7e8f317d2
feature: Authoring, Features of Web Editor
role: User
source-git-commit: 779be011c078fb3c2fae4fc6a92e3e2d734672b0
workflow-type: tm+mt
source-wordcount: '1197'
ht-degree: 1%

---

# Créer des documents Markdown à partir de l’éditeur {#id223MIE0B079}

Markdown est un langage de balisage léger qui peut vous aider à ajouter des éléments de mise en forme aux documents en texte brut. Adobe Experience Manager Guides permet de créer et de prévisualiser une rubrique Markdown \(.md\) à partir de l’éditeur. Vous pouvez également charger les documents Markdown existants et les modifier dans l’éditeur.

## Créer une rubrique Markdown

Pour créer une rubrique Markdown à partir de l’éditeur, procédez comme suit :

1. Dans le panneau Référentiel, sélectionnez ![](images/Add_icon.svg), puis sélectionnez **Rubrique** dans la liste déroulante.
2. Dans la boîte de dialogue **Nouvelle rubrique**, fournissez les détails suivants :

   ![](images/create-markdown-dialog.png){width="300" align="left"}

   * **Titre** : indiquez un titre pour la rubrique.
   * **Name** : le nom du fichier est suggéré automatiquement en fonction du titre du topic. Si votre administrateur a activé les noms de fichiers automatiques en fonction du paramètre UUID, le champ Nom ne s’affiche pas.
   * **Modèle** : sélectionnez **Markdown** dans la liste déroulante. Le modèle **Rubrique** est sélectionné par défaut.
   * **Chemin** : recherchez le chemin d’accès où vous souhaitez enregistrer le fichier de rubrique. Par défaut, le chemin du dossier actuellement sélectionné dans le référentiel s’affiche dans le champ Chemin .

   >[!NOTE]
   >
   > En cas de mise à niveau, vous devez ajouter le modèle Markdown dans le profil de dossier actuel utilisé. Vous pouvez [créer un modèle Markdown à partir de l’éditeur](./web-editor-features.md#templates) ou utiliser un modèle existant pour la création Markdown. Pour plus d’informations sur l’ajout de modèles de création dans Experience Manager Guides, consultez [Configuration de profils globaux ou au niveau du dossier](../cs-install-guide/conf-folder-level.md).
3. Sélectionnez **Créer**.

   La rubrique Markdown est créée au niveau du chemin d’accès sélectionné et est ouverte pour modification.

   ![](images/markdown-topic-author.png){width="650" align="left"}


>[!NOTE]
>
> Vous pouvez également créer une rubrique Markdown pour un dossier dans le panneau Référentiel. Sélectionnez le dossier dans lequel vous souhaitez créer une rubrique Markdown et sélectionnez **Nouveau**, puis **Rubrique** dans le menu Options. Vous pouvez désormais créer une rubrique Markdown en fournissant des détails sur la rubrique dans la boîte de dialogue **Créer une rubrique**.

## Connaître les fonctionnalités de l’éditeur pour une rubrique Markdown

Cette section vous guide à travers les différentes fonctionnalités disponibles dans l’éditeur pour la création de rubriques Markdown. L’interface de création est divisée en plusieurs sections ou zones :

* [Barre d’outils](#toolbar)
* [Zone d&#39;édition du contenu](#content-editing-area)
* [Modes Source, Côte à côte et Aperçu](#source-side-by-side-and-preview-modes)
* [Panneau de droite](#right-panel)


<!--
### Tab bar 

The tab bar features the file tabs of the topics or maps that are currently opened in the Editor along with other file-level options. 

Features available in the tab bar are explained as follows:

 ![](images/markdown-header.png){width="550" align="left"}




* **Topic tab**: Displays the currently opened topics in a tab. By default, you can view the file titles in the tab. As you hover over a file, you can view the file title and the file path as a tooltip.

    >![NOTE]
    >
    > As an administrator, you can also choose to view the list of files by filenames in the tabs. View [User preferences](./intro-home-page.md#user-preferences) for details.
* **Save all**: Saves the changes you have made in all opened topics. If you have multiple topics opened in the Editor, selecting **Save all** or pressing `Crtl+S` shortcut keys saves all documents in one click. You do not have to individually save each document.
* **AI Assistant**: [AI-powered Smart Help](./ai-based-smart-help.md) feature that helps you find relevant content from the Adobe Experience Manager Guides Documentation.
* **More actions**: Allows you to navigate to the **Assets UI**. As an administrator, you also get an option to navigate to the **Settings** page. Learn how to work with [settings](./web-editor-features.md#main-toolbar) or editor settings. 
* **Expand view**: Allows you to expand the page view using the **Expand** icon. In this view, the header bar is hidden, maximizing the content space. To return to the standard view, use the **Exit the expanded view** icon.

-->

### Barre d’outils

La barre d’outils se trouve juste en dessous de la barre d’onglets. Les fonctionnalités disponibles dans la barre d’outils sont expliquées comme suit :

![](images/markdown-main-toolbar.png){align="left"}

| Fonctions | Description |
|----------------|----------------|
| Modifier les actions | Permet d&#39;accéder à diverses fonctions d&#39;édition de documents, y compris **Couper**  ![](images/S_Cut_18_N.svg), **Annuler**  ![](images/S_Undo_18_N.svg), **Rétablir**  ![](images/S_Redo_18_N.svg), **Copier**  ![](images/S_Copy_18_N.svg), **Supprimer**  ![](images/S_Delete_18_N.svg) et **Rechercher et remplacer**  ![](images/S_FindAndReplace_18_N.svg). Vous pouvez accéder aux options disponibles à partir du menu déroulant **Menu**. |
| Options de formatage du texte | Permet d’accéder à diverses options de formatage de texte, y compris **Titres**  ![](images/S_DisplayHeading_18_N.svg), **Gras**  ![](images/S_TextBold_18_N.svg), **Italique**  ![](images/S_TextItalic_18_N.svg), **Barré**  ![](images/S_TextStrikethrough_18_N.svg), **Code**  ![](images/S_Code_18_N.svg) et **Citation en bloc**  ![](images/S_BlockQuoteMultipleLines_18_N.svg). |
| Options d&#39;insertion de contenu | Fournit des options pour insérer une **liste numérotée**  ![](images/S_TextNumbered_18_N.svg), **Liste ordonnée**  ![](images/S_TextBulleted_18_N.svg), **Tableau**  ![](images/tableAdd.svg), **Image** ![](images/S_ImageAdd_18_N.svg), **Référence croisée**  ![](images/S_LinkGlobe_18_N.svg) et **symbole**  ![](images/S_SpecialCharacter_18_N.svg) dans un document.<br><br> **Remarque** : vous pouvez également faire glisser et déposer des images et d’autres fichiers dans l’éditeur Markdown. Les fichiers sont ajoutés en tant que liens de référence croisée, tandis que les images sont affichées en tant qu’éléments d’image standard. |
| Historique des versions | Permet de créer des versions des fichiers Markdown et d’afficher l’historique des modifications. Vous pouvez comparer différentes versions et revenir aux versions précédentes si nécessaire. L’option Historique des versions est présente dans le menu déroulant **Menu**. |
| Enregistrer comme nouvelle version | Enregistre les modifications apportées à la rubrique et crée également une nouvelle version de la rubrique. Si vous travaillez sur une rubrique nouvellement créée, les informations de version apparaissent comme aucune. |
| Verrouiller/déverrouiller | Verrouille ou déverrouille le fichier courant. Le verrouillage d’un fichier vous donne un accès exclusif en écriture au fichier. Cela empêche d’autres utilisateurs de modifier le fichier. Déverrouillez le fichier si vous souhaitez que d’autres utilisateurs aient un accès en modification. En tant qu’administrateur, vous avez également accès à la fonctionnalité **Forcer le déverrouillage** qui vous permet de déverrouiller le fichier verrouillé par une autre personne. |

>[!NOTE]
>
> La fonctionnalité **Historique des versions** et les fonctionnalités mentionnées sous les actions de modification, la mise en forme du texte et l’insertion de contenu sont accessibles à partir des vues **Source** et **côte à côte** de la rubrique Markdown.

### Zone d&#39;édition du contenu

La zone de modification du contenu affiche la source Markdown de votre rubrique, dans laquelle vous apportez toutes les modifications au contenu. Dans la vue côte à côte, cette zone se divise en deux sections : vue source Markdown à gauche et Aperçu à droite. Plusieurs rubriques peuvent être ouvertes en même temps et s’afficher dans leurs onglets respectifs.

### Modes Source, Côte à côte et Aperçu

Pour la création Markdown, l’éditeur prend en charge trois modes d’affichage différents pour faciliter la création et la mise en forme du contenu :

![](images/markdown-footer.png){align="left"}

* Source
* Côte à côte
* Prévisualisation

**Source**

Il s’agit de l’affichage du code Markdown de l’éditeur. Vous pouvez modifier des rubriques Markdown comme vous le feriez dans n’importe quel éditeur Markdown standard. Dans la vue Source, vous avez la possibilité d&#39;enregistrer une révision du document, d&#39;insérer des en-têtes, d&#39;insérer un tableau, d&#39;insérer une image, etc.

Utilisez cette vue si vous souhaitez vous concentrer uniquement sur l’écriture et la modification du markdown brut sans afficher la sortie rendue.

**Côte à côte**

Ce mode divise l’éditeur en deux panneaux :

* Panneau Source qui affiche la rubrique Markdown que vous modifiez.
* Panneau d’aperçu qui affiche la sortie rendue de la rubrique Markdown en temps réel.

![](images/markdown-topic-side-by-side.png){width="550" align="left"}

Utilisez cette vue pour afficher la sortie rendue en temps réel lorsque vous modifiez des rubriques Markdown.

**Prévisualisation**

L’ouverture d’une rubrique Markdown en mode Prévisualisation permet de voir comment une rubrique sera affichée lorsqu’elle est consultée par un utilisateur dans son navigateur. Dans cette vue, toutes les fonctions de modification sont supprimées de la barre d’outils. Cependant, vous pouvez toujours accéder aux fonctions **Enregistrer en tant que nouvelles versions**, **Verrouiller/déverrouiller** de la barre d’outils, ainsi qu’à la fonction **Propriétés du fichier** dans le panneau de droite.

### Panneau de droite

Le panneau de droite vous donne accès au panneau **Propriétés du fichier).

Les propriétés du fichier comportent les deux sections suivantes :

**Général**

La section Général vous donne accès aux fonctionnalités suivantes :

* **Nom de fichier** : affiche le nom de fichier de la rubrique sélectionnée.
* **ID** : affiche l’ID de la rubrique sélectionnée.
* **Langue** : affiche la langue de la rubrique. Elle est définie à partir du champ langue de la page des propriétés.
* **Créé le** : affiche la date et l’heure de création de la rubrique.
* **Modifié le** : affiche la date et l’heure de modification de la rubrique.
* **Verrouillé par** : affiche l’utilisateur qui a extrait la rubrique.
* **État du document** : vous pouvez sélectionner et mettre à jour l’état du document de la rubrique actuellement ouverte. Pour plus d’informations, voir [État du document](./web-editor-document-states.md).
* **Balises** : il s’agit des balises de métadonnées de la rubrique. Elles sont définies dans le champ de balises de la page de propriétés. Vous pouvez les saisir ou les sélectionner dans la liste déroulante. Les balises s’affichent sous la liste déroulante. Pour supprimer une balise, sélectionnez l’icône en forme de croix en regard de la balise.
* **Modifier plus de propriétés** : vous pouvez modifier d’autres propriétés à partir de la page des propriétés du fichier.

**Références**

La section Références vous donne accès aux fonctionnalités suivantes :

* **Utilisé dans** : le champ Utilisé dans les références répertorie les documents dans lesquels le fichier actuel est référencé ou utilisé.
* **Liens sortants** : les liens sortants répertorient les documents auxquels il est fait référence dans le document actif.

>[!NOTE]
>
> Toutes les références de liens utilisés dans et sortants renvoient vers les documents sous forme d’un lien hypertexte. Vous pouvez facilement ouvrir et modifier les documents liés.

## Limites des fonctionnalités

Les fonctionnalités Experience Manager Guides suivantes ne s’appliquent actuellement pas à la création Markdown :

1. Révision
2. Fusionner
3. Assistant IA
4. Suivi des modifications





**Rubrique parente :**[ Présentation de l’éditeur](web-editor.md)
