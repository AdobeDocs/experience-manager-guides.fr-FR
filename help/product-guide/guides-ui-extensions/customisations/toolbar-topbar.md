---
title: Barre de tête et barre d’outils
description: Personnalisation de la barre d’outils et de la barre d’outils
role: User, Admin
exl-id: 7065c9b8-67ac-4f6d-8124-daa547f2dc3b
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 0%

---

# Personnalisation de la barre d’outils et de la barre d’outils

Pour personnaliser les `topbar` et `toolbar`, nous utiliserons les identifiants : `topbar` ou `toolbar`, et nous suivrons la même vue, la même structure de contrôleur.

Vous trouverez ci-dessous un exemple trivial de personnalisation de barre d’outils. Ici, nous avons supprimé le bouton `Insert Numbered List` et remplacé le bouton `Insert Paragraph` par notre propre composant à l’aide d’un gestionnaire personnalisé en cas de clic.

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
