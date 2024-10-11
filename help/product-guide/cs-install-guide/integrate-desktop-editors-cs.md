---
title: Intégration d’éditeurs XML de bureau
description: Découvrez comment intégrer des éditeurs XML de bureau
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
source-git-commit: b3ae1c02d3055fe15257d5de0365d30e7af21afb
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 1%

---

# Intégration d’éditeurs XML de bureau

Il y a beaucoup d&#39;éditeurs XML disponibles sur le marché, et vous pourriez déjà en utiliser un. Adobe FrameMaker est l’un des éditeurs XML les plus puissants, qui est fourni avec AEM connecteur. Grâce au connecteur d’AEM en FrameMaker, vous pouvez facilement vous connecter au référentiel AEM, extraire et archiver des fichiers et modifier des fichiers directement dans FrameMaker. Vous pouvez également configurer Experience Manager Guides pour lancer le FrameMaker à partir de l’éditeur web. Une fois le fichier ouvert dans FrameMaker, vous pouvez le modifier et le réarchiver dans le référentiel AEM.

## Activation de l’édition de fichiers dans FrameMaker à partir de l’éditeur web

Vous pouvez utiliser FrameMaker ou tout autre éditeur DITA pour créer et mettre à jour du contenu DITA. Cependant, si votre entreprise utilise FrameMaker comme éditeur DITA, vous pouvez donner à vos utilisateurs la possibilité d’ouvrir des documents DITA directement dans le FrameMaker à partir d’AEM.


Par défaut, vos utilisateurs ne voient pas le bouton **Ouvrir dans le FrameMaker** sur la barre d’outils AEM. Procédez comme suit pour ajouter ce bouton dans la barre d’outils AEM :

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour ajouter ce bouton dans la barre d’outils AEM :


| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframebuttonshow` | Booléen \(true/false\). Si vous souhaitez afficher le bouton **Ouvrir dans le FrameMaker**, définissez cette propriété sur true. <br> **Valeur par défaut** : false |



Si vous utilisez les versions 2409 et 2022 de septembre - Mise à jour 3 de FrameMaker, vous devez activer la configuration **FrameMaker Version 2022 Update 3 ou version ultérieure** pour que vos utilisateurs puissent transmettre les détails du serveur Experience Manager Guides à FrameMaker.  Par défaut, elle est désactivée.


| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframe2022above` | Booléen \(true/false\). Si vous utilisez la version de septembre 2022 de FrameMaker - Mise à jour 3 , définissez cette propriété sur true. <br> **Valeur par défaut** : false |



Lorsque vous définissez la propriété *openinframebuttonshow* sur true, le bouton **Ouvrir dans le FrameMaker** s’affiche lorsque vous sélectionnez un fichier DITA dans le référentiel AEM. Lorsque cette propriété n’est pas définie sur *true*, le bouton **Ouvrir dans le FrameMaker** s’affiche uniquement lorsque vous sélectionnez un fichier .fm ou .book dans le référentiel.



