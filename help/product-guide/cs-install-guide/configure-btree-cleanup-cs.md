---
title: Configuration de la tâche de nettoyage B-tree pour les services cloud
description: Configuration de la tâche de nettoyage B-tree pour les services cloud
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 5b29b2b5f725b5d9a2029fb232e62f387a5338fd
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 3%

---

# Configurer le nettoyage de l’arborescence B

Configurez la tâche de nettoyage B-tree et gérez le paramètre `Guides BTree deletion` pour que votre système reste optimisé et que le stockage reste propre.

## Configurer la tâche de nettoyage de l’arborescence B

Effectuez les étapes suivantes pour configurer la tâche de nettoyage B-tree :

1. Suivez les instructions fournies dans [Remplacements de la configuration](../cs-install-guide/download-install-additional-config-override.md) pour créer le fichier de configuration.

1. Dans le fichier de configuration, fournissez les détails (propriété) suivants :

   | PID | Clé de la propriété | Valeur de la propriété |
   |---|---|---|
   | `com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob` | `cronExpression` | **Valeur par défaut :** « 0 0 0 * * ? » |


## Configuration du paramètre d’activation de la suppression de l’arborescence B de Guides

Pour activer le paramètre, procédez comme suit :

1. Suivez les instructions fournies dans [Remplacements de la configuration](../cs-install-guide/download-install-additional-config-override.md) pour créer le fichier de configuration.

1. Dans le fichier de configuration, fournissez les détails (propriété) suivants :

   | PID | Clé de la propriété | Valeur de la propriété |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `btree.deletion.enabled` | **Valeur par défaut :** « True » |