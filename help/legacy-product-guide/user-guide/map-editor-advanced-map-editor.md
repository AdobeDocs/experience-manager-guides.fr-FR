---
title: Utilisation de l’éditeur de cartes avancé
description: Découvrez comment utiliser l’éditeur de carte avancé dans AEM Guides. connaître les fonctionnalités de l’éditeur de cartes avancé ; Modifiez des rubriques à l'aide d'un plan DITA et utilisez le mode Disposition, Création et Aperçu.
feature: Authoring, Map Editor
role: User
hide: true
exl-id: b63d7c0f-9c29-4fb4-b8fe-9790b16f8726
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '3788'
ht-degree: 0%

---

# Utilisation de l’éditeur de cartes avancé {#id1942D0S0IHS}

L’éditeur de carte avancé s’accompagne d’une interface utilisateur intuitive similaire à l’éditeur web. Lorsque vous ouvrez un fichier de mappage dans l’éditeur Web, vous avez la possibilité de le modifier à l’aide de l’interface de l’éditeur de mappages avancé. L’éditeur de carte avancé vous permet d’ajouter des références de rubrique et des références clés, de structurer votre contenu, etc.

En plus de modifier les fichiers de carte directement à partir de l’éditeur Web, vous pouvez également ouvrir les fichiers de rubrique dans une carte pour modifier l’éditeur Web. Cette rubrique vous guide à travers les fonctionnalités de l&#39;éditeur de carte avancé et vous explique comment ouvrir et modifier des fichiers dans un plan DITA dans l&#39;éditeur Web.

## Ajouter des rubriques à un fichier de mappage

Effectuez les étapes suivantes pour créer votre fichier de carte à l’aide de l’éditeur de carte avancé :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de mappage à modifier.

   >[!NOTE]
   >
   > Assurez-vous que vous n’avez pas activé le mode de sélection de la ressource.

1. Pour obtenir un verrou exclusif sur le fichier de mappage, sélectionnez le fichier de mappage et cliquez sur **Extraire**.

   >[!NOTE]
   >
   > Une fois que vous disposez d’un verrou exclusif sur un fichier map, les autres utilisateurs ne peuvent pas modifier le map. Cependant, ils pourraient travailler sur les rubriques du fichier de carte. Si votre administrateur a configuré votre éditeur web pour extraire des fichiers avant de les modifier, vous ne pourrez pas modifier un fichier tant que vous ne l’aurez pas extrait. De même, s’il est configuré, vous devrez archiver tout fichier extrait avant de le fermer

1. Une fois le fichier de mappage sélectionné, cliquez sur **Modifier les rubriques**.

   ![](images/edit-map-main-menu.png){width="800" align="left"}

   Vous pouvez également sélectionner l’option **Modifier les rubriques** dans le menu d’actions du fichier de mappage :

   ![](images/edit-map-action-menu.png){width="800" align="left"}

   Le fichier de mappage est ouvert pour modification dans l’éditeur web.

