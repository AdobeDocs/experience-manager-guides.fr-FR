---
title: Configuration de l’affichage des liens basés sur l’UUID
description: Découvrez comment configurer l’affichage des liens basés sur UUID
exl-id: ab1b0ecf-cb50-4fcd-b36e-d16a8c396054
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Configuration de l’affichage des liens basés sur l’UUID {#id2035G20M0QN}

Par défaut, lorsque vous créez un lien à l’aide de l’option Insérer une référence ou Insérer un contenu réutilisé de l’éditeur web, le lien est créé à l’aide de l’UUID du contenu référencé. La propriété **Lien** \(dans le panneau Propriétés\) du contenu référencé peut être configurée pour afficher le chemin d’accès relatif au fichier du contenu référencé ou l’UUID. Cet affichage est contrôlé par l’option **Activer les UUIDs** dans configMgr. Par défaut, elle est activée, ce qui signifie que l’UUID du contenu référencé est affiché dans le panneau Propriétés.

Effectuez les étapes suivantes pour afficher le chemin relatif ou l’UUID du contenu référencé dans l’éditeur web :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Dans les paramètres *XmlEditorConfig*, l’option **Activer les UUIDs** est activée par défaut. Cela signifie que l’UUID du contenu référencé est affiché dans la propriété **Lien** du panneau Propriétés.

   Si vous souhaitez afficher le chemin relatif du contenu lié, désélectionnez l’option **Activer les UUIDs** .

1. Cliquez sur **Enregistrer**.


**Rubrique parente :**&#x200B;[ Personnaliser l’éditeur web](conf-web-editor.md)
