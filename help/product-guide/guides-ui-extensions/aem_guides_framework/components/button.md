---
title: Bouton
description: Bouton
role: User, Admin
exl-id: 40e3f254-f94e-4f43-8ff5-2e6e1eb1cb6f
TQID: https://experienceleague.adobe.com/pmhyi9TN4gFF0opdy2SsTEUr4l1uLZMwhIwmUPMJSA0
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 62
ht-degree: 4%

---

# Bouton

Pour afficher un bouton, nous utilisons le composant, bouton .
Le composant Bouton dans l’interface utilisateur graphique représente un `<button/>` HTML.

```js title="buttonJSON.js"
const buttonJSON = {
  "component": "button",//tells the component name
  "label": "Yes, login",//tells the text for the button
  "variant": "cta",//tells the variants for the button which  provides default styles
  "on-click": "done",//tells what function to run after user clicks the button
};
```

Un bouton contenant un libellé de `Yes, login` est alors généré. Les autres propriétés incluent, sans s’y limiter, variante, libellé et en cas de clic.
> **_NOTE:_** La `on-<events>` est la syntaxe permettant d&#39;appeler les commandes dans les contrôleurs.

Le bouton rendu ressemblera à ceci :

![button](imgs/yes_login_button.png "Button")
