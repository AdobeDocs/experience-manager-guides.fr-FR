---
title: Icône
description: Icône
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
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
