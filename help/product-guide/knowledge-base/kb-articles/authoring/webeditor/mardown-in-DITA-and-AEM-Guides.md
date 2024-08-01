---
title: Utilisation de Markdown dans DITA AEM Guides
description: Migration et utilisation du markdown dans DITA AEM Guides
source-git-commit: dfda0ec4fe7301182299f6ab46d2772629ab6df7
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 0%

---

# Utilisation de Markdown dans AEM Guides

## Options disponibles

Il existe deux options pour utiliser des fichiers Markdown dans AEM Guides :

- Option 1 : importez les balises existantes dans AEM Guides et utilisez-les directement dans ditamap pour publier.

- Option 2 : convertir des fichiers de balisage existants en DITA

Parlons de chaque option :

### Option 1 : importez les balises existantes dans AEM Guides et utilisez-les directement dans ditamap pour publier.

Il dispose d’une configuration plus simple et d’une mise en oeuvre plus rapide. Toutefois, l’utilisation limitée des fonctionnalités d’AEM Guides comme la réutilisation du contenu.

L’utilisateur doit ajouter l’attribut `format="markdown" ` ou `format="mdita"` pour que les moteurs de publication comprennent le type de fichier et publient en conséquence.

Exemple de fichier : [Markdown Ditamap](https://acrobat.adobe.com/id/urn:aaid:sc:AP:da31137e-be84-44fb-8974-d038eeff0283)

![capture d’écran pour référence](../../assets/authoring/markdown_map.png)


#### Publish vers PDF et sortie web

AEM Guides propose l’option Web (Html5/AEM Site) et PDF (Native-PDF/DITA-OT) pour publier un fichier ditamap avec du contenu Markdown.

### Option 2 : convertir Markdown au format DITA

Utilisation complète des fonctionnalités d’AEM Guides qui permettent la réutilisation du contenu, la traduction conditionnelle de traitement, la référence, etc. Toutefois, il faudrait des efforts initiaux pour convertir le format `.md` au format `.dita`.

Markdown vers DITA peut être converti à l’aide d’outils externes comme Adobe FrameMaker et DITA-OT.


Pour Adobe FrameMaker, voir : [Import markdown](https://www.adobe.com/in/products/framemaker/features.html#import-markdown)

Pour DITA-OT, reportez-vous à : [Markdown as Input](https://www.dita-ot.org/dev/topics/markdown-input.html)

Exemple de fichier converti à l’aide d’Adobe FrameMaker : [Markdown to DITA sample](https://acrobat.adobe.com/id/urn:aaid:sc:AP:874881f3-ba43-410c-abc6-2df899536d79)

#### Publish vers PDF et sortie web

Une fois les fichiers Markdown convertis en DITA, l’utilisateur peut facilement publier la sortie dans n’importe quel format disponible dans AEM Guides.

Formats disponibles dans AEM Guides : [Formats de sortie](../../../../user-guide/generate-output-understand-presets.md)
