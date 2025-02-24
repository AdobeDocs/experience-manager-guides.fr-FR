---
title: Fonctionnalité native de publication PDF | Composants d’un modèle PDF
description: Découvrez les différents composants d’un modèle PDF et comment les personnaliser et les configurer.
exl-id: 0ddb3b81-42ca-4a66-be7d-051a5175d53a
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 47a6819654877e9a4e3e542fa6e5e360b3f3938f
workflow-type: tm+mt
source-wordcount: '4716'
ht-degree: 0%

---

# Composants d’un modèle PDF {#components-pdf-template}

Un modèle PDF comporte quatre composants : mises en page, feuilles de style, ressources et paramètres. Vous pouvez créer un modèle en personnalisant ces composants individuels et en associant le modèle à un paramètre prédéfini de sortie lors de la génération d’une sortie PDF. Les sections suivantes couvrent en détail ces composants et leur processus de personnalisation.


## Création et personnalisation de mises en page {#create-customize-page-layout}

Les paramètres du composant Mises en page vous permettent de concevoir la structure d’une page en définissant l’en-tête, le pied de page et la zone de contenu d’une page. L’éditeur de mise en page de WYSIWYG vous permet de créer une mise en page pour différentes sections d’un PDF, telles que les pages de première et de deuxième couverture, le chapitre, le tableau de
Contenu (table des matières), index, page vierge, pages de garde, pages de garde, liste des illustrations (LOF), liste des tableaux (LOT), glossaire, ou créez une mise en page pour une page personnalisée. Dans les paramètres du modèle PDF, vous pouvez attribuer une mise en page avec différentes sections dans un PDF, qui sont ensuite utilisées pour générer la sortie PDF.

### Création d’une mise en page {#create-page-layout}

>[!NOTE]
>
>Il existe des exemples de mises en page prêtes à l’emploi. Vous pouvez les personnaliser ou créer de nouvelles mises en page.

1. Dans l’éditeur web, accédez à l’onglet **Output**.
1. Développez la barre latérale gauche et cliquez sur **Modèles**.
1. Ouvrez le modèle que vous souhaitez utiliser.

   >[!NOTE]
   >
   >Vous pouvez ouvrir un modèle en double-cliquant sur son nom ou en cliquant sur l’icône > située en regard de son nom.

1. Pour créer une nouvelle mise en page, effectuez l’une des opérations suivantes :

   * Pointez sur **Mises en page**, cliquez sur l’icône (*Options*) **...** et sélectionnez **Nouvelle mise en page**.


   * Dans le panneau **Modèles**, cliquez sur l’icône **+** en regard de **Modèles** et choisissez **Mise en page** dans le menu contextuel.


     La boîte de dialogue **Ajouter une disposition** s’ouvre.

     <img src="assets/add-layout-2.png" alt="Boîte de dialogue Ajouter une disposition" width="250">

1. Spécifiez un nom pour la nouvelle mise en page.
   >[!NOTE]
   >
   >Évitez d’utiliser des caractères spéciaux lors de l’attribution d’un nom à une mise en page. Un espace dans le nom est remplacé par un trait de soulignement « _ ».

1. Cliquez sur **Terminé**.

   La nouvelle mise en page est créée et ajoutée sous Mises en page.


### Dupliquer une mise en page {#duplicate-page-layout}

1. Dans la section **Modèles** du modèle à dupliquer, double-cliquez sur **Mises en page** ou cliquez sur l’icône **>** avant **Mises en page**.

   La liste des mises en page du modèle s’affiche.

1. Pointez sur la mise en page à dupliquer, cliquez sur l’icône (*Options*) **...**, puis sélectionnez **Dupliquer** dans le menu contextuel.

1. Dans la boîte de dialogue _Dupliquer la mise en page_, saisissez un nom pour la mise en page.

1. Cliquez sur **Terminé**.
Une copie de la mise en page sélectionnée est créée et ajoutée sous Mises en page.

### Personnalisation d’une mise en page {#customize-page-layout}

1. Dans la section **Modèles** du modèle à modifier, double-cliquez sur **Mises en page** ou cliquez sur l’icône **>** avant **Mises en page**.

   La liste des mises en page du modèle s’affiche.
1. Pour personnaliser une mise en page, effectuez l’une des opérations suivantes :
   * Double-cliquez sur une mise en page.
   * Pointez sur une disposition de page, cliquez sur l’icône (*Options*) **...**, puis sélectionnez **Modifier** dans le menu contextuel.

   L’éditeur de mise en page s’ouvre alors pour être personnalisé.
1. Une fois les modifications effectuées, cliquez sur *Enregistrer tout* (ou `Crl+S`).

   Pour plus d’informations sur la définition d’éléments de disposition individuels tels que l’en-tête, le pied de page, le numéro de page, le titre, etc., consultez [Conception d’une mise en page](design-page-layout.md).

