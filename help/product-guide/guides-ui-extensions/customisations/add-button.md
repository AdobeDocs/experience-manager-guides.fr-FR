---
title: Personnalisation simple
description: Exemple de personnalisation simple
role: User, Admin
exl-id: 7f19f0b0-2a1b-4a8b-b28c-3918a1bc9096
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 0%

---

# Exemple de personnalisation simple

Découvrez comment intégrer ces personnalisations dans notre application AEM Guides.

Par exemple, nous voulons ajouter ce bouton dans une vue existante de l’application.
Pour cela, nous avons besoin de 3 éléments de base :

1. `id` de la vue JSON à laquelle nous voulons ajouter notre composant.
2. `target`, c’est-à-dire l’emplacement dans le fichier JSON auquel nous voulons ajouter le nouveau composant. `target` est défini à l’aide de `key` et `value`. La paire clé-valeur peut être n’importe quel attribut utilisé pour définir le composant, ce qui peut aider à son identification unique.
Nous pouvons également utiliser des index pour référencer la cible.
Nous avons 3 viewStates : `APPEND`, `PREPEND`, `REPLACE`.
3. JSON du composant nouvellement créé et des méthodes correspondantes.

Supposons que nous souhaitions ajouter un bouton à la boîte à outils d’annotation utilisée dans la révision, qui ouvre le fichier dans AEM.

```typescript
export default {
  id: 'annotation_toolbox', 
  view: {
    items: [
      {
        component: 'button',
        icon: 'linkOut',
        title: 'Open topic in Assets view',
        'on-click': 'openTopicInAEM',
        target: {
          key: 'value',
          value: 'addcomment',
          viewState: VIEW_STATE.APPEND

        },
      },
    ],
  },
  controller: {
    openTopicInAEM: function (args) {
        const topicIndex = tcx.model.getValue(tcx.model.KEYS.REVIEW_CURR_TOPIC)
        const {allTopics = {}} = tcx.model.getValue(tcx.model.KEYS.REVIEW_DATA) || {}
        tcx.appGet('util').openInAEM(allTopics[topicIndex])
    },
  },
}
```

Dans l’exemple ci-dessus, nous avons :

1. `id` du JSON dans lequel nous voulons insérer notre composant, c’est-à-dire `annotation_toolbox`
2. la cible est le bouton `addcomment` . Nous ajoutons notre bouton après le bouton `addcomment` à l’aide de viewState `append`.
3. Nous définissons l’événement &quot;onclick&quot; du bouton dans le contrôleur.

JSON de la &quot;boîte à outils d’annotation&quot; `.src/jsons/review_app/annotation_toolbox.json`

Avant la personnalisation, la boîte à outils d’annotation ressemblait à ceci :

![annotation-toolbox](imgs/annotation_toolbox.png "Annotation toolbox")

Après la personnalisation, la boîte à outils d’annotation se présente comme suit :

![customised-annotation-toolbox](imgs/customised_annotation_toolbox.png "Boîte à outils d’annotation personnalisée")

## Ajout de CSS

Pour assurer la cohérence, nous fournissons le composant déjà stylisé. Les styles inhérents au fichier JSON inséré lui sont appliqués.
La principale méthode de gestion des CSS consiste à utiliser la clé extraClass dans les extensions.

```js
{    
    "view":{
        items:[
            {
                compoenent:"button",
                extraClass:"underline bg-red",
            }
        ]
    }
}
```

Vous pouvez ajouter des styles personnalisés avec des classes CSS en ajoutant un fichier CSS aux bibliothèques clientes. Au cours du build, nous créons également une sortie [Tailwind](https://tailwindcss.com/docs/utility-first) pour les classes d’utilitaires en vent arrière. La configuration pour la même opération se trouve à l’emplacement `tailwind.config.js` de l’extension sur `./tailwind.config.js`.
