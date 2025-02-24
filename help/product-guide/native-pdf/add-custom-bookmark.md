---
title: Fonctionnalité native de publication PDF | Ajout d’un signet personnalisé dans la sortie PDF
description: Découvrez comment créer des feuilles de style utilisateur et créer des styles pour votre contenu.
exl-id: 6e6dbba3-da41-4066-b7b2-735a3d92b70a
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 1c96f25c3b970d04d23e8faf94a8f39095f6bd2c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---

# Ajout d’un signet personnalisé dans la sortie PDF

En règle générale, la table des matières d&#39;un plan DITA est répliquée sous forme de signets dans la sortie PDF finale, y compris le titre **Contenu** qui ouvre la page de la table des matières lorsqu&#39;elle est sélectionnée. Cette table des matières est créée à partir des titres de rubrique ou de section de votre plan DITA.

Vous pouvez parfois ajouter un signet personnalisé sur un contenu particulier dans votre sortie PDF pour faciliter la navigation. Pour ce faire, ajoutez un attribut `outputclass` sur l’élément et appliquez-lui l’attribut suivant :

`bookmark-level: 3`

Ici, le `bookmark-level` est un attribut et le nombre `3` est la valeur qui indique le niveau dans la hiérarchie des signets auquel le signet est ajouté. Dans l’exemple suivant, la rubrique de premier niveau « Contacts » comporte un tableau « Liste de contacts » dans lequel nous avons ajouté un attribut `outputclass` avec la valeur `custom-bookmark`.


<img src="./assets/custom-bookmark-attribute.png" width="500">

La définition suivante de la classe `custom-bookmark` est ajoutée dans le fichier CSS :

```css
…
/*Adding a custom bookmark*/
.custom-bookmark{
    bookmark-level: 2
}
…
```

Dans la sortie PDF, le tableau *Liste de contacts* est ajouté au 2e niveau de la liste des signets PDF, comme dans l&#39;exemple ci-dessous :

![](assets/custom-bookmark-in-pdf-output.png) {width="300" align="left"}

>[!NOTE]
>
>Vous devez choisir le niveau correct auquel le signet personnalisé est ajouté. Si vous spécifiez un nombre inférieur au signet du sujet parent, le signet personnalisé prend la position du signet parent et tous les autres signets s&#39;affichent en tant qu&#39;enfants. Cela peut entraîner une structure de signet inattendue.

**Suppression du titre du contenu des signets de sortie PDF**

Si vous ne souhaitez pas inclure le titre **Contents** dans la sortie PDF, vous pouvez le supprimer en plaçant le titre **Contents** dans `<p>` élément au lieu de `<h1>` élément .

Pour supprimer le titre du contenu des signets, procédez étape par étape comme suit :

1. Ouvrez le modèle PDF que vous utilisez pour la sortie PDF.
2. Ouvrez la **page de la table des matières** dans **mises en page**.
La page Table des matières s’affiche à droite.
3. Passez en mode **Source** et modifiez l&#39;élément dans lequel se trouve le contenu de `<h1>` en `<p>`.

Avant la modification :

```
<h1 class="toc-title">Contents</h1>
```

Après la modification :

```
<p class="toc-title">Contents</p>
```

Enregistrez les modifications et générez à nouveau la sortie.