## Utilisation des feuilles de style pour personnaliser PDF {#stylesheet-customization}

Les paramètres du composant Feuilles de style vous permettent de mettre en forme les composants de mise en page et le contenu DITA à l’aide de l’éditeur WYSIWYG ou d’utiliser directement le fichier CSS. Vous pouvez créer vos propres styles ou personnaliser les propriétés de style par défaut. L&#39;éditeur WYSIWYG vous donne accès à la plupart des propriétés dont vous avez besoin pour appliquer un style à votre mise en page ou à votre contenu DITA. Pour les personnalisations avancées, vous pouvez travailler directement dans la vue Source.

### Créer une nouvelle feuille de style {#create-stylesheet}

Bien que les fichiers CSS soient fournis pour le contenu et la mise en page, vous pouvez créer une nouvelle feuille de style pour appliquer plusieurs personnalisations à un type de style spécifique qui peut ensuite être appliqué à un composant cible. Par défaut, les exemples de fichiers CSS sont regroupés dans le produit . Ces fichiers CSS sont destinés à vous aider à organiser vos informations de style dans le contenu et les mises en page. Vous pouvez choisir de fusionner ces styles dans un ou plusieurs fichiers CSS.

Par défaut, chaque fois que vous créez une mise en page, le fichier `layout.css` est inclus dans la nouvelle mise en page. Si vous souhaitez que la mise en page contienne des styles provenant d’un autre fichier CSS, il vous suffit de faire glisser et de déposer le fichier CSS souhaité dans la zone d’édition du contenu de la nouvelle mise en page. Pour vérifier si le fichier CSS a été incorporé dans la mise en page, passez à la vue Source et vous trouverez un lien vers le fichier CSS dans l’élément `<head>`.

Pour créer une feuille de style, procédez comme suit :
1. Dans le panneau **Modèles**, effectuez l’une des opérations suivantes :
   * Passez la souris sur l’onglet **Feuilles de style**, cliquez sur l’icône (*Options*) **...**, puis sélectionnez **Nouvelle feuille de style**.
   * Cliquez sur l’icône **+** en regard de **Modèles** et choisissez **Feuille de style** dans le menu contextuel.

   La boîte de dialogue Ajouter une feuille de style s’ouvre.

   <img src="assets/add-stylesheet.png" alt="Ajouter une feuille de style" width="250">
1. Attribuez un nom à la nouvelle feuille de style.
1. Cliquez sur **Terminé**.

   Une nouvelle feuille de style est créée et ajoutée sous la section Feuilles de style .

### Créer un style {#create-style}

Par défaut, les fichiers CSS fournis avec le modèle contiennent des styles pour l’en-tête, le paragraphe, le caractère, le lien hypertexte, l’image, le tableau, la balise div, la page et d’autres styles. Vous pouvez remplacer le format de style par défaut ou créer un style.


Vous pouvez créer un nouveau style pour l&#39;utiliser dans la mise en page du modèle ou appliquer un style personnalisé pour n&#39;importe quel élément DITA. Pour appliquer ces styles personnalisés à l&#39;élément DITA, vous devez vous assurer que le nom de classe du style est identique au nom de l&#39;élément DITA ou à l&#39;attribut `outputclass`.  Par exemple, `<div>` dans DITA est régi par le `.div {}` dans CSS ou son attribut `outputclass`. Si vous appliquez des `<div outputclass="my-div">` dans DITA, elles sont régies par les `.div {}` ou les `.my-div {}` du CSS.



Pour créer un style, procédez comme suit :
1. Développez la barre latérale gauche et double-cliquez sur le modèle dans lequel vous souhaitez créer le style.
1. Développez la section **Feuilles de style**. Cela ouvre le panneau **Styles** qui contient toutes les options de mise en forme.
1. Sélectionnez l’icône + pour ajouter un nouveau style.

   La boîte de dialogue **Ajouter un style** s’ouvre.


   <img src="assets/add-style.png" alt="Ajouter un nouveau style" width="500"/>

1. Spécifiez un nom **Classe**. Pour appliquer un style à l&#39;élément DITA, assurez-vous que le nom de classe du style est identique au nom de l&#39;élément DITA ou à l&#39;attribut `outputclass`.
1. Dans le champ **Balise** (facultatif), sélectionnez une balise pour laquelle vous souhaitez créer un style.


1. Sélectionnez une **Pseudo classe** pour appliquer un style à un élément. Une pseudo-classe permet de définir un état spécial de l’élément. Par exemple, utilisez la pseudo-classe pour appliquer un style à un élément lorsque vous placez le pointeur de la souris dessus ou que vous placez le focus dessus. Vous pouvez également sélectionner plusieurs pseudo-classes. Par exemple, vous pouvez utiliser des `a::visited {color: blue;}` de pseudo-classe pour appliquer un style aux liens visités.

