---
title: Configurer l’option de modification dans Oxygen
description: Découvrez comment configurer l’option de modification dans le plug-in du connecteur Oxygen.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 1%

---

# Configurer l’option de modification dans Oxygen for Cloud Service

AEM Guides permet également aux utilisateurs de modifier leurs rubriques et plans DITA dans le plug-in Oxygen Connector.

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails (propriété) suivants pour configurer l’option **Modifier dans Oxygen** :



| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.editinoxygen` | Booléen \(true/false\). **Valeur par défaut** : false |

>[!NOTE]
>
> Cette configuration est désactivée par défaut et l’option n’est pas disponible dans l’éditeur web.

**Rubrique parente :**[ Personnaliser l’éditeur web](customize-overview.md)
