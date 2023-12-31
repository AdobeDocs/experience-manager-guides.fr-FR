---
title: Fonction de publication native d’un PDF | Utilisation des styles de barres de modification personnalisés
description: Découvrez comment appliquer des styles aux barres de modification.
exl-id: a81ec56c-ccbb-4599-a696-8edef7a73cdd
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Utilisation des styles de barres de modification personnalisés

Une barre de modification est une ligne verticale qui identifie visuellement le contenu nouveau ou révisé. AEM Guides vous permet d’afficher une barre de modification à gauche du contenu modifié dans les rubriques, ainsi que les rubriques modifiées dans la table des matières de la sortie du PDF.

Pour plus d’informations sur l’affichage de la barre de modifications, voir *Création d’un PDF avec une barre de modification entre les versions publiées* définition dans [Publier la sortie du PDF](../web-editor/native-pdf-web-editor.md).

## Modification du contenu dans les rubriques

La barre de modification s’affiche à gauche du contenu dans les rubriques qui ont été insérées, modifiées ou supprimées.

Vous pouvez modifier les styles suivants pour afficher le contenu modifié et parmi les barres de modification.


>[!NOTE]
>
>Ces styles font partie des `layout.css` et vous pouvez les modifier selon vos besoins.

Par exemple, vous pouvez utiliser l’attribut de couleur dans la variable `.inserted-block` style pour définir la manière dont le contenu inséré s’affiche dans la sortie du PDF publiée.


```css
...
.inserted-block { 
  color: #2ECC40; 
  display: inline; 
  -ro-comment-content: " "; 
  -ro-comment-style: underline; 
  -ro-comment-title: "Inserted"; 
  -ro-comment-date: attr(data-time); 
  -ro-comment-dateformat: "yyyy/dd/MM HH:mm:ss"; 
} 
...
```

De même, vous pouvez utiliser la variable `.deleted-block` style pour définir la manière dont votre contenu supprimé apparaît dans la sortie du PDF publiée.

```css
...
.deleted-block { 
  display: inline; 
  color: #FF6961; 
  text-decoration: line-through; 
  -ro-comment-content: " "; 
  -ro-comment-style: strikeout; 
  -ro-comment-title: "Deleted"; 
  -ro-comment-date: attr(data-time); 
  -ro-comment-dateformat: "yyyy/dd/MM HH:mm:ss"; 
} 
...
```

Vous pouvez utiliser `.inserted-change-bar` et `.deleted-change-bar` style pour modifier l’aspect des barres de modification qui apparaissent à gauche du contenu mis à jour.

Par exemple, vous pouvez utiliser `-ro-change-bar-color` dans `.inserted-change-bar` style pour afficher la barre de modification insérée en vert. Vous pouvez également utiliser `-ro-change-bar-color` dans `.deleted-change-bar` style pour afficher la barre de modification supprimée en rouge.

```css
...
.inserted-change-bar { 
  -ro-change-bar-color: #2ECC40; 
} 

.deleted-change-bar { 
  -ro-change-bar-color: #FF6961; 
  } 
...
```

<img src="./assets/changed-bar-content.png" alt="Modification du contenu des rubriques de la barre" width="500">

## Modification de la rubrique dans la table des matières (table des matières)

Vous pouvez également ajouter une barre de modification à gauche des rubriques modifiées dans la table des matières de la sortie du PDF. Vous pouvez utiliser `-ro-change-bar-color` dans la variable `.changed-topic` style pour ajouter une barre de modification dans la couleur de votre choix pour les rubriques mises à jour dans la liste de la table des matières.

Par exemple, vous pouvez ajouter une barre de modification de couleur verte.

```css
...
.changed-topic { 
 -ro-change-bar-color: #2ECC40; 
}  
...
```


Cette option affiche une barre de modification verte par rapport à toutes les rubriques de la table des matières dans lesquelles certaines mises à jour ont été effectuées. Vous pouvez cliquer sur la rubrique modifiée dans la table des matières et afficher les modifications détaillées.

<img src="./assets/changed-bar-TOC.png" alt="Table des matières de la barre modifiée" width="500">
