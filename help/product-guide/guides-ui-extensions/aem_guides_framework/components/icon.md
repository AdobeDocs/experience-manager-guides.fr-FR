---
sidebar_position: 4
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 2%

---


# Icône

Pour afficher une icône, nous utilisons le composant, l’icône .
Le composant de zone de texte dans l’interface utilisateur JSON représente un code HTML. `<icon/>`.

Icônes disponibles à l’adresse [Icônes de spectre d’Adobe](https://spectrum.adobe.com/page/icons/) sont compatibles avec notre application.

```js title="icon.js"
const iconJSON =  {
    "component": "icon", //tells the component name
    "icon": "info", // name of the icon to be used
    "size": "S", // size of the icon
    "title": "Information" // tooltip corresponding to the icon.
},
```

des icônes peuvent également être ajoutées aux boutons.

L’icône rendue se présente comme suit :

![icon](./imgs/info_icon.png "Icône")
