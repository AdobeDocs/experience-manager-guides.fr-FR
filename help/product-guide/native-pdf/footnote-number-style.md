---
title: Fonctionnalité Publish du PDF natif | Utilisation de styles personnalisés dans les notes de bas de page
description: Découvrez comment appliquer un style aux numéros dans les notes de bas de page.
exl-id: f1068f2f-2ace-4bdb-b5a4-46b03d4e43d6
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 0%

---

# Application de styles de bas de page


Les notes de bas de page sont placées au bas d’une page qui commentent ou citent une référence pour une partie désignée du texte.

Chaque note de bas de page comporte un marqueur de note de bas de page, qui est généralement un nombre ou un symbole comme un astérisque. Dans le contenu principal, le même marqueur de note de bas de page apparaît comme appel de note de bas de page et est indiqué par le même numéro ou symbole qu’un exposant.




## Modification des styles des appels de notes de bas de page et des marqueurs

Vous pouvez modifier les styles des appels de notes de bas de page et des marqueurs et gérer leur aspect dans la sortie du PDF. Ces styles vous permettent d’identifier rapidement les notes de bas de page dans le document.


**Exemple 1** :

Utilisez l’exemple donné pour ajouter un crochet avant et après l’appel de note de bas de page et le marqueur :

* Ajoutez le préfixe &quot;(&quot; et le suffixe &quot;)&quot; à l’aide de l’attribut content dans le style `footnote-call` , qui ajoute les crochets autour du numéro de note de bas de page dans le contenu du sujet.
* Ajoutez le préfixe &quot;(&quot; et le suffixe &quot;)&quot; à l’aide de l’attribut content dans le style `footnote-marker` , qui ajoute les crochets autour du numéro de note de bas de page.

```css
...
.fn::footnote-call { 
content: "(" counter(footnote, decimal) ")"; 
} 

.fn::footnote-marker { 
content: "(" counter(footnote, decimal) ")"; 
} 

...
```



<img src="./assets/pdf-output-footer-numbers.png" alt="Pied de page en sortie du PDF" width="500" border="2px">

*Ajoutez des crochets autour de l’appel de note de bas de page et du marqueur de note de bas de page.*

**Exemple 2** :

Vous pouvez également marquer l’appel de note de bas de page et le marqueur avec un astérisque ou un caractère grec inférieur au lieu d’un nombre.


```css
.fn::footnote-call {
 content: counter(footnote, asterisks);
}
.fn::footnote-marker {
 content: counter(footnote, asterisks) " ";
}
```

Dans la sortie, vous pouvez afficher quelque chose comme :

<img src="./assets/footnote-number-2.png" alt="Pied de page en sortie du PDF" width="500" border="2px">

*Ajoutez un astérisque à un appel de note de bas de page et un marqueur.*

## Masquer un appel de note de bas de page

Vous pouvez également appliquer un style aux appels de note de bas de page avec des attributs spécifiques. Par exemple, utilisez le style suivant pour masquer une note de bas de page avec les identifiants :
L’appel de note de bas de page est masqué dans le contenu principal, mais le marqueur de note de bas de page apparaît au bas de la page.

```css
.fn[id]::footnote-call {
		display: none;
                        }
```

## Mise en forme de la zone de note de bas de page

La zone de bas de page est l’endroit où toutes les notes de bas de page sont placées, généralement au bas d’une page. Vous pouvez formater la zone de note de bas de page à l’aide des mises en page ou des styles CSS.


### Dispositions de pages

Vous pouvez utiliser les propriétés de page pour les mises en page afin de mettre en forme la zone de note de bas de page dans les différentes sections d’un document PDF. Par exemple, vous pouvez spécifier les propriétés de marge et de marge intérieure de la zone de note de bas de page d’un chapitre. Vous pouvez également modifier le côté de la bordure, le style, la couleur, la largeur et le rayon.

Découvrez comment [utiliser les propriétés de page d’une mise en page](./design-page-layout.md#page-props-page-layout).

### Styles CSS

Vous pouvez appliquer des styles et mettre en forme la zone de note de bas de page dans un document de PDF. Par exemple, vous pouvez modifier la longueur, le style, la couleur et la largeur de la bordure.

```css
	@page {
	  @footnote {
   		border-top-style: solid;
   		border-top-color: #FF0000;
   		border-top-width: 3px;
 		        }
	      }
```

## Redémarrer la numérotation des notes de bas de page

Par défaut, les notes de bas de page sont numérotées en continu dans un document. Cependant, vous pouvez utiliser des mises en page ou des styles CSS pour redémarrer la numérotation des notes de bas de page.


### Dispositions de pages

Vous pouvez spécifier un numéro dans les mises en page pour redémarrer la numérotation des notes de bas de page dans les différentes sections d’un document PDF. Par exemple, sélectionnez un numéro dans le champ **Redémarrer la numérotation à partir de** du panneau Propriétés de la page pour redémarrer la numérotation des notes de bas de page pour chaque chapitre.

### Styles CSS

Utilisez le style suivant pour réinitialiser la numérotation des notes de bas de page sur chaque page de sortie du PDF :

```css
@page
{
counter-reset: footnote
}
```

Ainsi, les notes de bas de page de chaque page redémarrent à partir de 1.

## Afficher les notes de bas de page insérées

En règle générale, chaque note de bas de page apparaît comme un bloc ou commence sur une nouvelle ligne. Mais vous pouvez aussi les mettre en ligne ou à côté les uns des autres.

```css
.fn{
  	display: inline;
              }
```

## Application de styles aux références croisées de notes de bas de page

Vous pouvez également croiser une note de bas de page et vous référer à la même note de bas de page plusieurs fois dans la sortie de votre PDF. Vous pouvez ainsi vous reporter plusieurs fois à la même citation ou à la même note détaillée dans le document sans créer à nouveau une note de bas de page à son sujet.

Par exemple, la capture d’écran suivante montre comment la même note de bas de page est référencée de manière croisée dans toutes les villes de la sortie du PDF.
<img width="550" alt="références de notes de bas de page dans un pdf" src="./assets/link-footnotes.png" border="2px">

*Insérez la référence croisée dans une note de bas de page.*





Les styles CSS vous permettent également de mettre en forme les références croisées aux notes de bas de page. Par exemple, vous pouvez modifier la couleur d’arrière-plan des références croisées.

```css
    .xref-fn{
	background-color: red;
	}
```



