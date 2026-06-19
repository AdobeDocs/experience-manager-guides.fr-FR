---
title: Nouveau moteur de publication pour PDF natif | Génération de sortie PDF
description: Découvrez comment utiliser le nouveau moteur de publication pour la publication native de PDF
feature: Publishing, Native PDF Output
role: User
TQID: https://experienceleague.adobe.com/GV3iYtBdFVrQwFjdvfqnfDIWPMugO3hFjS4FZqspG2M
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: afb45297-4313-4f67-818e-bc0b03abe086id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d6596f3f-92a7-43ec-b444-237db6adad05id: f6b497f1-f8e0-42ce-8e95-56c28d94026eid: f9dbea21-a714-40dd-bc90-080d8046c93fid: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: cc72dcf1-72e1-48cc-b434-e7c27d62d67cid: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 39af88b1d4bd424a8e56f3a217bcd8ee79f4be15
workflow-type: tm+mt
source-wordcount: 844
ht-degree: 0%

---

# Utiliser le moteur PDF natif v2

Le nouveau moteur de publication *moteur PDF natif v2*, repose sur une structure de génération PDF mise à niveau et comprend des modifications de la gestion des polices, du traitement CSS et du comportement de rendu.

Par conséquent, la sortie PDF générée à l’aide du nouveau moteur de publication peut différer de la sortie générée à l’aide du moteur PDF existant (*moteur PDF natif v1*). Les différences peuvent être visibles dans des zones telles que la disposition du texte, l’espacement, le style, le rendu des images et le formatage des notes de bas de page.

Par exemple, le moteur PDF natif v2 prend en charge les polices `OpenType`, tandis que le moteur PDF natif v1 s’appuie principalement sur les polices `TrueType`. Des améliorations de rendu similaires peuvent affecter l’aspect général des PDF générés.

Pour plus d’informations sur la manière d’activer le moteur PDF natif v2 dans votre environnement, consultez la section [Configuration du nouveau moteur de publication pour le PDF natif](./conf-new-pdf-engine.md).

## Mises à jour CSS recommandées pour le nouveau moteur de publication

Si vous souhaitez restaurer l’aspect de la sortie PDF générée par le moteur PDF natif v1 lors de l’utilisation du moteur PDF natif v2, vous devrez peut-être mettre à jour votre CSS personnalisé. Les modifications CSS recommandées décrites ci-dessous peuvent aider à maintenir la cohérence de sortie après l’activation du nouveau paramètre.

