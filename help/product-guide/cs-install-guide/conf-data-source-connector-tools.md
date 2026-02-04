---
title: Configuration d’un connecteur de source de données à l’aide d’outils
description: Découvrez comment configurer un connecteur de source de données à l’aide des outils.
exl-id: d7cd412b-89ea-43a5-97b3-09944863bbee
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: c790d5edd1ab799564aebfa96f4a41288c977a6c
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 0%

---

# Configuration d’un connecteur de source de données à partir de l’interface utilisateur

Experience Manager Guides est fourni avec l’outil **Sources de données** qui vous permet de configurer des connecteurs prêts à l’emploi pour les sources de données. Vous pouvez configurer les connecteurs client REST JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce, Elasticsearch et Generic.


Outre ces connecteurs prêts à l’emploi, Experience Manager Guides fournit les connecteurs pour les sources de données Salsify, Akeneo et Microsoft Azure DevOps Boards (ADO). Vous pouvez télécharger et installer ces connecteurs open source à partir du [référentiel central Maven](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides). Les utilisateurs peuvent ensuite configurer ces connecteurs.
Découvrez comment [installer un connecteur open source](#install-open-source-connector).



Vous pouvez également vous connecter à des fichiers de données JSON à l’aide d’un connecteur de fichiers. Chargez le fichier JSON à partir de votre ordinateur ou parcourez-le à partir des ressources Adobe Experience Manager. Créez ensuite des fragments de contenu ou des rubriques à l’aide des générateurs.

Pour configurer un connecteur, procédez comme suit :

1. Sélectionnez le lien **Adobe Experience Manager** en haut et choisissez Outils.
1. Sélectionnez **Guides** dans la liste des outils.
1. Sélectionnez la mosaïque **Sources de données**. La page **Sources de données** s’affiche. Vous pouvez afficher les sources de données connectées.

   Vous pouvez basculer entre la **Vue Liste** ou la **Vue Mosaïque** pour afficher les différentes sources de données connectées sous forme de liste ou de mosaïques.

   <img src="./assets/data-sources-create-window.png" alt= "sources de données répertoriées sur la page sources de données" width="800">

   *Afficher ou créer un connecteur de source de données.*

1. Cliquez sur **Créer**.
1. Sélectionnez la base de données pour laquelle vous souhaitez créer le connecteur. Par exemple, le connecteur Elasticsearch.

   >[!NOTE]
   >
   >Toutes les bases de données prêtes à l’emploi disponibles sont répertoriées.

1. Cliquez sur **Suivant**.
1. Renseignez les informations de configuration et de connexion en fonction de la base de données.

   >[!TIP]
   >
   >* Survoler <img src="./assets/info-details.svg" alt= "icône info" width="25"> près du champ pour en savoir plus.
   >* Les champs comportant le caractère * sont obligatoires. Par exemple, vous pouvez saisir les informations suivantes pour le connecteur Elasticsearch.

   * **Nom** : saisissez le nom de la source de données.
   * **Type d’authentification** : sélectionnez le type d’authentification dans la liste déroulante. Par exemple, l’authentification de base nom d’utilisateur/mot de passe
   * **Nom d’utilisateur** : saisissez votre nom d’utilisateur.
   * **Mot de passe** : saisissez votre nom d’utilisateur et votre mot de passe.
   * **URL** : ajoutez l’URL de l’API.


1. Sélectionnez l’option **Exclure les modèles d’usine** pour exclure les modèles d’usine de l’utilisation pour la génération d’un topic et d’un fragment de code. Elles n’apparaissent pas sous la liste déroulante **Modèle de mappage de données** dans la boîte de dialogue **Ajouter un générateur de fragment de contenu** ou **Ajouter un générateur de rubrique**.
1. Sélectionnez **Tester la connexion**. Vous ne pouvez afficher le bouton **Tester la connexion** activé qu’après avoir ajouté les détails requis. Affichez un message de réussite si les détails de la connexion sont corrects. Dans le cas contraire, un message d’erreur s’affichera.
1. Sélectionnez **Enregistrer** dans la partie supérieure pour enregistrer le connecteur.     Afficher le bouton **Enregistrer** activé une fois que vous avez renseigné tous les détails et que la connexion a réussi.


   Si le connecteur est enregistré correctement, vous pouvez afficher la source de données connectée sur la page.

**Connexion à plusieurs ressources**

Vous pouvez ajouter ou utiliser plusieurs ressources basées sur différentes URL pour certains connecteurs tels que le client REST générique, Salsify, Akeneo et les tableaux de développement Azure Microsoft (ADO). Ensuite, contactez-les pour créer des fragments de contenu ou des rubriques à l’aide des générateurs qui les concernent.

Pour créer une ressource, procédez comme suit :

1. Sélectionnez ![ajouter une icône](assets/Add_icon.svg) dans la section **Ressource URL** pour ajouter une ressource pour chaque URL.
1. Configurez tous les détails de la boîte de dialogue **Ajouter une ressource**.
1. Cliquez sur **Ajouter**.
1. Vous pouvez modifier ![icône de modification](assets/edit_pencil_icon.svg) ou supprimer ![supprimer](assets/Delete_icon.svg) la ressource de la liste des ressources d’URL.
1. Vous pouvez également utiliser les ressources par défaut disponibles pour les sources de données telles que Salsify, Akeneo et Microsoft ADO. Désactivez les options de la ressource que vous ne souhaitez pas configurer pour une source de données.

Vous pouvez ainsi récupérer rapidement des données de n’importe quelle ressource pour une source de données spécifique dans un seul fragment de contenu ou une seule rubrique.



## Installation d’un connecteur open source{#install-open-source-connector}

Pour publier une dépendance présente sur le [référentiel central Maven](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides) dans les Cloud Services, vous devez inclure et incorporer la dépendance d’un connecteur open source.

1. Ajoutez la dépendance dans `all/pom.xml` dans le code de projet Git de Cloud Manager. Par exemple, vous pouvez ajouter la dépendance suivante pour le connecteur source de données des tableaux de développement Azure Microsoft.


   ```
   <dependency>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-azure-devops</artifactId>
       <version>1.0.0</version>
       <type>jar</type>
   </dependency> 
   ```

1. Incorporez la dépendance ajoutée.

   ```
   <embedded>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-azure-devops</artifactId>
       <type>jar</type>
       <target>/apps/aemdoxonaemcsstageprogram-vendor-packages/content/install</target>
   </embedded> 
   ```

1. Exécutez le pipeline pour appliquer les modifications dans les Cloud Services.
Le connecteur est installé dans votre environnement.


## Fonctionnalités disponibles pour un connecteur

* Basculez entre la vue **Liste** ou **Mosaïque** pour afficher les différentes sources de données connectées sous forme de liste ou de mosaïques.
* Cochez la case d’un seul connecteur. Cliquez sur **Tout sélectionner** pour sélectionner tous les connecteurs. Vous pouvez cliquer sur **Tout désélectionner** lorsque tous les connecteurs sont sélectionnés.

<img src="./assets/data-sources-features.png" alt= "fonctionnalités des sources de données sur la page sources de données" width="800">

*Modification, reconnexion, duplication ou suppression d’un connecteur de source de données.*

Vous pouvez utiliser les fonctionnalités suivantes pour le connecteur sur la page **Sources de données** :

* **Modifier** : modifiez les détails de configuration du connecteur sélectionné.

* **Reconnecter** : reconnectez-vous à un connecteur déconnecté.

* **Dupliquer** : créez un connecteur en double en utilisant le connecteur actuel comme base. Par défaut, le connecteur en double est créé avec un suffixe (comme connectorname_1). Par exemple, sample-astic-search_1.
Une erreur s’affiche si le connecteur portant le même nom existe.

* **Supprimer** : supprimez le connecteur sélectionné.


Une fois la source de données configurée, le connecteur est répertorié sous le panneau **Sources de données** dans l’éditeur web. Vous pouvez ensuite vous connecter à la source de données et insérer un fragment de contenu dans vos rubriques. Pour plus d’informations, consultez la section [&#x200B; Insérer un fragment de contenu à partir de votre source de données &#x200B;](../user-guide/web-editor-content-snippet.md).

