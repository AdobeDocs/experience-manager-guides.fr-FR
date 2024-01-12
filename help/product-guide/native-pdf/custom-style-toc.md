---
title: Fonction de publication native d’un PDF | Application d’un style personnalisé aux entrées de la table des matières et au contenu de la rubrique
description: Découvrez comment créer des feuilles de style et créer des styles pour votre contenu.
exl-id: f65c9683-a1fc-432a-854b-83e8f39d7dae
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---

# Application d’un style personnalisé aux entrées de la table des matières et au contenu de la rubrique

Parfois, vous pouvez appliquer un style personnalisé aux entrées de la table des matières ou à une rubrique particulière. Pour ce faire, vous pouvez associer une `outputclass` avec l’attribut `<topicref>` dans votre mappage DITA. En outre, si vous souhaitez appliquer un format personnalisé à une rubrique entière, cela peut également être réalisé en étendant la définition de style de l’attribut dans le CSS.

Prenons un exemple d’une nouvelle rubrique que vous souhaitez envoyer pour révision. Pour identifier facilement la rubrique mise à jour, vous devez ajouter une `outputclass` à l’attribut `<topicref>` dans votre mappage DITA, puis définissez un style personnalisé pour le même dans le CSS.

Dans l’exemple suivant, la variable *Histoire des vols* une rubrique a été affectée à une `outputclass` avec la valeur de `new-topic`.

<img src="./assets/new-topic-attribute-in-map.png" width="500">

La définition de classe de la variable `new-topic` dans une page CSS peut vous permettre de définir le style des éléments suivants :
* Entrée principale dans la table des matières ou la mini-table des matières
* Titre de la rubrique dans le contenu principal
* Contenu complet de la rubrique, y compris le titre

Voyons comment chacun de ces scénarios peut être défini dans le CSS. Dans la définition CSS suivante de la variable `new-topic` , la couleur du texte a été modifiée.

```css
…
.new-topic {
  color: #CC5309
}
…
```

Cette définition contrôle la couleur du texte dans la table des matières et le titre de la rubrique. La sortie de PDF suivante montre les différentes couleurs appliquées à l’entrée de la table des matières :

<img src="./assets/pdf-output-toc-entry.jpg" width="500">

Le titre de la rubrique est également stylisé avec la même couleur.

<img src="./assets/pdf-output-topic-title.jpg" width="500">

Si vous souhaitez que l’entrée de la table des matières et le titre du sujet aient des styles différents, vous pouvez les définir séparément, comme illustré ci-dessous :

```css
...
/*for styling TOC entry */
.new-topic {
  color: #CC3509
}

/* for styling topic's title */
.new-topic.title {
  color: #092ACC
}
...
```

Enfin, vous pouvez également appliquer des styles à l’ensemble du contenu de la rubrique. Pour ce faire, vous devez ajouter un suffixe &quot;`-content`&quot; au nom de la classe. Dans l’exemple suivant, une barre de modification a été ajoutée sur l’ensemble du contenu de la rubrique :

```css
...
/* for styling the topic's content */
.new-topic-content {
  -ro-change-bar-color: #A609CC;
}
...
```

À l’aide des attributs de style ci-dessus, une barre de modification est ajoutée à gauche du *Histoire du vol* , comme illustré ci-dessous :

<img src="./assets/pdf-output-topic-content.jpg" width="500">
