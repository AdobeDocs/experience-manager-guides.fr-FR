---
title: Vues de l’éditeur web
description: Affichez des documents en mode création, source et aperçu. Découvrez comment afficher du contenu en fonction de filtres conditionnels, afficher les balises de suivi des modifications et exporter une rubrique en tant que PDF dans AEM Guides.
feature: Authoring, Features of Web Editor
role: User
hide: true
exl-id: dbc27856-6903-4694-9875-77dc778c80bd
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '1449'
ht-degree: 0%

---

# Vues de l’éditeur web {#id204GK0D0V5Z}

L’éditeur web d’AEM Guides prend en charge l’affichage de documents dans trois modes ou vues différents :

## Création

Voici un exemple type de la vue Ce que vous voyez est ce que vous obtenez \(WYSISYG\) de l’éditeur web. Vous pouvez modifier la rubrique comme vous le feriez dans n’importe quel éditeur de texte enrichi standard. Dans la vue Auteur, vous disposez des options permettant d’enregistrer une révision du document, de rechercher et de remplacer du contenu, d’insérer un élément, d’insérer un lien hypertexte, d’insérer une référence de contenu, etc.

>[!NOTE]
>
> Lorsque vous utilisez la référence de contenu, le contenu référencé s’affiche également en mode Création en bleu. Le contenu référencé n’est pas modifiable.

## Source

La vue Source affiche le code XML sous-jacent qui constitue la rubrique. Si vous êtes à l’aise avec l’utilisation directe de code XML, vous devez utiliser la vue Source. Outre les modifications de texte standard effectuées dans cette vue, vous pouvez également ajouter des éléments et des attributs à l’aide du catalogue dynamique ou rechercher et remplacer du texte, des éléments ou des attributs.

- Pour appeler le catalogue dynamique, placez le curseur à la fin de toute balise d’élément où vous souhaitez insérer le nouvel élément et saisissez « &lt; ». L’éditeur affiche une liste de tous les éléments XML valides que vous pouvez insérer à cet emplacement. Utilisez les touches fléchées pour sélectionner l’élément à insérer et appuyez sur Entrée. Lorsque vous saisissez le crochet fermant « \>, la balise fermante de l’élément est automatiquement ajoutée.

  ![](images/smart-catalog-elements.png){width="400" align="left"}

- Vous pouvez également modifier facilement un élément à partir de la vue Source. Par exemple, si vous modifiez la balise d’ouverture d’un élément de `p` en `note`, la balise de `p` de fermeture est automatiquement remplacée par `/note`. Si vous remplacez un élément par un élément incorrect, l’erreur de validation s’affiche immédiatement.

- Si vous souhaitez ajouter un attribut à un élément, placez le curseur à l’intérieur de la balise de l’élément et appuyez sur la barre d’espace. Une liste d’attributs valides pour cet élément s’affiche dans le catalogue dynamique. Utilisez les touches fléchées pour sélectionner l’élément souhaité et appuyez sur Entrée pour insérer l’élément. Pour spécifier une valeur pour l’attribut, saisissez le signe égal \(=\) et l’éditeur saisit automatiquement les guillemets ouvrants et fermants «  » dans lesquels vous pouvez spécifier la valeur de l’attribut.

  ![](images/smart-catalog-attribute.png){width="350" align="left"}

- Dans la vue Source, il existe une option Retrait automatique qui réorganise le code XML dans un format présentable et facile à lire. En outre, si vous sélectionnez du texte et passez de la vue Auteur à Source ou de la vue Source à la vue Auteur, le texte sélectionné est également mis en surbrillance dans l’autre vue.
- La validation XML de votre document est une autre fonctionnalité puissante de la vue Source. Si vous ouvrez un document contenant un XML non valide, il s’ouvre dans la vue Source avec les informations sur le XML non valide. Par exemple, dans la capture d’écran suivante, les informations exactes sur le code XML erroné sont données dans le pop-up Erreur d’analyse .

  ![](images/invalid-topic-xml.png){width="650" align="left"}

  Dans la capture d’écran ci-dessus, une mise en surbrillance croisée est utilisée pour pointer la ligne contenant un XML erroné.

