---
title: Configuration de l’option à modifier dans Oxygen
description: Découvrez comment configurer l’option à modifier dans le module externe du connecteur Oxygen.
exl-id: 96081a6d-39cf-4697-8b43-6494543ea187
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 1%

---

# Configuration de l’option à modifier dans Oxygen

AEM Guides permet également aux utilisateurs de modifier leurs rubriques DITA et les mappages DITA dans le module externe connecteur Oxygen.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails (propriété) suivants pour configurer la variable **Modifier dans Oxygen** option :



| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.editinoxygen` | Booléen \(true/false\). **Valeur par défaut**: false |

>[!NOTE]
>
> Cette configuration est désactivée par défaut et l’option n’est pas disponible dans l’éditeur web.

**Rubrique parente :**[ Personnalisation de l’éditeur web](conf-web-editor.md)
