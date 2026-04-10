---
title: Configurer les noms de fichier
description: Découvrez comment désactiver le post-traitement d’un dossier chargé dans Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Désactivation du post-traitement pour un dossier

Par défaut, toutes les ressources chargées sont traitées à l’aide du workflow Ressource de mise à jour de la gestion des ressources numériques . Experience Manager Guides exécute un traitement supplémentaire, appelé post-traitement, dans le cadre de ce workflow. Cela permet également de générer les UUID

Lors du chargement de vos fichiers et dossiers sur le serveur **, vous pouvez également désactiver le post-traitement et la génération des UUID.

Les onglets suivants fournissent des instructions pour désactiver le post-traitement d’un dossier en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB Tab]

Suivez les instructions de la section [&#x200B; Remplacements de la configuration &#x200B;](download-install-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails (propriété) suivants pour désactiver le post-traitement sur un chemin donné ou ignorer le post-traitement pour un dossier :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Valeur de chaîne pour définir toute `/` NODE_OPTIONS standard (propriété à plusieurs valeurs, chaînes dont le chemin d’accès omet la <br> à la fin) **Valeur par défaut** : `/content/dam/projects/translation_output` |
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Valeur de chaîne pour définir toute `/` NODE_OPTIONS standard (propriété à plusieurs valeurs, chaînes dont le chemin d’accès omet la <br> à la fin) **Valeur par défaut** : `/content/dam` |

>[!TAB  On-Premise ]

Effectuez les étapes suivantes pour désactiver le post-traitement sur un chemin donné ou ignorer le post-traitement pour un dossier :


1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.config.ConfigManager** et cliquez dessus.

1. Sélectionnez l’option **Chemins ignorés pour le post-traitement** pour ignorer un dossier à des fins de post-traitement.

   Valeur de chaîne pour définir tout NODE_OPTIONS standard (propriété à plusieurs valeurs, chaînes dont le chemin d’accès omet la `/` à la fin)

   **Valeur par défaut** : `/content/dam/projects/translation_output`

   >[!NOTE]
   >
   > Cette propriété est désactivée par défaut et l’onglet Traduction est disponible dans le tableau de bord des cartes.

1. Sélectionnez l’option **Chemins activés pour le post-traitement** pour activer un chemin pour le post-traitement.

   Valeur de chaîne pour définir tout NODE_OPTIONS standard (propriété à plusieurs valeurs, chaînes dont le chemin d’accès omet la `/` à la fin)

   **Valeur par défaut** : `/content/dam/`

   >[!NOTE]
   >
   > Cette propriété est désactivée par défaut et l’onglet Traduction est disponible dans le tableau de bord des cartes.


1. Cliquez sur **Enregistrer**.

>[!ENDTABS]

## Règles d’activation ou de désactivation du post-traitement

Par défaut, le post-traitement est effectué pour chaque chemin d’accès au dossier sous le dossier de gestion des ressources numériques Experience Manager. Les configurations sont appliquées à n’importe quel dossier selon les règles suivantes :

* Si le parent est ignoré pour le post-traitement, mais que le dossier enfant est activé, l’enfant et tous ses successeurs sont considérés comme activés.
* Si le parent est activé pour le post-traitement mais que l&#39;enfant est ignoré, l&#39;enfant et tous ses successeurs sont considérés comme ignorés.
* Si le même chemin d’accès au dossier existe dans les configurations ignore.post.processing.paths et enabled.post.processing.paths, il est considéré comme ignoré pour le post-traitement.

