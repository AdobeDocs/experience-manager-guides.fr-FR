---
title: Configuration des noms de fichier
description: Découvrez comment désactiver le posttraitement d’un dossier chargé dans Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: fedd04f4a261ec199f86cb38ecd57e76b9393ae5
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 1%

---


# Désactivation du post-traitement d’un dossier

Par défaut, toutes les ressources chargées sont traitées à l’aide du workflow Ressources de mise à jour de gestion des actifs numériques . Dans le cadre de ce workflow, les Guides du Experience Manager exécutent un traitement supplémentaire, appelé posttraitement. Cela permet également de générer les UUID.

Lors du chargement de vos fichiers et dossiers dans le *Adobe Experience Manager Assets* , vous pouvez également désactiver le posttraitement et la génération des UUID.


Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails (propriété) suivants pour désactiver le posttraitement sur un chemin d’accès donné ou ignorer le posttraitement d’un dossier :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Valeur de chaîne pour définir toutes les OPTIONS NODE_standard (propriété à plusieurs valeurs, chaînes dont le chemin d’accès est omis). `/` à la fin) <br> **Valeur par défaut**: `/content/dam/projects/translation_output` |


| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Valeur de chaîne pour définir toutes les OPTIONS NODE_standard (propriété à plusieurs valeurs, chaînes dont le chemin d’accès est omis). `/` à la fin) <br> **Valeur par défaut**: `/content/dam` |


## Règles d’activation ou de désactivation du posttraitement

Par défaut, le posttraitement est effectué pour chaque chemin d’accès au dossier sous le dossier DAM du Experience Manager. Les configurations sont appliquées à n’importe quel dossier, conformément aux règles suivantes :

* Si le parent est ignoré pour le posttraitement, mais que le dossier enfant est activé, l’enfant et tous ses successeurs sont considérés comme activés.
* Si le parent est activé pour le posttraitement mais que l’enfant est ignoré, l’enfant et tous ses successeurs sont considérés comme ignorés.
* Si le même chemin d’accès au dossier existe dans les configurations ignored.post.processing.paths et enabled.post.processing.paths, il est considéré comme ignoré pour le posttraitement.
