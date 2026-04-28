---
title: Modification de rubriques dans l’éditeur web
description: Découvrez comment modifier des rubriques dans l’éditeur web. Connaître les différentes fonctionnalités d’édition permettant de modifier vos fichiers de rubrique dans AEM Guides.
feature: Authoring, Web Editor
role: User
hide: true
exl-id: 0341bdec-9635-4ced-b1c6-789b4e1aded8
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '1060'
ht-degree: 0%

---

# Modification de rubriques dans l’éditeur web {#id2056B040VUI}

L&#39;éditeur Web est fourni avec un éventail de fonctions d&#39;édition qui vous permettent de créer ou de modifier facilement vos fichiers de rubrique. En règle générale, vous devez effectuer les étapes suivantes pour modifier une rubrique dans l’éditeur web.

>[!IMPORTANT]
>
> Si vous rencontrez une erreur d’application lors de l’utilisation de l’éditeur web, actualisez la page pour continuer à travailler.

1. Pour apporter des modifications à votre rubrique, cliquez dans la limite de texte de l&#39;élément requis et commencez à apporter des modifications.

1. Pour insérer un élément spécifique, cliquez à l’extrémité de l’élément après quoi vous souhaitez insérer le nouvel élément et cliquez sur l’icône de l’élément requis dans la barre d’outils. Vous pouvez également utiliser le raccourci clavier `Alt+Enter` pour appeler la fenêtre contextuelle **Insérer un élément**.

   Une liste d’éléments qui peuvent être utilisés dans la rubrique s’affiche. AEM Guides place intelligemment les éléments en fonction de leur emplacement valide dans la rubrique.

   >[!NOTE]
   >
   > Vous pouvez également choisir l’icône à afficher dans la barre d’outils en configurant le fichier `ui_config.json` situé à l’emplacement - `/etc/designs/fmdita/clientlibs/xmleditor/`. Pour plus d’informations sur la personnalisation des fonctionnalités, contactez votre administrateur système.

1. Une fois la modification du document terminée, cliquez sur **Enregistrer**.

   >[!NOTE]
   >
   > Si vous ne souhaitez pas valider les modifications dans le référentiel AEM, cliquez sur **Fermer**, puis sur **Fermer sans enregistrer** dans la boîte de dialogue Modifications non enregistrées.


## Sélection partielle de contenu entre des éléments

Experience Manager Guides vous permet également de sélectionner du contenu sur plusieurs éléments. Après avoir sélectionné le contenu, vous pouvez effectuer les opérations suivantes :

- Mise en forme et suppression : mettez le contenu sélectionné en gras, en italique, soulignez-le ou même supprimez-le. Le contenu des balises ouvertes valides est ensuite fusionné et s’affiche sous un seul élément. Par exemple, vous pouvez sélectionner le contenu d’un paragraphe et étendre la sélection à un autre paragraphe. Ensuite, si vous mettez le contenu sélectionné en gras, tout le contenu en gras des balises ouvertes est fusionné et apparaît sous un seul élément de paragraphe.

De même, si vous supprimez le contenu sélectionné, le contenu restant après la suppression dans les balises ouvertes est fusionné.

- Entourer le contenu d’un élément valide : effectuez les étapes suivantes pour encapsuler le contenu avec un élément valide :

   - Select the content within an element.
   - Select the ![add](images/Add_icon.svg) icon from the secondary toolbar on the top to view the **Surround with Element** dialog box. The dialog box lists the valid elements for the selected content.
     >[!NOTE]
     >
     > You can also view the Surround with element dialog box by selecting the context menu of the selected content.

   - Select an element from the dialog box. The selected content is wrapped under that element. For example, if you select the content in a paragraph and then choose the `<note>` element from the **Surround with element** dialog box, the selected content appears under a note.\
     ![surround element dialog box](./images/surround-element.png) {width="300" align="left"}

## Refresh browser while editing the files

Experience Manager Guides provides the support to refresh the browser while you edit your content in the Web Editor. This feature helps you continue editing content in case you encounter an application error while working. If you hit the browser refresh while one or more files with unsaved changes are opened for editing, you are warned that the unsaved changes may be lost. You are given an option to cancel the refresh operation and save your files to preserve your changes.

Even on refreshing the browser, the views of the left and the right panel are retained in the Web Editor. Experience Manager Guides restores the last saved state of the files opened in the Web Editor when you refresh the browser. For example, the files opened in the Repository panel are opened again. The map panel is retained along with the previously opened map.

The active topic or DITA map is reopened in the content editing area.

The right panel is also reopened and displays the same view as before the refresh.

## Working copy indicator

AEM Guides provides the working copy indicator which shows whether the current \(working copy\) of file is in sync with the saved version or not. If you have made any changes to your current copy and have not saved your file, a \* mark appears along with the title on the topic&#39;s file tab. This indicator acts as a reminder to save your changes and disappears when you save your file.

![working copy indicator](images/working-copy-text-update-indicator.png){width="550" align="left"}

AEM Guides also indicates if the last saved \(working\) copy of the file is in sync with the saved version or not. If you have some unsaved changes between the working copy and the last saved version, a \* mark appears along with the version information shown in the right top corner of the topic&#39;s file tab. This indicator acts as a reminder to save and create a version from your current \(working\) copy of the file.

![Version update indicator](images/version-update-indicator.png){width="550" align="left"}


## Open locked files in Author and Source modes

When a DITA or Markdown file is locked or checked out by another user, editing or modifying the content is not possible. However, you can still view the file in a read-only format in both the **Author** and **Source** modes, in addition to the **Preview** mode.

In the read-only mode, you have the ability to view the content, tags, and attributes within the **Author** or **Source** modes. You can also modify the file properties.

The toolbar displays the following icons for read-only access:

- Toggle Tags view
- Historique des versions
- Libellé de version

Experience Manager Guides also displays a **Read only access** indicator near the version number.

![view read only file in author mode](images/locked-file-editor.png)

You can access the **Layout** view for read-only DITA maps. This view lets you see the DITA map and its properties but prevents edits.

>[!NOTE]
>
> Your folder-level administrative users must update *ui_config.json* so that you can harmoniously access the read-only files in the  Author, Source, and Layout modes.

## Locate an open file in the Repository View

While you open a file in the Web Editor, Experience Manager Guides provides the feature to locate the file in the Repository View. For example, it locates the current topic while you are editing it.

You can turn off the feature to locate the file with the **Always locate files in repository** option from the **Appearance** tab of the **User preferences**.


**Rubrique parente :**[ Utiliser l’éditeur web](web-editor.md)
