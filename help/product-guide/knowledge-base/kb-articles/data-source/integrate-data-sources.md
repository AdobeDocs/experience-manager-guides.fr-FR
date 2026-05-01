---
title: Architecture de l’intégration des sources de données externes dans AEM Guides
description: Découvrez l’architecture de l’intégration des sources de données externes dans AEM Guides.
exl-id: ce99033a-0ce1-4696-9d4c-89187273b0bd
source-git-commit: 12ba7129255257970ddd7a0989149be664ce9803
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 0%

---

# Intégration de sources de données externes

Les données provenant de systèmes externes peuvent être facilement intégrées à votre instance Experience Manager Guides. La connexion à des sources de données externes peut améliorer considérablement les fonctionnalités et la convivialité de votre système de gestion de contenu.


Vous pouvez vous connecter et récupérer efficacement des données à partir de sources externes à l’aide de l’intégration de données. Grâce à cette fonctionnalité, il n’est pas nécessaire de dépendre de l’équipe informatique pour obtenir les données, puis de les copier et coller manuellement ou de mettre à jour constamment les modifications dans le système externe.

Cette fonctionnalité assure la synchronisation avec la source d’origine et permet des mises à jour harmonieuses de la documentation sans recourir à des opérations de copier-coller manuel. Cela permet également de maintenir la cohérence des données entre Experience Manager Guides et la source de données externe.

De plus, après avoir récupéré le contenu à partir de sources de données externes, vous pouvez le créer au format DITA et réutiliser le contenu intégré.


## Framework d’intégration de source de données

La structure d’intégration d’une source de données comprend principalement deux composants principaux : les sources de données externes et leur intégration à l’instance Experience Manager Guides.

### Sources de données externes

Voici quelques-unes des sources de données auxquelles vous pouvez vous connecter à partir de Experience Manager Guides :

- Bases de données relationnelles (SGBD)
   - PostgreSQL, MySQL, Microsoft SQL Server, MariaDB et SQLite
- Bases de données non relationnelles
   - MongoDB, Apache Cassandra, Apache CouchDB et Redis
- Gestion des informations sur les produits (PIM) / Gestion du cycle de vie des produits (PLM)
   - Pimcore, Salsify, Akeneo et Informatica
- Systèmes de gestion de produits
   - Tableaux de développement Azure JIRA et Microsoft (ADO)
- Traitement analytique en ligne (OLAP) et systèmes d’analyse

### Intégration dans Experience Manager Guides



Grâce à l’utilisation d’un connecteur authentifié, les données sont transférées à partir d’un système externe et génèrent des données dans Experience Manager Guides.
![Architecture](assets/konnect-architecture.png)


### Intégration dans Experience Manager Guides

Pour intégrer le contenu dans Experience Manager Guides, procédez comme suit :

1. **Configurer le connecteur de source de données**
   - Le connecteur de source de données sert d’interface pour établir la connectivité avec les sources de données externes. Vous devez configurer le connecteur pour établir la connexion et inclure les méthodes d’authentification, telles que `Basic Auth` ou `API key Auth`. Tous les détails de configuration, y compris les informations chiffrées, sont stockés en toute sécurité dans Adobe Experience Manager.
   - La couche de connecteur est conçue pour être extensible, ce qui vous permet de créer vos implémentations pour la connexion à divers systèmes qui ne sont pas fournis prêts à l’emploi par Experience Manager Guides.
     ![Couche de connecteur](assets/data-source-connector-layer.jpg)
   >[!NOTE]
   >
   > Accédez au module de définition du connecteur et implémentez l’interface Connecteur pour créer un connecteur personnalisé. En savoir plus sur comment [configurer des connecteurs de source de données personnalisés](./conf-custom-data-source-connector.md).

1. **Personnaliser les modèles Velocity**

   - Experience Manager Guides prend en charge Velocity (https://velocity.apache.org/), un moteur de création de modèles très robuste qui transforme les données des fichiers JSON en contenu DITA. Velocity offre la possibilité de naviguer au sein des structures JSON avec n’importe quel niveau d’imbrication.
   - L’exemple suivant montre comment intégrer des modèles Velocity et des données provenant de Jira pour générer facilement des tableaux ou des listes ordonnées.
      - Réponse Jira

        ```
        {
            "expand": "schema,names",
            "total": 5,
            "hostname": "https://jira.corp.adobe.com",
            "maxResults": "200",
            "issues": [
                {
                    "key": "DXML-12756",
                    "fields": {
                        "description": "Implement the snippet generator in External Data Source integration",
                        "summary": "Implement the snippet generator in External Data Source integration"
                    }
                },
                {
                    "key": "DXML-12755",
                    "fields": {
                        "description": "Implement the topic generator in External Data Source integration",
                        "summary": "Implement the topic generator in External Data Source integration"
                    }
                },
                {
                    "key": "DXML-12745",
                    "fields": {
                        "description": "Implement the ability to register a new connector",
                        "summary": "Implement the ability to register a new connector"
                    }
                }
            ],
            "startAt": 0
        }
        ```

      - Modèles
        ![&#x200B; Moteur de modèle &#x200B;](assets/data-source-TemplatingEngine.png){width="800"}
      - Données générées à partir de la même source de données mais de modèles différents
        ![Données générées](assets/data-source-templates-topics.png){width="800"}

1. **Générer du contenu à l’aide des modèles**
   - Vous pouvez générer le contenu à partir des modèles que vous avez créés.
   - Vous pouvez générer différents types de contenu :
      - Extrait de code : il s’agit d’un contenu utilisable une seule fois. Vous pouvez générer les données à partir du connecteur dans le modèle défini, puis les incorporer dans la balise de votre choix.
      - Rubrique DITA : générez différentes rubriques à utiliser telles quelles dans le contenu ou réutilisables en tant que *composant réutilisable*.
      - Rubrique DITA + Mappage : vous pouvez également générer une carte complète avec la rubrique, puis utiliser les données pour publication directement ou les utiliser comme *composant réutilisable* dans d&#39;autres données.


1. **Publication du contenu intégré**
   - La publication est une fonctionnalité prête à l’emploi de Experience Manager Guides. Vous pouvez publier directement toutes les données générées à partir du système externe en tant que sortie de PDF ou du site AEM.

>[!MORELIKETHIS]
>
> Les documents suivants fournissent des informations supplémentaires sur la configuration des connecteurs et leur utilisation dans votre instance.
> - [Configuration d’un connecteur de source de données](../../../install-guide/conf-data-source-connector-tools.md)
> - [Générer du contenu à l’aide de fragments de code ou de rubriques](../../../user-guide/web-editor-content-snippet.md)
