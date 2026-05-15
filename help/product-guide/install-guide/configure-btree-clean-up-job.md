---
title: Configurer la tâche de nettoyage B-tree pour les services On-Premise
description: Configurer la tâche de nettoyage B-tree pour les services On-Premise
feature: Output Generation
role: Admin
level: Experienced
exl-id: ff6f968c-3440-4757-882a-676711ad05c3
TQID: https://experienceleague.adobe.com/qvOHGtHbgKS3xUv0pEXKTqeWblIDj8JKJwik8heXwPo
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 156
ht-degree: 2%

---

# Configurer le nettoyage de l’arborescence B

Configurez la tâche de nettoyage B-tree et gérez le paramètre `Guides B-tree deletion` pour que votre système reste optimisé et que le stockage reste propre.

## Configurer la tâche de nettoyage de l’arborescence B

Effectuez les étapes suivantes pour configurer la tâche de nettoyage B-tree :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et sélectionnez le lot *com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob*.

1. Mettez à jour l’expression cron pour configurer la fréquence d’exécution des tâches du planificateur de nettoyage de l’arborescence B.

1. Configurez le planificateur de nettoyage de l’arborescence B comme illustré ci-dessous.

   ![](assets/btree-cleanup-config.png)

1. Sélectionnez **Enregistrer**.


## Configuration du paramètre d’activation de la suppression de l’arborescence B de Guides

Pour activer le paramètre, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et sélectionnez le lot *com.adobe.fmdita.config.ConfigManager*.
1. Activez la `Guides btree deletion enabled` de paramètre.

   ![](assets/btree-cleanup-setting.png)

1. Sélectionnez **Enregistrer**.
