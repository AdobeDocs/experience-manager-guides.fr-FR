---
title: Libellé
description: Libellé
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 6%

---

# Libellé

Pour afficher n’importe quel texte ou chaîne, nous utilisons le composant, son libellé.
Le composant de libellé de l’interface utilisateur JSON représente un code HTML. `<label/>`.

Vous trouverez ci-dessous un exemple d’ajout d’une étiquette statique.

```js title="staticLabel.js"
const staticLabelJSON =  {
    "component": "label", //tells the component name
    "label": "This is an example label", // the string to be displayed
}
```

Sous JSON, une chaîne dynamique s’affiche :

```js title="dynamicLabel.js"
const labelJSON =  {
    "component": "label", //tells the component name
    "label": "@name", // the variable storing the text to be displayed
},
```

Le libellé rendu ressemblera à ceci :

![label](./imgs/label.png "Libellé")