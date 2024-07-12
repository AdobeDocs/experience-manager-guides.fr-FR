---
title: Configuration d’un connecteur de source de données à l’aide d’outils
description: Découvrez comment configurer un connecteur de source de données à l’aide des outils.
exl-id: 2a0ac0a0-b2a9-453e-851b-fb04c8903526
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---

# Configurer un connecteur de source de données à partir de l’interface utilisateur

Experience Manager Guides est fourni avec l’outil **Sources de données** qui vous aide à configurer des connecteurs prêts à l’emploi pour les sources de données. Vous pouvez configurer des connecteurs pour JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce et des bases de données Elasticsearch.

Pour configurer un connecteur, procédez comme suit :

1. Sélectionnez le lien **Adobe Experience Manager** en haut et choisissez Outils.
1. Sélectionnez **Guides** dans la liste des outils.
1. Sélectionnez la mosaïque **Sources de données** . La page **Sources de données** s’affiche. Vous pouvez afficher les sources de données connectées.

   Vous pouvez basculer entre le **mode Liste** ou le **mode Mosaïque** pour afficher les différentes sources de données connectées sous forme de liste ou de mosaïques.

   <img src="./assets/data-sources-create-window.png" alt= "sources de données répertoriées dans la page sources de données" width="800">

   *Afficher ou créer un connecteur de source de données.*
1. Cliquez sur **Créer**.
1. Sélectionnez la base de données pour laquelle vous souhaitez créer le connecteur. Par exemple, le connecteur Elasticsearch.
   >[!NOTE]
   >
   >Toutes les bases de données d&#39;usine disponibles sont répertoriées.

1. Cliquez sur **Suivant**.
1. Saisissez les détails de configuration et de connexion en fonction de la base de données.

   >[!TIP]
   >* Survol <img src="./assets/info-details.svg" alt= "icône info" width="25"> près du champ pour en afficher plus de détails.
   > * Les champs avec * sont obligatoires. Par exemple, vous pouvez saisir les détails suivants pour le connecteur Elasticsearch.

   * **Nom** : saisissez le nom de la source de données.
   * Type d’authentification : sélectionnez le type d’authentification dans la liste déroulante. Par exemple, authentification de base nom d’utilisateur-mot de passe
   * **Nom d’utilisateur** : saisissez votre nom d’utilisateur.
   * **Mot de passe** : saisissez votre nom d’utilisateur et votre mot de passe.
   * **URL** : ajoutez l’URL de l’API.

1. Sélectionnez **Tester la connexion**. Vous pouvez afficher le bouton **Tester la connexion** activé uniquement après avoir ajouté les détails requis. Affichez un message de réussite si les détails de la connexion sont corrects. Sinon, vous pouvez afficher un message d’erreur.



1. Sélectionnez **Enregistrer** en haut pour enregistrer le connecteur.     Affichez le bouton **Enregistrer** activé une fois que vous avez rempli tous les détails et que la connexion a réussi.


   Si le connecteur est enregistré correctement, vous pouvez afficher la source de données connectée sur la page.

## Fonctionnalités disponibles pour un connecteur

* Basculez entre le **mode Liste** ou le **mode Mosaïque** pour afficher les diverses sources de données connectées sous forme de liste ou de mosaïques.
* Cochez la case correspondant à un seul connecteur. Cliquez sur **Sélectionner tout** pour sélectionner tous les connecteurs. Vous pouvez cliquer sur **Tout désélectionner** lorsque tous les connecteurs sont sélectionnés.

<img src="./assets/data-sources-features.png" alt= "fonctions des sources de données sur la page sources de données" width="800">

*Modifier, reconnecter, dupliquer ou supprimer un connecteur de source de données.*

Vous pouvez utiliser les fonctionnalités suivantes pour le connecteur sur la page **Sources de données** :

* **Modifier** : modifiez les détails de configuration pour le connecteur sélectionné.

* **Reconnecter** : reconnectez-vous à un connecteur déconnecté.

* **Dupliquer** : créez un nouveau connecteur en double à l’aide du connecteur actuel comme base. Le connecteur en double est créé avec un suffixe (tel que connectorname_1) par défaut. Par exemple, sample-élastique-search_1.
Vous affichez une erreur si le connecteur portant le même nom existe.

* **Supprimer** : supprimez le connecteur sélectionné.


Une fois que vous avez configuré la source de données, le connecteur est répertorié sous le **panneau Sources de données** dans l’éditeur web. Vous pouvez ensuite vous connecter à la source de données et insérer un fragment de contenu dans vos rubriques. Pour plus d’informations, voir [Insertion d’un fragment de contenu à partir de votre source de données](../user-guide/web-editor-content-snippet.md).
