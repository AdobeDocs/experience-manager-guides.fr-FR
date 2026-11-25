---
title: Configurer les noms de fichier
description: Découvrez comment désactiver le post-traitement d’un dossier chargé dans Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: eaf974f4-c804-4392-b1f3-f4f24dd441f7
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
    internal-label: Filename configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 2296e0706603eef5c4a76542c4a58f7eb2e13c6c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%
---
# Désactivation du post-traitement pour un dossier

>[!NOTE]
>
>À compter de la version 2027.01.0 de Experience Manager Guides Cloud Service et de la version 5.3 On-Premise, le tableau de bord des cartes sera obsolète pour les nouveaux clients. Les nouveaux clients utiliseront la console de mappage par défaut. Avec la version 2027.03.0, le tableau de bord Carte sera désactivé par défaut. À l’avenir, nous vous recommandons d’utiliser la console Map pour la gestion et la publication des cartes. Si vous avez toujours besoin d’accéder au tableau de bord des cartes, contactez l’équipe du succès client pour obtenir de l’aide.

Par défaut, toutes les ressources chargées sont traitées à l’aide du workflow Ressource de mise à jour de la gestion des ressources numériques . Experience Manager Guides exécute un traitement supplémentaire, appelé post-traitement, dans le cadre de ce workflow. Cela permet également de générer les UUID

Lors du chargement de vos fichiers et dossiers sur le serveur *Adobe Experience Manager Assets*, vous pouvez également désactiver le post-traitement et la génération des UUID.

Les onglets suivants fournissent des instructions pour désactiver le post-traitement d’un dossier en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Suivez les instructions de la section [Remplacements de configuration](download-install-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails (propriété) suivants pour désactiver le post-traitement sur un chemin donné ou ignorer le post-traitement pour un dossier :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Valeur de chaîne pour définir les NODE_OPTIONS standard (propriété à plusieurs valeurs, chaînes dont le chemin d’accès omet `/` à la fin) <br> **Valeur Par Défaut** : `/content/dam/projects/translation_output` |
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Valeur de chaîne pour définir les NODE_OPTIONS standard (propriété à plusieurs valeurs, chaînes dont le chemin d’accès omet `/` à la fin) <br> **Valeur Par Défaut** : `/content/dam` |

>[!TAB On-Premise]

Effectuez les étapes suivantes pour désactiver le post-traitement sur un chemin donné ou ignorer le post-traitement pour un dossier :


1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.config.ConfigManager**.

1. Sélectionnez l’option **Chemins ignorés pour le post-traitement** pour ignorer un dossier pour le post-traitement.

   Valeur de chaîne pour définir les NODE_OPTIONS standard (propriété à plusieurs valeurs, chaînes dont le chemin d’accès omet `/` à la fin)

   **Valeur Par Défaut** : `/content/dam/projects/translation_output`

   >[!NOTE]
   >
   > Cette propriété est désactivée par défaut et l’onglet Traduction est disponible dans le tableau de bord des cartes.

1. Sélectionnez l’option **Chemins activés pour le post-traitement** pour activer un chemin pour le post-traitement.

   Valeur de chaîne pour définir les NODE_OPTIONS standard (propriété à plusieurs valeurs, chaînes dont le chemin d’accès omet `/` à la fin)

   **Valeur Par Défaut** : `/content/dam/`

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
