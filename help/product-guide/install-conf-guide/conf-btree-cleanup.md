---
title: Configuration de la tâche de nettoyage B-tree pour les services cloud
description: Configuration de la tâche de nettoyage B-tree pour les services cloud
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# Configurer le nettoyage de l’arborescence B

Configurez la tâche de nettoyage B-tree et gérez le paramètre `Guides BTree deletion` pour que votre système reste optimisé et que le stockage reste propre.

## Configurer la tâche de nettoyage de l’arborescence B

Les onglets suivants fournissent des instructions pour configurer une tâche de nettoyage B-tree en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB Tab]

1. Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md) pour créer le fichier de configuration.

1. Dans le fichier de configuration, fournissez les détails (propriété) suivants :

   | PID | Clé de la propriété | Valeur de la propriété |
   |---|---|---|
   | `com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob` | `cronExpression` | **Valeur par défaut :** « 0 0 0 * * ? » |

>[!TAB  On-Premise ]

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

>[!ENDTABS]

## Configuration du paramètre d’activation de la suppression de l’arborescence B de Guides

Les onglets suivants fournissent des instructions pour activer le paramètre en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB Tab]

1. Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md) pour créer le fichier de configuration.

1. Dans le fichier de configuration, fournissez les détails (propriété) suivants :

   | PID | Clé de la propriété | Valeur de la propriété |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `btree.deletion.enabled` | **Valeur par défaut :** « True » |

>[!TAB  On-Premise ]

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et sélectionnez le lot *com.adobe.fmdita.config.ConfigManager*.
1. Activez la `Guides btree deletion enabled` de paramètre.

   ![](assets/btree-cleanup-setting.png){align="left"}

1. Sélectionnez **Enregistrer**.

>[!ENDTABS]