---
title: Configurer l’affichage des liens basés sur l’UUID
description: Découvrez comment configurer l’affichage des liens basés sur l’UUID
exl-id: 2ae6a27f-983b-4aa0-be29-166899aeb4ff
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 1%

---

# Configurer l’affichage des liens basés sur l’UUID {#id2035G20M0QN}

Par défaut, lorsque vous créez un lien à l’aide de l’option Insérer une référence ou Insérer un contenu réutilisé dans l’éditeur web, le lien est créé à l’aide de l’UUID du contenu référencé. La propriété **Link** \(dans le panneau Propriétés\) du contenu référencé peut être configurée pour afficher le chemin d’accès relatif au fichier du contenu référencé ou de l’UUID. Par défaut, l’UUID du contenu référencé s’affiche dans le panneau Propriétés .

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(property\) suivants pour afficher le chemin d’accès relatif ou l’UUID du contenu référencé dans l’éditeur web :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uuid` | Booléen \(true/false\). Si vous souhaitez afficher le chemin d’accès relatif du contenu lié, définissez cette propriété sur false. <br> **Valeur par défaut** : true |

**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
