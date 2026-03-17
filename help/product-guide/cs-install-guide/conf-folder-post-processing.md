---
title: Configurer les noms de fichier
description: Découvrez comment désactiver le post-traitement d’un dossier chargé dans Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: 42722c6f-1b1c-4a7e-89ef-a373623eb774
source-git-commit: 635206ca34db633a998b0156e2549d86a83f8131
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 0%

---

# Désactivation du post-traitement pour un dossier

Par défaut, toutes les ressources chargées sont traitées à l’aide du workflow Ressource de mise à jour de la gestion des ressources numériques . Experience Manager Guides exécute un traitement supplémentaire, appelé post-traitement, dans le cadre de ce workflow. Cela permet également de générer les UUID

Lors du chargement de vos fichiers et dossiers sur le serveur *Adobe Experience Manager Assets*, vous pouvez également désactiver le post-traitement et la génération des UUID.

Suivez les instructions de la section [ Remplacements de la configuration ](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails (propriété) suivants pour désactiver le post-traitement sur un chemin donné ou ignorer le post-traitement pour un dossier :

>[!NOTE]
>
> Vous pouvez également utiliser des expressions régulières (regex) pour définir des règles qui s’appliquent à plusieurs dossiers ou à une hiérarchie de dossiers entière. Pour plus d’informations, consultez la section [Utiliser une expression régulière pour activer ou désactiver le post-traitement](#use-regex-to-enable-or-disable-post-processing).

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Valeur de chaîne pour définir toute `/` NODE_OPTIONS standard (propriété à plusieurs valeurs, chaînes avec chemin d’accès qui omet les <br> à la fin ou l’expression régulière) **Valeur par défaut** : `/content/dam/projects/translation_output` |

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Valeur de chaîne pour définir toute `/` NODE_OPTIONS standard (propriété à plusieurs valeurs, chaînes avec chemin d’accès qui omet les <br> à la fin ou l’expression régulière) **Valeur par défaut** : `/content/dam` |

## Règles d’activation ou de désactivation du post-traitement

Par défaut, le post-traitement est effectué pour chaque chemin d’accès au dossier sous le dossier de gestion des ressources numériques Experience Manager. Les configurations sont appliquées à n’importe quel dossier selon les règles suivantes :

* Si le parent est ignoré pour le post-traitement, mais que le dossier enfant est activé, l’enfant et tous ses successeurs sont considérés comme activés.
* Si le parent est activé pour le post-traitement mais que l&#39;enfant est ignoré, l&#39;enfant et tous ses successeurs sont considérés comme ignorés.
* Si le même chemin d’accès au dossier existe dans les configurations `ignored.post.processing.paths` et `enabled.post.processing.paths`, il est considéré comme ignoré pour le post-traitement.

## Utilisez une expression régulière pour activer ou désactiver le post-traitement.

Au lieu de spécifier des chemins de dossier individuels, vous pouvez utiliser des expressions régulières (regex) pour définir des règles qui s’appliquent à plusieurs dossiers ou à des hiérarchies de dossiers entières.

Les modèles Regex sont évalués par rapport au chemin d’accès complet de la ressource lors du post-traitement.

Lorsque des expressions régulières (regex) sont utilisées pour configurer les chemins de post-traitement ignorés et activés, AEM Guides évalue les deux configurations par rapport au chemin de la ressource. Si un chemin d’accès correspond à la fois à une règle Ignorer et à une règle Activer, les règles Ignorer sont toujours prioritaires.

Les exemples suivants illustrent la manière dont les règles ignorer et activer basées sur une expression régulière sont évaluées.

## Scénarios d’évaluation d’expression régulière pour le post-traitement

### Ignorer la hiérarchie parente, activer un dossier spécifique

**Ignorer regex**

`regex:/content/dam/lang-test/.*`

**Activer regex**

`regex:/content/dam/lang-test/.*/parent1`

Dans l’exemple ci-dessus, le post-traitement est désactivé pour `/content/dam/lang-test/en/parent1`.

Bien que le chemin d’accès corresponde à l’expression régulière activée, il est déjà associé à l’expression régulière ignorée. Ignorer les règles est prioritaire, de sorte que le post-traitement n’est pas activé.

### Ignorer un dossier spécifique, activer une hiérarchie plus large

**Ignorer regex**

`regex:/content/dam/lang-test/.*/parent1`

**Activer regex**

`regex:/content/dam/lang-test/.*`

Dans l’exemple ci-dessus, le post-traitement est désactivé pour `/content/dam/lang-test/en/parent1` et activé pour `/content/dam/lang-test/en/parent2`.

Le chemin d’accès `parent1` est explicitement ignoré et reste désactivé. Les autres dossiers qui correspondent uniquement à l’expression régulière activée sont traités.

### Ignorer le dossier parent, activer un dossier enfant

**Ignorer regex**

`regex:/content/dam/lang-test/.*/parent1`

**Activer regex**

`regex:/content/dam/lang-test/.*/parent1/child1`

Dans l’exemple ci-dessus, le post-traitement est désactivé pour `/content/dam/lang-test/en/parent1` et `/content/dam/lang-test/en/parent1/child2`, et activé pour `/content/dam/lang-test/en/parent1/child1`.

Le dossier enfant explicitement activé par l’expression régulière est traité. Les autres dossiers enfants restent désactivés, car leur chemin d’accès parent correspond à l’expression régulière ignorée.

### Ignorer le dossier enfant spécifique, activer la hiérarchie parente

**Ignorer regex**

`regex:/content/dam/lang-test/.*/parent1/child1`

**Activer regex**

`regex:/content/dam/lang-test/.*/parent1`

Dans l’exemple ci-dessus, le post-traitement est désactivé pour `/content/dam/lang-test/en/parent1/child1` et activé pour `/content/dam/lang-test/en/parent1` et `/content/dam/lang-test/en/parent1/child2`.

Seul le dossier enfant explicitement ignoré est ignoré. Le dossier parent et les autres dossiers enfants sont traités, car ils correspondent à l’expression régulière activée et ne correspondent pas à l’expression régulière ignorée.

