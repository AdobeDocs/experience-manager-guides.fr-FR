---
title: Configuration d’une invite pour archiver un fichier à la fermeture
description: Découvrez comment configurer une invite pour archiver un fichier à la fermeture
exl-id: 5b09ec46-aea4-4a3f-8bab-42414e31e37d
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%

---

# Configuration d’une invite pour archiver un fichier à la fermeture {#id222HC040PE8}

Lorsque l’utilisateur tente de fermer un fichier ouvert dans l’éditeur Web à l’aide de la fonction **Fermer** dans l’onglet du fichier ou dans la fonction **Fermer** dans le menu Options, une boîte de dialogue s’affiche si le fichier contient des données non enregistrées ou une version non enregistrée. L’utilisateur est invité à déverrouiller le fichier s’il est verrouillé.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer une invite d’archivage d’un fichier à la fermeture :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | Booléen \( true/ false\).<br> **Valeur par défaut**: false |

Lorsque cette configuration est activée, la variable **Déverrouiller le fichier** est sélectionnée par défaut dans la boîte de dialogue.

Pour plus d’informations, voir *Fermeture du fichier et enregistrement des scénarios* dans le guide as a Cloud Service Utilisation des guides Adobe Experience Manager .

**Rubrique parente :**[ Personnalisation de l’éditeur web](conf-web-editor.md)
