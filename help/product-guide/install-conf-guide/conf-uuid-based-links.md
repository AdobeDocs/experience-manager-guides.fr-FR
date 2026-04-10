---
title: Configurer l’affichage des liens basés sur l’UUID
description: Découvrez comment configurer l’affichage des liens basés sur l’UUID
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 1%

---

# Configurer l’affichage des liens basés sur l’UUID {#id2035G20M0QN}

Par défaut, lorsque vous créez un lien à l’aide de l’option Insérer une référence ou Insérer un contenu réutilisé dans l’éditeur, le lien est créé à l’aide de l’UUID du contenu référencé. La propriété **Link** \(dans le panneau Propriétés\) du contenu référencé peut être configurée pour afficher le chemin d’accès relatif au fichier du contenu référencé ou de l’UUID. Pour Cloud Service, l’UUID du contenu référencé s’affiche par défaut dans le panneau Propriétés . Pour On-Premise, cet affichage est contrôlé par l&#39;option **Activer les UUID** dans le `configMgr`. Par défaut, elle est activée, ce qui implique que l’UUID du contenu référencé s’affiche dans le panneau Propriétés .

Les onglets suivants fournissent des instructions pour afficher le chemin d’accès relatif ou l’UUID du contenu référencé dans l’éditeur en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB Tab]

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(property\) suivants pour afficher le chemin d’accès relatif ou l’UUID du contenu référencé dans l’éditeur.

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uuid` | Booléen \(true/false\). Si vous souhaitez afficher le chemin d’accès relatif du contenu lié, définissez cette propriété sur false. <br> **Valeur par défaut** : true |


>[!TAB  On-Premise ]

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** et cliquez dessus.

1. Dans les paramètres *XmlEditorConfig*, l&#39;option **Activer les UUIDs** est activée par défaut. Cela signifie que l’UUID du contenu référencé s’affiche dans la propriété **Link** du panneau Propriétés.

   Si vous souhaitez afficher le chemin d’accès relatif du contenu lié, désélectionnez l’option **Activer les UUID**.

1. Cliquez sur **Enregistrer**.

>[!ENDTABS]

**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur web](customize-overview.md)
