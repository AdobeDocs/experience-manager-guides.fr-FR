---
title: Configuration de la réplication DITA Assets
description: Découvrez comment configurer la réplication des ressources distantes
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 453da51a42984b912547570f2e1de70806b41171
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 3%

---

# Configuration de la réplication des ressources DITA

Les onglets suivants fournissent des instructions pour configurer la fonction de réplication des ressources DITA en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB ]

1. Suivez les instructions fournies dans [Remplacements de la configuration](../install-conf-guide/download-install-config-override.md) pour créer le fichier de configuration.

1. Dans le fichier de configuration, fournissez les détails (propriété) suivants :

   | PID | Clé de la propriété | Valeur de la propriété |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `publish.replicate` | **Valeur par défaut :** « true » |

>[!TAB  On-Premise ]

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et sélectionnez le lot *com.adobe.fmdita.config.ConfigManager*.

1. Configurez les `Replicate DITA assets` de paramètres en fonction de vos besoins. Par défaut, le paramètre est activé.


   ![](assets/dita-assets-replication.png){width="350" align="left"}


1. Sélectionnez **Enregistrer**.

>[!ENDTABS]
