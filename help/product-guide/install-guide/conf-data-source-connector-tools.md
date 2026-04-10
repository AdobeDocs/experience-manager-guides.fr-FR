---
title: Configuration d’un connecteur de source de données à l’aide d’outils
description: Découvrez comment configurer un connecteur de source de données à l’aide des outils.
exl-id: 2a0ac0a0-b2a9-453e-851b-fb04c8903526
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 0%

---

# Configuration d’un connecteur de source de données à partir de l’interface utilisateur

Experience Manager Guides est fourni avec l’outil **Sources de données** qui vous permet de configurer des connecteurs prêts à l’emploi pour les sources de données. Vous pouvez configurer des connecteurs pour les bases de données JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), Adobe Commerce et Elasticsearch.

Pour configurer un connecteur, procédez comme suit :

1. Sélectionnez le lien **** en haut et choisissez Outils.
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
   >* Survoler <img src="./assets/info-details.svg" alt= "icône info" width="25"> près du champ pour en savoir plus.
   > * Les champs comportant le caractère * sont obligatoires. Par exemple, vous pouvez saisir les informations suivantes pour le connecteur Elasticsearch.

   * **Nom** : saisissez le nom de la source de données.
   * Type d’authentification : sélectionnez le type d’authentification dans la liste déroulante. Par exemple, l’authentification de base nom d’utilisateur/mot de passe
   * **Nom d’utilisateur** : saisissez votre nom d’utilisateur.
   * **Mot de passe** : saisissez votre nom d’utilisateur et votre mot de passe.
   * **URL** : ajoutez l’URL de l’API.

1. Sélectionnez **Tester la connexion**. Vous ne pouvez afficher le bouton **Tester la connexion** activé qu’après avoir ajouté les détails requis. Affichez un message de réussite si les détails de la connexion sont corrects. Dans le cas contraire, un message d’erreur s’affichera.



1. Sélectionnez **Enregistrer** dans la partie supérieure pour enregistrer le connecteur.     Afficher le bouton **Enregistrer** activé une fois que vous avez renseigné tous les détails et que la connexion a réussi.


   Si le connecteur est enregistré correctement, vous pouvez afficher la source de données connectée sur la page.

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


Une fois la source de données configurée, le connecteur est répertorié sous le panneau **Sources de données** dans l’éditeur web. Vous pouvez ensuite vous connecter à la source de données et insérer un fragment de contenu dans vos rubriques. Pour plus d’informations, consultez la section [Utiliser les données de votre source de données](../user-guide/web-editor-content-snippet.md).

>[!NOTE]
>
>Vous pouvez également créer des connecteurs personnalisés et les utiliser avec les différentes sources de données. Découvrez comment [ configurer des connecteurs personnalisés ](../knowledge-base/kb-articles/data-source/conf-custom-data-source-connector.md).