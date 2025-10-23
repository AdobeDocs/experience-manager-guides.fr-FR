---
title: Créer un mappage
description: Création d’une carte avec l’éditeur de cartes dans Experience Manager Guides. Recherchez les étapes de création d’un fichier de mappage basé sur un modèle de mappage.
exl-id: b9cda118-ab6f-4d6b-9616-a083180ba069
feature: Authoring, Map Editor
role: User
source-git-commit: fd4612037581d1d554c9dc144b998ba8a2ab8ccf
workflow-type: tm+mt
source-wordcount: '1555'
ht-degree: 0%

---

# Créer un mappage {#id176FEN0D05Z}

Adobe Experience Manager Guides fournit deux modèles de carte prêts à l&#39;emploi : un plan DITA et un plan de signets. Vous pouvez également créer vos propres modèles de carte et les partager avec vos auteurs pour créer des fichiers de carte.

Pour créer un mappage, procédez comme suit :

1. Dans le panneau Référentiel, sélectionnez l’icône **Nouveau fichier** puis sélectionnez **DITA Map** dans le menu déroulant.

   ![](images/create-map-options.png){align="left"}

   Vous pouvez également accéder à cette option à partir de la page d&#39;accueil [Experience Manager Guides](./intro-home-page.md) et du menu d&#39;options d&#39;un dossier dans la vue Référentiel.

2. La boîte de dialogue **Nouvelle carte** s’affiche.

3. Dans la boîte de dialogue **Nouveau mappage**, fournissez les détails suivants :
   - Titre de la carte.
   - \(Facultatif\)* Nom de fichier du mappage. Le nom du fichier est suggéré automatiquement en fonction du titre de la rubrique. Si votre administrateur a activé les noms de fichiers automatiques en fonction du paramètre UUID, vous ne verrez pas le champ Nom .
   - Modèle sur lequel la rubrique sera basée. Pour un fichier de mappage, les options disponibles sont **Bookmap**, **Map** et **Subject schema**.
   - Chemin où enregistrer le fichier de mappage. Par défaut, le chemin du dossier actuellement sélectionné dans le référentiel s’affiche dans le champ Chemin .

   ![](images/new-map-dialog.png){width="300" align="left"}


4. Sélectionnez **Créer**.

La carte est créée à l’emplacement spécifié. En outre, la carte est ouverte dans l’éditeur de cartes pour modification.

![](images/map-file-in-map-editor.png){align="left"}

## Ajouter des rubriques à un fichier de mappage

En plus de modifier les fichiers de mappage directement à partir de l’éditeur, vous pouvez également ouvrir les fichiers de rubrique dans un mappage pour modifier l’éditeur. Vous pouvez ajouter des rubriques à un fichier de mappage.

Effectuez les étapes suivantes pour ajouter des rubriques à un fichier de mappage à partir de la console Mappage :

1. Dans la vue Référentiel, accédez au fichier de mappage à modifier et ouvrez-le.
1. Sélectionnez l’icône **Modifier**.

   ![](images/edit-map-icon.png){width="450" align="left"}

