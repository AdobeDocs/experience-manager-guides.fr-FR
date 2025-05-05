---
title: Définir l’éditeur de mappage avancé comme valeur par défaut
description: Découvrez comment définir l’éditeur de mappage avancé comme valeur par défaut
exl-id: 365264ab-f990-42c1-ab79-61a40ecea42f
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 126cecdaa481b9da1add4ba3664c26c2bc5da068
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# Définir l’éditeur de mappage avancé comme valeur par défaut {#id181AI0003PN}

>[!NOTE]
>
> L’éditeur de cartes de base, auparavant disponible dans Experience Manager Guides, a été abandonné à partir des versions 4.3 et 2307. Vous ne pouvez pas accéder à l’éditeur de cartes de base pour créer et gérer des mappages DITA.
>Il est recommandé d’utiliser l’éditeur de mappage avancé. L’éditeur de carte avancé offre des fonctionnalités améliorées et de meilleures options de personnalisation. Découvrez comment travailler avec l’ [éditeur de carte avancé](../user-guide/map-editor-advanced-map-editor.md).

Pour les versions antérieures aux versions 4.3 et 2307, Experience Manager Guides est fourni avec un éditeur de carte de base et un éditeur de carte avancé. L’éditeur de carte de base vous offre toutes les fonctionnalités nécessaires pour créer votre fichier de carte. L’éditeur de cartes avancé est bien plus riche en fonctionnalités et intégré à l’éditeur web. L’éditeur de mappage avancé permet aux auteurs de créer et de modifier des fichiers de mappage DITA avec une interface conviviale.

Par défaut, chaque fois qu’un nouveau fichier de mappage est créé, il est ouvert dans l’éditeur de mappage de base. Vous pouvez modifier ce comportement en activant le paramètre pour ouvrir l’éditeur de mappage avancé par défaut.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour activer l’éditeur de carte de base :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | ``fmdita.hide.oldmapeditor`` | Booléen \(true/false\). Si vous souhaitez utiliser l’éditeur de mappage avancé par défaut, définissez cette propriété sur true.<br> **Valeur par défaut** : false |

>[!NOTE]
>
> Par défaut, lorsqu’un auteur crée un fichier de mappage et choisit de l’ouvrir pour le modifier, l’éditeur de mappage de base est lancé. Lorsque l’option Modifier est sélectionnée pour un fichier de mappage dans l’interface utilisateur d’Assets, elle est également ouverte dans l’éditeur de mappage de base.

**Rubrique parente :**&#x200B;[ Personnaliser l’éditeur web](conf-web-editor.md)
