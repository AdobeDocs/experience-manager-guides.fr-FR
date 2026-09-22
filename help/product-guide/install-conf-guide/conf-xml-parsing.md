---
title: Configuration de l’entité d’analyse XML pour Cloud Service et On-Premise
description: Découvrez comment configurer l’entité d’analyse XML pour Cloud Service et On-Premise
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: e4019ae1e605bd26f7df676a4fab8c632fd8fa8e
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 1%
---
# Configurer la limite de taille d’entité de l’analyseur XML

Experience Manager Guides vous permet de configurer une limite de taille d’entité totale acceptée par l’analyseur XML lors de la publication. Cela permet d’éviter des problèmes tels que les attaques d’extension d’entité XML et le traitement des payloads surdimensionnées.

>[!NOTE]
>
>Vous pouvez configurer une limite à la taille totale des entités acceptées par l’analyseur XML lors de la publication, ce qui réduit les risques tels que les attaques d’extension d’entités XML et le traitement des payloads trop volumineuses. La gestion de la limite de taille d’entité diffère entre Java 21 et Java 25. Par conséquent, il est conseillé aux environnements qui effectuent une mise à niveau vers Java 25 de vérifier et de valider leur configuration pour s’assurer que les workflows de publication continuent de fonctionner sans erreur.

Cette configuration implique deux propriétés associées :

* **Appliquer la limite de taille totale d’entité de l’analyseur XML** (`dxml.publish.xml.apply.total.entity.size.limit`) : active ou désactive la vérification de la limite de taille totale d’entité.
* **Limite de taille totale d’entité de l’analyseur XML** (`dxml.publish.xml.total.entity.size.limit`) : indique la valeur de `totalEntitySizeLimit` JAXP (caractères) appliquée aux analyseurs XML sécurisés lorsque l’indicateur d’application est activé.

Les onglets suivants fournissent des instructions pour configurer ces propriétés en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB Tab]

1. Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md) pour créer le fichier de configuration.

1. Dans le fichier de configuration, fournissez les détails (propriété) suivants :

   | PID | Clé de la propriété | Valeur de la propriété |
   |---|---|---|
   | `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService` | `dxml.publish.xml.apply.total.entity.size.limit` | **Valeur par défaut :** « true » |
   | `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService` | `dxml.publish.xml.total.entity.size.limit` | **Valeur par défaut :** « 50000000 » |

>[!TAB  On-Premise ]

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et sélectionnez le lot *com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService*.

1. Configurez les paramètres suivants en fonction de vos besoins :

   * **Appliquer la limite de taille totale d’entité de l’analyseur XML** (`dxml.publish.xml.apply.total.entity.size.limit`) : par défaut, ce paramètre est désactivé.
   * **Limite de taille totale d’entité de l’analyseur XML** (`dxml.publish.xml.total.entity.size.limit`) : par défaut, cette valeur est définie sur `50000000` caractères. Ce paramètre prend effet uniquement lorsque le paramètre **Appliquer la limite de taille totale d’entité de l’analyseur XML** est activé.

1. Sélectionnez **Enregistrer**.

>[!ENDTABS]