| Description | Mise à jour CSS recommandée |
|-------------|------------------------------------------------|
| Les images mises à l’échelle peuvent apparaître différemment en raison des modifications du comportement de rendu des images. | Pour restaurer le comportement de rendu d’image, ajoutez : <br><br> `image-rendering: pixelated` |
| L&#39;alignement de la ligne de repère de la table des matières peut être légèrement différent en raison de changements dans le comportement de rendu de la ligne de repère. | Pour restaurer l&#39;alignement des lignes de repère de la table des matières, ajustez le style des éléments de ligne de repère de la table des matières dans votre feuille de style personnalisée. Les modifications CSS requises peuvent varier en fonction de la disposition et de la mise en forme de la table des matières. |
| L’espacement du texte et l’habillage des lignes peuvent différer en raison de modifications dans le rendu de la police et le traitement de la disposition des glyphes. | Si votre feuille de style utilise la `sans-serif` famille de polices ou des polices qui présentent des différences d&#39;espacement, ajoutez :<br><br> `-ro-glyph-layout-mode: quality;` |
| Les références de note de bas de page peuvent ne plus apparaître comme des indicateurs d’exposant en raison des modifications apportées au style de note de bas de page par défaut. | Pour restaurer les marques de bas de page de style exposant, ajoutez :<br><br>`.fn::footnote-marker` <br> `{ content: counter(footnote) " ";`<br> `vertical-align: super;`<br>`font-size: 65%;}` |
| Le texte souligné peut apparaître avec un espace plus grand entre le texte et le soulignement en raison des modifications du positionnement du soulignement. | Pour rétablir le positionnement du soulignement, utilisez la propriété `text-underline-offset` et ajustez la valeur de décalage selon vos besoins. Par exemple :<br><br>`text-decoration: underline;`<br>`text-underline-offset: -0.1em;` |
| L’espacement entre les marqueurs de liste et le texte de l’élément de liste peut différer en raison de modifications du comportement de rendu de la liste. | Pour rétablir l’espacement, augmentez la marge intérieure gauche des éléments de liste. Par exemple :<br><br>`.step {`<br> ` margin-top: 0.3rem;`<br> `margin-bottom: 0.5rem;`<br> `padding-left: calc(1.5rem + 1ch);}` |
| L’espacement avant les en-têtes peut différer en raison des changements de comportement de réduction de marge. | Pour rétablir l&#39;espacement, passez en revue les marges des éléments adjacents et réduisez ou supprimez le chevauchement des marges supérieure et inférieure si nécessaire. Par exemple :<br><br>`h1.chapter { `<br> `margin-top: 0;` <br>`}`<br>`chaptoc-body { margin-bottom: 0;`<br>` }` |
| Les marques de coche générées avec CSS peuvent apparaître avec des tailles ou des styles différents, car elles sont rendues à l’aide de différentes polices de secours. | Pour effectuer le rendu des marques de manière cohérente, utilisez une famille de polices contenant les deux glyphes. Par exemple :<br><br>`::marker {`<br> `font-family: -ro-symbols !important;}` |
| Les marqueurs de liste circulaire générés par CSS peuvent apparaître partiellement tronqués ou tronqués en raison de changements dans le comportement de positionnement des marqueurs. | Pour rétablir l’aspect des marques de liste circulaire, évitez d’utiliser le positionnement absolu pour la marque. Si un positionnement absolu est requis, spécifiez explicitement une valeur de `top` appropriée pour positionner correctement le marqueur. |
| L’ordre de lecture des éléments de liste dans la sortie PDF/UA peut différer lorsque les éléments de liste utilisent des styles de positionnement tels que `position: relative`. | Pour que l’ordre de lecture suive plus étroitement la structure du document source, appliquez la propriété CSS suivante aux éléments de liste <br><br>`li {`<br>`-ro-paint-reordering: avoid;}` |


## Solutions pour les problèmes connus

Les solutions de contournement suivantes peuvent aider à résoudre les problèmes connus dans la sortie PDF générée lors de l’utilisation du moteur PDF natif v2.

- `text-decoration` propriétés css appliquées au contenu du tableau ne sont pas rendues dans la sortie PDF.

  **Solution** : appliquez les propriétés de décoration de texte aux éléments de `span` du contenu du tableau au lieu de les appliquer directement aux éléments du tableau.

- Les propriétés CSS `-ro-colorbar-top-left` et `-ro-colorbar-top-right` n’affectent pas la barre de couleurs dans la sortie PDF.

  **Solution** : supprimez les valeurs correspondantes de la feuille de style utilisateur dans `mergedHTML.json` ou ajoutez des `!important` aux valeurs de propriété dans le document CSS afin qu’elles ne soient pas remplacées par la feuille de style utilisateur.

- Les barres de couleurs peuvent apparaître fusionnées lorsque la largeur de la page est limitée, car elles ne sont pas réduites en fonction de la taille de la page dans la sortie PDF.

  **Solution** : affichez les barres grises et colorées sur différents côtés de la page ou ajustez les paramètres des barres de couleurs afin qu’elles ne se chevauchent pas sur des largeurs de page plus petites.

## Correction de problèmes liés au nouveau moteur de publication

Les problèmes suivants dans la sortie PDF générée à l’aide de _Native PDF Engine v1_ sont résolus dans _Native PDF Engine v2_ :

- Lors de la génération d’une sortie Native PDF pour certains contenus, seule la première page est rendue dans PDF, malgré l’HTML intermédiaire contenant l’intégralité du contenu sur plusieurs pages. (GUIDES-28270)
- L’ordre de lecture du contenu dans la sortie PDF native avec les paramètres d’accessibilité activés est incorrect. Les numéros de page des pieds de page sont lus avant le contenu principal et non à la fin. (GUIDES-27790)
- La barre de couleurs dans la sortie Native PDF ne s’étend pas sur toute la largeur de la page et se chevauche lorsque la taille de la page est personnalisée, ce qui masque certaines zones de couleur. (GUIDES-15505)
- Le sélecteur `CSS:is()pseudo-class` n’est pas respecté dans la sortie PDF native, ce qui entraîne des différences de style par rapport au rendu du navigateur. (GUIDES-11328)