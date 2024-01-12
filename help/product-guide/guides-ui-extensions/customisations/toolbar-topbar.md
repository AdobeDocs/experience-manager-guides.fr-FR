---
title: Barre de tête et barre d’outils
description: Personnalisation de la barre d’outils et de la barre d’outils
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 0%

---


# Personnalisation de la barre d’outils et de la barre d’outils

Pour personnaliser la variable `topbar` et `toolbar`, nous utiliserons les identifiants : `topbar` ou `toolbar`et suivre la même vue, la même structure de contrôleur.

Vous trouverez ci-dessous un exemple trivial de personnalisation de barre d’outils. Ici, nous avons supprimé le `Insert Numbered List` et a remplacé le bouton `Insert Paragraph` avec notre propre composant à l’aide d’un gestionnaire personnalisé en cas de clic.

```js title = toolbar_customisation.js
const toolbarExtend = {
    id: "toolbar",
    view: {
        items: [
            {
                component: "div",
                target: {
                    key:"title",value: "Insert Numbered List",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                {
                    "component": "button",
                    "icon": "textParagraph",
                    "variant": "action",
                    "quiet": true,
                    "title": "Insert Paragraph",
                    "on-click": "INSERT_P"
                },

                target: {
                    key:"title",value: "Insert Paragraph",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
        ]
    },
    controller: {

        INSERT_P(){
            this.next("AUTHOR_INSERT_ELEMENT",  "p" )
        }
    }
}
```
