---
title: Définir l’éditeur de mappage avancé par défaut
description: Découvrez comment définir l’éditeur de carte avancé par défaut
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 0%

---

# Définir l’éditeur de mappage avancé par défaut {#id181AI0003PN}

>[!NOTE]
>
> L’éditeur de carte de base, auparavant disponible dans Experience Manager Guides, est obsolète à partir des versions 4.3 et 2307. Vous ne pouvez pas accéder à l&#39;éditeur de mappages de base pour créer et gérer des mappages DITA.
>Il est recommandé d’utiliser l’éditeur de carte avancé. L’éditeur de carte avancé offre des fonctionnalités améliorées et de meilleures options de personnalisation. Découvrez comment utiliser l’[éditeur de cartes avancé](../user-guide/map-editor-advanced-map-editor.md).

Pour les versions antérieures aux versions 4.3 et 2307, Experience Manager Guides est fourni avec un éditeur de carte de base et un éditeur de carte avancé. Basic Map Editor vous offre toutes les fonctionnalités nécessaires pour créer votre fichier de carte. L’éditeur de carte avancé est beaucoup plus riche en fonctionnalités et il est intégré à l’éditeur web. L&#39;éditeur de carte avancé permet aux auteurs de créer et de modifier des fichiers de carte DITA avec une interface conviviale.

Par défaut, chaque fois qu’un nouveau fichier de mappage est créé, il est ouvert dans l’éditeur de mappage de base. Vous pouvez modifier ce comportement en activant le paramètre pour ouvrir l’éditeur de carte avancé par défaut.

Les onglets suivants fournissent des instructions pour faire de l’Éditeur de mappage avancé l’éditeur par défaut pour les fichiers de mappage en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.


>[!BEGINTABS]

>[!TAB ]

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(property\) suivants pour activer l’éditeur de carte de base :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | ``fmdita.hide.oldmapeditor`` | Booléen \(true/false\). Si vous souhaitez utiliser l’éditeur de mappages avancé par défaut, définissez cette propriété sur true.<br> **Valeur par défaut** : false |

>[!NOTE]
>
> Par défaut, lorsqu’un auteur crée un fichier de mappage et choisit de l’ouvrir pour le modifier, l’éditeur de mappage de base est lancé. Lorsque l’option Modifier est sélectionnée pour un fichier de mappage dans l’interface utilisateur d’Assets, elle est également ouverte dans l’éditeur de mappage de base.

>[!TAB  On-Premise ]

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** et cliquez dessus.

1. Sélectionnez l’option **Masquer l’éditeur de carte de base**.

   Lorsque cette option est sélectionnée, le lien Éditeur de carte de base n’apparaît nulle part dans l’interface utilisateur. Par défaut, les fichiers de mappage s’ouvrent dans l’Éditeur de mappage avancé.

>[!ENDTABS]

**Rubrique parente :**[ Personnaliser l’éditeur web](customize-overview.md)
