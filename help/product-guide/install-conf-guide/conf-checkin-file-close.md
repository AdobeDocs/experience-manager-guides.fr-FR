---
title: Configurer l'invite pour archiver un fichier à la fermeture
description: Découvrez comment Configurer une invite pour archiver un fichier à la fermeture
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 6b1b5894-0d55-4230-83cf-6b219e969116
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Configurer l&#39;invite pour archiver un fichier à la fermeture {#id222HC040PE8}

Lorsque l’utilisateur tente de fermer un fichier ouvert dans l’éditeur à l’aide du bouton **Fermer** de l’onglet du fichier ou de l’option **Fermer** du menu Options, une boîte de dialogue s’affiche si le fichier contient des données non enregistrées ou une version non enregistrée. L’utilisateur est invité à déverrouiller le fichier s’il est verrouillé.

Les onglets suivants fournissent des instructions pour configurer l’option inviter à archiver un fichier à la fermeture par défaut dans l’éditeur en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB Tab]

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les informations \(property\) suivantes pour configurer une invite afin d’archiver un fichier à la fermeture :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | Boolean \( true/ false\).<br> **Valeur par défaut** : false |

Lorsque cette configuration est activée, la case **Déverrouiller le fichier** est cochée par défaut dans la boîte de dialogue.

Pour plus d’informations, voir la section *Scénarios de fermeture et d’enregistrement de fichier* dans le guide Utilisation d’Adobe Experience Manager Guides as a Cloud Service .

>[!TAB  On-Premise ]

>[!NOTE]
>
>La case **Déverrouiller le fichier** n’est pas cochée par défaut et vous devez l’activer à partir de configMgr. Effectuez les étapes suivantes pour activer l’option par défaut dans l’éditeur :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** et cliquez dessus.

1. Sélectionnez l’option **Demander l’enregistrement à la fermeture**.

1. Cliquez sur **Enregistrer**.


Lorsque cette configuration est activée, la case **Déverrouiller le fichier** est cochée par défaut dans la boîte de dialogue.

Pour plus d’informations, voir la section *Scénarios de fermeture et d’enregistrement de fichier* dans le guide Utilisation d’Adobe Experience Manager Guides as a Cloud Service .

>[!ENDTABS]

**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur](customize-overview.md)
