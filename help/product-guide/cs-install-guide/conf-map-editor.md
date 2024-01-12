---
title: Définir l’éditeur de mappage avancé comme valeur par défaut
description: Découvrez comment définir l’éditeur de mappage avancé comme valeur par défaut
exl-id: 365264ab-f990-42c1-ab79-61a40ecea42f
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# Définir l’éditeur de mappage avancé comme valeur par défaut {#id181AI0003PN}

AEM Guides est fourni avec un éditeur de cartes de base et un éditeur de cartes avancé. L’éditeur de carte de base vous offre toutes les fonctionnalités nécessaires pour créer votre fichier de carte. L’éditeur de cartes avancé est bien plus riche en fonctionnalités et intégré à l’éditeur web. L’éditeur de mappage avancé permet aux auteurs de créer et de modifier des fichiers de mappage DITA avec une interface conviviale.

Par défaut, chaque fois qu’un nouveau fichier de mappage est créé, il est ouvert dans l’éditeur de mappage de base. Vous pouvez modifier ce comportement en activant le paramètre pour ouvrir l’éditeur de mappage avancé par défaut.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour activer l’éditeur de carte de base :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | ``fmdita.hide.oldmapeditor`` | Booléen \(true/false\). Si vous souhaitez utiliser l’éditeur de mappage avancé par défaut, définissez cette propriété sur true.<br> **Valeur par défaut**: false |

>[!NOTE]
>
> Par défaut, lorsqu’un auteur crée un fichier de mappage et choisit de l’ouvrir pour le modifier, l’éditeur de mappage de base est lancé. Lorsque l’option Modifier est sélectionnée pour un fichier de mappage dans l’interface utilisateur d’Assets, elle est également ouverte dans l’éditeur de mappage de base.

**Rubrique parente :**[ Personnalisation de l’éditeur web](conf-web-editor.md)
