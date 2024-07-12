---
title: Configuration des noms de fichier
description: Découvrez comment désactiver le posttraitement d’un dossier chargé dans Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: 42722c6f-1b1c-4a7e-89ef-a373623eb774
source-git-commit: 5d99274da8fdacbd255d426fa4913b5773ca45f8
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 1%

---

# Désactivation du post-traitement d’un dossier

Par défaut, toutes les ressources chargées sont traitées à l’aide du workflow Ressources de mise à jour de gestion des actifs numériques . Experience Manager Guides exécute un traitement supplémentaire, appelé posttraitement, dans le cadre de ce workflow. Cela permet également de générer les UUID.

Lors du chargement de vos fichiers et dossiers sur le serveur *Adobe Experience Manager Assets*, vous pouvez également désactiver le post-traitement et la génération des UUID.


Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails (propriété) suivants pour désactiver le posttraitement sur un chemin d’accès donné ou ignorer le posttraitement d’un dossier :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Valeur de chaîne pour définir toutes les OPTIONS NODE_standard (propriété à plusieurs valeurs, chaînes dont le chemin omet `/` à la fin) <br> **Valeur par défaut** : `/content/dam/projects/translation_output` |


| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Valeur de chaîne pour définir toutes les OPTIONS NODE_standard (propriété à plusieurs valeurs, chaînes dont le chemin omet `/` à la fin) <br> **Valeur par défaut** : `/content/dam` |


## Règles d’activation ou de désactivation du posttraitement

Par défaut, le posttraitement est effectué pour chaque chemin d’accès au dossier sous le dossier DAM Experience Manager. Les configurations sont appliquées à n’importe quel dossier, conformément aux règles suivantes :

* Si le parent est ignoré pour le posttraitement, mais que le dossier enfant est activé, l’enfant et tous ses successeurs sont considérés comme activés.
* Si le parent est activé pour le posttraitement mais que l’enfant est ignoré, l’enfant et tous ses successeurs sont considérés comme ignorés.
* Si le même chemin d’accès au dossier existe dans les configurations ignored.post.processing.paths et enabled.post.processing.paths, il est considéré comme ignoré pour le posttraitement.
