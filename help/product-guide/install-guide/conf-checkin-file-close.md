---
title: Configuration d’une invite pour archiver un fichier à la fermeture
description: Découvrez comment configurer une invite pour archiver un fichier à la fermeture
exl-id: d184c97f-8405-4bcd-963d-635f17584897
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 1%

---

# Configuration d’une invite pour archiver un fichier à la fermeture {#id222HC040PE8}

Lorsque l’utilisateur tente de fermer un fichier ouvert dans l’éditeur Web à l’aide de la fonction **Fermer** dans l’onglet du fichier ou dans la fonction **Fermer** dans le menu Options, une boîte de dialogue s’affiche si le fichier contient des données non enregistrées ou une version non enregistrée. L’utilisateur est invité à déverrouiller le fichier s’il est verrouillé.

La variable **Déverrouiller le fichier** n’est pas activée par défaut et vous devez l’activer à partir de configMgr. Effectuez les étapes suivantes pour activer l’option par défaut dans l’éditeur web :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le bouton **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** du lot.

1. Sélectionnez la variable **Demander l’archivage à la fermeture** .

1. Cliquez sur **Enregistrer**.


Lorsque cette configuration est activée, la variable **Déverrouiller le fichier** est sélectionnée par défaut dans la boîte de dialogue.

Pour plus d’informations, voir *Fermeture du fichier et enregistrement des scénarios* dans le guide as a Cloud Service Utilisation des guides Adobe Experience Manager .

**Rubrique parente :**[ Personnalisation de l’éditeur web](conf-web-editor.md)
