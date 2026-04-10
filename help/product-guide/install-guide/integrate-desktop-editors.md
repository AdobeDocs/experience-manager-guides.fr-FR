---
title: Intégration d’éditeurs XML de bureau
description: Découvrez comment intégrer des éditeurs XML de bureau
exl-id: 268e8613-bb3b-4577-96fb-a588dabfd834
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 2%

---

# Intégration d’éditeurs XML de bureau {#id181GB01G0HS}

Il existe de nombreux éditeurs XML disponibles sur le marché, et vous pourriez en utiliser déjà un. Adobe FrameMaker est l’un des éditeurs XML les plus puissants, fourni avec le connecteur AEM. Grâce au connecteur AEM de FrameMaker, vous pouvez facilement vous connecter au référentiel AEM, extraire et archiver des fichiers et modifier des fichiers directement dans FrameMaker. Vous pouvez également configurer Experience Manager Guides pour lancer FrameMaker à partir de l’éditeur web. Une fois le fichier ouvert dans FrameMaker, vous pouvez le modifier et le archiver à nouveau dans le référentiel AEM.

## Activer l’édition de fichiers dans FrameMaker à partir de l’éditeur web

Vous pouvez utiliser FrameMaker ou tout autre éditeur DITA pour créer et mettre à jour du contenu DITA. Cependant, si votre entreprise utilise FrameMaker en tant qu&#39;éditeur DITA, vous pouvez donner à vos utilisateurs la possibilité d&#39;ouvrir des documents DITA directement dans FrameMaker à partir d&#39;AEM.

Par défaut, vos utilisateurs ne voient pas le bouton **Ouvrir dans FrameMaker** dans la barre d’outils AEM. Pour ajouter ce bouton à la barre d&#39;outils AEM, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** et cliquez dessus.
   ![](assets/open-in-fm-config.png)

1. Sélectionnez l’option **Afficher le bouton Ouvrir dans FrameMaker**.

1. Si vous utilisez la version 4.6 et la version de septembre 2022 de FrameMaker - Mise à jour 3, vous devez activer la configuration **Mise à jour 3 de FrameMaker version 2022 ou ultérieure** pour que vos utilisateurs puissent transmettre les détails du serveur Experience Manager Guides à FrameMaker. Par défaut, elle est désactivée.


1. Cliquez sur **Enregistrer**.


Lorsque vous activez l&#39;option **Afficher le bouton Ouvrir dans FrameMaker**, le bouton **Ouvrir dans FrameMaker** s&#39;affiche lors de la sélection d&#39;un fichier DITA dans le référentiel AEM. Lorsque cette option n’est *pas activée*, le bouton **Ouvrir dans FrameMaker** s’affiche uniquement lorsque vous sélectionnez un fichier .fm ou .book dans le référentiel.



