---
title: Présentation
description: Présentation du Guide de référence des API pour AEM Guides
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
feature: API Introduction
role: Developer
level: Experienced
source-git-commit: 00a926e82f7d848e0c8041de758f20e79758b01b
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 0%

---

# Présentation {#id1761C0007W7}

Adobe Experience Manager Guides \(ultérieurement appelé *AEM Guides*\) est une solution d’entreprise de bout en bout qui permet à Adobe Experience Manager \(AEM\) de disposer de fonctionnalités de solution de gestion de contenu de composant \(CCMS\) pour la création et la diffusion de contenu basé sur DITA. Les clients peuvent accéder aux workflows d’AEM Guides par programmation à l’aide des API d’AEM Guides pour les intégrer à d’autres applications d’entreprise. Ces API peuvent également être utilisées par les partenaires d’Adobe pour améliorer la proposition de valeur d’AEM Guides en étendant ses fonctionnalités ou en l’intégrant à d’autres applications ou services.

## API AEM GUIDES

Les API d’AEM Guides sont disponibles dans deux formats : HTTP et Java. Ces API présentent les fonctions essentielles d’AEM Guides aux développeurs d’applications. Grâce à ces fonctions, les développeurs et développeuses peuvent créer leurs propres plug-ins pour étendre les workflows prêts à l’emploi. Les API sont disponibles pour gérer les sorties de contenu DITA, utiliser les plans DITA, ajouter des attributs conditionnels aux profils au niveau du dossier et convertir des documents HTML et Words au format DITA.

## Installation des fichiers JAR sur votre référentiel Apache Maven local {#install-jar-local}

Pour pouvoir utiliser les fichiers JAR exposés par AEM Guides, vous devez les installer sur votre référentiel Apache Maven local. Pour installer les fichiers JAR sur le référentiel Maven de votre emplacement, procédez comme suit :

1. Extrayez le contenu du fichier du package AEM Guides \(.zip\) sur votre système local.

2. Dans l’invite de commande, accédez au dossier suivant dans le chemin d’accès au contenu extrait :

   ```
   \jcr_root\libs\fmdita\osgi-bundles\install
   ```

3. Exécutez la commande suivante pour installer le lot d’API dans votre référentiel Maven local :

   ```
   mvn install:install-file -Dfile=api-X.x.jar -DgroupId=com.adobe.fmdita -DartifactId=api -Dversion=X.x -Dpackaging=jar**
   ```

   >[!NOTE]
   >
   > Dans la commande ci-dessus, X.x doit être remplacé par le numéro de version réel dans les paramètres Dfile et Dversion.

4. \(*Facultatif*\) Installez une dépendance dans le référentiel de votre projet Maven local. Pour ce faire, créez un dossier dans votre projet Maven, puis exécutez la commande `mvn install` donnée à l’étape précédente avec le paramètre supplémentaire suivant :

   ```
   -DlocalRepositoryPath=<path_to_project_repository>
   ```

   Ensuite, pour exposer le dossier de référentiel local du projet au processus de création Maven, ajoutez un élément `repository` dans le fichier pom.xml parent, comme illustré ci-dessous :

   ```XML
   <repositories>
      <repository>
         <id>project-repository</id>
         <url>file://${project.basedir}/repository</url>
      </repository>
   </repositories>
   ```


Ce processus installe les fichiers JAR d’API dans le référentiel Maven local.

## Utilisation du fichier JAR de l’API de service dans un projet Maven

Après avoir installé les fichiers JAR de l’API dans votre référentiel Maven local, procédez comme suit pour utiliser le fichier JAR dans vos projets :

1. Ajoutez le fichier JAR à votre base de code et validez-le dans le référentiel de base de code sous un dossier, tel que « dependencies ». Notez que le nom du dossier dépend de votre hiérarchie de base de code.