- La fonction Rechercher et remplacer vous permet de rechercher du texte, un élément ou un attribut dans la vue Source.
Pour plus d’informations, consultez la description de la fonctionnalité **Rechercher et remplacer** dans la section [Barre d’outils principale](web-editor-features.md#id#id2051EA0G05Z).

- La vue Source propose de nombreux raccourcis pour vous aider à parcourir et à travailler rapidement sur un document. Le tableau suivant répertorie les actions prises en charge et leurs touches de raccourci :

  | Pour ce faire : | Utiliser ce raccourci |
  |----------|-----------------|
  | Ajouter plusieurs curseurs | **Ctrl**+Clic gauche |
  | Sélections de texte multiples et non consécutives | **Ctrl**+Clic gauche pour faire glisser et sélectionner du texte |
  | Sélectionner du texte sur les lignes et entre les lignes | **Alt**+Clic gauche pour faire glisser et sélectionner du texte |
  | Annuler la sélection multiple ou quitter le mode plein écran | **Échap** |
  | Afficher la saisie automatique | **Ctrl**+**Espace** |
  | Accédez à la balise d’ouverture ou de fermeture de la balise active | **Ctrl**+**J** |
  | Développer ou réduire la balise active et son contenu | **Ctrl**+**Q** |
  | Sélectionner l&#39;élément courant et son contenu | **Ctrl**+**L** |
  | Ajouter un retrait négatif à l’élément actif | **Maj**+**Tabulation** |
  | Supprimer l&#39;élément courant et son contenu | **Maj**+**Ctrl**+**K** |
  | Déplacer le curseur d&#39;un mot vers la gauche | **Alt**+**Flèche Gauche** |
  | Déplacer le curseur d&#39;un mot vers la droite | **Alt**+**Flèche Droite** |
  | Faire défiler une ligne vers le haut sans modifier l’emplacement du curseur | **Ctrl**+**Flèche Haut** |
  | Faire défiler une ligne vers le bas sans modifier l’emplacement du curseur | **Ctrl**+**Flèche Bas** |
  | Activer/désactiver le mode plein écran | **F11** |
  | Insérer une nouvelle ligne après l&#39;élément courant | **Ctrl**+**Entrée** |
  | Insérer une nouvelle ligne avant l&#39;élément courant | **Maj**+**Ctrl**+**Entrée** |
  | Rechercher et sélectionner l’occurrence suivante du mot actuel | **Ctrl**+**D** |
  | Déplacer l&#39;élément courant et son contenu d&#39;un élément vers le haut | **Maj**+**Ctrl**+**Flèche Haut** |
  | Déplacer l&#39;élément courant et son contenu d&#39;un élément vers le bas | **Maj**+**Ctrl**+**Flèche Bas** |
  | Placer l’élément actif dans une balise de commentaire | **Ctrl**+**/** |
  | Dupliquer l&#39;élément courant et son contenu | **Maj**+**Ctrl**+**D** |
  | Supprimez le texte situé après le curseur. Si le curseur se trouve avant un élément d’ouverture, l’élément entier est supprimé. | **Ctrl**+**K**+**K** |
  | Supprime le texte à gauche du curseur sur la ligne active. Si le curseur se trouve après la balise de fermeture d’un élément, l’élément entier est supprimé. | **Ctrl**+**K**+**Retour arrière** |
  | Convertir le texte actuel en majuscules | **Ctrl**+**K**+**U** |
  | Convertir le texte actuel en minuscules | **Ctrl**+**K**+**L** |
  | Faire défiler l’élément actif jusqu’au centre de l’éditeur | **Ctrl**+**K**+**C** |
  | Ajouter un curseur au-dessus de la position actuelle | **Ctrl**+**Alt**+**Flèche Haut** |
  | Ajouter un curseur sous la position actuelle | **Ctrl**+**Alt**+**Flèche Bas** |
  | Recherche récursive du mot courant \(en direction avant\) | **Ctrl**+**F3** |
  | Recherche récursive du mot courant \(en sens inverse\) | **Maj**+**Ctrl**+**F3** |


## Prévisualisation

L’ouverture d’une rubrique en mode Aperçu montre comment une rubrique s’affichera lorsqu’elle sera consultée par un utilisateur dans son navigateur. Dans le cas d&#39;un plan DITA, un aperçu du plan s&#39;affiche, dans lequel un seul document composite de toutes les rubriques du plan s&#39;affiche.

Le mode Aperçu vous propose les fonctionnalités suivantes :

- [Affichage du contenu en fonction de filtres conditionnels](#id2114BI00VXA)
- [Afficher les balises de suivi des modifications](#id2114BJ00CE8)
- [Exporter une rubrique en tant que PDF](#id2114BL00B5U)

### Affichage du contenu en fonction de filtres conditionnels {#id2114BI00VXA}

Si vous avez utilisé des conditions dans votre rubrique ou mappage, celles-ci s’affichent dans le panneau Filtres . Par défaut, toutes les conditions sont sélectionnées et l’intégralité du contenu est affichée. Si vous désélectionnez une condition, le contenu comportant cette condition est supprimé de la vue. Vous pouvez également choisir de mettre en surbrillance le contenu conditionné.

L’image suivante présente une rubrique qui utilise deux conditions : `Audience` et `Product`. Le contenu conditionné est mis en surbrillance avec un arrière-plan jaune.

![](images/preview-filters.png){width="800" align="left"}

### Afficher les balises de suivi des modifications {#id2114BJ00CE8}

Si un document contient des marques de suivi des modifications \(ou des repères visuels\), vous pouvez également prévisualiser le document avec ou sans ces marques. Lors de la prévisualisation d’un document, le panneau de droite contient les options Filtres et Suivi .

![](images/preview-tracking_cs.png){width="400" align="left"}

Vous pouvez choisir parmi trois options **Tracking** :

- **Pas de balisage** : dans cette vue, toutes les insertions et suppressions sont acceptées et une vue simple du document est présentée. Dans cette vue, vous ne voyez aucune balise de suivi des modifications.
- **Original** : dans cette vue, toutes les insertions sont rejetées et toutes les suppressions sont restaurées, puis un aperçu s&#39;affiche. En d’autres termes, vous obtenez le formulaire d’origine du document avant d’activer le mode de suivi des modifications.
- **Afficher les balises** : dans cette vue, vous obtenez toutes les balises pour le contenu inséré et supprimé.

  L’image suivante présente l’aperçu d’un fichier de carte avec des balises :

  ![](images/preview-map-with-track-changes.PNG){width="800" align="left"}


### Exporter une rubrique en tant que PDF {#id2114BL00B5U}

PDF est l’un des formats de sortie les plus courants. Il est utilisé à chaque étape possible du cycle de développement du document. AEM Guides vous offre la possibilité de générer la PDF d’une rubrique individuelle ou d’un fichier de mappage entier. La fonction Exporter en tant que PDF permet à l’auteur, à l’éditeur ou à un administrateur de générer facilement la sortie PDF pour une rubrique individuelle. Il utilise les configurations DITA-OT enregistrées au niveau du profil de dossier pour générer le PDF.

Cette fonctionnalité prend en charge les fonctionnalités suivantes :

- Générer le PDF de la copie de travail active d&#39;une rubrique.
- Acceptez le nom de la transformation DITA-OT et les arguments de ligne de commande pour générer le PDF.
- Enregistrez la sortie générée sur le système local.
- Résolvez les références de clé et de contenu utilisées dans la rubrique avant de générer la sortie.

Pour exporter une rubrique en tant que PDF, procédez comme suit :

1. Ouvrez la rubrique en mode Aperçu .

1. Cliquez sur l’icône **Exporter en tant que PDF** \(![](images/export-as-pdf-icon.svg)\).

   La boîte de dialogue Exporter en tant que PDF s’affiche.

   ![](images/export-as-pdf-dialog.png){width="350" align="left"}

1. *\(Facultatif\)* Spécifiez le nom de la transformation DITA-OT et les arguments de ligne de commande que vous souhaitez utiliser.

1. Cliquez sur **Télécharger**.

   >[!NOTE]
   >
   > Assurez-vous d’avoir activé la fenêtre pop-up dans la configuration du navigateur, sinon le PDF ne sera pas téléchargé.

   Le PDF est généré et ouvert dans un nouvel onglet ou une boîte de dialogue s’affiche pour vous permettre d’enregistrer le PDF sur votre système local.


**Rubrique parente :**&#x200B;[ Utiliser l’éditeur web](web-editor.md)
