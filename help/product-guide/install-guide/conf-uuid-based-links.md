---
title: Configuration de l’affichage des liens basés sur l’UUID
description: Découvrez comment configurer l’affichage des liens basés sur UUID
exl-id: ab1b0ecf-cb50-4fcd-b36e-d16a8c396054
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Configuration de l’affichage des liens basés sur l’UUID {#id2035G20M0QN}

Par défaut, lorsque vous créez un lien à l’aide de l’option Insérer une référence ou Insérer un contenu réutilisé de l’éditeur web, le lien est créé à l’aide de l’UUID du contenu référencé. La variable **Lien** La propriété \(dans le panneau Propriétés\) du contenu référencé peut être configurée pour afficher le chemin d’accès relatif au fichier du contenu référencé ou l’UUID. Cet affichage est contrôlé par la fonction **Activation des UUID** dans configMgr. Par défaut, elle est activée, ce qui signifie que l’UUID du contenu référencé est affiché dans le panneau Propriétés.

Effectuez les étapes suivantes pour afficher le chemin relatif ou l’UUID du contenu référencé dans l’éditeur web :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le bouton **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** du lot.

1. Dans le *XmlEditorConfig* les paramètres, **Activation des UUID** est activée par défaut. Cela signifie que l’UUID du contenu référencé s’affiche dans la variable **Lien** dans le panneau Propriétés.

   Si vous souhaitez afficher le chemin relatif du contenu lié, désélectionnez la **Activation des UUID** .

1. Cliquez sur **Enregistrer**.


**Rubrique parente :**[ Personnalisation de l’éditeur web](conf-web-editor.md)