1. Le fichier de mappage s’ouvre dans l’éditeur de mappages. Si vous avez ouvert un nouveau fichier de mappage, seul le titre du mappage s’affiche dans l’éditeur.

   ![](images/new-map-file-in-editor.png){align="left"}


   - **A** - \(*Barre d’onglets*\) : similaire à la barre d’onglets de l’éditeur. Afficher [barre d’onglets](./web-editor-tab-bar.md) dans l’éditeur pour plus d’informations.

   - **B** - \(*Toolbar*\) Il s’agit de la barre d’outils qui vous permet d’utiliser des fichiers de mappage. Pour plus d’informations sur les fonctionnalités disponibles via la barre d’outils, consultez la section [Fonctionnalités disponibles dans la barre d’outils de l’éditeur de cartes](#features-available-in-the-map-editors-toolbar).

   - **C** - \(*Vues des cartes*\) : permet de basculer l’éditeur de cartes entre les options Disposition, Auteur, Source et Aperçu. La vue **Disposition** permet d&#39;organiser les rubriques dans un plan DITA. Cela donne l’arborescence ou la vue hiérarchique de la carte. La vue **Auteur** vous permet de modifier les rubriques dans l’éditeur de cartes. Cela donne également la vue WYSIWYG du fichier de mappage. La vue **Source** vous permet d&#39;utiliser le code XML sous-jacent du fichier de mappage. L’aperçu vous donne une vue consolidée de toutes les rubriques et sous-cartes dans le fichier de mappage.

   - **D** - \(*Panneau de gauche*\) : donne accès au panneau de gauche, qui permet d’accéder aux collections, au référentiel, à la carte, au plan et à d’autres fonctionnalités. Vous pouvez le développer ou le réduire en sélectionnant l’icône Développer/Réduire . Pour plus d’informations sur les fonctionnalités disponibles dans le panneau de gauche, consultez la section [Panneau de gauche](./web-editor-left-panel.md) dans l’éditeur.

   - **E** - \(*Zone centrale*\) : zone d’édition du contenu de la carte.

   - **F** - \(*Panneau de droite*\) : permet d’accéder au panneau Propriétés. Vous pouvez afficher les propriétés de contenu et les propriétés de mappage de la rubrique ou du mappage sélectionné. Pour plus d’informations sur les fonctionnalités disponibles dans ce panneau, consultez le [panneau de droite](web-editor-right-panel.md) dans l’éditeur.

1. Dans le panneau de gauche, passez à la vue **Référentiel**.

1. Dans le référentiel Adobe Experience Manager, accédez au dossier contenant les rubriques ou les sous-mappages à ajouter.

1. Sélectionnez le fichier de rubrique ou de mappage dans la vue **Référentiel** et faites-le glisser dans la zone d’édition du contenu du mappage \(middle\).

   La rubrique est ajoutée dans la carte.

   ![ajout d’une rubrique dans l’éditeur de mappages](images/map-editor-add-topic.png){align="left"}

1. Pour ajouter des rubriques suivantes ou une sous-carte, faites glisser et déposez la rubrique ou la sous-carte vers l’emplacement souhaité dans la carte.

   Tenez compte des points suivants lors de la création de votre fichier map :

   - Le fichier est ajouté à un emplacement où la barre rectangle en tirets apparaît dans la zone de modification de carte. Dans la capture d’écran suivante, la rubrique *Exemple de rubrique* est ajoutée entre les rubriques *Suggestion intelligente 1* et *Suggestion intelligente 2*.

     ![](images/horizontal-line-in-adv-map-editor.png){align="left"}

   - Pour remplacer une rubrique, glissez-déposez la nouvelle rubrique en haut de la rubrique à remplacer. et le déposer indique qu’il sera remplacé par le topic qui y est déposé.

   - Si vous ajoutez une sous-carte à votre plan DITA, la sous-carte s&#39;affiche sous la forme d&#39;un lien dans le plan DITA. Pour afficher toutes les rubriques de la sous-carte, cliquez sur le lien de sous-carte tout en maintenant la touche Ctrl enfoncée. Le contenu de la sous-carte est affiché dans un nouvel onglet. De même, pour ouvrir une rubrique à partir du plan DITA, maintenez la touche Ctrl enfoncée tout en cliquant sur le lien de la rubrique et elle s&#39;ouvre dans le nouvel onglet.

   - Vous pouvez utiliser les touches de raccourci CTRL+Z et CTRL+Y ou leurs icônes respectives dans la barre d’outils pour annuler ou rétablir toute modification de la carte.

   - Pour modifier la position d’une rubrique, sélectionnez la rubrique \(en sélectionnant l’icône de rubrique\), puis faites-la glisser à l’emplacement souhaité dans le fichier de mappage. Dans la capture d’écran suivante, la rubrique *Suggestion intelligente 1* est déplacée après la rubrique *Exemple de rubrique*.

     ![](images/move-topic-adv-map-editor.png){align="left"}

   - Pour vérifier les propriétés de votre fichier de carte, cliquez avec le bouton droit de la souris n&#39;importe où dans la zone d&#39;édition de la carte et choisissez **Propriétés** dans le menu contextuel. En fonction de votre version de Adobe Experience Manager, vous pouvez afficher des propriétés telles que les métadonnées, la planification de l’activation \(de\), les références, l’état du document, etc.

1. Sélectionnez **Enregistrer**.

## Création d’un mappage à partir de l’interface utilisateur d’Assets

Vous pouvez également créer un fichier de mappage à partir de l’interface utilisateur d’Assets et l’ouvrir dans l’éditeur de mappages pour le modifier.

Pour créer un mappage à partir de l’interface utilisateur d’Assets, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez à l’emplacement où vous souhaitez créer le fichier de mappage.

1. Sélectionnez **Créer** \> **Plan DITA**.

1. Sur la page Plan directeur, sélectionnez le type de modèle de carte à utiliser, puis sélectionnez **Suivant**.

   >[!NOTE]
   >
   > La manière dont les rubriques sont référencées dans un fichier de mappage dépend du modèle de mappage. Par exemple, si vous sélectionnez le modèle Mappage, les références de rubrique \(`topicref`\) sont utilisées pour faire référence aux rubriques. Dans le cas d&#39;un Bookmap, les références de rubrique sont créées à l&#39;aide de l&#39;élément `chapter` dans DITA.

   ![](images/map-template.png){align="left"}

1. Sur la page Propriétés , spécifiez le mappage **Titre**.

1. \(Facultatif\) Spécifiez le fichier **Nom**.

   Si votre administrateur a configuré le nom de fichier automatique en fonction du paramètre UUID, vous ne verrez pas l’option permettant de spécifier le nom du fichier. Un nom de fichier basé sur l&#39;UUID est automatiquement attribué au fichier.

   Si l’option d’affectation de nom au fichier est disponible, le nom est également automatiquement suggéré en fonction du Titre de votre carte. Si vous souhaitez spécifier manuellement le nom du fichier de mappage, assurez-vous que le nom du fichier ne contient pas d’espaces, d’apostrophes ou de crochets et se termine par `.ditamap`.

1. Sélectionnez **Créer**.

   Le message Mappage créé s’affiche.

   Chaque nouveau fichier de mappage que vous créez à partir de l’interface utilisateur d’Assets ou de l’éditeur se voit attribuer un identifiant de mappage unique. En outre, la nouvelle carte est enregistrée comme dernière copie de travail dans la gestion des ressources numériques. Tant que vous n’avez pas enregistré une révision d’un mappage nouvellement créé, vous n’afficherez aucun numéro de version dans l’historique des versions. Si vous ouvrez la carte pour la modifier, les informations de version s’affichent dans le coin supérieur droit de l’onglet du fichier de carte :

   ![](images/first-version-map-none.png){align="left"}

   Les informations de version d’un mappage nouvellement créé s’affichent sous la forme *aucune*. Lorsque vous enregistrez une nouvelle version, un numéro de version 1.0 lui est attribué. Pour plus d’informations sur l’enregistrement d’une nouvelle version, voir [Enregistrer en tant que nouvelle version](web-editor-features.md#save-as-new-version).

   Vous pouvez choisir d’ouvrir le mappage pour le modifier dans l’éditeur de mappages configuré ou d’enregistrer le fichier de mappage dans le référentiel Adobe Experience Manager.

   >[!NOTE]
   >
   > Pour utiliser l’éditeur de mappages avancé, accédez au fichier de mappage dans l’éditeur. Si votre administrateur a configuré l’éditeur de carte avancé comme éditeur par défaut dans les fichiers de carte, le fichier de carte est ouvert directement dans l’éditeur de carte avancé pour être modifié. Consultez la section *Définir l’éditeur de carte avancé par défaut* dans Installation et configuration d’Adobe Experience Manager Guides as a Cloud Service.

### Ajouter des rubriques à un fichier de mappage à partir de l’interface utilisateur d’Assets

Pour ajouter des rubriques à un fichier de mappage à partir de l’interface utilisateur d’Assets, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de mappage à modifier.

   >[!NOTE]
   >
   > Assurez-vous que vous n’avez pas activé le mode de sélection de la ressource.

1. Pour obtenir un verrou exclusif sur le fichier de mappage, sélectionnez le fichier de mappage, puis sélectionnez l’option **Extraction** en haut.

   >[!NOTE]
   >
   > Une fois que vous disposez d’un verrou exclusif sur un fichier map, les autres utilisateurs ne peuvent pas modifier le map. Cependant, ils pourraient travailler sur les rubriques du fichier de carte. Si votre administrateur a configuré votre éditeur pour verrouiller les fichiers avant de les modifier, vous ne pourrez pas modifier un fichier tant que vous ne l’aurez pas verrouillé.

1. Une fois le fichier de mappage sélectionné, sélectionnez **Modifier les rubriques**.

   ![](images/edit-map-main-menu.png){align="left"}

   Vous pouvez également sélectionner l’option **Modifier les rubriques** dans le menu d’actions du fichier de mappage :

   ![](images/edit-map-action-menu.png){align="left"}

   Le fichier de mappage est ouvert pour modification dans l’éditeur. Pour ajouter des rubriques au fichier de mappage, suivez les étapes (4-8) de la section [Ajouter des rubriques à un fichier de mappage](#add-topics-to-a-map-file).




**Rubrique parente : [Présentation de l’éditeur de cartes](map-editor.md)
