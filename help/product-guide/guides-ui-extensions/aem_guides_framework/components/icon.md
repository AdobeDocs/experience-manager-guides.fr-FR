---
title: Icône
description: Icône
role: User, Admin
exl-id: 5ba41c77-7329-49fc-bce5-02682261ea8e
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 6%

---

# Icône

Pour afficher une icône, nous utilisons le composant, l’icône .
Le composant de zone de texte dans l’interface utilisateur de JUI représente un fichier HTML `<icon/>`.

Les icônes disponibles dans les [icônes de spectre d’Adobe](https://spectrum.adobe.com/page/icons/) sont compatibles avec notre application.

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
