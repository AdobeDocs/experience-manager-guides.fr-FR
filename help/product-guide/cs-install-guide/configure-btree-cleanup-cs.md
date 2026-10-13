---
title: Configuration de la tâche de nettoyage B-tree pour les services cloud
description: Configuration de la tâche de nettoyage B-tree pour les services cloud
feature: Output Generation
role: Admin
level: Experienced
exl-id: de464e92-f17b-4c99-98f2-fdba8d214129
TQID: 'https://experienceleague.adobe.com/-n4Winzqo-HNb2FDH6RI223UT9uvuOc8-OT7mgXjblc'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '132'
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
