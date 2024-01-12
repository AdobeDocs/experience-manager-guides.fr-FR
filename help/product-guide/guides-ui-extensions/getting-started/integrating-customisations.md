---
title: Installation et configuration
description: Installation et utilisation du package d’extension AEM Guides
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---


# Installation et utilisation du package d’extension AEM Guides

Les extensions vous donnent la possibilité de personnaliser votre application AEM Guides afin de mieux répondre à vos besoins. Cette structure d’extension est prise en charge avec AEM Guides v4.3 et versions ultérieures (on-prem) et 2310 (cloud).

## Conditions requises

Ce module nécessite [git bash](https://github.com/git-guides/install-git) et npm

## Installation

Le moyen le plus simple d’amorcer l’installation de la structure AEM Guides est de passer par l’interface de ligne de commande

```bash
npx @adobe/create-guides-extension
```

## Ajout de code de personnalisation

1. Ajoutez des fichiers de code pour chaque composant que vous souhaitez étendre dans le `src/` répertoire . Certains fichiers d’exemple ont déjà été ajoutés pour vous.
2. Maintenant dans la `index.ts` situé dans le fichier `src/` directory :
   - Importez la variable `.ts` fichiers avec les personnalisations que vous souhaitez ajouter à votre version.
   - Ajoutez les imports à `window.extension`
   - Enregistrez le du composant personnalisé `id` et de l&#39;import correspondant à `tcx extensions`
   - Reportez-vous à l’exemple `/src/index.ts`

## Création du code personnalisé

- Exécuter `npm run build` dans le répertoire racine. Vous obtiendrez 3 fichiers dans le répertoire , `dist/`:
   - `build.css`
   - `guides-extension.js`
   - `guides-extension.umd.cjs`

![Sortie de build](./../imgs/build_output.png)

## Ajout de la personnalisation à AEM

- Accédez à `CRXDE` `crx/de/index.jsp#/`
- Sous , `apps` créer un noeud du type `cq:ClientLibraryFolder`

![Structure du dossier](./../imgs/crxde_folder_structure.png)

- Dans le `properties` du noeud, sélectionnez `Multi` ajoutez la propriété Name suivante : `categories`
Type : `String []`
Valeur : `apps.fmdita.review_overrides`, `apps.fmdita.xml_editor.page_overrides`

![Propriétés du dossier](./../imgs/crxde_folder_properties.png)

- Pour ajouter le js généré, créez un fichier, par exemple : `tcx1.js` dans le noeud créé ci-dessus. Ici, ajoutez le code provenant de `dist/guides-extension.umd.cjs` ou `dist/guides-extension.js`. Créez maintenant un fichier. `js.txt`, nous ajoutons ici le nom de notre fichier js, qui dans ce cas serait :

```t
#base=.
tcx1.js
```

- Pour ajouter le CSS créé, créez un fichier, par exemple : `tcx1.css` dans le noeud créé ci-dessus. Ici, ajoutez le code provenant de `dist/build.css`. Créez maintenant un fichier. `css.txt`, nous ajoutons ici le nom de notre fichier CSS, qui dans ce cas serait :

```t
#base=.
tcx1.css
```

- Effectuez une `shift + refresh` pour charger l’application avec les personnalisations.

## Résolution des problèmes

Vérifiez que toutes les étapes ci-dessus ont été effectuées correctement.
Après avoir ajouté votre code à tcx.js, effectuez une actualisation irréversible (Maj+Actualiser).
Ouvrez maintenant AEM, cliquez avec le bouton droit de la souris, puis cliquez sur `Inspect`
Accédez à Sources et recherchez votre `[node_name].js` (par exemple : extensions.js). Effectuez un contrôle/Cmd + D pour rechercher votre fichier. Si la variable `.js` existe avec le code JS à partir duquel vous avez collé le fichier. `dist/guides-extension.umd.cjs` ou `dist/guides-extension.js`, votre configuration est terminée.
