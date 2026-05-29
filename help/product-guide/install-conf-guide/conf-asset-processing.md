---
title: Configuration du traitement des ressources pour Cloud Service
description: Découvrez comment configurer le traitement des ressources pour Cloud Service
feature: Output Generation
role: Admin
level: Experienced
exl-id: 0b66a515-d8f1-4ea6-913f-e152ae114698
source-git-commit: 5af3356dff3c42b8a93ed97b5ee20b23976769a4
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 3%

---

# Configuration de la fonctionnalité de traitement des ressources

Les onglets suivants fournissent des instructions pour configurer la fonction de traitement des ressources en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB ]

1. Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md) pour créer le fichier de configuration.

1. Dans le fichier de configuration, fournissez les détails (propriété) suivants :

   | PID | Clé de la propriété | Valeur de la propriété |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `enable.asset.processing.scheduler` | **Valeur par défaut :** « true » |

>[!TAB  On-Premise ]

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et sélectionnez le lot *com.adobe.fmdita.config.ConfigManager*.

1. Configurez le paramètre **Activer Guides tâche planifiée de traitement des ressources** (`enable.asset.processing.scheduler`) en fonction de vos besoins. Par défaut, le paramètre est activé.

1. Sélectionnez **Enregistrer**.

>[!ENDTABS]
