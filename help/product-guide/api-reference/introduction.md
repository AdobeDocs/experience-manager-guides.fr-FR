---
title: Présentation
description: Présentation du Guide de référence des API pour AEM Guides
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
feature: API Introduction
role: Developer
level: Experienced
source-git-commit: 67e844faece8b6bb8988bb0e67f357cda1db9a4d
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Présentation {#id1761C0007W7}

Adobe Experience Manager Guides \(ultérieurement appelé *AEM Guides*\) est une solution d’entreprise de bout en bout qui permet à Adobe Experience Manager \(AEM\) de disposer de fonctionnalités de solution de gestion de contenu de composant \(CCMS\) pour la création et la diffusion de contenu basé sur DITA. Les clients peuvent accéder aux workflows d’AEM Guides par programmation à l’aide des API d’AEM Guides pour les intégrer à d’autres applications d’entreprise. Ces API peuvent également être utilisées par les partenaires d’Adobe pour améliorer la proposition de valeur d’AEM Guides en étendant ses fonctionnalités ou en l’intégrant à d’autres applications ou services.

## API AEM GUIDES

Les API d’AEM Guides sont disponibles dans deux formats :

- [API Java](#java-based-apis)
- [API REST](#rest-based-apis)

Ces API présentent les fonctions essentielles d’AEM Guides aux développeurs d’applications. Grâce à ces fonctions, les développeurs et développeuses peuvent créer leurs propres plug-ins pour étendre les workflows prêts à l’emploi. Les API sont disponibles pour gérer les sorties de contenu DITA, utiliser les plans DITA, ajouter des attributs conditionnels aux profils au niveau du dossier et convertir des documents HTML et Words au format DITA.


### API Java

Vous pouvez utiliser les API Java disponibles dans Experience Manager Guides pour créer des modules externes personnalisés et étendre les workflows prêts à l’emploi.

**Configuration de SDK à partir du référentiel central Maven pour AEM Guides as a Cloud Service**

>[!INFO]
>
>Consultez [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-dox-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-dox-sdk-api/latest/index.html) pour obtenir la documentation la plus récente et détaillée sur l’utilisation de l’API Java pour Experience Manager Guides as a Cloud Service.

Pour configurer et utiliser les fichiers JAR de l’API de service du référentiel Maven dans vos projets, ajoutez l’API SDK en tant que dépendance de projet dans le fichier `pom.xml` de votre projet, comme illustré ci-dessous.

    « XML
    &lt;dependency>
    &lt;groupId>com.adobe.aem&lt;/groupId>
    &lt;artifactId>aem-dox-sdk-api&lt;/artifactId>
    &lt;version>${RELEASE}&lt;/version>
    &lt;/dependency>
    
     »

>[!NOTE]
>
> Assurez-vous d’utiliser la même version du fichier JAR de l’API que le package AEM Guides installé sur votre serveur.

**Configuration et utilisation du fichier JAR de l’API à partir du référentiel central Maven (On-premise)**

>[!INFO]
>
>Consultez [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html) pour obtenir la documentation la plus récente et détaillée sur l’utilisation de l’API Java pour la configuration On-premise Experience Manager Guides.

Pour configurer et utiliser les fichiers JAR de l’API de service pour les déploiements on-premise, ajoutez le fichier JAR de l’API de service en tant que dépendance de projet dans le fichier `pom.xml` de votre projet, comme illustré ci-dessous :

    « XML
    &lt;dependency>
    &lt;groupId>com.adobe.aem&lt;/groupId>
    &lt;artifactId>aem-guides-sdk-api&lt;/artifactId>
    &lt;version>${RELEASE}&lt;/version>
    &lt;/dependency>
    
     »

>[!NOTE]
>
> Assurez-vous d’utiliser la même version du fichier JAR de l’API que le package AEM Guides installé sur votre serveur.


**Configuration et utilisation du fichier JAR de l’API à partir du référentiel Maven public AEM Guides (On-premise)**

>[!NOTE]
>
> Le référentiel public AEM Guides Maven sera abandonné après la version 5.3.0 de Experience Manager Guides. Le fichier JAR de l’API ne sera disponible que dans le référentiel central Maven par la suite.

Effectuez les étapes suivantes pour utiliser les fichiers JAR de l’API de service à partir du référentiel Maven public :

1. Configurez le référentiel Maven public AEM Guides dans votre fichier `pom.xml` ou `settings.xml` comme illustré ci-dessous :

   ```XML
   <repository>
       <id>fmdita-public</id>
       <name>fmdita-public</name>
       <url>https://repo.aem-guides.com/repository/fmdita-public</url>
    </repository>
   ```

1. Une fois le référentiel configuré, ajoutez le fichier JAR de l’API de service en tant que dépendance de projet dans le fichier `pom.xml` du projet.

   ```XML
   <dependency>
       <groupId>com.adobe.fmdita</groupId>
       <artifactId>api</artifactId>
       <version>${RELEASE}</version>
   </dependency>
   ```

   >[!NOTE]
   >
   > Utilisez la même version du fichier JAR de l’API que le package AEM Guides que vous avez installé sur le serveur.

Une fois que le fichier JAR de l’API de service est ajouté en tant que dépendance de projet dans le fichier `pom.xml` du projet, vous pouvez créer et utiliser des API Java AEM Guides dans votre projet.


### API REST

Experience Manager Guides fournit un ensemble complet d’API REST qui permettent aux développeurs d’accéder aux fonctionnalités de base d’HTTP et d’interagir avec celles-ci.

Ces API sont idéales pour :

- Intégration de Experience Manager Guides à d’autres systèmes d’entreprise
- Automatisation des workflows de publication et de révision
- Création d’applications et d’extensions personnalisées

Pour plus d’informations sur l’utilisation de l’API, les paramètres et les exemples de requêtes, consultez les rubriques appropriées dans la section **Référence de l’API** de la documentation de Experience Manager Guides.

## Ressources supplémentaires

Voici une liste d’autres ressources utiles d’AEM Guides, disponibles sur la page [En savoir plus et assistance](https://helpx.adobe.com/fr/support/xml-documentation-for-experience-manager.html) :

- Guide de l’utilisateur
- Guide d’installation et de configuration
- Guide de démarrage rapide
- [Page d’archivage de l’aide](https://helpx.adobe.com/fr/xml-documentation-for-experience-manager/archive.html) \(accédez à l’ancienne version\)
