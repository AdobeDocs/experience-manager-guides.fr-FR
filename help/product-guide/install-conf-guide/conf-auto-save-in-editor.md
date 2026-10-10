---
title: Configuration de l’enregistrement automatique des fichiers dans l’éditeur
description: Découvrez comment configurer l’enregistrement automatique des fichiers dans l’éditeur
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 142a588a-3d26-48ee-a3fe-23882922243c
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
source-wordcount: '275'
ht-degree: 1%
---
# Configuration de l’enregistrement automatique des fichiers dans l’éditeur {#id199CC0J0M5Z}

L’une des fonctionnalités les plus courantes de l’éditeur basé sur un navigateur est la possibilité d’enregistrer les données après une période spécifique. L’éditeur AEM Guides prend également en charge l’enregistrement automatique des fichiers de rubrique et de mappage à l’intervalle de temps spécifié. Lorsque cette fonctionnalité est déclenchée, la copie de travail de la rubrique ou du mappage est enregistrée. Aucune nouvelle version de la rubrique ou du mappage n&#39;est créée. Pour créer une nouvelle version, vous devez cliquer sur l’icône Enregistrer la révision dans la barre d’outils de l’éditeur.

La fonction d’enregistrement automatique n’est pas activée par défaut et vous devez l’activer à l’aide du fichier de configuration pour Cloud Service et depuis le `configMgr` pour On-Premise .

Les onglets suivants fournissent des instructions pour activer la fonction d’enregistrement automatique dans l’éditeur en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB ]

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer l’enregistrement automatique du fichier et l’intervalle de temps d’enregistrement automatique :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.autosave` | Booléen \(true/false\).<br> **Valeur par défaut** : false |
| `xmleditor.autosaveinterval` | Spécifiez l’intervalle en secondes pour déclencher la fonction d’enregistrement automatique. |  |

>[!TAB  On-Premise ]

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** et cliquez dessus.

1. Dans les paramètres *XmlEditorConfig*, sélectionnez l’option **Enregistrement automatique**.

1. Dans le champ **Intervalle d’enregistrement automatique**, spécifiez l’intervalle de temps en secondes pour déclencher la fonction d’enregistrement automatique.

1. Cliquez sur **Enregistrer**.

>[!ENDTABS]
