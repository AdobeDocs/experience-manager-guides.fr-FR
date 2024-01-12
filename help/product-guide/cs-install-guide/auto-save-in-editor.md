---
title: Configuration de l’enregistrement automatique du fichier dans l’éditeur web
description: Découvrez comment configurer l’enregistrement automatique du fichier dans l’éditeur web
exl-id: 4d99c3d8-cf6a-4cf3-aaec-9009a0376c1e
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 1%

---

# Configuration de l’enregistrement automatique du fichier dans l’éditeur web {#id199CC0J0M5Z}

L’une des fonctionnalités les plus courantes de l’éditeur basé sur un navigateur est la possibilité d’enregistrer les données après une période spécifique. L’éditeur web de Guides d’AEM prend également en charge l’enregistrement automatique des fichiers de rubrique et de mappage dans l’intervalle de temps spécifié. Lorsque cette fonction est déclenchée, la copie de travail de la rubrique ou du mappage est enregistrée. Une nouvelle version de la rubrique ou du mappage n’est pas créée. Pour créer une version, vous devez cliquer sur l’icône Enregistrer la révision dans la barre d’outils de l’éditeur web.

La fonction d’enregistrement automatique n’est pas activée par défaut et vous devez l’activer à l’aide du fichier de configuration.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer l’enregistrement automatique du fichier et l’intervalle d’enregistrement automatique :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.autosave` | Booléen \(true/false\).<br> **Valeur par défaut**: false |
| `xmleditor.autosaveinterval` | Spécifiez l’intervalle en secondes pour déclencher la fonction d’enregistrement automatique. |

**Rubrique parente :**[ Personnalisation de l’éditeur web](conf-web-editor.md)
