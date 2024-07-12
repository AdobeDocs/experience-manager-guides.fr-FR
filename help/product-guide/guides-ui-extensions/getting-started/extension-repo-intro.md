---
title: Présentation du référentiel d’extension
description: Structure du répertoire du package d’extension AEM Guides
role: User, Admin
exl-id: 99a00b3e-a5c9-41d8-a73d-8690d587277e
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---

# Structure du répertoire du package d’extension AEM Guides

```text
├── src
│   ├── **/*{js,ts}
│   ├── index.ts
├── dist
│   ├── guides-extension.js
│   ├── guides-extension.umd.cjs
│   ├── build.css
├── node_modules
├── package.json
├── package-lock.json 
└── .gitignore
└── buildCSS.mjs // for creating tailwind classes
└── vite.config.js // config for specifying TS and javascript build options
└── taliwind.config.js // config for tailwind we can add custom config for a design system here
├── jsons // jsons for the aem app
│   ├── context_menus // jsons for the context menus
│   ├── review_app // jsons for the review app
│   ├── xmleditor // jsons for xmleditor
```

## /src

```text
├── src
│   ├── **/*{js,ts}
│   ├── index.ts
```

Le répertoire source contient les fichiers de script ou javascript de votre extension. Le fichier index.ts est le point d’entrée de votre extension. Vous pouvez y importer tous vos composants et les exporter sous la forme d’un seul objet. Cet objet sera utilisé par l’extension pour effectuer le rendu des composants.

### /dist

Il s’agit du répertoire de build final. Contient le JS final et le CSS, qui doivent être copiés dans l’AEM

```test
├── dist
│   ├── gudies-extension.js // you can either choose es module (this one) or .cjs(other one) file
│   ├── gudies-extension.umd.cjs
│   ├── build.css // this is your tailwind css output
```

## /jsons

Ce répertoire contient les fichiers JSON des différentes vues. Vous pouvez utiliser ces fichiers JSON pour identifier les cibles et personnaliser la vue.

```text
├── jsons // jsons for the aem app
│   ├── context_menus // jsons for the context menus
│   ├── review_app // jsons for the review app
│   ├── xmleditor // jsons for xmleditor
```