2. Configurez les fichiers pom.xml du projet comme suit :

   Fichier pom.xml du projet parent :

   >[!IMPORTANT]
   >
   > Dans le fragment de code suivant, X.x doit être remplacé par le numéro de version réel et le nom de fichier du fichier JAR de l’API. Ces informations sont identiques à celles fournies à l’étape 3 du [processus d’installation](#install-jar-local).

   ```XML
   <plugin>
   
       <groupId>org.apache.maven.plugins</groupId>
   
      <artifactId>maven-install-plugin</artifactId>
   
       <version>2.5.2</version>
   
       <configuration>
   
               <groupId>com.adobe.fmdita</groupId>
   
               <artifactId>api</artifactId>
   
               <version>X.x</version>
   
               <file>${basedir}/dependencies/fmdita/api-X.x.jar</file>
   
               <packaging>jar</packaging>
   
               <generatePom>true</generatePom>
   
       </configuration>
   
       <executions>
   
           <execution>
   
               <id>inst_fmdita</id>
   
                   <goals>
   
                       <goal>install-file</goal>
   
                   </goals>
   
                   <phase>clean</phase>
   
           </execution>
   
       </executions>
   </plugin>
   ```

   Fichier pom.xml du module enfant :

   ```XML
   <plugin>
      <groupId>org.apache.maven.plugins</groupId>
   
      <artifactId>maven-install-plugin</artifactId>
   
      <configuration>
   
         <groupId>com.adobe.fmdita</groupId>
   
         <artifactId>api</artifactId>
   
         <version>3.6</version>
   
         <file>${basedir}/../dependencies/fmdita/api-3.6.jar</file>
   
         <packaging>jar</packaging>
   
         <generatePom>true</generatePom>
   
      </configuration>
   
      <executions>
   
         <execution>
   
            <id>inst_fmdita</id>
   
            <goals>
   
               <goal>install-file</goal>
   
            </goals>
   
            <phase>clean</phase>
   
         </execution>
   
      </executions>
   
   </plugin>
   ```


## Configurer et utiliser le JAR de l’API de service à partir du référentiel Maven public

Suivez les étapes suivantes pour configurer et utiliser les fichiers JAR de l’API de service à partir du référentiel Maven public dans vos projets :

1. Pour utiliser le fichier JAR de l’API de service dans un projet, configurez le référentiel Maven public AEM Guides dans votre fichier pom.xml.
2. Configurez le référentiel Maven public dans le fichier settings.xml de Maven comme suit :

   ```XML
   <repository>
      <id>fmdita-public</id>
      <name>fmdita-public</name>
      <url>https://repo.aem-guides.com/repository/fmdita-public</url>
   </repository>
   ```

3. Une fois le référentiel configuré, ajoutez le fichier JAR de l’API de service en tant que dépendance de projet dans le fichier pom.xml du projet.

   >[!NOTE]
   >
   > Utilisez la même version du fichier JAR de l’API que le package AEM Guides que vous avez installé sur le serveur.

4. Configurez la dépendance Maven comme illustré ci-dessous :

   ```XML
   <dependency>
      <groupId>com.adobe.fmdita</groupId>
      <artifactId>api</artifactId>
      <version>4.0</version>
   </dependency>
   ```


Une fois que le fichier JAR de l’API de service est ajouté en tant que dépendance de projet dans le fichier pom.xml du projet, vous pouvez créer et utiliser des API Java AEM Guides dans votre projet.

## Utilisation du fichier JAR de l’API à partir du référentiel central Maven pour AEM Guides as a Cloud Service

Pour AEM Guides as a Cloud Service, le fichier JAR de l’API a été déployé sur Maven Central. Vous pouvez utiliser le fichier JAR de l’API sans aucune configuration.

>[!NOTE]
>
> La convention d’affectation des noms du fichier JAR de l’API a été mise à jour conformément à la convention d’affectation des noms des modules complémentaires cloud.

Pour utiliser le fichier JAR de l’API, vous devez ajouter la dépendance au fichier pom.xml de votre projet, comme illustré ci-dessous :

```XML
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-dox-sdk-api</artifactId>
   <version>${RELEASE}</version>
</dependency>
```

>[!NOTE]
>
> Comme les packages dans le fichier JAR de l’API sont toujours identiques, aucune modification de code n’est nécessaire pour utiliser ce fichier JAR de l’API dans les projets cloud existants.

### API Java

Vous pouvez utiliser les API Java disponibles dans Experience Manager Guides pour créer des modules externes personnalisés et étendre les workflows prêts à l’emploi. Consultez [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) pour obtenir la documentation la plus récente et détaillée sur l’utilisation de l’API Java.



## Ressources supplémentaires

Voici une liste d’autres ressources utiles d’AEM Guides, disponibles sur la page [En savoir plus et assistance](https://helpx.adobe.com/fr/support/xml-documentation-for-experience-manager.html) :

- Guide de l’utilisateur
- Guide d’installation et de configuration
- Guide de démarrage rapide
- [Page d’archivage de l’aide](https://helpx.adobe.com/fr/xml-documentation-for-experience-manager/archive.html) \(accédez à l’ancienne version\)
