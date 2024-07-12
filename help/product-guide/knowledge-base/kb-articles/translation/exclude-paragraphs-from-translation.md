---
title: Exclusion de paragraphes dans une rubrique de la traduction
description: Comment exclure des paragraphes d’une rubrique de la traduction
feature: Translation
role: User
exl-id: 21e41bb4-52f3-4352-92d9-4a60f636de99
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Comment exclure des paragraphes d’une rubrique de la traduction

Le moyen le plus simple est d’utiliser l’attribut translation=no .

+ Les auteurs peuvent insérer l’attribut supplémentaire **translation=no** sur les paragraphes qu’ils ne souhaitent pas traduire. Le fournisseur de traduction doit être informé et il peut effectuer une configuration de son côté pour ignorer le texte avec cet attribut.
+ La traduction automatique prête à l’emploi (avec le connecteur de traduction Microsoft d’évaluation) présente le même comportement.
+ Tests avec traduction Microsoft : si vous définissez l’attribut **translate=no** au niveau du paragraphe, il ne traduit pas le paragraphe complet. Cet attribut peut être défini sur n’importe quel élément et le contenu à l’intérieur de cet élément ne sera pas traduit.


Voici quelques captures d’écran qui expliquent cela :

**Contenu Source**

![Contenu Source](assets/source-content.jpg)

**Contenu traduit en espagnol**

![Contenu traduit en espagnol](assets/trans-content.jpg)
