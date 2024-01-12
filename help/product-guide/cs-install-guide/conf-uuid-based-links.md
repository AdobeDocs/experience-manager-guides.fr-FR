---
title: Configuration de l’affichage des liens basés sur l’UUID
description: Découvrez comment configurer l’affichage des liens basés sur UUID
exl-id: 2ae6a27f-983b-4aa0-be29-166899aeb4ff
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 1%

---

# Configuration de l’affichage des liens basés sur l’UUID {#id2035G20M0QN}

Par défaut, lorsque vous créez un lien à l’aide de l’option Insérer une référence ou Insérer un contenu réutilisé de l’éditeur web, le lien est créé à l’aide de l’UUID du contenu référencé. La variable **Lien** La propriété \(dans le panneau Propriétés\) du contenu référencé peut être configurée pour afficher le chemin d’accès relatif au fichier du contenu référencé ou l’UUID. Par défaut, l’UUID du contenu référencé s’affiche dans le panneau Propriétés.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour afficher le chemin relatif ou l’UUID du contenu référencé dans l’éditeur web :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uuid` | Booléen \(true/false\). Si vous souhaitez afficher le chemin relatif du contenu lié, définissez cette propriété sur false. <br> **Valeur par défaut**: true |

**Rubrique parente :**[ Personnalisation de l’éditeur web](conf-web-editor.md)
