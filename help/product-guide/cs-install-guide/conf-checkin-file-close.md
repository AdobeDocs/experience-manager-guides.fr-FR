---
title: Configurer l'invite pour archiver un fichier à la fermeture
description: Découvrez comment Configurer une invite pour archiver un fichier à la fermeture
exl-id: 5b09ec46-aea4-4a3f-8bab-42414e31e37d
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: ccaf2ead1a9a24ab822298c6b9ef6866a1c32e8c
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 1%

---

# Configurer l&#39;invite pour archiver un fichier à la fermeture {#id222HC040PE8}

Lorsque l’utilisateur tente de fermer un fichier ouvert dans l’éditeur web à l’aide du bouton **Fermer** de l’onglet du fichier ou de l’option **Fermer** du menu Options, une boîte de dialogue s’affiche si le fichier contient des données non enregistrées ou une version non enregistrée. L’utilisateur est invité à déverrouiller le fichier s’il est verrouillé.

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les informations \(property\) suivantes pour configurer une invite afin d’archiver un fichier à la fermeture :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | Boolean \( true/ false\).<br> **Valeur par défaut** : false |

Lorsque cette configuration est activée, la case **Déverrouiller le fichier** est cochée par défaut dans la boîte de dialogue.

Pour plus d’informations, voir la section *Scénarios de fermeture et d’enregistrement de fichier* dans le guide Utilisation d’Adobe Experience Manager Guides as a Cloud Service .

**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
