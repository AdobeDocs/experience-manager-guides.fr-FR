---
title: Utiliser Markdown dans DITA AEM Guides
description: Migrer et utiliser Markdown dans DITA AEM Guides
author: Pulkit Nagpal(punagpal)
exl-id: a94c0129-df40-4b61-ac60-679b2ffe7e86
TQID: https://experienceleague.adobe.com/z41KjrBkAeDaH-iKXOFLH44qOQElziip1FqcRhnKaUI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 281
ht-degree: 0%

---

# Utiliser Markdown dans AEM Guides

## Options disponibles

Il existe deux options pour utiliser les fichiers Markdown dans AEM Guides :

- Option 1 : importez les markdown existants dans AEM Guides et utilisez-les directement dans ditamap pour la publication

- Option 2 : convertir les fichiers Markdown existants en DITA

Parlons de chaque option :

### Option 1 : importer le markdown existant dans AEM Guides et l’utiliser directement dans ditamap pour la publication

Sa configuration est simplifiée et sa mise en œuvre plus rapide. Cependant, l’utilisation limitée des fonctionnalités d’AEM Guides, telles que la réutilisation du contenu,

L’utilisateur ou l’utilisatrice doit ajouter des `format="markdown" ` ou des `format="mdita"` d’attributs afin que les moteurs de publication comprennent le type de fichier et publient en conséquence.

Exemple de fichier : [Markdown Ditamap] (:aaid:sc:AP:da31137e-be84-44fb-8974-d038eeff0283)

![capture d’écran pour référence](../../assets/authoring/markdown_map.png)


#### Publication sur PDF et sortie web

AEM Guides offre à la fois l’option Web (Html5/AEM Site) et PDF (Native-PDF/DITA-OT) pour publier un ditamap avec du contenu Markdown

### Option 2 : convertir Markdown en format DITA

Utilisation complète des fonctionnalités d’AEM Guides qui permettent la réutilisation du contenu, le traitement conditionnel, la traduction, la ligne de base, etc. Cependant, des efforts initiaux seraient nécessaires pour convertir le `.md` au format `.dita`.

Markdown peut être converti en DITA à l’aide d’outils externes tels qu’Adobe FrameMaker et DITA-OT.


Pour Adobe FrameMaker, voir : [Import Markdown](https://www.adobe.com/in/products/framemaker/features.html#import-markdown)

Pour DITA-OT, reportez-vous à : [Markdown comme entrée](https://www.dita-ot.org/dev/topics/markdown-input.html)

Exemple de fichier converti à l’aide d’Adobe FrameMaker : [exemple Markdown vers DITA] (:aaid:sc:AP:874881f3-ba43-410c-abc6-2df899536d79)

#### Publication sur PDF et sortie web

Une fois les fichiers Markdown convertis en DITA, l’utilisateur peut publier facilement la sortie dans n’importe quel format disponible dans AEM Guides.

Formats disponibles dans AEM Guides : [formats de sortie](../../../../user-guide/generate-output-understand-presets.md)
