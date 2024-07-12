---
title: Widgets de rendu
description: Fonctionnement du rendu dans les widgets JUI
role: User, Admin
exl-id: 381cc7b9-c957-40be-9db4-8347eefe2fa7
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---

# Widgets de rendu

Nous pouvons générer un widget en le référençant à l’aide de son `id`

Pour effectuer le rendu du widget `widget_languages` n’importe où dans l’application, nous pouvons utiliser la syntaxe simple :

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

Ici `@files` est une liste d&#39;objets de fichier contenant des champs

```typescript
- fileName: string
- contributors: Array<String>
```
