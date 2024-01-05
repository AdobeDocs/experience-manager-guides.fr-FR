---
title: Icône
description: Icône
source-git-commit: 2e1cb576fa3b0a765304508e5f7962a154f1a72c
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 6%

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