1. Cliquez sur l’icône **Modifier**.

   ![](images/edit-map-icon.png){width="550" align="left"}

   La carte est ouverte dans l’interface de l’éditeur de cartes avancé. Si vous avez ouvert un nouveau fichier de mappage, seul le titre du mappage s’affiche dans l’éditeur.

   ![](images/new-map-file-in-editor.png){width="800" align="left"}

   - **A** - \(*Barre d’outils principale*\) : similaire à la barre d’outils principale de l’éditeur web. Voir [Barre d’outils principale](web-editor-features.md#id2051EA0G05Z) dans l’éditeur web pour plus d’informations.

   - **B** - \(*barre d’outils Secondaire*\) Il s’agit de la barre d’outils Secondaire qui vous permet d’utiliser des fichiers de mappage. Pour plus d’informations sur les fonctionnalités disponibles via la barre d’outils Secondaire, consultez [Fonctionnalités disponibles dans la barre d’outils de l’éditeur de cartes avancé](#id205DEC0005Z).

   - **C** - \(*Vues des cartes*\) : permet de basculer l’éditeur de cartes entre les options Disposition, Auteur, Source et Aperçu. La **disposition** vue permet d&#39;organiser les rubriques dans un plan DITA. Cela donne l’arborescence ou la vue hiérarchique de la carte. La vue **Auteur** vous permet de modifier les rubriques dans l’éditeur de cartes. Cela donne également la vue WYSIWYG du fichier de mappage. La vue **Source** vous permet d&#39;utiliser le code XML sous-jacent du fichier de mappage. L’aperçu vous donne une vue consolidée de toutes les rubriques et sous-cartes dans le fichier de mappage. Le lien **Fermer** ferme le fichier de mappage.

   - **D** - \(*Panneau de gauche*\) : donne accès au panneau de gauche, qui permet d’accéder aux Favoris, au Référentiel, à la Carte, à la Composition et à d’autres fonctionnalités. Vous pouvez le développer ou le réduire en cliquant sur l’icône Développer la barre latérale \(![](images/sidebar-expand-icon.svg)\). Pour plus d’informations sur les fonctionnalités disponibles dans le panneau de gauche, consultez [Panneau de gauche](web-editor-features.md#id2051EA0M0HS) dans l’éditeur web.

   - **E** - \(*Zone centrale*\) : zone d’édition du contenu de la carte.

   - **F** - \(*Panneau de droite*\) : permet d’accéder au panneau Propriétés. Vous pouvez afficher les propriétés de contenu et les propriétés de mappage de la rubrique ou du mappage sélectionné. Pour plus d’informations sur les fonctionnalités disponibles dans ce panneau, consultez [Panneau de droite](web-editor-features.md#id2051EB003YK) dans l’éditeur web.

1. Dans le panneau de gauche, passez à la **Vue du référentiel**.

1. Dans le référentiel AEM, accédez au dossier contenant les rubriques ou les sous-mappages à ajouter.

1. Sélectionnez le fichier de rubrique ou de mappage dans la **Vue du référentiel** et faites-le glisser dans la zone d’édition du contenu du mappage \(au milieu\).

   La rubrique est ajoutée dans la carte.

   ![ajout d’une rubrique dans l’éditeur de mappages](images/map-editor-add-topic.png){width="800" align="left"}

1. Pour ajouter des rubriques suivantes ou une sous-carte, faites glisser et déposez la rubrique ou la sous-carte vers l’emplacement souhaité dans la carte.

   Tenez compte des points suivants lors de la création de votre fichier map :

   - Le fichier est ajouté à un emplacement où la barre horizontale apparaît dans la zone d’édition de la carte. Dans la capture d’écran suivante, la rubrique *Présentation* est ajoutée entre les rubriques *Description générale* et *Lancement et site d’entrée*.

     ![](images/horizontal-line-in-adv-map-editor.png){width="350" align="left"}

   - Pour remplacer une rubrique, placez la rubrique en haut, à gauche ou à droite de la rubrique à remplacer. Une barre verticale située à gauche ou à droite d&#39;une rubrique indique qu&#39;elle sera remplacée par la rubrique déposée dessus.

     ![](images/vertical-bar-left-right.png){width="550" align="left"}

     Cependant, avant de remplacer une rubrique, vous recevez une invite de confirmation. La rubrique n&#39;est remplacée qu&#39;après confirmation.

     ![](images/replace-topic-confirm.png){width="300" align="left"}

   - Si vous ajoutez une sous-carte à votre plan DITA, la sous-carte s&#39;affiche sous la forme d&#39;un lien dans le plan DITA. Pour afficher toutes les rubriques de la sous-carte, cliquez sur le lien de la sous-carte tout en maintenant la touche Ctrl enfoncée. Le contenu de la sous-carte est affiché dans un nouvel onglet. De même, pour ouvrir une rubrique à partir du plan DITA, appuyez sur Ctrl+Clic sur le lien de la rubrique et elle s&#39;ouvre dans le nouvel onglet.

   - Vous pouvez utiliser les touches de raccourci CTRL+Z et CTRL+Y ou leurs icônes respectives dans la barre d’outils pour annuler ou rétablir toute modification de la carte.

   - Pour modifier la position d’une rubrique, sélectionnez la rubrique \(en cliquant sur l’icône de rubrique\), puis faites-la glisser à l’emplacement souhaité dans le fichier de mappage. Assurez-vous que la barre horizontale est visible à l’emplacement où vous souhaitez placer la rubrique. Dans la capture d’écran suivante, la rubrique *Lancement et site d’entrée* est déplacée après la rubrique *Présentation*.

     ![](images/move-topic-adv-map-editor.png){width="350" align="left"}

   - Pour vérifier les propriétés de votre fichier de carte, cliquez avec le bouton droit de la souris n&#39;importe où dans la zone d&#39;édition de la carte et choisissez **Propriétés** dans le menu contextuel. Selon votre version d’AEM, vous pouvez voir des propriétés telles que les métadonnées, la planification de l’activation, les références, l’état du document, etc.

1. Cliquez sur **Enregistrer**.


## Fonctionnalités disponibles dans la barre d’outils de l’éditeur de cartes avancé {#id205DEC0005Z}

La barre d’outils de l’éditeur de cartes avancé est similaire à celle de la rubrique Éditeur web. Les opérations de base telles que le basculement du panneau de gauche, l’enregistrement du mappage, la création d’une nouvelle version du mappage, l’annulation/la restauration de la dernière opération et la suppression des éléments sélectionnés sont communes aux deux éditeurs. Pour plus d’informations sur le fonctionnement de ces opérations, consultez la section [Connaître les fonctionnalités de Web Editor](web-editor-features.md#).

Les opérations spécifiques à la carte suivantes sont également disponibles sur la barre d’outils en mode Mise en page et Création :

## Mode Mise en page {#id205DEC0005Z_layout_view}

Lorsque vous ouvrez une carte pour la modifier, le mode Mise en page de l’éditeur de cartes s’ouvre. Ce mode affiche la hiérarchie de la carte dans une arborescence et vous permet d’organiser les rubriques dans une carte.

>[!NOTE]
>
> Le mode Mise en page affiche uniquement les références présentes dans une carte. Si des références sont rompues, un petit symbole croisé s&#39;affiche à gauche de la référence

Vous pouvez effectuer les tâches suivantes en mode Mise en page :

**Insérer une référence de rubrique** - ![](images/insert-topic-reference.png)

Affiche la boîte de dialogue de recherche de rubrique. Accédez au fichier de rubrique/mappage à insérer et cliquez sur Sélectionner pour l’ajouter au mappage.
![](images/insert-topic-reference-dialog.png){width="800" align="left"}


**Insérer un groupe de sujets** - ![](images/insert-topic-group.png)

Insérez l’élément `topicgroup`. Pour plus d&#39;informations sur le regroupement des rubriques, consultez la documentation [topicgroup](https://docs.oasis-open.org/dita/v1.0/langspec/topicgroup.html) dans Spécification du langage OASIS DITA.

**Insérer une définition de clé** - ![](images/Key_icon.svg)

Affiche la boîte de dialogue Insérer une clé. Utilisez cette boîte de dialogue pour définir toute définition de clé que vous souhaitez utiliser dans le mappage.

![](images/insert-key-definition-dialog.png){width="300" align="left"}

**Insérer avant/insérer après** - ![](images/insert_element_before_icon.svg)/![](images/insert_element_after_icon.svg)

Affiche la boîte de dialogue Insérer un élément. Sélectionnez l&#39;élément à insérer dans le mappage. Selon l&#39;opération, le nouvel élément est inséré avant ou après l&#39;élément courant dans la carte.

**Insérer le sujet principal** - ![](images/frontmatter.svg)

Cette icône s’affiche lorsque vous ouvrez une carte des signets à des fins de modification. Vous pouvez insérer des composants au début de la liasse, tels qu’une table des matières, un index et une liste de tables.

**Insérer le sujet précédent** - ![](images/backmatter.svg)

Cette icône s’affiche lorsque vous ouvrez une carte des signets à des fins de modification. Vous pouvez insérer des composants pour une fin de livre, tels qu&#39;un index, un glossaire et une liste de figures.

**Déplacer l’élément sélectionné vers la gauche/droite** - ![](images/left-arrow-icon.png)/![](images/right-arrow-icon.png)

Cliquez sur la flèche de gauche pour déplacer la rubrique vers la gauche de la hiérarchie. Cela permet essentiellement de promouvoir le sujet respectif un niveau plus haut dans la hiérarchie. Par exemple, cliquer sur la flèche de gauche alors qu&#39;une rubrique enfant est sélectionnée la rend apparentée à la rubrique au-dessus. De même, si vous cliquez sur la flèche droite, le sujet est poussé vers la droite, ce qui en fait l&#39;enfant du sujet au-dessus.

**Déplacer l’élément sélectionné vers le haut/bas![](images/arrowup.svg)** - / ![](images/arrowdown.svg)

Cliquez sur les icônes de flèche vers le haut ou vers le bas pour déplacer la rubrique vers le haut ou vers le bas dans la hiérarchie.

>[!NOTE]
>
> Vous pouvez également faire glisser et déposer les références pour les déplacer dans un mappage.

**Verrouiller/Déverrouiller** - ![](images/LockClosed_icon.svg) / ![](images/LockOpen_icon.svg)

Obtient un verrou sur le fichier de carte et libère le verrou. Si votre fichier de mappage contient des modifications non enregistrées, au moment de la libération du verrou, vous êtes invité à enregistrer le fichier de mappage. Les modifications sont enregistrées dans la version actuelle du fichier de mappage.

**Fusionner** - ![](images/merge-icon.svg)

Pour plus d’informations sur la fusion de contenu à partir d’une autre version du même fichier ou d’un fichier différent, consultez [Fusion](web-editor-features.md#id205DF04E0HS) dans l’éditeur web.

**Historique des versions** - ![](images/version-history-web-editor-ico.svg)

Vérifiez les versions et les libellés disponibles sur votre rubrique active, puis revenez à n’importe quelle version à partir de l’éditeur lui-même.

**Libellé de version** - ![](images/version-label-icon.svg)

Affiche la boîte de dialogue de gestion des libellés de version. Sélectionnez une version dans la liste déroulante. Sélectionnez le libellé à appliquer à la version sélectionnée, puis cliquez sur **Ajouter un libellé** pour l’ajouter.

**Afficher les options** - ![](images/view-options.svg)

Affiche une liste déroulante qui vous permet d&#39;afficher les numéros de ligne, la case à cocher et le nom de fichier.

- **Afficher les numéros de ligne**

Affiche ou masque le numéro de ligne pour chaque rubrique. Les numéros de ligne s’affichent en fonction du niveau dans la hiérarchie.

- **Afficher la case à cocher**

Affiche ou masque une case à cocher pour chaque rubrique. Vous pouvez utiliser la case à cocher pour sélectionner la ou les rubriques et effectuer diverses tâches à l’aide du menu Options. Pour plus d’informations, consultez le menu [Options](#id228ID8006H8).

- **Afficher le nom du fichier**

Affiche le nom de fichier des titres des rubriques.

>[!NOTE]
>
> Lorsque vous placez le pointeur de la souris sur le titre d&#39;une rubrique, le chemin d&#39;accès au fichier s&#39;affiche.


**Affichage des rubriques en fonction de filtres conditionnels** Si vous avez appliqué des conditions à une rubrique, une icône de filtre s’affiche à droite de la rubrique. Lorsque vous placez le pointeur sur une icône de filtre, la condition appliquée et sa valeur d’attribut s’affichent.

**Menu Options en mode Mise en page**

Outre l’organisation des rubriques dans le fichier de mappage, vous pouvez également effectuer les actions suivantes à l’aide du menu Options disponible pour un élément en mode Mise en page :

![](images/map-editor-options-menu.png){width="650" align="left"}

- **Ajouter** : vous pouvez choisir d’ajouter une nouvelle rubrique ou une référence vide à partir de l’éditeur de cartes :
   - **Référence vide** : cette option vous permet d&#39;ajouter une référence vide dans votre plan DITA. Vous pouvez double-cliquer ultérieurement sur la référence vide insérée et ajouter les détails de la rubrique. Pour plus d’informations, consultez la section [Créer une rubrique](web-editor-features.md#id228ICI0105U) dans l’éditeur web.
   - **Nouvelle rubrique** : lorsque vous choisissez de créer une nouvelle rubrique à partir du menu, vous accédez à la boîte de dialogue Créer une rubrique. Dans la boîte de dialogue Créer une rubrique , fournissez les détails requis et cliquez sur Créer. Pour plus d’informations, consultez la section [Créer une rubrique](web-editor-features.md#id228ICI0105U) dans l’éditeur web.
- **Déplacer** : permet de déplacer une rubrique vers le haut/bas/droite/gauche dans la hiérarchie. Vous pouvez également faire glisser une rubrique ou une carte du panneau Référentiel vers la carte ouverte dans l’éditeur de cartes.
- **Annuler** : permet d’annuler la dernière opération en mode Mise en page.
- **Rétablir** : permet de rétablir la dernière opération en mode Mise en page.
- **Copier** : copie la référence sélectionnée du fichier de mappage.

  >[!NOTE]
  >
  > Vous pouvez afficher et sélectionner les cases à cocher pour copier plusieurs références.

- **Coller** : collez les références copiées à l’emplacement actuel dans la hiérarchie.
- **Supprimer** : supprimez les références sélectionnées du fichier de mappage.

  >[!NOTE]
  >
  > Vous pouvez afficher et sélectionner les cases à cocher pour supprimer plusieurs références.


## Panneau de droite dans l’éditeur de cartes

Le panneau de droite affiche les propriétés de contenu et les propriétés de carte en mode Mise en page de l’éditeur de cartes.

**Propriétés du contenu**

Le panneau Propriétés du contenu contient des informations sur le type de rubrique actuellement sélectionnée dans la carte, son URL de lien et ses attributs. Pour plus d’informations, voir [Propriétés du contenu](web-editor-features.md#id228IDB00HMM) dans l’éditeur web.

- **Autres attributs** Si votre administrateur a créé un profil pour les attributs, vous obtiendrez ces attributs ainsi que leurs valeurs configurées. À l’aide du panneau Propriétés du contenu , vous pouvez choisir ces attributs et les affecter au contenu approprié dans votre rubrique. Vous pouvez également affecter des attributs configurés par votre administrateur sous l’onglet **Attributs d’affichage** dans les paramètres de l’éditeur. Les attributs définis pour un élément sont affichés en mode Mise en page et Plan. Cela vous permet d’avoir un aperçu rapide de toutes les rubriques d’un mappage pour lequel un attribut particulier est défini. Par exemple, toutes les rubriques dont l’attribut de plateforme est défini sur « Android ».

  ![mode mise en page](images/layout-inline-attributes.png){width="650" align="left"}


  Pour plus d’informations, consultez la description de la fonctionnalité *Attributs d’affichage* dans la section *Paramètres de l’éditeur* dans le [Panneau de gauche](web-editor-features.md#id2051EA0M0HS).

- **Métadonnées** à l’aide des métadonnées , vous pouvez définir les informations de métadonnées. Vous pouvez définir le titre de navigation, le texte du lien, la description courte et les mots-clés.

Pour plus d&#39;informations sur les métadonnées et les attributs de rubrique standard, reportez-vous à la documentation [topicref](https://docs.oasis-open.org/dita/v1.2/os/spec/langref/topicref.html) dans Spécification de langage OASIS DITA.

**Propriétés de la carte**

Affiche la boîte de dialogue Propriétés du mappage dans laquelle vous pouvez définir les attributs et les informations de métadonnées du mappage.

## Vue Auteur {#id205DEC0005Z_author_view}

La vue **Auteur** vous permet de modifier votre plan DITA dans l&#39;éditeur web. La vue WYSIWYG de l’éditeur de cartes s’affiche, et certaines des icônes affichées en mode Création sont identiques à la vue Mise en page. Pour plus d’informations, voir [Mode Mise en page](#id205DEC0005Z_layout_view). En outre, vous pouvez voir les icônes suivantes et effectuer les tâches associées à partir de la vue Auteur :

**Insérer avant/insérer après** - ![](images/insert_element_before_icon.svg)/![](images/insert_element_after_icon.svg)

Affiche la boîte de dialogue Insérer un élément. Sélectionnez l&#39;élément à insérer dans le mappage. Selon l&#39;opération, le nouvel élément est inséré avant ou après l&#39;élément courant dans la carte.

**Insérer un élément** - ![](images/Add_icon.svg)

Affiche la boîte de dialogue Insérer un élément. Sélectionnez l’élément à insérer. Vous pouvez utiliser le clavier pour faire défiler la liste des éléments et appuyer sur Entrée pour insérer l’élément requis. Vous pouvez également cliquer directement sur l’élément pour l’insérer dans le mappage.

**Insérer une table de relation** - ![](images/relationship_table_icon.svg)

Insère une table de relation dans le mappage. Comme le concept d’utilisation de la table de relation est identique à celui expliqué dans la section Éditeur de mappage de base , consultez [Utilisation des tables de relation dans l’éditeur de mappage de base](map-editor-basic-map-editor.md#id1944B0I0COB) pour plus d’informations.

**Insertion de contenu réutilisable** - ![](images/content-reuse-icon.png)

Affiche la boîte de dialogue Réutiliser le contenu . Utilisez cette boîte de dialogue pour insérer le contenu que vous souhaitez réutiliser dans votre carte.

**Actualiser l’attribut de titre de navigation** - ![](images/navtitle-refresh-icon.svg)

Synchronise l&#39;élément `title` d&#39;un fichier référencé dans un mapping avec la valeur spécifiée dans son attribut `@navtitle`. Vous pouvez ajouter différents types de fichiers de référence dans un mappage, par exemple des mappages de rubrique, de référence, de tâche, \(sub\), etc. La plupart de ces fichiers prennent en charge l’attribut `@navtitle`. Si un fichier contient l’attribut `@navtitle`, l’attribut `@navtitle` du même fichier dans le mappage est mis à jour. Si l’attribut `@navtitle` n’est pas présent, l’attribut `@navtitle` est ajouté à ce fichier de référence et son `title` est également mis à jour pour afficher le `@navtitle`.

>[!NOTE]
>
> Votre administrateur peut configurer l’ajout automatique de l’attribut `@navtitle` à chaque fichier de référence que vous ajoutez à une carte. Pour plus d’informations sur la configuration de l’attribut `@navtitle` d’ajout automatique, voir *Inclure l’attribut @navtitle par défaut* dans Installation et configuration d’Adobe Experience Manager Guides as a Cloud Service.

Cliquez sur l’icône Actualiser l’attribut de titre de navigation pour synchroniser les valeurs de l’élément de `title` et de l’attribut de `@navtitle`.

**Activer/désactiver la vue Balises** - ![](images/Label_icon.svg)

Affiche ou masque les balises XML. Les balises servent de repères visuels indiquant la limite d’un élément. Dans ce mode, si vous souhaitez insérer une référence de rubrique/mappage, faites glisser et déposez le fichier souhaité avant ou après la balise. La barre horizontale ne s’affiche pas en mode Balises .

**Activer/Désactiver Le Suivi Des Modifications** - ![](images/track-change-icon.svg)

Vous pouvez conserver une trace de toutes les mises à jour effectuées dans le fichier de mappage en activant le mode Suivi des modifications. Une fois le suivi des modifications activé, toutes les insertions et suppressions sont capturées dans le document. Pour plus d’informations, consultez [Activation/désactivation du suivi des modifications](web-editor-features.md#id205DF0203Y4) dans l’éditeur web.

**Créer une tâche de révision** - ![](images/create-review-task-icon.svg)

Vous pouvez créer une tâche de révision de la rubrique active ou mapper le fichier directement à partir de l&#39;éditeur Web. Ouvrez le fichier pour lequel vous souhaitez créer la tâche de révision et cliquez sur Créer une tâche de révision pour lancer le processus de création de révision. Suivez les instructions données dans la section [Rubriques de révision ou cartes](review.md#) pour plus de détails.

## Modifier les rubriques via le plan DITA {#id17ACJ0F0FHS}

La modification d’une rubrique individuelle ne donne pas le contexte complet à l’auteur. Un auteur ne dispose d&#39;aucune information sur l&#39;emplacement d&#39;une rubrique dans un plan DITA. Sans ces informations contextuelles, il devient un peu difficile pour les auteurs de créer du contenu.

AEM Guides permet aux auteurs d&#39;ouvrir un plan DITA dans l&#39;éditeur Web et de voir le placement des rubriques dans le plan. Cela permet aux auteurs de savoir où exactement le sujet est placé sur la carte et de créer du contenu plus pertinent. En outre, si plusieurs auteurs travaillent sur un projet, ils peuvent connaître tous les sujets disponibles sur la carte et réutiliser le contenu, si nécessaire.

Pour modifier des rubriques via un plan DITA, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez au plan DITA qui contient les rubriques à modifier.
1. Cliquez sur le plan DITA pour l&#39;ouvrir dans la console Plan DITA.
1. Sélectionnez l&#39;onglet **Rubriques** pour afficher la liste des rubriques disponibles dans le plan DITA.

   >[!TIP]
   >
   > L’onglet Rubriques vous donne la possibilité de télécharger le fichier de mappage avec ses dépendants. Pour plus d&#39;informations, voir [Exporter un fichier de plan DITA](authoring-download-assets.md#id218UBA00IXA).

1. Dans la barre d&#39;outils principale, cliquez sur **Modifier les rubriques**.

   Le plan DITA s&#39;ouvre dans l&#39;éditeur Web.

   >[!NOTE]
   >
   > Vous pouvez également sélectionner le fichier de plan DITA dans l&#39;interface utilisateur d&#39;Assets et cliquer sur **Modifier les rubriques** dans la barre d&#39;outils principale pour lancer l&#39;éditeur Web.

   ![](images/web-editor-map-view_cs.png){width="350" align="left"}

1. \(*Facultatif*\) Vous pouvez également sélectionner une rubrique dans la carte et extraire le fichier avant de le modifier. Pour extraire un ou plusieurs fichiers, sélectionnez-les dans le volet de gauche, puis cliquez sur **Extraire**. Vous pouvez également déverrouiller n&#39;importe quel fichier en sélectionnant le fichier extrait et en cliquant sur l&#39;icône **Annuler l&#39;extraction et déverrouiller** dans la vue Carte.

   >[!IMPORTANT]
   >
   > Si votre administrateur a configuré l’option **Désactiver la modification sans extraction**, vous devez extraire le fichier avant de le modifier. Si vous n’extrayez pas le fichier, le document s’ouvre dans l’éditeur en mode lecture seule.

   La capture d&#39;écran suivante met en surbrillance les icônes Extraction et verrouillage \(A\), Annuler l&#39;extraction et déverrouiller \(B\), Enregistrer comme nouvelle version et déverrouiller \(C\), Modifier \(D\), Aperçu \(E\), différentes icônes indiquant différents types de fichiers DITA \(F\) et les fichiers extraits \(G\).

   ![](images/file-checkout-map-editor.png){width="550" align="left"}

1. Cliquez sur un lien de rubrique pour l’ouvrir dans l’éditeur web afin de le modifier.

   Vous pouvez ouvrir plusieurs rubriques dans l’éditeur et chaque rubrique est ouverte dans un nouvel onglet de l’éditeur. Même si votre plan DITA contient des sous-plans, les rubriques des sous-plans sont également ouvertes dans un nouvel onglet pour modification. Si vous souhaitez visualiser les rubriques sous une sous-carte, vous pouvez cliquer sur la sous-carte et la développer.

   ![](images/web-editor-multiple-topics.png){width="800" align="left"}

   Si vous cliquez sur un fichier de mappage, le mappage est ouvert dans un nouvel onglet du navigateur web.

1. Une fois la modification des rubriques terminée, vous pouvez effectuer les opérations suivantes :

   - Vous pouvez les enregistrer individuellement. Si vous cliquez sur **Fermer sans enregistrer** vos rubriques, une boîte de dialogue s’affiche pour vous inviter à enregistrer les rubriques non enregistrées :

     ![](images/save-multiple-topics.PNG){width="550" align="left"}

     Vous pouvez choisir d’enregistrer toutes les rubriques sélectionnées ou de désélectionner les rubriques que vous ne souhaitez pas enregistrer.

   - Vous pouvez archiver la rubrique à l’aide du bouton **Enregistrer en tant que nouvelle version et déverrouiller**. Lorsque vous enregistrez une version de la rubrique, une nouvelle version est créée et le verrou est également libéré.

     Il est recommandé d’enregistrer vos modifications avant d’archiver les fichiers.  Lorsque vous enregistrez les modifications, le fichier XML est validé.

   - Vous pouvez également sélectionner et archiver plusieurs rubriques à l’aide du bouton **Enregistrer en tant que nouvelle version et Déverrouiller**. Lorsque vous enregistrez une version des rubriques, une nouvelle version est créée pour chaque rubrique et le verrou est également libéré. Vous pouvez également afficher la progression de l’archivage des rubriques dans la boîte de dialogue **Enregistrer en tant que nouvelle version et déverrouiller**. Un message de réussite s’affiche lorsque les fichiers sont archivés.

   - Si votre administrateur a activé l&#39;option d&#39;archivage des fichiers à la fermeture, une invite vous sera présentée pour enregistrer les fichiers chaque fois que les fichiers extraits seront fermés. Lorsque cette option est activée, lorsque vous fermez l’éditeur avec des fichiers modifiés, la liste des fichiers extraits qui doivent être enregistrés s’affiche. Les fichiers extraits s’affichent avec une icône de verrouillage :

     ![](images/save-on-close.PNG){width="550" align="left"}

      - Cliquez sur le bouton **Fermer sans enregistrer** pour fermer les fichiers sans enregistrer les modifications.

      - Cliquer sur le bouton **Enregistrer** permet d’enregistrer les modifications, mais sans archiver les fichiers.

      - Sélectionnez l’option **Vérification des fichiers**, puis cliquez sur le bouton **Enregistrer** pour archiver les fichiers \(crée une autre version\) et enregistrer également les fichiers.


## Prévisualiser un mappage

En plus de pouvoir voir la position de chaque fichier de rubrique dans une carte, il est souhaitable d’afficher le contenu de la carte dans un flux consécutif. La fonction Aperçu de la carte vous permet de voir l&#39;intégralité du contenu du fichier de carte en un seul clic. Vous n’avez pas besoin de générer une sortie du fichier de mappage pour voir à quoi ressemblera le mappage entier une fois publié. Vous pouvez simplement accéder à l&#39;aperçu de la carte et tous les sujets et sous-cartes sont rendus sous la forme d&#39;un livre.

Vous pouvez accéder à l’aperçu d’une carte depuis :

- **Interface utilisateur d’Assets** : dans l’interface utilisateur d’Assets, accédez à l’emplacement du mappage, sélectionnez le fichier de mappage et choisissez **Prévisualiser le mappage** dans la barre d’outils. L’aperçu de la carte s’affiche dans un nouvel onglet. Vous pouvez afficher le contenu de toutes les rubriques en mode Aperçu. Dans cet affichage, vous ne pouvez modifier aucune rubrique.

  >[!NOTE]
  >
  > Si l’option *Prévisualiser le mappage* n’est pas visible dans la barre d’outils principale, elle a peut-être été déplacée sous le menu de la barre d’outils **Plus**.

- **Éditeur de carte avancé** : dans l’éditeur de carte avancé, cliquez sur l’icône Aperçu pour afficher l’aperçu de la carte actuelle.

  ![](images/map-preview-icon.png){width="350" align="left"}

  Vous pouvez effectuer les tâches supplémentaires suivantes en mode Aperçu :

   - Cliquez avec le bouton droit de la souris sur une rubrique, puis sélectionnez **Modifier** pour ouvrir la rubrique afin de la modifier dans un nouvel onglet.

     >[!NOTE]
     >
     > Si vous ne disposez pas de droits de modification, la rubrique s’ouvre en mode lecture seule.

   - Accédez à la rubrique souhaitée en cliquant sur le titre de la rubrique dans l’arborescence de carte \(dans le panneau de gauche\).

   - La rubrique actuelle dans la prévisualisation de la carte est également mise en surbrillance dans l&#39;arborescence de la carte.


**Rubrique parente :** [Utiliser l’éditeur de cartes](map-editor.md)
