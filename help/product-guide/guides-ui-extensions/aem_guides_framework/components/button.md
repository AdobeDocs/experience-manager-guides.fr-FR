---
sidebar_position: 1
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 1%

---


# Bouton

Pour afficher un bouton, nous utilisons le composant, le bouton .
Le composant Bouton de l’interface utilisateur JSON représente un code HTML. `<button/>`.

```js title="buttonJSON.js"
const buttonJSON = {
  "component": "button",//tells the component name
  "label": "Yes, login",//tells the text for the button
  "variant": "cta",//tells the variants for the button which  provides default styles
  "on-click": "done",//tells what function to run after user clicks the button
};
```

Cela génère un bouton avec un libellé `Yes, login`. Les autres propriétés incluent, sans s’y limiter, variant, label, on-click.
> **_REMARQUE :_**  La variable `on-<events>` est la syntaxe permettant d’appeler les commandes dans les contrôleurs.

Le bouton rendu se présente comme suit :

![button](imgs/yes_login_button.png "Bouton")
