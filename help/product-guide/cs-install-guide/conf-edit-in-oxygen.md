---
title: Configurer l’option de modification dans Oxygen
description: Découvrez comment configurer l’option de modification dans le plug-in du connecteur Oxygen.
exl-id: 96081a6d-39cf-4697-8b43-6494543ea187
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/cBWLIunbSxmmPxc5JTFc7z45xhLwWo7EEQj8zR-DpaY
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 103
ht-degree: 1%

---

# Configurer l’option de modification dans Oxygen

AEM Guides permet également aux utilisateurs de modifier leurs rubriques et plans DITA dans le plug-in Oxygen Connector.

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails (propriété) suivants pour configurer l’option **Modifier dans Oxygen** :



| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.editinoxygen` | Booléen \(true/false\). **Valeur par défaut** : false |

>[!NOTE]
>
> Cette configuration est désactivée par défaut et l’option n’est pas disponible dans l’éditeur web.

**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur web](conf-web-editor.md)
