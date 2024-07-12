---
title: Bouton
description: Bouton
role: User, Admin
exl-id: 40e3f254-f94e-4f43-8ff5-2e6e1eb1cb6f
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 5%

---

# Bouton

Pour afficher un bouton, nous utilisons le composant, le bouton .
Le composant Bouton dans JUI représente un fichier HTML `<button/>`.

```js title="buttonJSON.js"
const buttonJSON = {
  "component": "button",//tells the component name
  "label": "Yes, login",//tells the text for the button
  "variant": "cta",//tells the variants for the button which  provides default styles
  "on-click": "done",//tells what function to run after user clicks the button
};
```

Un bouton portant le libellé `Yes, login` est ainsi généré. Les autres propriétés incluent, sans s’y limiter, variant, label, on-click.
> **_REMARQUE :_** `on-<events>` est la syntaxe permettant d’appeler les commandes dans les contrôleurs.

Le bouton rendu se présente comme suit :

![button](imgs/yes_login_button.png "Button")
