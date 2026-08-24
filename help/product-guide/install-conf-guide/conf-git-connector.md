---
title: Configuration d’un connecteur Git dans AEM Guides
description: Découvrez comment configurer un Git dans Experience Manager Guides.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: b73e904c7e0a6f398e471be6fc874de30742e519
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 1%

---

# Création et configuration du connecteur Git à partir de l’interface utilisateur

>[!NOTE]
>
> Cette fonction est désactivée par défaut. Pour l’activer dans votre environnement, contactez votre équipe du succès client.

Utilisez l’outil Sources de données de Experience Manager Guides pour créer et configurer un connecteur Git à partir de l’interface utilisateur. Une fois le connecteur configuré, vous pouvez l’utiliser pour importer du contenu d’un référentiel Git dans Experience Manager Guides.

>[!NOTE]
>
> Avant de commencer, assurez-vous que le connecteur Git est déployé sur votre projet Cloud Manager. Pour plus d’informations, consultez la section [Ajout d’un connecteur Git à votre projet Cloud Manager.](#add-git-connector-to-your-cloud-manager-project)


1. Sélectionnez le lien **** en haut et choisissez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils.
1. Sélectionnez la mosaïque **Sources de données**. La page **Sources de données** s’affiche.
1. Sélectionnez **Créer**.
1. Dans la liste des connecteurs de source de données, sélectionnez **GitHub**.

   ![](assets/github-connector-tile.png){width="600"}

1. Sélectionnez **Suivant**.
1. Saisissez les détails de configuration et de connexion.

   ![](assets/conf-git-connector.png){width="600"}

   >[!TIP]
   >
   >* Survoler <img src="./assets/info-details.svg" alt= "icône info" width="25"> près du champ pour en savoir plus.
   >* Les champs comportant le caractère * sont obligatoires. Par exemple, vous pouvez saisir les informations suivantes pour le connecteur Git.

   - **Nom** : saisissez le nom de la source de données.
   - **Chemin d’accès racine AEM cible** : saisissez le chemin d’accès dans le référentiel AEM où le contenu importé depuis Git doit être stocké.
   - **Filtre de type de fichier (inclusion)** : indiquez les types de fichiers à inclure lors de l’importation.
   - **Chemin exclu (regex)** : spécifiez les modèles de chemin à exclure de l’importation.
   - **Type d’authentification** : sélectionnez le type d’authentification dans la liste déroulante. Actuellement, la méthode d’authentification **PAT (Personal Access Token)** est la seule prise en charge. Saisissez le chemin d’accès lors de la configuration du connecteur pour authentifier et accéder au référentiel Git.

     Découvrez comment [générer un jeton d’accès personnel GitHub](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token-classic).

     Lors de la sélection des portées pendant la génération PAT sur GitHub, veillez à activer les portées suivantes :
     - **repo** : cochez la case de niveau supérieur. Toutes les sous-portées sont sélectionnées automatiquement, ce qui permet d’accéder au contenu du référentiel, au statut de validation et aux déploiements.
     - **admin:org** : sélectionnez uniquement **lecture:org**. Cela est nécessaire pour résoudre l’appartenance à l’organisation et à l’équipe.
   * **URL du référentiel** : saisissez l’URL du référentiel Git à partir de laquelle le contenu doit être importé.
   * **Branche** : renseignez la branche à utiliser pour l’importation de contenu.

1. Testez la connexion. Le bouton **Tester la connexion** n’est activé qu’après avoir saisi les détails requis. Si les détails de la connexion sont corrects, un message de réussite s’affiche. Dans le cas contraire, un message d’erreur s’affiche.

   ![](assets/git-connector-test-connection.png){width="600"}

1. Sélectionnez **Enregistrer** dans la partie supérieure pour enregistrer le connecteur.

   Le bouton Enregistrer n’est activé qu’une fois tous les détails requis saisis et la connexion établie. Si le connecteur est enregistré correctement, vous pouvez afficher le connecteur Github configuré sur la page **Sources de données**.

   ![](assets/git-connector-connected.png){width="600"}

## Ajouter le connecteur Git à votre projet Cloud Manager

Avant que le connecteur Git ne soit disponible pour configuration à partir de la page **Sources de données**, il doit être incorporé en tant que dépendance dans votre projet AEM. Effectuez les étapes suivantes pour ajouter la dépendance :

>[!NOTE]
>
> Pour afficher les versions du connecteur Git disponibles, consultez [Référentiel Maven central](https://central.sonatype.com/artifact/com.adobe.aem.addon.guides/konnect-github).

1. Dans le `all/pom.xml` de votre projet AEM, ajoutez Connecteur Git en tant que dépendance sous `<dependencies>` :

   ```xml
   <dependency>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-github</artifactId>
       <version>1.0.1</version>
   </dependency>
   ```

1. Dans le même `pom.xml`, ajoutez la dépendance à la section `<embeddeds>` de la configuration `filevault-package-maven-plugin` :

   ```xml
   <embedded>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-github</artifactId>
       <type>jar</type>
       <target>/apps/YOUR-vendor-packages/content/install</target>
   </embedded>
   ```

   Remplacez `YOUR-vendor-packages` par le nom du package fournisseur de votre projet.

1. Validez et envoyez les modifications à votre référentiel Git Cloud Manager, puis exécutez le pipeline pour les déployer.

Une fois le pipeline terminé, le connecteur Git est installé dans votre environnement et disponible pour configuration à partir de la page **Sources de données**.





