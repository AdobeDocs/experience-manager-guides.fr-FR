---
title: PDF
description: Generate and configure PDF output for FrameMaker documents in AEM Guides.
feature: Publishing FrameMaker Documents
role: User
hide: true
exl-id: 3a8cb163-94ac-48b1-ae6b-1309179f462a
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 3%

---

# PDF {#id205BB0T20RH}

Les options suivantes sont disponibles pour la sortie PDF :

>[!NOTE]
>
> To open output presets for PDF, click on a FrameMaker \(`.fm` or `.book`\) file, then click on Output Presets, and then click on the PDF Output option.

| Options de PDF | Description |
|-----------|-----------|
| Type de sortie | Type de sortie que vous souhaitez générer. Pour générer une sortie PDF, choisissez l’option PDF . |
| Nom du paramètre | Attribuez un nom explicite aux paramètres de sortie PDF que vous êtes en train de créer. Par exemple, vous pouvez spécifier *sortie des clients internes* ou *sortie des utilisateurs finaux*. |
| **Job Settings** |  |
| Options | Choose the PDF preset that you want to use for generating PDF output. |
| Generate Tagged PDF | Select this option to generate tagged PDFs that will contain information on document&#39;s content and structure. This information is used by the on-screen readers. |
| Generate PDF for Each File in Book | If you are generating output for a book file, select this option to generate a separate PDF for each file in the book. |
| Generate PDF for review Only | Select this option to generate PDF with commenting feature enabled. |
| Create Named Destination for all Elements and Paragraphs | Select this option to create named destinations based on elements and paragraphs. |
| **Display Settings** |  |
| Open Document on Page | Specify the page number that should be displayed on opening the PDF. |
| Initial Zoom Level | Choose the document zoom level. |
| Registration Mark | Pour imprimer un document avec des traits de coupe et des repères de montage, choisissez une option dans la liste déroulante des repères de montage. |
| Largeur et hauteur de page | Spécifiez la largeur et la hauteur de la page. |
| Plage de pages | Choisissez si vous souhaitez publier toutes les pages de la liasse ou une plage de pages. Si vous choisissez Plage, vous devez spécifier la plage de pages De et À. |
| Convertir CYMK en RGB | Sélectionnez cette option pour convertir les couleurs CYMK en RGB dans le PDF généré. |
| Générer des signets PDF | Créez un PDF accessible contenant des signets. |
| Chemin de destination | Chemin d’accès dans votre référentiel AEM où est stockée la sortie PDF. |
| Exécuter le workflow de post-génération | Lorsque vous sélectionnez cette option, une nouvelle liste déroulante Workflow de post-génération s’affiche, contenant tous les workflows configurés dans AEM. Vous devez sélectionner un workflow à exécuter une fois le workflow de génération de sortie terminé. |

**Rubrique parente :**[ générer la sortie des documents FrameMaker](fm-output-generatation.md)
