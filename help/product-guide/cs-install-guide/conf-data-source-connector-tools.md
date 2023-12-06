---
title: Configuration d’un connecteur de source de données à l’aide d’outils
description: Découvrez comment configurer un connecteur de source de données à l’aide des outils.
exl-id: d7cd412b-89ea-43a5-97b3-09944863bbee
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 0%

---

# Configurer un connecteur de source de données à partir de l’interface utilisateur

Les guides du Experience Manager sont fournis avec la variable **Sources de données** qui vous aide à configurer des connecteurs prêts à l’emploi pour les sources de données. Vous pouvez configurer les connecteurs client REST JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce, Elasticsearch et générique.

Pour configurer un connecteur, procédez comme suit :

1. Sélectionnez la variable **Adobe Experience Manager** Cliquez sur Lien dans la partie supérieure et sélectionnez Outils.
1. Sélectionner **Guides** dans la liste des outils.
1. Sélectionnez la variable **Sources de données** mosaïque. La variable **Sources de données** s’affiche. Vous pouvez afficher les sources de données connectées.

   Vous pouvez basculer entre les **Mode Liste** ou **Mosaïque** pour afficher les différentes sources de données connectées sous forme de liste ou de mosaïques.

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

   * **Nom**: saisissez le nom de la source de données.
   * Type d’authentification : sélectionnez le type d’authentification dans la liste déroulante. Par exemple, authentification de base nom d’utilisateur-mot de passe
   * **Nom d’utilisateur**: saisissez votre nom d’utilisateur.
   * **Password**: saisissez votre nom d’utilisateur et votre mot de passe.
   * **URL**: ajoutez l’URL de l’API.

1. Sélectionner **Tester la connexion**. Vous pouvez afficher la **Tester la connexion** activée uniquement une fois que vous avez ajouté les détails requis. Affichez un message de réussite si les détails de la connexion sont corrects. Sinon, vous pouvez afficher un message d’erreur.



1. Sélectionner **Enregistrer** en haut pour enregistrer le connecteur.     Afficher la variable **Enregistrer** activée une fois que vous avez renseigné tous les détails et que la connexion a réussi.


   Si le connecteur est enregistré correctement, vous pouvez afficher la source de données connectée sur la page.

## Fonctionnalités disponibles pour un connecteur

* Basculer entre les **Mode Liste** ou **Mosaïque**  pour afficher les différentes sources de données connectées sous forme de liste ou de mosaïques.
* Cochez la case correspondant à un seul connecteur. Cliquez sur **Tout sélectionner** pour sélectionner tous les connecteurs. Cliquez sur **Tout désélectionner** lorsque tous les connecteurs sont sélectionnés.

<img src="./assets/data-sources-features.png" alt= "fonctions des sources de données sur la page sources de données" width="800">

*Modification, reconnexion, duplication ou suppression d’un connecteur de source de données.*

Vous pouvez utiliser les fonctionnalités suivantes pour le connecteur sur la **Sources de données** page :

* **Modifier**: modifiez les détails de configuration du connecteur sélectionné.

* **Reconnecter**: reconnectez-vous à un connecteur déconnecté.

* **Dupliquer**: créez un nouveau connecteur en double à l’aide du connecteur actuel en tant que base. Le connecteur en double est créé avec un suffixe (tel que connectorname_1) par défaut. Par exemple, sample-élastique-search_1.
Vous affichez une erreur si le connecteur portant le même nom existe.

* **Supprimer**: supprimez le connecteur sélectionné.


Une fois que vous avez configuré la source de données, le connecteur est répertorié sous le **Panneau Sources de données** dans l’éditeur Web. Vous pouvez ensuite vous connecter à la source de données et insérer un fragment de contenu dans vos rubriques. Pour plus d’informations, voir [Insertion d’un fragment de contenu à partir de votre source de données](../user-guide/web-editor-content-snippet.md).
