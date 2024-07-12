---
title: Fonctionnalité Publish du PDF natif | Utilisation de JavaScript pour utiliser du contenu ou du style
description: Découvrez comment créer des feuilles de style et créer des styles pour votre contenu.
exl-id: 2f301f6a-0d1c-4194-84c2-0fddaef8d3ec
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 1%

---

# Utilisation de JavaScript pour utiliser du contenu ou du style

La fonction Publication de PDF natif vous permet d’exécuter JavaScript pour manipuler le contenu ou le style appliqué au contenu avant la génération du PDF final. Cette fonctionnalité vous permet de contrôler entièrement la manière dont votre sortie finale est générée. Par exemple, vous pouvez ajouter des informations d’avis juridique à la sortie du PDF, qui réside dans un autre PDF. JavaScript vous permet d’ajouter les informations d’avis juridique une fois le PDF créé pour le contenu de base, mais avant la génération du PDF final.\
Pour prendre en charge l’exécution de JavaScript, la fonction Publication de PDF natif vous donne les fonctions de rappel suivantes :

* `window.pdfLayout.onBeforeCreateTOC(callback)` : Cette fonction de rappel est exécutée avant la génération de la table des matières.
* `window.pdfLayout.onBeforePagination(callback)` : Cette fonction de rappel est exécutée après la génération de la table des matières, mais avant l’ajout de sauts de page dans le PDF.
* `window.pdfLayout.onAfterPagination(callback)` : Cette fonction de rappel est exécutée après la table des matières et les sauts de page ajoutés dans le PDF.

>[!NOTE]
>
>En interne, une séquence d’exécution est conservée pour ces fonctions de légende. Tout d’abord, onBeforeCreateTOC est exécuté, suivi de onBeforePagination, et enfin, onAfterPagination est exécuté.

En fonction du type de contenu ou de modification de style que vous souhaitez effectuer, vous pouvez choisir la fonction de rappel à utiliser. Par exemple, si vous souhaitez ajouter du contenu, il est recommandé de le faire avant que la table des matières ne soit générée. De même, si vous souhaitez effectuer certaines mises à jour de style, celles-ci peuvent être effectuées avant ou après la pagination.

Dans l&#39;exemple suivant, la position des titres des illustrations est changée de au-dessus des images en dessous des images. Pour cela, vous devez activer l’option Exécution JavaScript dans le paramètre prédéfini. Pour ce faire, procédez comme suit :

1. Ouvrez le paramètre prédéfini à modifier.
1. Accédez à l’onglet **Avancé** .
1. Sélectionnez l’option **Activer JavaScript** .
1. Enregistrez le paramètre prédéfini et fermez-le.

Créez ensuite un fichier JavaScript avec le code suivant et enregistrez-le dans le dossier Ressources de votre modèle :

```css
...
/*
* DITA only allows the figure title to be placed above images 
* This JavaScript code is used to move the figure title below the image
* */
window.addEventListener('DOMContentLoaded', function () {
    window.pdfLayout.onBeforeCreateTOC(function() {
        var titleNodes = document.querySelectorAll('.fig > .title')
        for (var i = 0; i < titleNodes.length; i++) {
            var titleNode = titleNodes[i]
            var figNode = titleNode.parentNode
            var imageNode = figNode.querySelector('.image')
            if(imageNode && imageNode.parentNode !== figNode) {
              imageNode = imageNode.parentNode
            }
            if (figNode && imageNode && imageNode.parentNode === figNode) {
                figNode.insertBefore(imageNode, titleNode)
            }
        }
    })
});
...
```

>[!NOTE]
>
>La fonction `window.addEventListener('DOMContentLoaded', function ()` doit être appelée avant l’utilisation des fonctions de rappel.

Ensuite, ce script doit être appelé à partir d’un fichier de modèle utilisé pour générer la sortie du PDF. Dans notre exemple, nous l’ajouterons dans le modèle de table des matières. Assurez-vous que la balise `<script>` est ajoutée dans une balise `<div>` prédéfinie à l’intérieur de la balise `<body>`. Si vous l’ajoutez dans la balise `<head>` ou en dehors de la balise `<body>`, le script ne s’exécutera pas.

<img src="./assets/js-added-resources-template.png" width="500">

La sortie générée à l’aide de ce code et le modèle affiche le titre de la figure sous l’image :

<img src="./assets/fig-title-below-image.png" width="500">

## Ajout d’un filigrane à la sortie du PDF pour les brouillons de documents {#watermark-draft-document}

Vous pouvez également utiliser JavaScript pour ajouter des filigranes conditionnels. Ces filigranes sont ajoutés à votre document lorsque la condition définie est remplie.\
Par exemple, vous pouvez créer un fichier JavaScript avec le code suivant pour créer un filigrane vers la sortie PDF du document qui n’est pas encore approuvé. Ce filigrane n’apparaît pas si vous générez le PDF du document dans le docstate &quot;Approuvé&quot;.

```css
...
/*
* This file can be used to add a watermark to the PDF output
* */

window.addEventListener('DOMContentLoaded', function () {
    var watermark = 'Draft'
    var metaTag = document.getElementsByTagName('meta')
    css = "@page {\n  @left-middle {\n    content: \"".concat(watermark, "\";\n    z-index: 100;\n    font-family: sans-serif;\n    font-size: 80pt;\n    font-weight: bold;\n    color: gray(0, 0.3);\n    text-align: center;\n    transform: rotate(-54.7deg);\n    position: absolute;\n    left: 0;\n    top: 0;\n    width: 100%;\n    height: 100%;\n  }\n}")
    head = document.head || document.getElementsByTagName('head')[0], style = document.createElement('style');
    style.appendChild(document.createTextNode(css));
    window.pdfLayout.onBeforePagination(function () {
        for (let i = 0; i < metaTag.length; i++) {
            if (metaTag[i].getAttribute('name') === 'docstate' && metaTag[i].getAttribute('value') !== 'Approved') {
                head.appendChild(style);
            }
        }
    })
});
...
```

La sortie du PDF générée à l’aide de ce code affiche un filigrane *Draft* sur la page de garde de votre document :

<img src="./assets/draft-watermark.png" width="500">
