---
title: Fonctionnalité de publication native de PDF | Utilisation de styles personnalisés dans les notes de bas de page
description: Découvrez comment appliquer un style aux nombres dans les notes de bas de page.
exl-id: f1068f2f-2ace-4bdb-b5a4-46b03d4e43d6
feature: Output Generation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/2RWli1VfPmRWJkkiE-bI0ubuPTqlDXQTkkYpOe-6Ll4
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2: id: d6596f3f-92a7-43ec-b444-237db6adad05id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 673
ht-degree: 0%

---

# Application des styles de note de bas de page


Les notes de bas de page sont des notes placées au bas d’une page qui commentent ou citent une référence pour une partie désignée du texte.

Chaque note de bas de page comporte un marqueur de note de bas de page au bas de la page, qui est généralement un nombre ou un symbole comme un astérisque. Dans le contenu principal, le même marqueur de note de bas de page apparaît comme un appel de note de bas de page et est indiqué par le même numéro ou symbole qu’un exposant.




## Modification des styles des appels de note de bas de page et des marqueurs

Vous pouvez modifier les styles des appels de note de bas de page et des marqueurs, ainsi que leur aspect dans la sortie PDF. Ces styles vous permettent d’identifier rapidement les notes de bas de page dans le document.


**Exemple 1** :

Utilisez l’exemple donné pour ajouter un crochet avant et après l’appel de note de bas de page et le marqueur :

* Ajoutez le préfixe « ( » et le suffixe «) » à l’aide de l’attribut content dans le style `footnote-call`, qui ajoute les crochets autour du numéro de note de bas de page dans le contenu du sujet.
* Ajoutez le préfixe « ( » et le suffixe «) » à l’aide de l’attribut content dans le style `footnote-marker`, qui ajoute les crochets autour du numéro de note de bas de page au bas de la page.

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



<img src="./assets/pdf-output-footer-numbers.png" alt="Pied de page dans la sortie PDF" width="500" border="2px">

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

Dans la sortie, vous pouvez afficher des éléments tels que :

<img src="./assets/footnote-number-2.png" alt="Pied de page dans la sortie PDF" width="500" border="2px">

*Ajouter un astérisque à un appel de note de bas de page et à un marqueur.*

## Masquer un appel de note de bas de page

Vous pouvez également appliquer un style aux appels de note de bas de page avec des attributs spécifiques. Par exemple, utilisez le style suivant pour masquer une note de bas de page avec les identifiants :
L’appel de note de bas de page est masqué dans le contenu principal, mais l’indicateur de note de bas de page s’affiche au bas de la page.

```css
.fn[id]::footnote-call {
        display: none;
                        }
```

## Mise en forme de la zone de la note de bas de page

Toutes les notes de bas de page sont placées dans la zone de note de bas de page, généralement en bas de la page. Vous pouvez mettre en forme la zone de note de bas de page à l’aide des mises en page ou des styles CSS.


### Mises en page

Vous pouvez utiliser les propriétés de page des mises en page pour appliquer un style à la zone de note de bas de page dans les différentes sections d’un document PDF. Par exemple, vous pouvez spécifier les marges et les propriétés de remplissage de la zone de note de bas de page dans un chapitre. Vous pouvez également modifier le côté, le style, la couleur, la largeur et le rayon de la bordure.

Découvrez comment [utiliser les propriétés de page d’une mise en page](./design-page-layout.md#page-props-page-layout).

### Styles CSS

Vous pouvez appliquer des styles et mettre en forme la zone de note de bas de page dans un document PDF. Vous pouvez, par exemple, modifier la longueur, le style, la couleur et la largeur de la bordure.

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

Par défaut, les notes de bas de page sont numérotées en continu dans un document. Vous pouvez toutefois utiliser des mises en page de page ou des styles CSS pour redémarrer la numérotation des notes de bas de page.


### Mises en page

Vous pouvez spécifier un nombre dans les mises en page pour redémarrer la numérotation des notes de bas de page dans les différentes sections d’un document PDF. Par exemple, sélectionnez un nombre dans le champ **Redémarrer la numérotation depuis** du panneau Propriétés de la page pour redémarrer la numérotation des notes de bas de page pour chaque chapitre.

### Styles CSS

Utilisez le style suivant pour réinitialiser la numérotation des notes de bas de page sur chaque page de la sortie PDF :

```css
@page
{
counter-reset: footnote
}
```

Ainsi, les notes de bas de page de chaque page redémarrent à partir de 1.

## Afficher les notes de bas de page intégrées

En règle générale, chaque note de bas de page s’affiche sous la forme d’un bloc ou commence sur une nouvelle ligne. Mais vous pouvez également les placer en ligne ou à côté les uns des autres.

```css
.fn{
      display: inline;
              }
```

## Application de styles aux références croisées de note de bas de page

Vous pouvez également faire référence à une note de bas de page de manière croisée et faire référence à la même note de bas de page plusieurs fois dans votre sortie PDF. Cela vous permet de faire référence à la même citation ou note détaillée à plusieurs reprises dans le document sans créer de note de bas de page pour celui-ci.

Par exemple, la capture d’écran ci-dessous montre comment la même note de bas de page est référencée de manière croisée à toutes les villes dans la sortie PDF.
<img width="550" alt="références de note de bas de page dans un pdf" src="./assets/link-footnotes.png" border="2px">

*Insérer la référence croisée à une note de bas de page.*





À l’aide des styles CSS, vous pouvez également mettre en forme les références croisées avec les notes de bas de page. Par exemple, vous pouvez modifier la couleur d&#39;arrière-plan des références croisées.

```css
    .xref-fn{
    background-color: red;
    }
```



