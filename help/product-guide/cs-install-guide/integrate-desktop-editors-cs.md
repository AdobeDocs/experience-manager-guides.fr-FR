---
title: Intégration d’éditeurs XML de bureau
description: Découvrez comment intégrer des éditeurs XML de bureau
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
exl-id: 86ba53fa-0e08-4791-9018-09fe974691da
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 1%

---

# Intégration d’éditeurs XML de bureau

Il existe de nombreux éditeurs XML disponibles sur le marché, et vous pourriez en utiliser déjà un. Adobe FrameMaker est l’un des éditeurs XML les plus puissants, fourni avec le connecteur AEM. Grâce au connecteur AEM de FrameMaker, vous pouvez facilement vous connecter au référentiel AEM, extraire et archiver des fichiers et modifier des fichiers directement dans FrameMaker. Vous pouvez également configurer Experience Manager Guides pour lancer FrameMaker à partir de l’éditeur web. Une fois le fichier ouvert dans FrameMaker, vous pouvez le modifier et le archiver à nouveau dans le référentiel AEM.

## Activer l’édition de fichiers dans FrameMaker à partir de l’éditeur web

Vous pouvez utiliser FrameMaker ou tout autre éditeur DITA pour créer et mettre à jour du contenu DITA. Cependant, si votre entreprise utilise FrameMaker en tant qu&#39;éditeur DITA, vous pouvez donner à vos utilisateurs la possibilité d&#39;ouvrir des documents DITA directement dans FrameMaker à partir d&#39;AEM.


Par défaut, vos utilisateurs ne voient pas le bouton **Ouvrir dans FrameMaker** dans la barre d’outils AEM. Pour ajouter ce bouton à la barre d&#39;outils AEM, procédez comme suit :

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(property\) suivants pour ajouter ce bouton à la barre d’outils d’AEM :


| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframebuttonshow` | Booléen \(true/false\). Si vous souhaitez afficher le bouton **Ouvrir dans FrameMaker**, définissez cette propriété sur true. <br> **Valeur par défaut** : false |



Si vous utilisez la version 2409 et la version de septembre 2022 de FrameMaker - Mise à jour 3, vous devez activer la configuration **Mise à jour 3 de FrameMaker version 2022 ou ultérieure** pour que vos utilisateurs puissent transmettre les détails du serveur Experience Manager Guides à FrameMaker.  Par défaut, il est désactivé.


| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframe2022above` | Booléen \(true/false\). Si vous utilisez la version de septembre 2022 de FrameMaker - Mise à jour 3 , définissez cette propriété sur true. <br> **Valeur par défaut** : false |



Lorsque vous définissez la propriété *openinframebuttonshow* sur true, le bouton **Ouvrir dans FrameMaker** s&#39;affiche lors de la sélection d&#39;un fichier DITA dans le référentiel AEM. Lorsque cette propriété n’est pas définie sur *true*, le bouton **Ouvrir dans FrameMaker** s’affiche uniquement lorsque vous sélectionnez un fichier .fm ou un fichier .book dans le référentiel.
