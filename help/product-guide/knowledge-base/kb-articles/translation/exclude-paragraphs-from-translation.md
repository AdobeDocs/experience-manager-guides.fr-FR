---
title: Exclure de la traduction des paragraphes d’un sujet
description: Comment exclure des paragraphes d’une rubrique de la traduction
feature: Translation
role: User
exl-id: 21e41bb4-52f3-4352-92d9-4a60f636de99
TQID: https://experienceleague.adobe.com/IAY5PLpWlHEpMygjmHI-BqS75-VqAU5x1o9mdiu4Aac
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 0%

---

# Comment exclure des paragraphes d’une rubrique de la traduction

Le moyen le plus simple est d’utiliser l’attribut translation=no .

+ Les auteurs peuvent insérer l’attribut supplémentaire **translation=no** sur les paragraphes qu’ils ne souhaitent pas traduire. Le fournisseur de traduction doit être informé et il peut effectuer une configuration de son côté pour ignorer le texte avec cet attribut.
+ La traduction automatique prête à l’emploi (avec le connecteur d’évaluation Microsoft Translation) présente le même comportement.
+ Test avec la traduction Microsoft : si vous définissez l’attribut **translate=no** au niveau du paragraphe, le paragraphe entier n’est pas traduit. Cet attribut peut être défini sur n’importe quel élément et le contenu de cet élément ne sera pas traduit.


Voici quelques captures d’écran qui expliquent cela plus en détail :

**Contenu**

![Contenu ](assets/source-content.jpg)

**Contenu traduit en espagnol**

![Contenu traduit en espagnol](assets/trans-content.jpg)
