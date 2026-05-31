---
title: Configuration de la tâche de nettoyage du magasin de référence
description: Configuration de la tâche de nettoyage du magasin de référence
feature: Output Generation
role: Admin
level: Experienced
exl-id: 58f98313-fc91-43b3-9553-aa5ab4946925
source-git-commit: 370a28a06a37b632873a79c9b83b8660a0221dd8
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 3%

---

# Configuration du nettoyage du magasin de référence

Configurez la tâche Nettoyage du magasin de référence et gérez le paramètre `Guides BTree deletion` pour que votre système reste optimisé et que le stockage reste propre.

## Configuration de la tâche de nettoyage du magasin de référence

Les onglets suivants fournissent des instructions pour configurer la tâche de nettoyage du magasin de référence en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

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

1. Mettez à jour l’expression cron pour configurer la fréquence d’exécution des tâches du planificateur de nettoyage du magasin de référence.

1. Configurez le planificateur de nettoyage du magasin de référence comme illustré ci-dessous.

   ![](assets/btree-cleanup-config.png)

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
1. Activez le paramètre **Guides btree deletion enabled** (btree.deletion.enabled).

   ![](assets/btree-cleanup-setting.png)

1. Sélectionnez **Enregistrer**.

>[!ENDTABS]
