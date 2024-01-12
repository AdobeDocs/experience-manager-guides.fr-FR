---
title: Zone de texte
description: Zone de texte
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 3%

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
