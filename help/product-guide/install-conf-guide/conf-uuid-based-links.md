---
title: Configurer l’affichage des liens basés sur l’UUID
description: Découvrez comment configurer l’affichage des liens basés sur l’UUID
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: d2383230-ff8f-4e9b-a529-9b9d167ebf90
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 1%
---
# Configurer l’affichage des liens basés sur l’UUID {#id2035G20M0QN}

Par défaut, lorsque vous créez un lien à l’aide de l’option Insérer une référence ou Insérer un contenu réutilisé dans l’éditeur, le lien est créé à l’aide de l’UUID du contenu référencé. La propriété **Link** \(dans le panneau Propriétés\) du contenu référencé peut être configurée pour afficher le chemin d’accès relatif au fichier du contenu référencé ou de l’UUID. Pour Cloud Service, l’UUID du contenu référencé s’affiche par défaut dans le panneau Propriétés . Pour On-Premise, cet affichage est contrôlé par l&#39;option **Activer les UUID** dans le `configMgr`. Par défaut, elle est activée, ce qui implique que l’UUID du contenu référencé s’affiche dans le panneau Propriétés .

Les onglets suivants fournissent des instructions pour afficher le chemin d’accès relatif ou l’UUID du contenu référencé dans l’éditeur en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB ]

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

**Rubrique parente :**[ Personnaliser l’éditeur](customize-overview.md)
