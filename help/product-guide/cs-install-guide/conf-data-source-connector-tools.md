---
title: Configuration d’un connecteur de source de données à l’aide d’outils
description: Découvrez comment configurer un connecteur de source de données à l’aide des outils.
exl-id: d7cd412b-89ea-43a5-97b3-09944863bbee
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: acd16f23a7b3023a62b3c15007b03d4f3b2cfb4f
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 0%

---

# Configurer un connecteur de source de données à partir de l’interface utilisateur

Les guides du Experience Manager sont fournis avec la variable **Sources de données** qui vous aide à configurer des connecteurs prêts à l’emploi pour les sources de données. Vous pouvez configurer les connecteurs client REST JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce, Elasticsearch et générique.

Outre ces connecteurs prêts à l’emploi, Experience Manager Guides fournit les connecteurs pour les sources de données Salsify, Akeneo et Microsoft Azure DevOps (ADO). Vous pouvez les télécharger et les installer. Les utilisateurs peuvent ensuite configurer ces connecteurs.

Vous pouvez également vous connecter aux fichiers de données JSON à l’aide d’un connecteur de fichier. Téléchargez le fichier JSON sur votre ordinateur ou parcourez-le à partir des ressources Adobe Experience Manager. Créez ensuite des fragments de contenu ou des rubriques à l’aide des générateurs.

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
   >
   >* Survol <img src="./assets/info-details.svg" alt= "icône info" width="25"> près du champ pour en afficher plus de détails.
   > * Les champs avec * sont obligatoires. Par exemple, vous pouvez saisir les détails suivants pour le connecteur Elasticsearch.

   * **Nom**: saisissez le nom de la source de données.
   * **Type d’authentification**: sélectionnez le type d’authentification dans la liste déroulante. Par exemple, authentification de base nom d’utilisateur-mot de passe
   * **Nom d’utilisateur**: saisissez votre nom d’utilisateur.
   * **Password**: saisissez votre nom d’utilisateur et votre mot de passe.
   * **URL**: ajoutez l’URL de l’API.


1. Sélectionnez la variable **Exclure les modèles d’usine** pour exclure les modèles d’usine de l’utilisation pour la génération de rubriques et de fragments de code. Ils n’apparaîtront pas sous la propriété **Modèle de mappage de données** dans la liste déroulante  **Ajout d’un générateur de fragments de contenu** ou le **Ajout d’un générateur de rubrique** de la boîte de dialogue


1. Sélectionner **Tester la connexion**. Vous pouvez afficher la **Tester la connexion** activée uniquement une fois que vous avez ajouté les détails requis. Affichez un message de réussite si les détails de la connexion sont corrects. Sinon, vous pouvez afficher un message d’erreur.



1. Sélectionner **Enregistrer** en haut pour enregistrer le connecteur.     Afficher la variable **Enregistrer** activée une fois que vous avez renseigné tous les détails et que la connexion a réussi.


   Si le connecteur est enregistré correctement, vous pouvez afficher la source de données connectée sur la page.

**Connexion à plusieurs ressources**

Vous pouvez ajouter ou utiliser plusieurs ressources en fonction de différentes URL pour certains connecteurs tels que Generic REST Client, Salsify, Akeneo et Microsoft Azure DevOps Board (ADO). Ensuite, connectez-vous avec eux pour créer des fragments de contenu ou des rubriques à l’aide des générateurs.

Pour créer une ressource, procédez comme suit :

1. Sélectionner ![icône ajouter](assets/Add_icon.svg) dans le **Section de ressource URL** pour ajouter une ressource pour chaque URL.
1. Configurez tous les détails dans la variable **Ajouter une ressource** de la boîte de dialogue
1. Cliquez sur **Ajouter**.
1. Vous pouvez modifier ![icône de modification](assets/edit_pencil_icon.svg) ou supprimer ![delete](assets/Delete_icon.svg) la ressource de la liste des ressources d’URL.

1. Vous pouvez également utiliser les ressources par défaut disponibles pour les sources de données telles que Salsify, Akeneo et Microsoft ADO. Désactivez les options de la ressource que vous ne souhaitez pas configurer pour une source de données.

Vous pouvez ainsi récupérer rapidement des données d’une des ressources d’une source de données spécifique dans un seul fragment de contenu ou une seule rubrique.

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
