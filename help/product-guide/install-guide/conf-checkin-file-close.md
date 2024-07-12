---
title: Configuration d’une invite pour archiver un fichier à la fermeture
description: Découvrez comment configurer une invite pour archiver un fichier à la fermeture
exl-id: d184c97f-8405-4bcd-963d-635f17584897
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 1%

---

# Configuration d’une invite pour archiver un fichier à la fermeture {#id222HC040PE8}

Lorsque l’utilisateur tente de fermer un fichier ouvert dans l’éditeur Web à l’aide du bouton **Fermer** de l’onglet du fichier ou de l’option **Fermer** du menu Options, une boîte de dialogue s’affiche si le fichier contient des données non enregistrées ou une version non enregistrée. L’utilisateur est invité à déverrouiller le fichier s’il est verrouillé.

La case à cocher **Déverrouiller le fichier** n’est pas activée par défaut et vous devez l’activer à partir de configMgr. Effectuez les étapes suivantes pour activer l’option par défaut dans l’éditeur web :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Sélectionnez l&#39;option **Demander l&#39;archivage à la fermeture** .

1. Cliquez sur **Enregistrer**.


Lorsque cette configuration est activée, la case à cocher **Déverrouiller le fichier** est sélectionnée par défaut dans la boîte de dialogue.

Pour plus d’informations, reportez-vous à la section *Fermeture de fichier et scénarios d’enregistrement* du guide Utilisation de l’as a Cloud Service Adobe Experience Manager Guides.

**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
