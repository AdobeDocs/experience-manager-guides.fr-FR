---
title: Configurer l’option de modification dans Oxygen
description: Découvrez comment configurer l’option de modification dans le plug-in du connecteur Oxygen.
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 41ecbbb2-81c3-473d-b48b-7370a74a6474
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '104'
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
> Cette configuration est désactivée par défaut et l’option n’est pas disponible dans l’éditeur.

**Rubrique parente :**[ Personnaliser l’éditeur](customize-overview.md)
