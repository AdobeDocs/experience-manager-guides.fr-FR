---
title: Intégration d’éditeurs XML de bureau
description: Découvrez comment intégrer des éditeurs XML de bureau
exl-id: 268e8613-bb3b-4577-96fb-a588dabfd834
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
source-git-commit: 434d7efd24147af23b4c65aeebf4c144ce3adda7
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 2%

---

# Intégration d’éditeurs XML de bureau {#id181GB01G0HS}

Il y a beaucoup d&#39;éditeurs XML disponibles sur le marché, et vous pourriez déjà en utiliser un. Adobe FrameMaker est l’un des éditeurs XML les plus puissants, qui est fourni avec AEM connecteur. Grâce au connecteur d’AEM en FrameMaker, vous pouvez facilement vous connecter au référentiel AEM, extraire et archiver des fichiers et modifier des fichiers directement dans FrameMaker. Vous pouvez également configurer Experience Manager Guides pour lancer le FrameMaker à partir de l’éditeur web. Une fois le fichier ouvert dans FrameMaker, vous pouvez le modifier et le réarchiver dans le référentiel AEM.

## Activation de l’édition de fichiers dans FrameMaker à partir de l’éditeur web

Vous pouvez utiliser FrameMaker ou tout autre éditeur DITA pour créer et mettre à jour du contenu DITA. Cependant, si votre entreprise utilise FrameMaker comme éditeur DITA, vous pouvez donner à vos utilisateurs la possibilité d’ouvrir des documents DITA directement dans le FrameMaker à partir d’AEM.

Par défaut, vos utilisateurs ne voient pas le bouton **Ouvrir dans le FrameMaker** sur la barre d’outils AEM. Procédez comme suit pour ajouter ce bouton dans la barre d’outils AEM :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.
   ![](assets/open-in-fm-config.png)

1. Sélectionnez l’option **Afficher l’ouverture dans le bouton de FrameMaker** .

1. Si vous utilisez la version 4.6 et la version de septembre 2022 de FrameMaker - Mise à jour 3, vous devez activer la configuration **FrameMaker Version 2022 Update 3 ou ultérieure** pour que vos utilisateurs puissent transmettre les détails du serveur Experience Manager Guides à FrameMaker. Par défaut, elle est désactivée.


1. Cliquez sur **Enregistrer**.


Lorsque vous activez l’option **Afficher le bouton Ouvrir dans le FrameMaker**, le bouton **Ouvrir dans le FrameMaker** s’affiche lorsque vous sélectionnez un fichier DITA dans le référentiel AEM. Lorsque cette option est *non activée*, le bouton **Ouvrir dans le FrameMaker** s’affiche uniquement lorsque vous sélectionnez un fichier .fm ou .book dans le référentiel.



