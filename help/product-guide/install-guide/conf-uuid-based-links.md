---
title: Configurer l’affichage des liens basés sur l’UUID
description: Découvrez comment configurer l’affichage des liens basés sur l’UUID
exl-id: ab1b0ecf-cb50-4fcd-b36e-d16a8c396054
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/QlYbIRVwAM10wfcu-Fz3CzOkCCUDZHbVzZo3xCxT3wI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 211
ht-degree: 0%

---

# Configurer l’affichage des liens basés sur l’UUID {#id2035G20M0QN}

Par défaut, lorsque vous créez un lien à l’aide de l’option Insérer une référence ou Insérer un contenu réutilisé dans l’éditeur web, le lien est créé à l’aide de l’UUID du contenu référencé. La propriété **Link** \(dans le panneau Propriétés\) du contenu référencé peut être configurée pour afficher le chemin d’accès relatif au fichier du contenu référencé ou de l’UUID. Cet affichage est contrôlé par l’option **Activer les UUIDs** dans configMgr. Par défaut, elle est activée, ce qui implique que l’UUID du contenu référencé s’affiche dans le panneau Propriétés .

Effectuez les étapes suivantes pour afficher le chemin d’accès relatif ou l’UUID du contenu référencé dans l’éditeur web :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** et cliquez dessus.

1. Dans les paramètres *XmlEditorConfig*, l&#39;option **Activer les UUIDs** est activée par défaut. Cela signifie que l’UUID du contenu référencé s’affiche dans la propriété **Link** du panneau Propriétés.

   Si vous souhaitez afficher le chemin d’accès relatif du contenu lié, désélectionnez l’option **Activer les UUID**.

1. Cliquez sur **Enregistrer**.


**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur web](conf-web-editor.md)
