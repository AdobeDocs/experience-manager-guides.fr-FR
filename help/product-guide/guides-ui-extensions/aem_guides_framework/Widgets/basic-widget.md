---
title: Widgets
description: Présentation des widgets
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 0%

---


# Widgets

Plusieurs composants de base, comme décrit dans la section Composants , peuvent être combinés pour créer un widget.
Les widgets peuvent être utilisés pour créer un nouveau composant &quot;plus complexe&quot; ou pour donner une structure aux éléments d’un composant.

Explorons le concept d&#39;un widget !

Nous allons commencer par créer un widget simple pour afficher une liste de langues.

```js title="basicWidget.js"
const widgetJSON =  {
    "component": "div", 
    "id": "widget_languages", 
    "items": [ // adding components to the widget
        {
            "component": "div",
            "items": [
                {
                    "component": "icon",
                    "icon": "info"
                },
                {
                    "component": "label",
                    "label": "List of some languages"
                }
            ]
        },
        {
            "component": "list",
            "data": "@languages"
        }
    ]
},
```

Ici, `@languages` est un tableau défini dans le modèle de `widget_languages` en tant que : [&quot;Anglais&quot;, &quot;Français&quot;, &quot;Hindi&quot;, &quot;Espagnol&quot;, &quot;Urdu&quot;]

Le widget de base rendu se présente comme suit :

![basic_widget](imgs/basic_widget.png "Widget de base")
