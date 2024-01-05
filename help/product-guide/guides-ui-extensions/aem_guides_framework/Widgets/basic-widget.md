---
title: Widgets
description: Présentation des widgets
source-git-commit: f9a72e44fe1a3d90180ff728189a24ea9c7b1b1a
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
