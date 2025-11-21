---
title: Configuration de l’enregistrement automatique des fichiers dans l’éditeur web
description: Découvrez comment configurer l’enregistrement automatique des fichiers dans l’éditeur web
exl-id: 4d99c3d8-cf6a-4cf3-aaec-9009a0376c1e
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 1%

---

# Configuration de l’enregistrement automatique des fichiers dans l’éditeur web {#id199CC0J0M5Z}

L’une des fonctionnalités les plus courantes de l’éditeur basé sur un navigateur est la possibilité d’enregistrer les données après une période spécifique. AEM Guides Web Editor prend également en charge l’enregistrement automatique des fichiers de rubrique et de mappage à l’intervalle de temps spécifié. Lorsque cette fonctionnalité est déclenchée, la copie de travail de la rubrique ou du mappage est enregistrée. Aucune nouvelle version de la rubrique ou du mappage n&#39;est créée. Pour créer une nouvelle version, vous devez cliquer sur l’icône Enregistrer la révision dans la barre d’outils de l’éditeur web.

La fonction d’enregistrement automatique n’est pas activée par défaut et vous devez l’activer à l’aide du fichier de configuration.

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer l’enregistrement automatique du fichier et l’intervalle de temps d’enregistrement automatique :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.autosave` | Booléen \(true/false\).<br> **Valeur par défaut** : false |
| `xmleditor.autosaveinterval` | Spécifiez l’intervalle en secondes pour déclencher la fonction d’enregistrement automatique. |  |

**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
