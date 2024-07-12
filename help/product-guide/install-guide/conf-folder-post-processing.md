---
title: Configuration des noms de fichier
description: Découvrez comment désactiver le posttraitement d’un dossier chargé dans Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: ff6e1322-9655-42aa-b353-199c70c9de49
source-git-commit: d525775afeeb89754762ff514126b1c3a3307b3f
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# Désactivation du post-traitement d’un dossier

Par défaut, toutes les ressources chargées sont traitées à l’aide du workflow Ressources de mise à jour de gestion des actifs numériques . Experience Manager Guides exécute un traitement supplémentaire, appelé posttraitement, dans le cadre de ce workflow. Cela permet également de générer les UUID.

Lors du chargement de vos fichiers et dossiers sur le serveur *Adobe Experience Manager Assets*, vous pouvez également désactiver le post-traitement et la génération des UUID.


Effectuez les étapes suivantes pour désactiver le posttraitement sur un chemin d’accès donné ou ignorer le posttraitement d’un dossier :


1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.config.ConfigManager**.

1. Sélectionnez l’option **Chemins ignorés pour le traitement Post** pour ignorer un dossier en post-traitement.

   Valeur de chaîne pour définir toutes les OPTIONS NODE_standard (propriété à plusieurs valeurs, chaînes dont le chemin omet `/` à la fin).

   **Valeur par défaut** : `/content/dam/projects/translation_output`

   >[!NOTE]
   >
   > Cette propriété est désactivée par défaut et l’onglet Traduction est disponible dans le tableau de bord de la carte.

1. Sélectionnez l’option **Chemins activés pour le traitement Post** pour activer un chemin d’accès pour le post-traitement.

   Valeur de chaîne pour définir toutes les OPTIONS NODE_standard (propriété à plusieurs valeurs, chaînes dont le chemin omet `/` à la fin).

   **Valeur par défaut** : `/content/dam/`

   >[!NOTE]
   >
   > Cette propriété est désactivée par défaut et l’onglet Traduction est disponible dans le tableau de bord de la carte.


1. Cliquez sur **Enregistrer**.



## Règles d’activation ou de désactivation du posttraitement

Par défaut, le posttraitement est effectué pour chaque chemin d’accès au dossier sous le dossier DAM Experience Manager. Les configurations sont appliquées à n’importe quel dossier, conformément aux règles suivantes :

* Si le parent est ignoré pour le posttraitement, mais que le dossier enfant est activé, l’enfant et tous ses successeurs sont considérés comme activés.
* Si le parent est activé pour le posttraitement mais que l’enfant est ignoré, l’enfant et tous ses successeurs sont considérés comme ignorés.
* Si le même chemin d’accès au dossier existe dans les configurations ignored.post.processing.paths et enabled.post.processing.paths, il est considéré comme ignoré pour le posttraitement.
