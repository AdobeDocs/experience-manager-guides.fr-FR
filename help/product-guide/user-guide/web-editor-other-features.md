---
title: Fonctionnalités supplémentaires de l’éditeur
description: Découvrez d’autres fonctionnalités de l’éditeur dans Adobe Experience Manager Guides. Découvrez comment utiliser ces fonctionnalités pour améliorer la création dans Experience Manager Guides.
exl-id: 1833b1e3-c7f1-4f2c-be35-235b65ba2f36
feature: Authoring, Web Editor
role: User
source-git-commit: c8ea6eae180ce7045a0364713604711aae2bb6bd
workflow-type: tm+mt
source-wordcount: '2556'
ht-degree: 0%

---

# Fonctionnalités supplémentaires de l’éditeur {#id2056B0B0YPF}

L’éditeur comporte d’autres fonctionnalités utiles que vous pouvez utiliser :

## Fonctions du menu contextuel dans l’onglet d’un fichier

Lorsque vous ouvrez un fichier dans l’éditeur, vous pouvez effectuer différentes actions à partir du menu contextuel. Vous pouvez afficher différentes options selon que vous ouvrez un fichier multimédia, un fichier DITA unique ou plusieurs fichiers.

**Fichier multimédia**

Les fonctions suivantes sont disponibles dans le menu contextuel de l’onglet d’un fichier multimédia ouvert :

![](images/media-file-context-menu.png){width="300" align="left"}


**Fichier DITA unique**

Le menu contextuel de l’onglet d’un fichier ouvert contient les fonctions suivantes :

![](images/single-file-context-menu.png){width="400" align="left"}

**Plusieurs fichiers**

Lorsque plusieurs fichiers sont ouverts, le menu contextuel propose d’autres options :

![](images/multiple-files-context-menu.png){width="550" align="left"}

Les différentes options du menu contextuel sont expliquées ci-dessous :

***Enregistrer*** : vous pouvez choisir parmi les options suivantes :

- **Enregistrer** : pour enregistrer un fichier sans créer de nouvelle version, sélectionnez **Enregistrer**. Chaque fois que vous créez une rubrique, une copie de travail sans version de la rubrique est créée dans la gestion des ressources numériques. L’enregistrement de votre document met à jour la copie de travail de votre document dans la gestion des ressources numériques. Un simple enregistrement sur cette version ne crée pas de nouvelle version d’une rubrique. Si votre rubrique est en cours de révision, l&#39;enregistrement d&#39;une rubrique ne permet pas à vos réviseurs d&#39;accéder au contenu de la rubrique modifiée.

- **Enregistrer tout** : si plusieurs documents sont ouverts dans l’éditeur, vous avez également la possibilité d’**Enregistrer tout** les documents ouverts.


***Enregistrer Comme Nouvelle Version***

