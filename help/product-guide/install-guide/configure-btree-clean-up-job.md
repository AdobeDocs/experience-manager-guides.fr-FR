---
title: Configurer la tâche de nettoyage B-tree pour les services On-Premise
description: Configurer la tâche de nettoyage B-tree pour les services On-Premise
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: e1b332b100cc8e3937557e4617d66352c1a0dc3c
workflow-type: tm+mt
source-wordcount: '145'
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

   ![](assets/btree-cleanup-config.png){align="left"}

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

   ![](assets/btree-cleanup-setting.png){align="left"}

1. Sélectionnez **Enregistrer**.

