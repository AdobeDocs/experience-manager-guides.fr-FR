---
sidebar_position: 3
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '62'
ht-degree: 0%

---


# Champ de texte et zone de texte

Pour utiliser le texte comme entrée, nous utilisons les composants, le champ de texte et la zone de texte.
Le composant de zone de texte dans l’interface utilisateur JSON représente un code HTML. `<textarea/>`.

```js title="textArea.js"
const textAreaJSON =  {
    "component": "textarea", //tells the component name
    "id": "input_name", // can be used to give a unique identifier to a component
    "data": "@name", // the variable storing the inputted text
    "on-keyup": {
        "name": "submitName",
        "eventArgs": {
            "keys": [
            "ENTER"
            ]
        }
    },
},
```

Ici, `on-keyup` est la syntaxe permettant d’appeler les commandes dans les contrôleurs.
Cette opération génère une zone de texte dans laquelle l’utilisateur appuie sur ENTRÉE pour appeler l’événement. `submitName`

La zone de texte rendue se présente comme suit :

![text-area](./imgs/text_area.png "Zone de texte")
