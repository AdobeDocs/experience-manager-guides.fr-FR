---
title: Configuration d’une invite pour archiver un fichier à la fermeture
description: Découvrez comment configurer une invite pour archiver un fichier à la fermeture
exl-id: 5b09ec46-aea4-4a3f-8bab-42414e31e37d
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%

---

# Configuration d’une invite pour archiver un fichier à la fermeture {#id222HC040PE8}

Lorsque l’utilisateur tente de fermer un fichier ouvert dans l’éditeur Web à l’aide du bouton **Fermer** de l’onglet du fichier ou de l’option **Fermer** du menu Options, une boîte de dialogue s’affiche si le fichier contient des données non enregistrées ou une version non enregistrée. L’utilisateur est invité à déverrouiller le fichier s’il est verrouillé.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer une invite d’archivage d’un fichier à la fermeture :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | Booléen \( true/ false\).<br> **Valeur par défaut** : false |

Lorsque cette configuration est activée, la case à cocher **Déverrouiller le fichier** est sélectionnée par défaut dans la boîte de dialogue.

Pour plus d’informations, reportez-vous à la section *Fermeture de fichier et scénarios d’enregistrement* du guide Utilisation de l’as a Cloud Service Adobe Experience Manager Guides.

**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
