---
title: Widgets
description: Présentation des widgets
role: User, Admin
exl-id: 96e960df-d595-4d58-8ad4-27057f857bac
TQID: https://experienceleague.adobe.com/SssVShlzFB3kjQCV-cNAOZVYb0TYSQ1CjtWoax2Q-LU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 86
ht-degree: 2%

---

# Widgets

Plusieurs composants de base, comme décrit dans la section Composants , peuvent être combinés pour créer un widget.
Les widgets peuvent être utilisés pour créer un nouveau composant « plus complexe » ou donner une structure aux éléments d’un composant.

Plongeons dans le concept d’un widget !

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

Ici, `@languages` est un tableau défini dans le modèle de `widget_languages` comme suit : [« anglais », « français », « hindi », « espagnol », « ourdou »]

Le widget de base rendu ressemblera à ceci :

![basic_widget](imgs/basic_widget.png "Widget de base")