Pour créer une nouvelle version du fichier, sélectionnez **Enregistrer comme nouvelle version**. Pour plus d’informations sur **Enregistrer** et **Enregistrer en tant que nouvelle version**, consultez la section [Connaître les fonctionnalités de l’éditeur](web-editor-features.md#).

***Copier*** : vous pouvez choisir parmi les options suivantes :

- **Copier l’UUID** : pour copier l’UUID du fichier actif dans le Presse-papiers, sélectionnez **Copier \> Copier l’UUID**.
- **Copier le chemin** : pour copier dans le presse-papiers le chemin d’accès complet du fichier actif, sélectionnez **Copier \> Copier le chemin**.


***Localiser dans*** : vous pouvez choisir parmi les options suivantes :

- **Mappage** : si vous avez ouvert un plan DITA volumineux et que vous souhaitez trouver l&#39;emplacement exact d&#39;un fichier dans le plan, sélectionnez **Localiser dans \> Mappage**. Lorsque vous sélectionnez l’option Localiser dans le mappage , le fichier \(d’où l’option est appelée\) est situé et mis en surbrillance dans la hiérarchie du mappage. Pour pouvoir utiliser cette fonctionnalité, vous devez ouvrir le fichier de mappage dans l’éditeur. Si la vue de carte est masquée, l’appel de cette fonction affiche la vue de carte et le fichier est mis en surbrillance dans la hiérarchie de carte.

- **Référentiel** : tout comme Localiser dans Map, **Localiser dans \> référentiel** indique l’emplacement du fichier dans le référentiel \(ou DAM\). La vue du référentiel est ouverte et le fichier sélectionné est mis en surbrillance dans le référentiel. Si le fichier se trouve dans un dossier, ce dossier est développé pour afficher l’emplacement du fichier sélectionné dans le référentiel.


***Ajouter à*** : vous pouvez choisir parmi les options suivantes :

- **Collections** : pour ajouter le fichier sélectionné aux collections, sélectionnez **Ajouter aux \> collections**. Pour plus d’informations, consultez la description de la fonctionnalité **Collections** dans la section [Panneau de gauche](web-editor-features.md#left-panel).

- **Contenu réutilisable** : pour copier le fichier sélectionné dans la liste de contenu réutilisable, sélectionnez **Ajouter à \> Contenu réutilisable**. Pour plus d’informations, consultez la description de la fonctionnalité **Contenu réutilisable** dans la section [Panneau de gauche](web-editor-features.md#left-panel).

***Propriétés***

Pour afficher la page des propriétés AEM du fichier sélectionné, sélectionnez **Propriétés**.

***Fractionner*** : vous pouvez choisir parmi les options suivantes :

**Haut, Bas, Gauche ou Droite**

Par défaut, l’éditeur vous permet d’afficher une rubrique à la fois. Il peut y avoir des cas où vous souhaitez afficher plusieurs sujets en même temps. Le fractionnement de l’écran de l’éditeur vous permet d’afficher plusieurs rubriques en même temps. Par exemple, si vous avez deux rubriques : A et B ouvertes dans l’éditeur. Cliquez avec le bouton droit sur la rubrique B et choisissez **Fractionner \> vers le haut** pour diviser la fenêtre de l’éditeur en deux parties. La rubrique B est affichée dans la moitié supérieure et la rubrique A est affichée dans la moitié inférieure. De même, vous pouvez également fractionner l’écran horizontalement en sélectionnant **Fractionner \> à gauche** ou **Fractionner \> à droite**. Vous pouvez déplacer vos documents d&#39;un écran à l&#39;autre en faisant glisser l&#39;onglet Fichier et en le déposant sur l&#39;écran où vous souhaitez le placer. De même, vous pouvez réorganiser les onglets de fichiers en les faisant glisser et en les déplaçant selon vos préférences.



<!--------------------------------------------

***Quick Generate***

Generate the output for the selected file. Output can be generated only for files that are a part of an output preset. For more details, view [Article-based publishing from the Web Editor](web-editor-article-publishing.md#id218CK0U019I).

--->

***Fermer*** : vous pouvez choisir parmi les options suivantes :

**Fermer**, **Fermer les autres** ou **Tout fermer**

Pour fermer le fichier à partir duquel vous avez appelé le menu contextuel, sélectionnez **Fermer \> Fermer**. Utilisez **Fermer \> Fermer les autres** pour fermer tous les autres fichiers ouverts, à l’exception du fichier actif. Pour fermer tous les fichiers ouverts, sélectionnez l’option **Fermer \> Fermer tout** dans le menu contextuel. Vous pouvez également choisir de fermer l’éditeur. Si votre session contient des fichiers non enregistrés, vous êtes invité à les enregistrer.

**Fermer un fichier et enregistrer des scénarios**

Lorsque vous tentez de fermer un fichier ouvert dans l’éditeur à l’aide du bouton **Fermer** de l’onglet du fichier ou de l’option **Fermer** du menu Options, Experience Manager Guides vous invite à enregistrer vos modifications et à déverrouiller un fichier verrouillé.

Les invites sont basées sur les configurations suivantes sélectionnées par votre administrateur :

- **Demander le déverrouillage à la fermeture :** vous avez la possibilité de déverrouiller le fichier \(que vous avez verrouillé\) lorsque vous fermez l’éditeur.
- **Demander la nouvelle version à la fermeture** : l’option permettant d’enregistrer le fichier \(que vous avez modifié\) en tant que nouvelle version s’affiche à la fermeture de l’éditeur.

Votre expérience d’enregistrement de fichier dépend des trois scénarios suivants, dans lesquels vous disposez des éléments suivants :

- Aucune modification n’a été apportée au contenu.
- Modifiez le contenu et enregistrez les modifications.
- A modifié le contenu mais n’a pas enregistré les modifications.

Vous pouvez afficher les options suivantes selon que le fichier est verrouillé/déverrouillé et qu’il contient des modifications enregistrées ou non :

- **Déverrouiller et fermer** : le verrouillage du fichier est désactivé et le fichier est fermé.
- **Enregistrer en tant que nouvelle version** : les modifications que vous avez apportées à votre contenu seront enregistrées et une nouvelle version de votre fichier sera créée. Vous pouvez également ajouter des libellés et des commentaires pour la version nouvellement enregistrée. Pour plus d’informations sur l’enregistrement d’une nouvelle version, voir [Enregistrer en tant que nouvelle version](web-editor-features.md#save-as-new-version).

- **Déverrouiller le fichier** : si vous choisissez de déverrouiller un fichier, le verrouillage sera relâché et les modifications seront enregistrées dans la version actuelle du fichier.

  >[!NOTE]
  >
  > Si vous désélectionnez l’option pour déverrouiller le fichier, vous obtenez également une option pour fermer le fichier sans enregistrer les modifications.

  Par exemple, l’une des invites est affichée dans la capture d’écran suivante :

  ![](images/file-close-save-changes-unlock.png){width="400" align="left"}

**Repères visuels pour les références rompues**

Si votre rubrique contient des références croisées ou des références de contenu rompues, elles s&#39;affichent en rouge.

**Copie-collage intelligent**

Vous pouvez facilement copier et coller du contenu dans et entre des rubriques. La structure de l’élément source est conservée au niveau de la destination. En outre, si le contenu copié contient des références de contenu, même celles-ci sont copiées.

**Mémoriser le dernier emplacement parcouru**

L’éditeur fournit une boîte de dialogue de navigation dynamique dans les fichiers. L’éditeur mémorise le dernier emplacement utilisé lors de l’insertion d’une référence ou d’un contenu. La première fois que vous appelez la boîte de dialogue de recherche de fichier \(via Insérer une référence ou Insérer réutiliser le contenu\), vous accédez à l’emplacement où le document actif est enregistré. Au cours de la même session, si vous essayez d’insérer une autre référence, la boîte de dialogue de recherche de fichier permet d’accéder automatiquement à l’emplacement à partir duquel vous avez inséré la dernière référence.

>[!NOTE]
>
> Dans le cas d’un fichier image, audio ou vidéo, la boîte de dialogue de recherche de fichier correspond par défaut à l’emplacement du fichier et non au dernier emplacement utilisé.

## Prise en charge de la publication d’articles

Dans l&#39;éditeur, vous pouvez générer la sortie pour une ou plusieurs rubriques ou l&#39;ensemble du plan DITA. Vous devez créer des paramètres prédéfinis de sortie pour votre plan DITA, puis vous pouvez facilement générer la sortie pour une ou plusieurs rubriques. Si vous avez mis à jour quelques rubriques dans votre carte, vous pouvez également générer la sortie uniquement pour ces rubriques à partir de l’éditeur. Pour plus d’informations, consultez la section [Publication basée sur des articles](web-editor-article-publishing.md#id218CK0U019I).

## Prise en charge des documents Markdown

L&#39;éditeur vous permet d&#39;utiliser les documents Markdown \(.md\) avec vos documents DITA. Vous pouvez facilement créer et prévisualiser un document Markdown dans l&#39;éditeur et l&#39;ajouter dans votre fichier map via l&#39;éditeur de map DITA. Pour plus d’informations, consultez [Créer des documents Markdown à partir de l’éditeur](web-editor-markdown-topic.md#).

## Prise en charge du terme de glossaire DITA

L&#39;éditeur prend en charge les termes du glossaire DITA que vous pouvez insérer en ajoutant des éléments `term` ou `abbreviated-form`.

## Utiliser les équations de MathML

### Insérer des équations MathML

Experience Manager Guides vous offre une prise en charge prête à l’emploi pour insérer des équations MathML par intégration à l’application [MathType Web](https://docs.wiris.com/en/mathtype/mathtype_web/intro). Pour insérer une équation MathML, sélectionnez l’icône **Élément** et saisissez mathml. Lorsque vous sélectionnez l’élément mathml dans la liste, la boîte de dialogue **Insérer un MathML** s’affiche :

![insérer l’équation mathml dans l’éditeur mathml](images/insert-mathml-equation.png){width="550" align="left"}

À l&#39;aide des outils d&#39;équation de MathML, créez votre équation et sélectionnez **Insérer** pour l&#39;ajouter à votre document. L&#39;équation est insérée avec un arrière-plan gris clair.

Vous pouvez à tout moment mettre à jour une équation en cliquant avec le bouton droit de la souris sur une équation existante et en sélectionnant **Modifier MathML** dans le menu contextuel.

### Validation des équations dans l’éditeur de MathML

Experience Manager Guides valide les équations de MathML lorsque vous enregistrez une rubrique qui les contient.
Lorsque vous insérez une équation à l’aide de l’éditeur MathML, Experience Manager Guides met l’équation en surbrillance rouge en cas de problèmes de syntaxe. Vous pouvez le corriger avant de l’insérer. Si vous n&#39;apportez aucune modification, mais que vous sélectionnez **Insérer**, un avertissement s&#39;affiche.

![valider l’équation mathml](images/validate-mathml-equation.png){width="400" align="left"}

Si vous insérez l&#39;équation MathML qui contient une erreur de syntaxe, une erreur de validation se produit lorsque vous essayez d&#39;enregistrer la rubrique.


## Insérer des notes de bas de page

Insérez une note de bas de page dans votre contenu à l’aide de l’élément `fn`. En mode création, la valeur de la note de bas de page s’affiche en ligne avec le contenu. Cependant, lorsque vous basculez en mode Aperçu ou que vous publiez votre document, la note de bas de page s’affiche à la fin de la rubrique.


## Renommer ou remplacer un élément

L’éditeur affiche le chemin de navigation de l’élément en bas à gauche de la rubrique. Si vous souhaitez permuter ou remplacer un élément par un autre élément, vous pouvez le faire à partir du menu contextuel du chemin de navigation. Par exemple, vous pouvez permuter `p` élément avec `note` ou tout autre élément valide au niveau du contexte.

![](images/rename-element.png){width="400" align="left"}

Dans le chemin de navigation, cliquez avec le bouton droit sur le nom d’un élément à remplacer, puis sélectionnez Renommer l’élément dans le menu contextuel. La boîte de dialogue Renommer l’élément affiche tous les éléments valides autorisés à l’emplacement actuel. Dans la boîte de dialogue Renommer l’élément , sélectionnez l’élément que vous souhaitez utiliser. L’élément d’origine est remplacé par le nouvel élément .

Outre le menu contextuel du chemin de navigation, la boîte de dialogue Renommer l’élément est également accessible à partir d’autres emplacements :

- Sélectionnez le nom de l’élément dans le chemin de navigation pour sélectionner le contenu de l’élément et cliquez avec le bouton droit sur le contenu sélectionné pour afficher le menu contextuel.

- Activez la vue Balises, sélectionnez la balise d’ouverture d’un élément, puis cliquez avec le bouton droit de la souris sur le contenu sélectionné pour afficher le menu contextuel.

- Vous pouvez accéder à la boîte de dialogue Renommer l’élément en appelant le menu Options d’un élément dans le panneau Plan.

## Habillage et débrouillage d’un élément

### Développer un élément

- Envelopper un élément permet d’ajouter une balise d’élément au texte sélectionné. Vous pouvez renvoyer le texte à la ligne sur n&#39;importe quel élément enfant en respectant les normes DITA. Par exemple, si vous avez du texte sous un élément `note`, vous pouvez encapsuler le texte dans un élément `p`.

- L’option **Développer** est disponible dans le menu contextuel du chemin de navigation de la rubrique. Pour encapsuler un élément, cliquez avec le bouton droit de la souris sur l’élément et ouvrez le menu contextuel. Sélectionnez l’élément dans la boîte de dialogue **Enrouler l’élément**. Le texte apparaît dans le nouvel élément.

- Vous pouvez également sélectionner le texte ou l’élément dans le contenu, puis sélectionner l’option **Enrouler l’élément** dans le menu contextuel.

### Déplier un élément

Déplier un élément vous permet de supprimer la balise d’élément du texte sélectionné et de le fusionner avec son élément parent. Par exemple, si vous disposez d’un élément `p` dans un élément `note`, vous pouvez déplier l’élément `p` pour fusionner le texte directement dans l’élément `note`. L’option **Déplier l’élément** est disponible dans le menu contextuel du chemin de navigation de la rubrique. Pour déplier un élément, cliquez avec le bouton droit de la souris sur l’élément pour ouvrir le menu contextuel, puis sélectionnez **Déplier l’élément** pour supprimer l’élément et fusionner le texte de l’élément avec son élément parent.

## Gestion des espaces pour les éléments DITA

Dans le langage XML, les espaces comprennent les espaces, les tabulations, les retours à la ligne et les lignes vides. Experience Manager Guides convertit plusieurs espaces blancs conséquents en un seul espace. Cela permet de conserver la vue WYSIWYG de l’éditeur.

>[!NOTE]
>
> Dans certains éléments où les espaces blancs doivent être conservés conformément aux règles DITA, les multiples espaces blancs qui en résultent sont conservés. Par exemple, les éléments `<pre>` et `<codeblock>`.


## Conserver les sauts de ligne et la mise en retrait

Les éléments DITA contenant des sauts de ligne et des espaces sont pris en charge et rendus conformément à leur définition dans les modes Auteur, Source ou Aperçu, ainsi que dans la sortie publiée finale. La capture d’écran suivante montre le contenu de l’élément `msgblock` dans lequel les sauts de ligne et les espaces \(retrait\) ont été conservés :

![](images/new-line-support_cs.png){align="left"}



## Gestion des espaces insécables dans l’éditeur

- Vous pouvez insérer des espaces insécables dans votre document à l&#39;aide de l&#39;icône de ![](images/symbol-icon.svg) **Symobol** ou des touches de raccourci **Alt** + **Space**.  Ces espaces insécables s’affichent en tant qu’indicateurs lorsque vous modifiez une rubrique dans l’éditeur. Vous pouvez désactiver l’affichage des espaces insécables à l’aide de l’option **Afficher l’espace insécable en mode création** de l’onglet **Apparence** des [Préférences utilisateur](./intro-home-page.md#user-preferences).

- Si vous copiez et collez du contenu avec un espace insécable à partir de sources externes dans la vue **Auteur**, l’espace insécable est converti en espace.
Cependant, si vous copiez et collez du contenu avec un espace insécable à partir de la vue **Auteur**, il est conservé.


## Générer automatiquement l’identifiant de l’élément

Vous pouvez générer automatiquement des identifiants pour les éléments de votre rubrique DITA. Ces identifiants sont uniques dans une rubrique DITA. Par exemple, si vous générez des identifiants pour un élément de paragraphe, les identifiants seront p\_1, p2, p\_3, etc. Vous pouvez sélectionner plusieurs éléments et générer des identifiants pour chaque élément sélectionné.

Procédez comme suit pour générer automatiquement un identifiant pour un ou plusieurs éléments :

1. Ouvrez la rubrique dans l’éditeur.
1. Sélectionnez le contenu auquel vous souhaitez attribuer des identifiants.
1. Cliquez avec le bouton droit et sélectionnez **Générer des identifiants** dans le menu contextuel.

   Vous pouvez également cliquer avec le bouton droit dans le chemin de navigation et sélectionner **Générer des identifiants**.



## Gestion des fichiers volumineux dans l’éditeur

Les principales fonctionnalités visant à améliorer la gestion des fichiers volumineux sont mentionnées comme suit :

- Pour améliorer les performances, certaines fonctionnalités telles que Annuler, Rétablir, le panneau de contour et la marque d’intégrité sont désactivées. Il est recommandé de diviser les rubriques en rubriques plus petites pour une expérience optimale.

- Un message d’alerte s’affiche en haut pour les fichiers volumineux, comme illustré dans le fragment de code ci-dessous. Cette alerte met en surbrillance le nombre d’éléments en fonction de la valeur spécifiée dans le paramètre **largeFileTagCount** du fichier uiconfig.json. Par défaut, la valeur de **largeFileTagCount** est 2 500.

![](images/add-toast-notification.png){width="600" align="left"}


- En outre, le nombre de balises s’affiche dans la barre inférieure de l’interface. Lorsque vous passez la souris sur cette valeur de nombre de balises, une info-bulle s’affiche. Sélectionnez l’onglet **En savoir plus** pour plus d’informations sur la gestion des fichiers volumineux.

![](images/add-toast-tag-count.png){width="600" align="left"}


- Le message d&#39;alerte est disponible uniquement pour les fichiers DITA et est visible dans tous les modes : Auteur, Source et Disposition.

**Rubrique parente :**[ Présentation de l’éditeur](web-editor.md)
