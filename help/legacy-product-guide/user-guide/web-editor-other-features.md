---
title: Autres fonctionnalités de l’éditeur web
description: Explorez d’autres fonctionnalités de l’éditeur web dans AEM Guides. Découvrez comment utiliser ces fonctionnalités pour améliorer la création dans AEM Guides.
feature: Authoring, Web Editor
role: User
hide: true
exl-id: 7639fa76-b319-44b5-9ff8-2b8c1a716b7b
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '2564'
ht-degree: 0%

---

# Autres fonctionnalités de l’éditeur web {#id2056B0B0YPF}

L’éditeur web comporte d’autres fonctionnalités utiles que vous pouvez utiliser :

**Fonctions du menu contextuel dans l’onglet d’un fichier**

Lorsque vous ouvrez un fichier dans l’éditeur web, vous pouvez effectuer différentes actions à partir du menu contextuel. Différentes options peuvent s&#39;afficher selon que vous ouvrez un fichier multimédia, un fichier DITA unique ou plusieurs fichiers.

**Fichier multimédia**

Les fonctions suivantes sont disponibles dans le menu contextuel de l’onglet d’un fichier multimédia ouvert :

![](images/media-file-context-menu.png){width="300" align="left"}

**Fichier DITA unique**

You get the following functions in the context menu of an opened file&#39;s tab:

:   ![](images/single-file-context-menu.png){width="300" align="left"}

**Plusieurs fichiers**

Lorsque plusieurs fichiers sont ouverts, le menu contextuel propose d’autres options :

![](images/multiple-files-context-menu.png){width="550" align="left"}

Les différentes options du menu contextuel sont expliquées ci-dessous :

***Enregistrer*** : vous pouvez choisir parmi les options suivantes :

- **Enregistrer** : pour enregistrer un fichier sans créer de nouvelle version, sélectionnez **Enregistrer**. Chaque fois que vous créez une rubrique, une copie de travail sans version de la rubrique est créée dans la gestion des ressources numériques. L’enregistrement de votre document met à jour la copie de travail de votre document dans la gestion des ressources numériques. Doing a simple save on this version does not create a new version of a topic. Si votre rubrique est en cours de révision, l&#39;enregistrement d&#39;une rubrique ne permet pas à vos réviseurs d&#39;accéder au contenu de la rubrique modifiée.

- **Enregistrer tout** : si plusieurs documents sont ouverts dans l’éditeur web, vous avez également la possibilité d’**Enregistrer tout** les documents ouverts.


***Enregistrer Comme Nouvelle Version***

