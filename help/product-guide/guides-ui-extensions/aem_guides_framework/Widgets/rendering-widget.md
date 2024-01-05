---
title: Widgets de rendu
description: Fonctionnement du rendu dans les widgets JUI
source-git-commit: f9a72e44fe1a3d90180ff728189a24ea9c7b1b1a
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---

# Widgets de rendu

Nous pouvons générer un widget en le référençant à l’aide de la fonction `id`

Pour générer le widget `widget_languages` n’importe où dans l’application, nous pouvons utiliser la syntaxe simple :

```json
{
    "component": "widget",
    "id": "widget_languages"
}
```

Les widgets peuvent également être utilisés pour effectuer le rendu d’éléments complexes. Par exemple, je souhaite générer la liste des contributeurs à chaque fichier.
Ici, le widget peut être construit comme suit :

```js title="fileContributorsWidget.js"
const widgetJSON =  {
    component: "div", 
    id: "file_contributors", 
    items: [ // adding components to the widget
        {
            component: "div",
            items: [
                {
                    component: "icon",
                    icon: "file"
                },
                {
                    component: "label",
                    label: "@fileName"
                }
            ]
        },
        {
            component: "list",
            data: "@contributors",
            itemConfig: {
                component: "label"
            }
        }
    ]
},
```

Maintenant, pour générer une liste des contributeurs pour chaque fichier, nous écrivons la liste comme suit :

```js title="fileContributorsList.js"
const listJSON = {
    component: "list"
    data: "@files"
    itemConfig: {
        component: "widget",
        id: "file_contributors"
    }
}
```

Ici `@files` est une liste d’objets de fichier contenant des champs

```typescript
- fileName: string
- contributors: Array<String>
```
