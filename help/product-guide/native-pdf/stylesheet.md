---
title: Fonctionnalité native de publication PDF | Utiliser les styles de contenu courants
description: Découvrez comment créer des feuilles de style utilisateur et créer des styles pour votre contenu.
exl-id: 42ba7347-d81d-45d9-9627-8d164e4f9539
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '3778'
ht-degree: 1%

---

# Utiliser les styles de contenu courants {#work-with-common-styles}

Une feuille de style contient les définitions des styles pour les éléments utilisés dans votre sortie PDF. Vous pouvez choisir d’utiliser les exemples de feuilles de style ou d’en créer de nouvelles. Dans la plupart des cas, la création d’une copie de l’exemple de feuille de style prête à l’emploi vous aidera à démarrer rapidement.

L’éditeur de styles est un éditeur WYSIWYG qui masque toutes les complexités d’un code CSS derrière l’interface utilisateur. L’éditeur de style vous permet de personnaliser facilement et très rapidement les styles pour les éléments de votre choix. Les styles sont classés sous les titres suivants :

* Styles de titre
* Styles de paragraphe
* Styles de caractère
* Styles d’hyperlien
* Styles d’image
* Styles de liste
* Styles de tableau
* Styles Div
* Styles de page
* Autres styles

Lorsque vous travaillez avec du contenu DITA structuré, le mappage de style pour la plupart des éléments DITA est en place dans la feuille de style par défaut. Si vous utilisez des éléments DITA standard, vous pouvez modifier leur apparence en apportant directement des modifications à la définition de style. Ces définitions de style sont disponibles dans la catégorie Autre style . Pour plus d’informations, voir [Utilisation d’autres styles](#other-styles) plus loin dans cette rubrique.

Les sections suivantes présentent les paramètres de style les plus couramment utilisés sous la forme d’exemples.

>[!NOTE]
>
>Dans les exemples suivants, on suppose que vous utilisez l’exemple de feuille de style fourni avec le produit.

## Utiliser les styles de titre {#heading-styles}

Les styles d’en-tête encapsulent tous les styles de base des en-têtes utilisés dans votre contenu. OOTB vous obtiendrez 6 styles d’en-tête de base et un style d’en-tête pour l’en-tête du sujet/chapitre et du titre de l’annexe. Dans un document structuré, le H1 représente le titre du sujet ou du chapitre et les H2 à H6 sont utilisés pour les sous-sujets ou sections d&#39;un sujet/chapitre. Cette hiérarchie d’en-têtes est automatiquement appliquée à votre contenu chaque fois que l’en-tête correspondant est trouvé.

>[!NOTE]
>
>Vous pouvez créer vos propres styles d’en-tête personnalisés et les utiliser dans votre contenu à l’aide de la classe outputclass. Pour plus d’informations, voir l’étape 4 dans [Utilisation de l’orientation de page et rotation d’affichage](design-page-layout.md#page-orientation-rotation) par exemple.

### Créer des en-têtes personnalisés au niveau du chapitre {#create-chapter-level-heading}

Dans un livre (ou une carte), vous travaillez avec Chapters. Les styles d’en-tête de base sont conçus de manière à être appliqués aux en-têtes de niveau chapitre sans aucune personnalisation. Cependant, si vous souhaitez créer des en-têtes spécialisés pour votre contenu, vous devrez créer ces en-têtes. Par exemple, l’en-tête de `h1.chapter` par défaut est appliqué au titre de votre chapitre. Si vous souhaitez que le titre du chapitre s’affiche dans un style différent, vous devez personnaliser le style du `h1.chapter`. De même, vous pouvez créer des styles personnalisés pour les sous-titres de votre chapitre. Par exemple, si vous souhaitez créer un style personnalisé pour tous les en<sup>têtes </sup> 2 et 3<sup>e niveau </sup> de votre chapitre, vous devez créer un style sous la forme `h2.chatper` et `h3.chatper`.

Comme la fonction Publication native de PDF contient les définitions de style de base pour les styles les plus courants, même si vous supprimez un style par erreur, le style par défaut est appliqué au contenu. Par exemple, si votre feuille de style ne contient aucune définition de style pour le style h2, la fonction Publication native de PDF appliquera un style de base au contenu h2.

Dans cet exemple, nous allons créer un style de titre de chapitre de 2e niveau :

1. Ouvrez la feuille de style requise pour la modification.
   >[!NOTE]
   >
   >Consultez la section [Personnaliser un style prédéfini ou nouveau](components-pdf-template.md#customize-style) pour ouvrir une feuille de style à des fins de personnalisation ou de modification.

1. Dans la liste **Styles**, développez le **Styles de titre**.
1. Cliquez avec le bouton droit sur **Styles de titre** style et choisissez **Nouveau style**.
1. Dans la boîte de dialogue *Ajouter un style*, conservez le nom **Balise** au format `h2` et saisissez `chapter` dans le champ de nom **Classe**.
1. Cliquez sur **Terminé**.

Un nouveau style d’en-tête nommé `h2.chapter` est créé et ajouté sous la liste Styles d’en-tête .

Une fois un style créé, vous pouvez personnaliser ses propriétés à l’aide de l’éditeur de style.

### Créer des en-têtes de numérotation automatique {#auto-number-heading}

L’un des styles de sortie les plus couramment utilisés est celui des en-têtes numérotés automatiquement. Ces en-têtes représentent le numéro de chapitre, le numéro de sujet et le numéro de sous-sujet. Les en-têtes de numérotation automatique sont différents des styles de liste dans lesquels une liste d’éléments au sein d’une rubrique se voient attribuer des numéros automatiques.

Dans cet exemple, nous allons personnaliser les en-têtes du niveau 1 au niveau 3 pour utiliser des numéros automatiques dans différents formats.

1. Ouvrez la feuille de style requise pour la modification.

   >[!NOTE]
   >
   >Consultez la section [Personnaliser un style prédéfini ou nouveau](components-pdf-template.md#customize-style) pour ouvrir une feuille de style à des fins de personnalisation ou de modification.

1. Dans la liste **Styles**, développez le **Styles de titre**.

1. Sélectionnez le style **h1** dans la liste.
Les propriétés du style h1 s’affichent dans le panneau Propriétés avec son aperçu.

   >[!NOTE]
   >
   >Le panneau Aperçu vous donne une vue en temps réel des mises à jour de style que vous appliquez à n’importe quel élément.

1. Sélectionnez la propriété **Autonumber**.

   Les styles que vous pouvez appliquer à la liste de numérotation automatique sont affichés sous la propriété Numérotation automatique.

1. Définissez les propriétés suivantes :
   * **Style** : permet d’effectuer un choix parmi un large éventail de styles de numérotation génériques ou spécifiques aux paramètres régionaux. Vous pouvez choisir des styles tels que Arabe-Indic, Dévanagari, Géorgien, Décimal, Lower-Alpha, etc. Pour l’exemple actuel, sélectionnez `upper-alpha`.

   * **Format** : le format par défaut est défini sur `<x>`, où la valeur `x` est remplacée par le style de numérotation que vous avez sélectionné dans la propriété Style. Par exemple, si vous avez sélectionné le style `decimal` (1), la valeur de `x` s’incrémente automatiquement pour chaque instance du style `h1` et prend la valeur 2, 3, etc. Vous pouvez également ajouter du texte personnalisé dans le champ pour mettre en forme le style d’en-tête. Par exemple, si vous souhaitez que tous les en-têtes h1 comportent le préfixe `Chapter`, vous devez définir ce champ comme `Chapter <x>`.

   * **Insérer un caractère** : si vous souhaitez ajouter un caractère spécial au format, cliquez sur le bouton Insérer un caractère (<img src="./assets/insert-chars.png" width="25">). Sélectionnez le caractère souhaité à ajouter au format de style, puis cliquez sur Insérer. Vous pouvez choisir différents types de caractères spéciaux dans la liste déroulante Sélectionner une catégorie . Dans notre exemple, sélectionnez la citation en double angle avec pointage droit dans la catégorie Ponctuation.

     <img src="./assets/insert-special-chars.png" width="400">


   * **Commencer la numérotation à partir de** : si vous souhaitez que la numérotation commence à partir d’un nombre spécifique, indiquez cette valeur. Dans notre exemple, conservez la valeur par défaut de 1.

   * **Retrait** : si vous souhaitez mettre en retrait l’en-tête, vous devez définir la valeur Retrait. Dans notre exemple, définissez-le sur 0 px.

     >[!NOTE]
     >
     >Vous pouvez saisir la valeur en pixels, pt (points), rem, em, % (pourcentage) ou en pouces.

   * **Largeur du préfixe** : il s’agit de la zone occupée par le format de numéro automatique. Il est automatiquement défini sur une taille qui peut facilement s’adapter au format de style sélectionné. Si vous souhaitez augmenter la taille, vous pouvez remplacer la valeur par défaut.

     Lorsque vous définissez cette valeur manuellement, essayez de modifier les autres propriétés qui auront un impact sur la largeur. Par exemple, modifiez la taille de la police, le format avec un préfixe (chapitre) ou un suffixe ( :), définissez la valeur maximale dans la propriété *Commencer la numérotation à partir de* et les différentes propriétés de la police pour obtenir la taille optimale.

     Dans notre exemple, conservez la valeur par défaut.

   * **Espacement** : spécifiez l’espacement horizontal et vertical. Dans notre exemple, conservez les valeurs par défaut.

     Avec les personnalisations ci-dessus, le style est personnalisé comme illustré ci-dessous :

     <img src="./assets/h1-style-custmization.png" width="500">

   * **Appliquer la mise en forme à** : les propriétés de la catégorie Numérotation automatique vous aideront à définir le style de numérotation. Pour appliquer d’autres personnalisations au style de numérotation ou au contenu de votre format d’en-tête, vous pouvez choisir Numérotation ou Paragraphe dans ce champ. Si vous choisissez Numérotation, les modifications apportées à la Police, à la Bordure, à la Mise en page et aux autres catégories seront appliquées uniquement au style de numérotation de l&#39;en-tête. Cependant, si vous choisissez Paragraphe, les modifications seront appliquées au contenu de l’en-tête et non au style de numérotation.

   Utilisez les paramètres suivants pour générer une sortie affichée dans la capture d’écran suivante :

   | **Style de titre** | **Propriété** | **Valeur**. | **Commentaires supplémentaires** |
   | :- | :- | :- | :- |
   | h1 | Style | Décimale | Ces propriétés se trouvent dans la catégorie Numéro automatique . |
   |  | Format | `Capter <x>:` |  |
   |  | Largeur du préfixe | 160 px |  |
   |  | Police > Alignement du texte | Gauche | Assurez-vous que l’option Appliquer la mise en forme à est définie sur Numérotation |
   | h2 | Style | Décimale | Ces propriétés se trouvent dans la catégorie Numéro automatique . |
   |  | Format | `Section <x>:` |  |
   |  | Largeur du préfixe | 125 px |  |
   |  | Police > Alignement du texte | Gauche | Assurez-vous que l’option Appliquer la mise en forme à est définie sur Numérotation |
   | h3 | Style | Décimale | Ces propriétés se trouvent dans la catégorie Numéro automatique . |
   |  | Insérer niveau | 2 |  |
   |  | Format | `Section <2>.<x>:` |  |
   |  | Largeur du préfixe | 125 px |  |
   |  | Police > Alignement du texte | Gauche | Assurez-vous que l’option Appliquer la mise en forme à est définie sur Numérotation |

   <img src="./assets/auto-number-output.png" width="500">

## Utilisation des styles de paragraphe {#paragraph-style}

Vous pouvez créer un style de paragraphe pour appliquer une mise en forme spéciale à un paragraphe entier. Toutefois, à l’aide de la pseudo-classe , vous ne pouvez appliquer un style qu’à une partie spécifique du texte. Dans l’exemple suivant, nous allons créer un style de paragraphe pour utiliser le style de lettrine.

### Créer le style de lettrine {#drop-cap-style}

Un style de lettrine (ou lettrine) est utilisé dans les magazines et les documents littéraires dans lesquels le premier caractère d’un paragraphe ou d’une section se voit attribuer un style spécial. Vous pouvez obtenir le même effet à l’aide de la fonction Publication native de PDF.

Dans l’exemple suivant, nous allons créer un style de lettrine :

1. Ouvrez la feuille de style requise pour la modification.

   >[!NOTE]
   >
   >Consultez la section [Personnaliser un style prédéfini ou nouveau](components-pdf-template.md#customize-style) pour ouvrir une feuille de style à des fins de personnalisation ou de modification.

1. Dans la liste **Styles**, développez le **Styles de paragraphe**.

1. Cliquez avec le bouton droit de la souris sur **Style de paragraphe** et choisissez **Nouveau style**.

1. Dans la boîte de dialogue *Ajouter un style*, conservez le nom **Balise** au format p et, dans le champ **Pseudo** **Classe**, sélectionnez `::first-letter`.

1. Cliquez sur **Terminé**.

   Un nouveau style de paragraphe nommé `::first-letter` est créé et ajouté sous la liste **Styles de paragraphe**.

1. Sélectionnez `::first-letter` sous le style p et définissez les propriétés suivantes :

   * **Police** : définissez la police souhaitée pour la première lettre de votre paragraphe. Dans notre exemple, définissez la Famille de polices sur cursive, l’épaisseur de la police sur 500, la taille de la police sur 30 pt et choisissez une couleur de police.

   * **Disposition** : permet de définir l’alignement vertical du texte autour du style de lettrine. Dans notre exemple, nous allons définir l’Alignement vertical sur le bas.

La balise `p` étant mappée avec l&#39;élément `<p>` dans DITA, il n&#39;est pas nécessaire d&#39;ajouter explicitement ce style à l&#39;aide de l&#39;attribut outputclass. Lorsqu’un élément de `<p>` est utilisé dans votre contenu, le style de lettrine lui est automatiquement appliqué. Dans la capture d’écran suivante, le titre du chapitre, la description courte et les éléments de liste de définitions n’ont pas été formatés avec le style de lettrine. Seul le style de paragraphe est formaté avec le style de lettrine :

<img src="./assets/char-style-drop-cap.png" width="500">

## Utilisation des styles de caractères {#char-style}

À l’aide des styles de caractères, vous pouvez créer des styles pour mettre en forme des caractères ou des mots dans votre contenu. Par exemple, vous pouvez créer un style de caractère pour le code intégré ou le nom de fichier, ou vous pouvez créer un style qui utilise plusieurs formats de style sur le contenu sélectionné.

### Création d’un style de caractère intégré {#inline-char-style}

La mise en forme des caractères intégrés ou des mots d’un paragraphe est un style très courant. Le processus de création d’un style intraligne implique deux tâches : d’abord, créer un nouveau style dans la feuille de style, puis appliquer le style dans votre contenu à l’aide de l’attribut `outputclass` .

Dans l’exemple suivant, nous allons créer un style de caractère intégré :

1. Ouvrez la feuille de style requise pour la modification.

   >[!NOTE]
   >
   >Consultez la section [Personnaliser un style prédéfini ou nouveau](components-pdf-template.md#customize-style) pour ouvrir une feuille de style à des fins de personnalisation ou de modification.

1. Dans la liste **Styles**, développez le **Styles de caractères**.

1. Cliquez avec le bouton droit de la souris sur le **Style de caractère** et choisissez **Nouveau style**.

1. Dans la boîte de dialogue Ajouter un style , conservez le nom **Balise** comme étendue et saisissez `BoldItalic` dans le champ de nom **Classe**.

   <img src="./assets/create-char-style.png" width="400">

1. Cliquez sur **Terminé**.

   Un nouveau style de caractère nommé code est créé et ajouté sous la liste Styles de caractères .

1. Sélectionnez `span.BoldItalic` dans la liste **Style de caractère** et définissez les propriétés suivantes :

   * **Police** : toutes les propriétés liées aux polices peuvent être personnalisées à partir de cette section. Par défaut, certaines polices sont fournies avec le produit. Vous pouvez choisir la police souhaitée pour le style de caractère. Dans notre exemple, définissez la famille de polices sur *Serif*, puis sélectionnez *Gras* et *Italique* dans la propriété Style de police. Vous pouvez également personnaliser d’autres propriétés de police, telles que l’épaisseur de la police (en gras, plus clair), la décoration du texte (en soulignement, surligné), la taille de la police, la couleur de la police, l’alignement du texte, etc.

     >[!NOTE]
     >
     >Vous pouvez également ajouter des polices à votre modèle, qui sont stockées dans la section Ressources de votre modèle. Pour plus d’informations sur l’ajout de polices et l’utilisation des ressources, voir [&#x200B; Utilisation des ressources &#x200B;](components-pdf-template.md#work-with-resources).

   * **Disposition** : vous pouvez définir les propriétés liées à la disposition, telles que la hauteur et la largeur, la marge, le remplissage, l’alignement, etc.

   * **Arrière-plan** : les propriétés Arrière-plan vous permettent de mettre en forme la couleur d’arrière-plan d’un style particulier. Vous pouvez définir la couleur ou l’image d’arrière-plan de n’importe quel style.

Une fois le style de caractère intégré créé, vous devez l’appliquer à votre contenu. Pour appliquer le style de code intégré, accédez à la vue source et ajoutez l’attribut `outputclass` dans le contenu souhaité :

`outputclass="BoldItalic"`

L’exemple suivant illustre l’application du format gras italique à différents endroits dans le texte en cours d’exécution :

<img src="./assets/char-format-applied.png" width="500">

## Personnaliser le style de liste {#custom-list-style}

Les styles de liste contiennent les paramètres de style par défaut pour les listes ordonnées et non ordonnées. Vous pouvez facilement personnaliser ces styles de liste pour répondre à vos besoins en matière de documentation.

Dans l’exemple suivant, nous allons personnaliser le style de liste numérotée ou ordonnée :

1. Ouvrez la feuille de style requise pour la modification.

   >[!NOTE]
   >
   >Consultez la section [Personnaliser un style prédéfini ou nouveau](components-pdf-template.md#customize-style) pour ouvrir une feuille de style à des fins de personnalisation ou de modification.

1. Dans la liste **Styles**, développez le **Styles de liste**.

1. Sélectionnez le style **ol** dans la liste.

   Les propriétés de l’ancien style sont affichées dans le panneau Propriétés avec son aperçu.

   <img src="./assets/list-style-default.png" width="500">

1. Sélectionnez l’option **Formatage avancé**.

   Un message de confirmation s’affiche.

1. Cliquez sur **Oui** dans le message *Confirmation* pour ouvrir les propriétés **Formatage avancé**.

   Les propriétés suivantes sont disponibles par défaut :

   * **Level** : par défaut, il existe 6 niveaux de listes numérotées. Le niveau que vous sélectionnez dans cette liste déroulante contrôle les modifications de style au niveau sélectionné et à tous les niveaux suivants. Par exemple, si vous sélectionnez le niveau 4, toutes les modifications de style que vous appliquez sont définies sur les niveaux 4, 5 et 6.

   * **Type de style de liste** : vous pouvez choisir un certain nombre de styles de numérotation de liste. La liste contient des styles de numérotation génériques et spécifiques aux paramètres régionaux utilisés pour créer une liste numérotée. Certains des types de style de liste sont l’arabe, le cambodgien, le dévanâgari, l’éthiopien, le hangûl, l’hébreu, le japonais, le coréen, le chinois simple, l’ourdou, etc.

   De plus, vous pouvez utiliser les propriétés de formatage avancé suivantes :

   * **Format des nombres** : le format par défaut est défini sur `<x>`, où la valeur `x` est remplacée par le style de numérotation que vous avez sélectionné dans la propriété Type de style de liste. Par exemple, si vous avez sélectionné le style `decimal` (1), la valeur de `x` s’incrémente automatiquement pour chaque instance de l’élément de liste et prend la valeur 2, 3, etc. Vous pouvez également ajouter du texte personnalisé dans le champ pour mettre en forme le style de liste. Par exemple, si vous souhaitez que tous les styles de liste de premier niveau aient un suffixe « `)` », vous devez définir ce champ pour le style de liste de premier niveau sur « `<x>)` ».

   * **Insérer un caractère** : si vous souhaitez ajouter un caractère spécial au format numérique, cliquez sur le bouton Insérer un caractère (<img src="./assets/insert-chars.png" width="25">). Sélectionnez le caractère souhaité à ajouter au format de style, puis cliquez sur Insérer. Vous pouvez choisir différents types de caractères spéciaux dans la liste déroulante Sélectionner une catégorie .

   * **Insérer un niveau** : vous pouvez inclure le nombre de l&#39;un des niveaux précédents dans votre format numérique. Par exemple, si vous souhaitez inclure le format des nombres du 5e niveau dans le format des nombres du 6e niveau, choisissez 5 dans la liste déroulante Insérer un niveau. Notez que la liste déroulante Insérer un niveau affiche uniquement les nombres des niveaux précédents et non le niveau suivant. Par exemple, lorsque vous êtes au niveau 3, la liste Insérer un niveau affiche uniquement les niveaux 1 et 2.

     <img src="./assets/list-insert-level.png" width="400">

     Vous pouvez également modifier le Format des nombres pour présenter les valeurs de liste selon vos besoins. Par exemple, lorsque vous utilisez un style de numérotation imbriqué pour le niveau 3, vous pouvez le mettre en forme en tant que « `<2>.<x>))` ». La liste numéro 2 s&#39;affiche, suivie d&#39;un point, suivie de la liste numéro 3, puis de deux crochets, comme `2.3))`.

   * **Retrait** : si vous souhaitez mettre la liste en retrait, vous devez définir la valeur Retrait. Toute modification du retrait peut être examinée dans le panneau Aperçu et ajustée.

     >[!NOTE]
     >
     >Vous pouvez saisir la valeur en pixels, pt (points), rem, em, % (pourcentage) ou en pouces.

   * **Largeur du préfixe** : il s’agit de la zone occupée par le format numérique. Il est automatiquement défini sur une taille qui peut facilement s’adapter au format sélectionné. Si vous souhaitez augmenter la taille, vous pouvez remplacer la valeur par défaut.

     Lorsque vous définissez cette valeur manuellement, essayez de modifier les autres propriétés qui auront un impact sur la largeur. Par exemple, modifiez la taille de la police, le format avec un préfixe ou un suffixe, ainsi que les différentes propriétés de la police pour obtenir la taille optimale.

   * **Espacement** : spécifiez l’espacement horizontal entre le format des nombres de la liste et le contenu. L’espacement vertical contrôle l’écart entre les deux éléments de liste.

     La capture d’écran suivante affiche la liste triée personnalisée pour chaque niveau :

     <img src="./assets/list-number-format-final.png" width="500">

## Utiliser le style de tableau {#table-styles}

À l’aide des feuilles de style, vous pouvez concevoir *n* nombre de styles de tableau. À l’aide des styles de tableau, vous pouvez concevoir la manière dont l’ensemble du tableau, une ligne ou une colonne particulière est conçu. Avec le contrôle au niveau de la cellule, vous pouvez créer des styles de tableau très présentables.

Dans l’exemple suivant, nous allons voir comment créer un style de tableau et les différentes options de style de tableau que vous pouvez personnaliser :

1. Ouvrez la feuille de style requise pour la modification.

   >[!NOTE]
   >
   >Consultez la section [Personnaliser un style prédéfini ou nouveau](components-pdf-template.md#customize-style) pour ouvrir une feuille de style à des fins de personnalisation ou de modification.

1. Dans la liste **Styles**, cliquez avec le bouton droit de la souris sur le **Style de tableau** et choisissez **Nouveau style**.

1. Dans la boîte de dialogue *Ajouter un style*, conservez le nom **Balise** au format `table` et saisissez `double-border` dans le champ de nom **Classe**.

1. Cliquez sur **Terminé**.

   Un nouveau style de tableau nommé `table.double-border` est créé et ajouté sous la liste Styles de tableau .

1. Sélectionnez `table.double-border` dans la liste **Styles de tableau** et définissez les propriétés suivantes :

   * **Appliquer le formatage à** : vous pouvez appliquer le formatage de style à l’ensemble du tableau, aux lignes ou colonnes impaires/paires, ou à la première/dernière ligne ou colonne.

     >[!NOTE]
     >
     >Les paramètres suivants sont disponibles sous la section **Général** lorsque **Appliquer la mise en forme à** est défini sur **Tableau entier**.

   * **Habillage du texte** : sélectionnez le mode d’habillage du texte autour du tableau. Cela s’avère utile lorsque le tableau se trouve dans un autre élément de niveau bloc et qu’il doit être rendu avec d’autres contenus de l’élément de bloc. Les options d’habillage sont *gauche* ou *droite* alignées ou *aucune*.

   * **Réduction de la bordure** : sélectionnez l’aspect de la bordure du tableau. Si vous sélectionnez Réduire, une seule ligne de bordure est tracée entre les cellules du tableau. Toutefois, pour un style distinct, la bordure est visible autour de chaque cellule avec une marge intérieure supplémentaire.

     <img src="./assets/table-style-collapse-separate.png" width="500">

   * **Espacement des bordures** : ce paramètre n’est disponible que lorsque l’option Réduction de la bordure est définie sur Séparer. Ce paramètre vous permet de spécifier l’espacement vertical et horizontal entre les bordures des cellules.

     <img src="./assets/table-border-spacing.png" width="500">

     >[!NOTE]
     >
     >Les paramètres suivants sont disponibles sous la section **Cellule** lorsque **Appliquer la mise en forme à** est défini sur **Tableau entier**.

   * **Marge intérieure** : spécifiez la marge intérieure entre les cellules du tableau. Vous pouvez spécifier différentes valeurs de marge intérieure pour le haut, le bas, la gauche et la droite.

   * **Alignement vertical** : spécifiez l’alignement vertical pour le contenu de cellule. Les options disponibles sont les suivantes : Haut, Milieu et Bas.

   * **Bordure, style, couleur, largeur, rayon :** spécifiez les propriétés liées à la bordure. Vous pouvez choisir de n&#39;avoir des bordures que sur des côtés spécifiques comme Gauche ou Droite. Le style de bordure répertorie les styles de bordure disponibles, tels que Continu, Tiret, Ligne double, etc. Spécifiez la couleur de la bordure à l’aide de la palette de couleurs. Vous pouvez spécifier la largeur de la bordure en px, pt, rem, em, % et en unités. Le rayon définit la courbe pour créer des coins circulaires.

   Les autres propriétés sous Police, Bordure, Mise en page, Pagination et Arrière-plan sont expliquées dans d’autres exemples de cette rubrique. Selon votre sélection dans la propriété **Appliquer la mise en forme à**, vous pouvez appliquer ces valeurs à l’ensemble du tableau ou aux lignes ou colonnes sélectionnées.

   Vous trouverez ci-dessous un aperçu d’un exemple de tableau avec différentes lignes formatées de manière différente :

   <img src="./assets/table-final-design.png" width="500">

## Utilisation d’autres styles {#other-styles}

Si vous utilisez du contenu structuré (DITA), vous remarquerez que presque tous les éléments DITA sont associés à un mappage de style dans la feuille de style par défaut. Par exemple, le style d’un élément de `<shortdesc>` est défini sous la définition de style **Autre style** > **.shortdesc**. Vous pouvez facilement personnaliser n’importe lequel de ces styles qui seront automatiquement appliqués dans la sortie PDF générée à partir de votre contenu structuré. Cela signifie que, contrairement aux autres styles personnalisés, vous n’avez pas besoin d’ajouter un attribut `outputclass` au contenu de ces styles.

Si vous souhaitez créer une définition de style pour un élément qui n’est pas disponible par défaut ou si vous disposez d’un élément personnalisé, vous pouvez facilement le créer dans la feuille de style. Le seul point à prendre en compte est la création du style portant le même nom que le nom de l’élément structuré.

Dans l’exemple suivant, nous allons créer un style de titre de fenêtre (`wintitle`) :

1. Ouvrez la feuille de style requise pour la modification.

   >[!NOTE]
   >
   >Consultez la section [Personnaliser un style prédéfini ou nouveau](components-pdf-template.md#customize-style) pour ouvrir une feuille de style à des fins de personnalisation ou de modification.

1. Dans la liste **Styles**, développez **Autres styles**.

1. Cliquez avec le bouton droit sur **Autre style** et choisissez **Nouveau style**.

1. Dans la boîte de dialogue *Ajouter un style*, conservez le nom **Balise** en tant que *vide* et saisissez `wintitle` dans le champ de nom **Classe**.

   Comme `wintitle` est un nom d&#39;élément DITA reconnu, sa définition de style est automatiquement mappée à l&#39;élément `<wintitle>` dans votre source.

1. Cliquez sur **Terminé**.

   Un nouveau style nommé `.wintitle` est créé et ajouté sous la liste **Autres styles**.

1. Sélectionnez .wintitle dans la liste **Autres styles** et définissez les propriétés selon vos besoins.

La capture d’écran suivante affiche le style wintitle appliqué au texte « Contrôle de Principal ».

<img src="./assets/other-style-wintitle.png" width="500">


## Définir un style unique pour une mise en page d’une seule page

Lors de la publication de la sortie Native PDF, tous les styles sont fusionnés dans la PDF finale. Il est donc essentiel d’attribuer un style unique à chaque modèle dans le CSS.
Utilisez des noms de styles CSS distincts pour appliquer des polices et des styles spécifiques à différentes sections d’un PDF. Par exemple, vous pouvez définir la police souhaitée pour la page de garde à l’aide du code CSS suivant.

```css
...
[data-page-layout="Front"] * { 
    font-size: 18pt; 
}  
...
```


Le reste du document utilise la police par défaut que vous avez spécifiée pour la balise body en `content.css` ou `layout.css`. Cela permet de s’assurer que les styles ne sont pas fusionnés et que chaque section conserve sa conception prévue. Si vous souhaitez différentes tailles de police, créez des styles spécifiques pour chacune d’elles.

Par exemple, vous pouvez définir les styles suivants pour définir la taille de police 18 sur les paragraphes de la page de couverture avant et la taille de police 11 pt pour la page de couverture arrière :

```css
[data-page-layout="Front"] p { //For all paragraphs inside Front page
  font-size: 18pt; 
} 
  
[data-page-layout="Back"] p { //For all paragraphs inside Back page
  font-size: 11pt; 
}
```

>[!NOTE]
>
> Dans l’exemple précédent, « Front » et « Back » sont les exemples de noms des fichiers de disposition que vous pouvez utiliser dans les modèles.


## Définition d’un style CSS personnalisé pour le contenu avec préfixe et suffixe

Si vous définissez les styles CSS personnalisés, ils sont prioritaires lors de la génération de la sortie PDF native.
Le style CSS par défaut suivant masque le contenu du préfixe et du suffixe.

```css
...
.prefix-content, .suffix-content{
    display: none;
} 
...
```

Pour autoriser ces préfixes dans l’élément `<note>`, incluez le CSS suivant dans votre `content.css` :

```css
...
.prefix-content{
    display: inline !important;
}
...
```

L’élément `<note>` génère un `<span>` supplémentaire avec la classe prefix-content correspondant à son attribut type. Cette règle CSS cible la classe `.prefix-content` dans `<note>` éléments avec un attribut type, ce qui vous permet de mettre en forme ou de manipuler le contenu du préfixe selon vos besoins.

