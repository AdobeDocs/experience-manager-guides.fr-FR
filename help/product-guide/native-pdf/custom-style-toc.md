---
title: Fonctionnalité de publication native de PDF | Appliquer un style personnalisé aux entrées de table des matières et au contenu de rubrique
description: Découvrez comment créer des feuilles de style utilisateur et créer des styles pour votre contenu.
exl-id: f65c9683-a1fc-432a-854b-83e8f39d7dae
feature: Output Generation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/cqknNhuPThhuNTsLZzwnrUzPJguIPs4J-3rX6PVR2V8
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: febac97b369bad427f0f650f2cdc69b0ca6c9f69
workflow-type: tm+mt
source-wordcount: 460
ht-degree: 0%

---

# Application d’un style personnalisé aux entrées de la table des matières et au contenu de la rubrique

Vous pouvez appliquer des styles personnalisés aux entrées de la table des matières, aux en-têtes de rubriques ou à des rubriques individuelles à l’aide de l’attribut `outputclass` sur les éléments de mappage pris en charge, tels que `<topicref>` et `<topichead>`. Pour appliquer une mise en forme personnalisée à une rubrique entière, étendez la définition de style de l’attribut `outputclass` dans votre CSS.

## Donner un style à une rubrique référencée via `<topicref>`

Vous pouvez appliquer un `outputclass` sur un élément de `<topicref>` pour appliquer un style à l’entrée de la table des matières, au titre de la rubrique ou au contenu complet de la rubrique dans le PDF généré.

Par exemple, pour identifier une rubrique qui nécessite une révision, ajoutez un attribut outputclass à l&#39;élément `<topicref>` correspondant dans votre plan DITA et définissez les styles associés dans votre CSS.

Dans l’exemple suivant, un attribut `outputclass` a été affecté à la rubrique *Historique des vols* avec la valeur `new-topic`.

<img src="./assets/new-topic-attribute-in-map.png" width="500">

La classe `new-topic` peut être utilisée pour définir des styles pour :

* Entrée principale de la table des matières ou de la mini-table des matières
* Titre de la rubrique dans le contenu principal
* L’intégralité du contenu de la rubrique, y compris le titre

La définition CSS suivante modifie la couleur du texte pour l’entrée de la table des matières et le titre de la rubrique :

```css
.new-topic {
  color:#CC5309
}
```

Cette définition contrôle la couleur du texte dans la table des matières et le titre de la rubrique. La sortie PDF ci-dessous affiche la couleur différente appliquée à l’entrée de la table des matières :

<img src="./assets/pdf-output-toc-entry.jpg" width="500">

Le titre du sujet est également stylisé à l’aide de la même couleur.

<img src="./assets/pdf-output-topic-title.jpg" width="500">

Si vous souhaitez que l’entrée de la table des matières et le titre du sujet aient des styles différents, vous pouvez les définir séparément, comme illustré ci-dessous :

```css
...
/*for styling TOC entry */
.new-topic {
  color:#CC3509
}

/* for styling topic's title */
.new-topic.title {
  color:#092ACC
}
...
```

Pour appliquer des styles à l’ensemble du contenu de la rubrique, ajoutez le suffixe `-content` au nom de la classe. L&#39;exemple suivant ajoute une barre de modification au contenu de la rubrique :

```css
...
/* for styling the topic's content */
.new-topic-content {
  -ro-change-bar-color:#A609CC;
}
...
```

À l’aide des attributs de style ci-dessus, une barre de modification est ajoutée à gauche de la rubrique *Historique des vols*, comme illustré ci-dessous :

<img src="./assets/pdf-output-topic-content.jpg" width="500">

## Application de styles aux éléments `topichead`

Vous pouvez utiliser l’attribut `outputclass` sur un élément `<topichead>` pour appliquer différents styles à l’entrée de la table des matières et à l’en-tête généré pour le `topichead`.

Par exemple, si vous définissez les `topichead` suivantes dans votre plan DITA :

```xml
<topichead navtitle="Getting Started" outputclass="new-topichead">
    ...
</topichead>
```

La classe `new-topichead` est appliquée à l’entrée topichead dans la table des matières et à l’en-tête généré pour la rubrique topichead.

Si vous souhaitez appliquer un style différent à l’en-tête, définissez une classe distincte pour celui-ci, de la même manière que `<topicref>` prend en charge un style distinct pour l’entrée de la table des matières et le titre du topic :

```css
...
/* Style for the topichead TOC entry */
.new-topichead {
  color: #CC5309;
}

/* Style for the topichead heading */
.new-topichead.title {
  color: #092ACC;
}...
```

Si vous souhaitez appliquer un style au contenu associé à la rubrique, ajoutez le suffixe `- content` au nom de la classe :

```css
.new-topichead-content {
    border-left: 2px solid #cccccc;
    padding-left: 8px;
}
```



## Supprimer les lignes vides de la table des matières

Si vous n’avez défini le titre d’aucune rubrique, des lignes vides apparaissent dans la table des matières pour ces rubriques.

Pour supprimer les lignes vides de la table des matières et de la mini table des matières, ajoutez le style suivant dans la `layout.css` :

```css
.toc-body a:empty,
.chaptoc-body a:empty {
    display: none;
} 
```