Pour créer une nouvelle version du fichier, sélectionnez **Enregistrer comme nouvelle version**. Pour plus d’informations sur **Enregistrer** et **Enregistrer en tant que nouvelle version**, consultez [Connaître les fonctionnalités de l’éditeur web](web-editor-features.md#).

***Copier*** : vous pouvez choisir parmi les options suivantes :

- **Copier l’UUID** : pour copier l’UUID du fichier actif dans le Presse-papiers, sélectionnez **Copier \> Copier l’UUID**.
- **Copier le chemin** : pour copier dans le presse-papiers le chemin d’accès complet du fichier actif, sélectionnez **Copier \> Copier le chemin**.


***Localiser dans*** : vous pouvez choisir parmi les options suivantes :

- **Mappage** : si vous avez ouvert un plan DITA volumineux et que vous souhaitez trouver l&#39;emplacement exact d&#39;un fichier dans le plan, sélectionnez **Localiser dans \> Mappage**. Lorsque vous sélectionnez l’option Localiser dans le mappage , le fichier \(d’où l’option est appelée\) est situé et mis en surbrillance dans la hiérarchie du mappage. Pour pouvoir utiliser cette fonctionnalité, vous devez ouvrir le fichier de mappage dans l’éditeur web. Si la vue de carte est masquée, l’appel de cette fonction affiche la vue de carte et le fichier est mis en surbrillance dans la hiérarchie de carte.

- **Référentiel** : tout comme Localiser dans Map, **Localiser dans \> référentiel** indique l’emplacement du fichier dans le référentiel \(ou DAM\). La vue du référentiel est ouverte et le fichier sélectionné est mis en surbrillance dans le référentiel. Si le fichier se trouve dans un dossier, ce dossier est développé pour afficher l’emplacement du fichier sélectionné dans le référentiel.


***Ajouter à*** : vous pouvez choisir parmi les options suivantes :

- **Favoris** : pour ajouter le fichier sélectionné à la collection de favoris, sélectionnez **Ajouter aux favoris**. Pour plus d’informations, consultez la description de la fonctionnalité **Favoris** dans la section [Panneau de gauche](web-editor-features.md#id2051EA0M0HS).



- **Contenu réutilisable** : pour copier le fichier sélectionné dans la liste de contenu réutilisable, sélectionnez **Ajouter à \> Contenu réutilisable**. Pour plus d’informations, reportez-vous à la description de la fonctionnalité **Contenus réutilisables** dans la section [Panneau de gauche](web-editor-features.md#id2051EA0M0HS).




***Propriétés***

Pour afficher la page des propriétés AEM du fichier sélectionné, sélectionnez **Propriétés**.

***Fractionner*** : vous pouvez choisir parmi les options suivantes :

**Haut, Bas, Gauche ou Droite**

Par défaut, l’éditeur web vous permet d’afficher une rubrique à la fois. Il peut y avoir des cas où vous souhaitez voir deux sujets ou plus en même temps. Le fractionnement de l’écran de l’éditeur vous permet d’afficher plusieurs rubriques en même temps. Par exemple, si vous avez deux rubriques : A et B ouvertes dans l’éditeur. Cliquez avec le bouton droit sur la rubrique B et choisissez **Fractionner \> vers le haut** pour diviser la fenêtre de l’éditeur en deux parties. Topic B is displayed in the upper half and Topic A is displayed in the bottom half. Similarly, you can also split the screen horizontally by selecting **Split \> Left** or **Split \> Right**. The following screenshot of the Web Editor displays topics split horizontally and vertically. In each split, you can have a different view. For example in the following screenshot, the screen 1 is in Source view mode, screen 2 has two documents opened in Author mode, and screen 3 is in the Preview mode. You can move your documents from one screen to the other by dragging the file tab and dropping it on to the screen where you want to place it. Similarly, you can also reorder file tabs by dragging and moving them as per your preference.

![](images/split-editor.png){width="800" align="left"}

***Quick Generate***

Generate the output for the selected file. La sortie ne peut être générée que pour les fichiers qui font partie d’un paramètre prédéfini de sortie. Pour plus d’informations, consultez la section [&#x200B; Publication basée sur des articles à partir de l’éditeur web &#x200B;](web-editor-article-publishing.md#id218CK0U019I).

***Close***: You can choose from the following options:

**Close**, **Close Others**, or **Close All**

If you want to close the file from which you invoked the context menu, then select **Close \> Close**. Use **Close \> Close Others** to close all other opened file except the currently active file. To close all open files, select the **Close \> Close All** option from the context menu or you can also choose to close the Web Editor. If there are any unsaved files in your session, then you are prompted to save those files.

**File close and save scenarios**

When you try to close a file opened in the Web Editor using the **Close** button on the file&#39;s tab or the **Close** option in the Options menu, AEM Guides prompts you to save your edits and unlock a locked file.

The prompts are based on the following configurations selected by your administrator:

- **Ask for check-in on close:** You are given the option to check in the file \(which you have checked out\) when you close the editor.
- **Ask for new version on close**: You are given the option to save the file \(which you have edited\) as a new version when you close the editor.

Your file saving experience will depend on the following three scenarios, wherein you have:

- Not done any changes to the content.
- Edited the content and saved the changes.
- Edited the content but not saved the changes.

You may see the following options depending on whether the file is locked/unlocked and has saved or unsaved changes:

- **Unlock and Close**: The lock on the file is released, and the file gets closed.

  ![](images/file-close-unlock-file.png){width="400" align="left"}

- **Save as a New Version**: This will save the changes you have made in your content and create a new version of your file. You can also add labels and comments for the newly saved version. Pour plus d’informations sur l’enregistrement d’une nouvelle version, voir [Enregistrer comme nouvelle version](web-editor-features.md#save-as-new-version-id209ME400GXA).

- **Unlock the File**: If you choose to unlock a file, it will release the lock on your file and the changes are saved in the current version of the file.

  >[!NOTE]
  >
  > If you deselect the option to unlock the file, you also get an option to close the file without saving the changes.

  For example, one of the prompts is shown in the following screenshot:

  ![](images/file-close-save-changes-unlock.png){width="400" align="left"}

**Visual cues for broken references**

- If your topic contains broken cross-references or content references, they are shown in red text.

**Smart copy-paste**

- You can easily copy paste content within and across topics. The source element structure is maintained at the destination. Also, if the copied content contains content references, then even those are copied.

**Remember last browsed location**

- The Web Editor provides a smart file browse dialog. The editor remembers the last used location while inserting a reference or content. The first time you invoke the file browse dialog \(via Insert Reference or Insert Reuse Content\), then you are taken to the location where the current document is saved. In the same session, if you try to insert another reference, then the file browse dialog automatically navigates to the location from where you inserted the last reference.

>[!NOTE]
>
> In case of an image, audio, or video file, the file browse dialog defaults to the file&#39;s location and not the last used location.

**Support for article-based publishing**

- From the Web Editor, you can generate the output for one or more topics, or the entire DITA map. You need to create output presets for your DITA map and then you can easily generate the output for one or more topics. If you have updated a few topics in your map, you can also generate the output only for those topics from the Web Editor. Pour plus d’informations, consultez la section [&#x200B; Publication basée sur des articles à partir de l’éditeur web &#x200B;](web-editor-article-publishing.md#id218CK0U019I).

**Prise en charge des documents Markdown**

- L&#39;éditeur Web vous permet d&#39;utiliser les documents Markdown \(.md\) avec vos documents DITA. Vous pouvez facilement créer et prévisualiser un document Markdown dans l’éditeur web et l’ajouter dans votre fichier map via l’éditeur de map DITA. Pour plus d’informations, voir [Créer des documents Markdown à partir de l’éditeur web](web-editor-markdown-topic.md#).

**Prise en charge du terme de glossaire DITA**

- L&#39;éditeur Web prend en charge les termes du glossaire DITA que vous pouvez insérer en ajoutant des éléments `term` ou `abbreviated-form`.

**Insérer des équations MathML**

- Experience Manager Guides vous offre une prise en charge prête à l’emploi pour insérer des équations MathML par intégration à l’application [MathType Web](https://docs.wiris.com/en/mathtype/mathtype_web/intro). Pour insérer une équation MathML, sélectionnez l&#39;icône **Insérer un élément** et saisissez mathml. Lorsque vous sélectionnez l’élément mathml dans la liste, la boîte de dialogue **Insérer un MathML** s’affiche :

![insérer l’équation mathml dans l’éditeur mathml](images/insert-mathml-equation.png){width="550" align="left"}

À l&#39;aide des outils d&#39;équation de MathML, créez votre équation et cliquez sur **Insérer** pour l&#39;ajouter à votre document. L&#39;équation est insérée avec un arrière-plan gris clair, comme illustré ci-dessous :

![exemple d’équation mathml](images/sample-mathml-equation.PNG){width="400" align="left"}

Vous pouvez à tout moment mettre à jour une équation en cliquant avec le bouton droit de la souris sur une équation existante et en sélectionnant **Modifier MathML** dans le menu contextuel.

- **Validation des équations dans l&#39;éditeur MathML**

  Experience Manager Guides valide les équations de MathML lorsque vous enregistrez une rubrique qui les contient.
Lorsque vous insérez une équation à l’aide de l’éditeur MathML, Experience Manager Guides met l’équation en surbrillance rouge en cas de problèmes de syntaxe. Vous pouvez le corriger avant de l’insérer. Si vous n&#39;apportez aucune modification, mais que vous sélectionnez **Insérer**, un avertissement s&#39;affiche.

  ![valider l’équation mathml](images/validate-mathml-equation.png){width="400" align="left"}

  Si vous insérez l&#39;équation MathML qui contient une erreur de syntaxe, une erreur de validation se produit lorsque vous essayez d&#39;enregistrer la rubrique.


**Insérer des notes de bas de page**

- Insérez une note de bas de page dans votre contenu à l’aide de l’élément `fn`. En mode création, la valeur de la note de bas de page s’affiche en ligne avec le contenu. Cependant, lorsque vous basculez en mode Aperçu ou que vous publiez votre document, la note de bas de page s’affiche à la fin de la rubrique.


**Renommer ou remplacer un élément**

- L’éditeur web affiche le chemin de navigation de l’élément en haut de la rubrique. Si vous souhaitez permuter ou remplacer un élément par un autre élément, vous pouvez le faire à partir du menu contextuel du chemin de navigation. Par exemple, vous pouvez permuter `p` élément avec `note` ou tout autre élément valide au niveau du contexte.

![](images/rename-element.png){width="400" align="left"}

Dans le chemin de navigation, cliquez avec le bouton droit sur le nom d’un élément à remplacer, puis sélectionnez Renommer l’élément dans le menu contextuel. La boîte de dialogue Renommer l’élément affiche tous les éléments valides autorisés à l’emplacement actuel. Dans la boîte de dialogue Renommer l’élément , sélectionnez l’élément que vous souhaitez utiliser. L’élément d’origine est remplacé par le nouvel élément .

Outre le menu contextuel du chemin de navigation, la boîte de dialogue Renommer l’élément est également accessible à partir d’autres emplacements :

- Cliquez sur le nom de l’élément dans le chemin de navigation pour sélectionner le contenu de l’élément et cliquez avec le bouton droit sur le contenu sélectionné pour afficher le menu contextuel.

- Activez la vue Balises, cliquez sur la balise d’ouverture d’un élément, puis cliquez avec le bouton droit sur le contenu sélectionné pour afficher le menu contextuel.

- Vous pouvez accéder à la boîte de dialogue Renommer l’élément en appelant le menu Options d’un élément dans le panneau Plan.



**Enrouler un élément**

- Envelopper un élément permet d’ajouter une balise d’élément au texte sélectionné. Vous pouvez renvoyer le texte à la ligne sur n&#39;importe quel élément enfant en respectant les normes DITA. Par exemple, si vous avez du texte sous un élément `note`, vous pouvez encapsuler le texte dans un élément `p`.

  L’option **Développer** est disponible dans le menu contextuel du chemin de navigation de la rubrique. Pour encapsuler un élément, cliquez avec le bouton droit de la souris sur l’élément et ouvrez le menu contextuel. Sélectionnez l’élément dans la boîte de dialogue **Enrouler l’élément**. Le texte apparaît dans le nouvel élément.

  Vous pouvez également sélectionner le texte ou l’élément dans le contenu, puis sélectionner l’option **Enrouler l’élément** dans le menu contextuel.

**Déplier un élément**

- Déplier un élément vous permet de supprimer la balise d’élément du texte sélectionné et de le fusionner avec son élément parent. Par exemple, si vous disposez d’un élément `p` dans un élément `note`, vous pouvez déplier l’élément `p` pour fusionner le texte directement dans l’élément `note`. L’option **Déplier l’élément** est disponible dans le menu contextuel du chemin de navigation de la rubrique. Pour déplier un élément, cliquez avec le bouton droit de la souris sur l’élément pour ouvrir le menu contextuel, puis sélectionnez **Déplier l’élément** pour supprimer l’élément et fusionner le texte de l’élément avec son élément parent.

**Gestion des espaces pour les éléments DITA**

- Dans le langage XML, les espaces comprennent les espaces, les tabulations, les retours à la ligne et les lignes vides. Experience Manager Guides convertit plusieurs espaces blancs conséquents en un seul espace. Cela permet de conserver l’affichage WYSIWYG de l’éditeur web.

  >[!NOTE]
  >
  >Dans certains éléments où les espaces blancs doivent être conservés conformément aux règles DITA, les multiples espaces blancs qui en résultent sont conservés. Par exemple, les éléments `<pre>` et `<codeblock>`.


**Conserver les sauts de ligne et la mise en retrait**

- Les éléments DITA contenant des sauts de ligne et des espaces sont pris en charge et rendus conformément à leur définition dans les modes Auteur, Source ou Aperçu, ainsi que dans la sortie publiée finale. La capture d’écran suivante montre le contenu de l’élément `msgblock` dans lequel les sauts de ligne et les espaces \(retrait\) ont été conservés :

![](images/new-line-support_cs.png){width="500" align="left"}



**Gestion des espaces insécables dans l’éditeur web**

- Vous pouvez insérer des espaces insécables dans votre document à l&#39;aide de l&#39;icône **Insérer des caractères spéciaux** ![Insérer des caractères spéciaux](images/insert-special-chars-icon.svg) ou des touches de raccourci **Alt** + **Espace**.  Ces espaces insécables s&#39;affichent en tant qu&#39;indicateurs lorsque vous modifiez une rubrique dans l&#39;éditeur Web. Vous pouvez désactiver l’affichage des espaces insécables à l’aide de l’option **Afficher l’indicateur d’espace insécable en mode création** dans l’onglet **Apparence** de l’**Icône Préférences utilisateur** ![Icône Préférences utilisateur](images/user_preference_editor_icon.svg).

- Si vous copiez et collez du contenu avec un espace insécable à partir de sources externes dans la vue **Auteur**, l’espace insécable est converti en espace.
Cependant, si vous copiez et collez du contenu avec un espace insécable à partir de la vue **Auteur**, il est conservé.


**Générer automatiquement l’identifiant de l’élément**

- Vous pouvez générer automatiquement des identifiants pour les éléments de votre rubrique DITA. Ces identifiants sont uniques dans une rubrique DITA. Par exemple, si vous générez des identifiants pour un élément de paragraphe, les identifiants seront p\_1, p2, p\_3, etc. Vous pouvez sélectionner plusieurs éléments et générer des identifiants pour chaque élément sélectionné.

Procédez comme suit pour générer automatiquement un identifiant pour un ou plusieurs éléments :

1. Ouvrez la rubrique dans l&#39;éditeur Web.
1. Sélectionnez le contenu auquel vous souhaitez attribuer des identifiants.
1. Cliquez avec le bouton droit et sélectionnez **Générer des identifiants dans le menu contextuel**.

   Vous pouvez également cliquer avec le bouton droit dans le chemin de navigation et sélectionner **Générer des identifiants**.


**Rubrique parente :**&#x200B;[&#x200B; Utiliser l’éditeur web](web-editor.md)