1. Ajoutez le sélecteur pour le nouveau style. Le champ **Sélecteur** vous permet d’ajouter des sélecteurs personnalisés en plus de la combinaison Classe, Balise et Pseudo-Classe . Par exemple, vous pouvez créer `table a.link` style pour tous les liens hypertexte d’un tableau.

   Pour plus d’informations sur les balises CSS, consultez la section [Voir la grammaire des styles CSS](https://www.w3.org/TR/CSS21/syndata.html#characters).

1. Cliquez sur **Terminé**.

   Un nouveau style est créé et ajouté à la liste de styles.

### Personnaliser un style prédéfini ou nouveau {#customize-style}

Une fois que vous avez créé un fichier CSS avec des styles par défaut ou que vous souhaitez personnaliser les styles dans un fichier CSS existant, vous pouvez utiliser l’éditeur de styles pour ce faire.

Pour personnaliser un style, procédez comme suit :
1. Double-cliquez sur **Feuilles de style** ou cliquez sur l’icône **>** avant **Feuilles de style**.

   Cette option affiche les fichiers CSS par défaut (contenu et mise en page) et personnalisés.
1. Ouvrez une feuille de style à modifier.

   Pour ouvrir la feuille de style pour la modifier, effectuez l&#39;une des opérations suivantes :
   * Double-cliquez sur le nom de la feuille de style.
   * Pointez sur le nom de la feuille de style, cliquez sur (icône Options)..., puis sélectionnez Modifier.

   Cette action ouvre la feuille de style à modifier et affiche la liste des styles dans le panneau Styles.

   <img src="assets/customize-style.png" alt="Personnaliser le style" width="800">

1. Pour personnaliser un style, sélectionnez-le pour l’afficher et personnalisez-le à l’aide de l’éditeur de styles.


### Propriétés des styles

Dans le panneau central, vous pouvez modifier les propriétés, mais il peut être difficile d’obtenir un instantané de toutes les valeurs présentes.  Le volet **Propriétés** donne un aperçu rapide de tous les attributs et valeurs du style.

Dans le panneau central, vous pouvez modifier les propriétés couramment utilisées, mais pas toutes les propriétés prises en charge par CSS. Dans le volet **Propriétés**, vous pouvez modifier toutes les propriétés prises en charge par CSS et les prévisualiser. Il n’est pas nécessaire de passer à la vue source pour modifier des propriétés.


En savoir plus sur l’utilisation de l’éditeur de style pour [utiliser les styles de contenu courants](stylesheet.md).

## Utilisation des ressources {#work-with-resources}

Il s’agit d’un conteneur pour toutes les ressources utilisées pour concevoir un modèle. Vous pouvez le considérer comme un dossier, qui contient des ressources telles que des images d’arrière-plan, des polices personnalisées, des logos, etc. Chaque fois que vous ajoutez une ressource dans votre modèle, elle est chargée ou archivée dans le dossier de ressources. Vous pouvez ensuite utiliser ces ressources pour personnaliser ou concevoir vos modèles PDF.

Pour ajouter un fichier de ressource au dossier Ressources , procédez comme suit :

1. Passez la souris sur l’onglet du dossier Ressources , cliquez sur (icône Options)... et choisissez Importer.

   La boîte de dialogue Charger Assets s’ouvre.

   <img src="assets/resources-import-assets.png" alt="Chargement de ressources" width="300">

   Le chemin d’accès où le fichier de ressource sera chargé s’affiche dans le champ **Sélectionner le dossier de ressources**.
   >[!NOTE]
   >
   >Vous ne pouvez pas modifier le chemin d’accès pour charger des ressources. Par défaut, toutes les ressources sont stockées sous le dossier `/content/dam/dita-templates/pdf/<PDF-template-name>` .

1. Cliquez sur **Choisir les fichiers** pour parcourir le fichier de ressource à partir de votre ordinateur local

1. Cliquez sur **Télécharger**.
Le fichier sélectionné est importé et répertorié sous le dossier Ressources .

## Paramètres PDF avancés {#advanced-pdf-settings}

Utilisez la section Paramètres pour configurer les paramètres avancés de la mise en page du PDF, en commençant par la page paire ou impaire de PDF, les formats des références croisées et en activant les repères d’impression dans le PDF final généré
à l’aide du modèle.

>
>
> À compter de la version Experience Manager Guides 5.0/2025.02.0, la section **Imprimer** dans les Paramètres avancés de PDF a été déplacée vers le panneau **Paramètres prédéfinis de sortie**. Pour configurer les paramètres d’impression, consultez [Publication d’une sortie PDF](../web-editor/native-pdf-web-editor.md#print).

Pour configurer, cliquez sur **Paramètres** dans le panneau **Modèles** pour afficher les options suivantes :

### Général

Définissez les paramètres de configuration de base pour démarrer un chapitre à partir d’une page paire ou impaire, la structure de la table des matières, puis définissez le format de ligne de repère pour les entrées de la table des matières. Vous pouvez définir le paramètre suivant :

* **Démarrer tout nouveau chapitre à partir de** : permet de définir la manière dont chaque chapitre est publié dans le PDF final. Vous pouvez choisir entre les options **Nouvelle page**, **Page impaire**, **Page paire** ou **Page actuelle**. Si vous choisissez de commencer un nouveau chapitre à partir d’une page impaire, une page vierge est insérée après un chapitre qui se termine sur une page impaire. Par exemple, si votre chapitre se termine à la page numéro 15, le processus de publication insère une 16<sup>ème</sup> page vierge afin que le nouveau chapitre puisse commencer à partir de la 17<sup>ème</sup> page.  Si vous sélectionnez l’option **Page en cours**, tous les chapitres sont publiés en continu, sans saut de page. Par exemple, si un chapitre se termine au milieu de la page 15, le chapitre suivant commence également à partir de la 15e page elle-même.

* **Démarrer chaque rubrique à partir d’une nouvelle page** : si vous souhaitez que chaque rubrique de votre chapitre commence à partir d’une nouvelle page, sélectionnez l’option **Démarrer chaque rubrique à partir d’une nouvelle page**. Si vous souhaitez que vos rubriques restent ouvertes sans interstices de page, désélectionnez cette option.

* **Structure de la table des matières** : permet de personnaliser la hiérarchie de la table des matières. Elle utilise les paramètres supplémentaires suivants :

   * **Utiliser des en-têtes jusqu’au niveau** : permet d’ajuster le nombre de niveaux d’en-tête à afficher dans la structure de la table des matières de votre PDF.
   * **Ne pas afficher le numéro de page pour le premier niveau de la table des matières** : sélectionnez cette option pour masquer les numéros de page correspondants pour tous les chapitres qui contiennent des rubriques imbriquées ou enfants. Prenons l’exemple suivant où une sortie est créée sans sélectionner cette option.

  <img src="assets/page-number-in-toc.png" alt="Chargement de ressources" width="250">

  Dans l’exemple ci-dessus, les titres de rubriques ou de chapitres Premier niveau sont Paramètres PDF avancés, Annexe et Juridique . Un numéro de page est attribué à tous ces en-têtes.

  Désormais, si vous sélectionnez cette option et générez la sortie, vous obtiendrez la table des matières suivante :

  <img src="assets/page-number-missing-in-toc.png" alt="Chargement de ressources" width="250">

  Vous remarquerez ici que le premier chapitre Paramètres avancés du PDF ne comporte aucun numéro de page, car il comporte des rubriques imbriquées ou enfants. En revanche, un numéro de page est affecté à Annexe et Juridique, car il s’agit de rubriques autonomes sans rubrique enfant.

* **Ne pas afficher le numéro de chapitre dans la table des matières** : sélectionnez cette option pour afficher les noms des chapitres sans les numéros de chapitre dans la table des matières.   Par défaut, les numéros de chapitre s’affichent dans la table des matières de votre sortie PDF.
* **Format des lignes de repère** : utilisez la liste déroulante pour sélectionner les lignes de repère pointillés, pleins ou espacés afin de relier les niveaux de titre aux numéros de page correspondants.
Pour appliquer la structure de la table des matières et le style des niveaux d’en-tête, voir [Ajouter une table des matières de chapitre](design-page-layout.md#add-chapter-toc).

  >[!NOTE]
  >
  >Si vous êtes un développeur ou une développeuse CSS, vous pouvez également définir le format de ligne de repère directement dans le fichier CSS.

* **Utiliser le marqueur de continuation de tableau** : sélectionnez cette option pour définir des marqueurs pour les tableaux longs qui s’étendent sur plusieurs pages.
Vous pouvez définir le texte à afficher avant et après la coupure. Par exemple, un tableau se rompt à la page 5 et vous définissez `<Continued on page %page-num%>` pour **Texte avant la rupture**.  Le texte indique « Suite page 6 » au bas de la page 5.

  Utilisez des variables de langue pour définir le texte du marqueur de continuation avant et après la coupure. Selon la langue choisie, la valeur localisée est automatiquement sélectionnée dans la sortie PDF. Par exemple, vous pouvez publier du `Continued on page %page-num%` sous forme de texte en anglais et du `Fortsetzung auf Seite %page-num%` en allemand.

  Survoler <img src="./assets/info-details.svg" alt= "icône info" width="25"> près de l’option pour en savoir plus.
* **Lier les termes du glossaire à la page du glossaire** : sélectionnez cette option pour afficher les termes du glossaire sous forme de liens hypertexte dans le contenu et les lier aux termes de la page du glossaire. Cela permet aux lecteurs de consulter rapidement la définition d’un terme défini dans le glossaire.

  Pour convertir les termes du glossaire en liens hypertexte, vous devez effectuer les opérations suivantes :
   * Activez **Glossaire** dans l&#39;onglet **Ordre de mise en page** pour un plan DITA.
   * Ajoutez le glossaire dans les pages Back Matter pour une carte Livre.

  Si vous n’activez pas la page Glossaire, les termes du glossaire dans le contenu ne sont pas convertis en liens hypertexte dans la sortie PDF.
  <!--For more information on using table continuation markers, see Use table continuation markers.-->

### Mises en page {#page-layouts}

Les paramètres Mises en page vous permettent de spécifier la mise en page à utiliser pour une section spécifique de votre document. Par exemple, pour sélectionner une disposition pour la table des matières, cliquez sur le menu déroulant sous le champ Table des matières et sélectionnez la disposition que vous avez conçue pour générer la table des matières.

Il est important de noter que les paramètres de la carte des signets sont prioritaires sur ceux de la mise en page.

Les paramètres suivants sont disponibles sous la section Mise en page :

<img src="assets/template-page-layout.png" alt="Mises en page" width="550">


**Mise en page par défaut** : sélectionnez une mise en page qui agit comme mise en page par défaut pour toutes les pages de votre PDF. Il s’agit de la mise en page de base appliquée aux sections ou aux rubriques pour lesquelles vous n’avez pas créé de mise en page dédiée.

**Mise en page pour différentes sections** : vous pouvez mettre en correspondance une mise en page avec les sections suivantes de votre sortie PDF. Si vous avez conçu une mise en page pour la section associée, sélectionnez-la dans la liste déroulante. Si aucune mise en page n’a été créée pour des sections spécifiques, la mise en page par défaut est appliquée.

* **Chapitres et rubriques** : vous pouvez spécifier la mise en page pour le champ Chapitre et rubriques. La mise en page sélectionnée sera appliquée à tous les chapitres et rubriques.

* **Table des matières** : si vous avez conçu la mise en page de la table des matières, sélectionnez **Table des matières** dans la liste déroulante. Ainsi, toutes les pages de la table des matières de votre document auront la mise en page de la table des matières.

* **Liste des illustrations et Liste des tableaux** : vous pouvez également définir la mise en page des illustrations et des tableaux. La mise en page sélectionnée sera appliquée à tous les tableaux et figures.

* **Index** : si vous avez conçu une disposition de page d’index, mappez-la à l’option Index . À l’aide des feuilles de style, vous pouvez mettre en forme différents éléments d’index dans la sortie PDF. Utilisez les styles d’index `.idx-header`, `.idx-footer`, `.idx-body`, `.idx-title`, `.idx-keyword-group`, `.idx-unit`, `.idx-keyword`, `.idx-name`, `.idx-link` et `.idx-child` pour personnaliser les styles pour les éléments de l’index.

* **Glossaire** : si vous disposez d’une mise en page de type Glossaire, mappez-la à l’option Glossaire.

  Les termes figurant dans le glossaire de votre sortie PDF sont toujours triés par ordre alphabétique.

  Vous pouvez également ajouter la `sort-as` de balise pour définir une clé de tri pour les termes du glossaire. Experience Manager Guides utilise ensuite la clé de tri pour trier les termes du glossaire à la place des termes du glossaire. Si vous n’avez pas défini la clé de tri, elle utilise les termes du glossaire pour le tri. Par exemple, vous pouvez ajouter la balise `sort-as` à la `glossterm` et définir sa valeur sur `A` pour le terme « USB » (par exemple, `<glossterm>USB<sort-as>A</sort-as></glossterm>`). De même, vous pouvez ajouter `sort-as` balise et définir sa valeur sur `B` pour le terme « Pen Drive ». Lorsque vous triez ces termes du glossaire, la clé de tri `A` pour le terme de glossaire « USB » apparaît avant la clé de tri `B` pour le terme de glossaire « Pen Drive ». Ainsi, dans la sortie PDF, « USB » vient avant « Pen Drive » sur la page du glossaire.

  À l’aide des feuilles de style, vous pouvez mettre en forme différents éléments du glossaire dans la sortie PDF. Utilisez les styles du glossaire `.glo-header`, `.glo-footer`, `.glo-body`, `.glo-title`, `.glo-unit`, `.glo-link` et `.glo-term` pour personnaliser les styles pour les éléments du glossaire.

  En savoir plus sur l’utilisation de l’éditeur de style pour [utiliser les styles de contenu courants](stylesheet.md).

* **Pages du sujet principal et Pages du sujet arrière** : ces mises en page définissent le style des pages du sujet principal ou secondaire de votre livre. Si vous avez conçu la disposition du sujet principal, mappez-la à l’option **Pages du sujet principal**. Lorsque vous sélectionnez la disposition du sujet de front dans la liste déroulante, elle est appliquée à tous les sujets présents dans le sujet de front.

  Si vous avez conçu la disposition du sujet arrière, mappez-la à l’option **Pages du sujet arrière**. Lorsque vous sélectionnez la disposition du sujet de fond dans la liste déroulante, cette dernière est appliquée à tous les sujets présents dans le sujet de fond.

  **Pages du sujet principal** est également utilisé comme disposition de secours pour les **table des matières**, **Liste des illustrations** et Liste des tableaux.  De même, la disposition **Pages du sujet arrière** est également utilisée comme disposition de secours pour les dispositions **Index** et **Glossaire**. Si vous n’avez pas sélectionné la disposition pour ces éléments, la disposition Pages du recto ou du verso est appliquée.  Si vous n’avez pas sélectionné la disposition Pages du recto ou du verso du sujet, la mise en page par défaut leur est appliquée.

* **Mise en page pour les pages vides** :    Vous pouvez également définir la mise en page pour les pages vides. La mise en page sélectionnée sera appliquée à toutes les pages vides. Par exemple, si vous avez conçu une mise en page Page vierge pour toutes les pages vides, sélectionnez **Vide** dans la liste déroulante. Toutes les pages vides du document auront alors la mise en page Vierge.

* **Page de garde et page de fond** : si vous avez conçu une disposition de page de garde, mappez-la à l’option **Page de garde**. De même, si vous disposez d’une mise en page de page d’arrière-plan, mappez-la à l’option **Page d’arrière-plan**. Si aucune disposition de page de garde ou de page arrière n’a été créée, la mise en page par défaut est appliquée.



Pour plus d’informations sur les mises en page, voir [Création d’une mise en page](design-page-layout.md).

### Ordre de mise en page {#page-order}

Vous pouvez afficher ou masquer les sections suivantes dans votre PDF et organiser l’ordre dans lequel elles doivent apparaître dans votre sortie PDF finale :



* Table des matières
* Chapitres et sujets
* Liste des figures
* Liste des tables
* Index
* Glossaire
* Citation

  <img src="assets/page-order-advance-settings.png" alt="Ordre de mise en page" width="550">

  Si vous ne souhaitez pas afficher une section particulière dans votre sortie PDF, vous pouvez la masquer en désactivant le bouton bascule.

  Vous pouvez également définir l’ordre dans lequel ces différentes sections sont générées dans votre PDF. Pour modifier l’ordre par défaut de ces sections, sélectionnez les barres pointillées pour faire glisser et déposer les sections à l’emplacement souhaité.

  >[!NOTE]
  >
  > Les paramètres d&#39;ordre et d&#39;inclusion s&#39;appliquent uniquement à un plan DITA. Pour un bookmap, ces paramètres ne sont pas applicables. Les pages d’une carte des signets s’affichent dans l’ordre des sections de la carte des signets.


.
La disposition **Chapitre et rubriques** est toujours activée par défaut. Vous ne pouvez pas activer/désactiver cette fonctionnalité.

**Fusionner des pages**

Par défaut, toutes les sections commencent sur une nouvelle page. Sélectionnez l’option **Page précédente** ou **Page suivante** dans le menu déroulant **Fusionner avec** pour fusionner une section avec une page précédente ou suivante. La section sera publiée en continuant avec la page sélectionnée dans la sortie PDF. Il n’y aura pas de saut de page entre les deux.

>[!NOTE]
>
> Ce paramètre s’applique uniquement à la section et non à ses composants.  Par exemple, si vous sélectionnez l’option **Page précédente** pour **Chapitres et rubriques**, la section **Chapitres et rubriques** fusionne avec la page précédente. Les différents chapitres et sujets sont publiés conformément aux paramètres **Général**. Par exemple, si dans **Démarrer un nouveau chapitre à partir du paramètre**, vous sélectionnez **Page impaire**, une page vierge est insérée après un chapitre qui se termine sur une page impaire.

Lorsque vous fusionnez une section avec sa page précédente ou suivante, le contenu est fusionné et le style de la section cible dans laquelle le contenu est fusionné est appliqué.

Par exemple, si vous activez **Table des matières** et **Chapitre et rubriques** et sélectionnez l’option **Page suivante** pour **Table des matières**, la **Table des matières** fusionne avec la section suivante, qui est **Chapitre et rubriques**. Le style de la section **Chapitre et rubriques** est appliqué au contenu fusionné des deux sections.

L’option de fusion fonctionne successivement. Par conséquent, si vous avez sélectionné **Page suivante** pour plusieurs sections continues, elles fusionnent toutes avec la première section (dans la direction suivante), qui n’a pas cette propriété définie. Par exemple, vous activez **Table des matières**, **Chapitre et rubriques**, **Liste des illustrations** et **Index**. Ensuite, si vous définissez **Page suivante** pour **Table des matières**, **Chapitre et rubriques**, **Liste des illustrations** et **Aucune** pour **Index**, ils fusionnent tous avec **Index**.


**Pages statiques**

Les différentes mises en page vous aident à concevoir la sortie des différentes sections. Ces sections sont générées à partir du plan DITA lorsque vous publiez la sortie.
Vous pouvez également créer des mises en page personnalisées et les publier en tant que pages statiques dans la sortie PDF. Cela vous permet d’ajouter du contenu statique, tel que des notes ou des pages vierges.

Pour ajouter une mise en page personnalisée, procédez comme suit :

1. Sélectionnez **Ajouter** ![](assets/add-icon.svg) pour ajouter une nouvelle disposition de page. Ajout d’ouvertures de panneau de mise en page.
2. Sélectionnez la mise en page dans la liste, puis cliquez sur Ajouter. La nouvelle mise en page est ajoutée à la liste des mises en page.


Vous pouvez également effectuer les actions suivantes :

* Sélectionnez les barres en pointillés pour faire glisser et déposer la mise en page à l’emplacement souhaité.

* Sélectionnez **Supprimer la disposition** ![](assets/delete-icon.svg) pour supprimer une disposition.

* Vous pouvez également fusionner une page statique avec la page précédente ou la page suivante.

* Vous pouvez également ajouter plusieurs fois une disposition personnalisée et les classer. Cela vous permet de publier le contenu statique en conséquence.

  Par exemple, vous pouvez utiliser une mise en page personnalisée pour publier un avertissement statique plusieurs fois dans la sortie PDF.



### Organisation de la page

Les pages d&#39;un document PDF sont généralement publiées en fonction du contenu organisé dans le fichier de plan DITA ou de bookmap. Cependant, vous pouvez également modifier l’ordre des pages dans le document PDF. Par exemple, vous pouvez imprimer un document de plusieurs pages sous la forme d’une brochure. Lorsque vous assemblez, pliez et agrafez les feuilles, vous obtenez un seul livre avec le bon ordre de page.  Vous pouvez alors lire le livret publié comme un livre.

<img src="assets/template-page-organization.png" alt="Organisation de la page" width="550">


Les paramètres ci-dessous sont disponibles dans la section **Organisation de la page** :

#### Ordre des pages

Sélectionnez un ordre de page qui détermine l’ordre des pages dans votre document PDF. Vous pouvez choisir les options suivantes dans la liste déroulante :

* **Par défaut** : ordre par défaut des pages en fonction du fichier source.
* **Pages impaires en premier** : toutes les pages impaires sont déplacées avant toutes les pages paires.
* **Pages paires en premier** : toutes les pages paires sont déplacées avant toutes les pages impaires.
* **Inverser** : l’ordre des pages est inversé.
* **Brochure** : toutes les pages sont classées comme dans une brochure.
* **Livret de droite à gauche** : toutes les pages sont dans l’ordre des livrets de droite à gauche.
* **Personnalisé** : définissez un ordre personnalisé des pages au lieu d’un ordre prédéfini.
   * « a..b » — Toutes les pages consécutives de a à b.
   * « a, b, c » — Nouvel ordre de page a, b, c.
   * « a*b » — La page a est répétée b fois.
   * « -a » — Les numéros de page négatifs sont comptés à rebours à partir de la dernière page et peuvent être combinés à d’autres commandes personnalisées.
   * « X » : toutes les pages du document. Même résultat que « 1..-1 ».

Ainsi, par exemple, vous pouvez donner une commande personnalisée telle que « 2,3,5*2,7..10,-1,-2.
L’ordre de page donné entraîne l’affichage dans un PDF des numéros de page suivants du document d’origine, en supposant qu’il comporte 25 pages au total : 2, 3, 5, 5, 7, 8, 9, 10, 25, 24.

#### Configuration de plusieurs pages par feuille

Sélectionnez cette option pour publier plusieurs pages sur une seule feuille de papier.  Sélectionnez ensuite le nombre de lignes et de colonnes, puis publiez les pages sur une seule feuille sous la forme d’une grille. Par exemple, vous pouvez publier les pages sous la forme d’une grille de 2 lignes et 4 colonnes.

Définissez la taille de la feuille cible et l’orientation dans laquelle vous souhaitez publier la feuille. Vous pouvez également définir la marge et les propriétés de remplissage de la feuille.

### Références croisées {#cross-references}

Utilisez l’onglet **Référence croisée** pour définir la manière dont les références croisées sont publiées dans le PDF. Vous pouvez mettre en forme les références croisées pour le titre de rubrique, les tableaux, les figures, etc.

>[!NOTE]
>
> Si vous avez défini le texte du lien lors de l’insertion de la référence croisée, il est prioritaire par rapport au format de référence croisée défini dans le modèle PDF natif.

Vous pouvez également utiliser des variables pour définir une référence croisée.  Lorsque vous utilisez une variable, sa valeur est sélectionnée dans les propriétés. Vous pouvez utiliser une seule variable ou une combinaison de variables pour définir une référence croisée. Vous pouvez également utiliser une combinaison d’une chaîne et d’une variable.

Vous pouvez, par exemple, utiliser `View details on {chapter}`. Si le nom du chapitre est « Paramètres généraux », la référence croisée dans la sortie est « Voir les détails sur les paramètres généraux ».

AEM Guides fournit les variables prêtes à l’emploi suivantes :

* {title} : crée une référence croisée au titre de la rubrique. Par exemple, consultez la section Liens utiles à la page 2.
* {page} Ajoute une référence croisée aux numéros de page. Par exemple, reportez-vous à la page 1.
* {description} : ajoute une référence croisée au texte de la description. Par exemple, consultez les détails d’AEM Guides.
* {chapter} : ajoute une référence croisée aux numéros de chapitres. Par exemple, reportez-vous au chapitre 1.
* {bookmarkText} : crée une référence croisée au texte marqué d’un signet. Par exemple, voir mots_vides page 5.
* {captionText} : crée une référence croisée avec la légende de la figure ou du tableau de votre rubrique. Par exemple, reportez-vous à la section Circulation d’air à la page 2.
* {figure} : ajoute une référence croisée au numéro de la figure. Sélectionne le numéro de figure parmi les styles de numéros automatiques que vous avez définis pour la légende.  Par exemple, vous pouvez utiliser « Voir {figure} sur la page {page} ». La référence croisée dans la sortie contient le numéro de figure généré automatiquement et son numéro de page, « Voir Figure 1 à la page 5 ».
* {table} : ajoute une référence croisée au numéro de la table. Sélectionne le numéro du tableau à partir des styles de numéros automatiques que vous avez définis pour la légende. Par exemple, vous pouvez utiliser « Voir {table} sur la page {page} ». La référence croisée dans la sortie contient le numéro de tableau généré automatiquement et son numéro de page, « Voir le tableau 1 à la page 5 ».



  >[!NOTE]
  >
  >Vous pouvez créer des styles de numérotation automatique pour les balises de légende et de légende.

#### Format de référence croisée par défaut

Si vous laissez le champ de texte vide et que vous n’avez pas défini le texte du lien lors de l’insertion d’une référence croisée, Experience Manager Guides ajoute les variables suivantes pour les références croisées respectives :

* **Titre** : `{title}`
* **Description** : `{description}`
* **Paragraphe** : `{bookmarkText}`
* **Signet** : `{bookmarkText}`
* **Image** : `{captionText}`
* **Tableau** : `{captionText}`

L’ordre de priorité des références croisées est le suivant :
* Texte du lien ajouté dans les renvois
* Format des références croisées défini dans le modèle PDF natif
* Format de référence croisée par défaut


#### Variables de langue dans les références croisées

Vous pouvez également utiliser des variables de langue pour définir des références croisées localisées. Selon la langue choisie, la valeur localisée est automatiquement sélectionnée dans la sortie PDF.

Par exemple, vous pouvez ajouter une variable de langue « reference-label » et définir les valeurs en anglais et en allemand.

* Anglais - « View on page {page} »
* Allemand - «Einzelheiten finden Sie auf der Seite {page}»


Lorsque vous ajoutez des `${lng:<variable name>}` à la section Paragraphe, les références croisées dans les paragraphes de la sortie contiennent le texte localisé et le numéro de page.\
Par exemple, les captures d’écran ci-dessous montrent les références croisées « View on page 1 » en anglais et « Einzelheiten finden Sie auf der Seite 1 » en allemand.

<img src="./assets/english-output-corss-reference.png" alt="Sortie en anglais d&apos;une référence croisée dans un pragrah" width ="800" border="2px">

*Référence croisée dans un paragraphe lorsqu’il est publié en langue anglaise.*

<img src="./assets/german-output-corss-reference.png" alt="Sortie allemande d&apos;une référence croisée dans un pragrah" width ="800" border="2px">


*Référence croisée dans un paragraphe lorsqu’il est publié en allemand.*

<!--For more information, see *Format cross-references*.-->
