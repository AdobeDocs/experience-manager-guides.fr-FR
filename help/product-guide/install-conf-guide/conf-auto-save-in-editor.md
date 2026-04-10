---
title: Configuration de l’enregistrement automatique des fichiers dans l’éditeur web
description: Découvrez comment configurer l’enregistrement automatique des fichiers dans l’éditeur web
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 1%

---

# Configuration de l’enregistrement automatique des fichiers dans l’éditeur web {#id199CC0J0M5Z}

L’une des fonctionnalités les plus courantes de l’éditeur basé sur un navigateur est la possibilité d’enregistrer les données après une période spécifique. AEM Guides Web Editor prend également en charge l’enregistrement automatique des fichiers de rubrique et de mappage à l’intervalle de temps spécifié. Lorsque cette fonctionnalité est déclenchée, la copie de travail de la rubrique ou du mappage est enregistrée. Aucune nouvelle version de la rubrique ou du mappage n&#39;est créée. Pour créer une nouvelle version, vous devez cliquer sur l’icône Enregistrer la révision dans la barre d’outils de l’éditeur web.

La fonction d’enregistrement automatique n’est pas activée par défaut et vous devez l’activer à l’aide du fichier de configuration pour Cloud Service et depuis le `configMgr` pour On-Premise .

Les onglets suivants fournissent des instructions pour activer la fonction d’enregistrement automatique dans l’éditeur web en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB Tab]

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer l’enregistrement automatique du fichier et l’intervalle de temps d’enregistrement automatique :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.autosave` | Booléen \(true/false\).<br> **Valeur par défaut** : false |
| `xmleditor.autosaveinterval` | Spécifiez l’intervalle en secondes pour déclencher la fonction d’enregistrement automatique. |

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