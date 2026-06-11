---
title: Configuration d’un connecteur Git dans AEM Guides
description: Découvrez comment configurer un Git dans Experience Manager Guides.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 5f626c210e74c6d11e2441f719cfbfeb33bf55c5
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 1%

---

# Création et configuration du connecteur Git à partir de l’interface utilisateur

Utilisez l’outil Sources de données de Experience Manager Guides pour créer et configurer un connecteur Git à partir de l’interface utilisateur. Une fois le connecteur configuré, vous pouvez l’utiliser pour importer du contenu d’un référentiel Git dans Experience Manager Guides.


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
   >* Les champs comportant le caractère * sont obligatoires. Par exemple, vous pouvez saisir les informations suivantes pour le connecteur Elasticsearch.

   * **Nom** : saisissez le nom de la source de données.
   * **Chemin d’accès racine AEM cible** : saisissez le chemin d’accès dans le référentiel AEM où le contenu importé depuis Git doit être stocké.
   * **Filtre de type de fichier (inclusion)** : indiquez les types de fichiers à inclure lors de l’importation.
   * **Chemin exclu (regex)** : spécifiez les modèles de chemin à exclure de l’importation.
   * **Type d’authentification** : sélectionnez le type d’authentification dans la liste déroulante. Actuellement, la méthode d’authentification **PAT (Personal Access Token)** est la seule prise en charge. Saisissez le chemin d’accès lors de la configuration du connecteur pour authentifier et accéder au référentiel Git.
   * **URL du référentiel** : saisissez l’URL du référentiel Git à partir de laquelle le contenu doit être importé.
   * **Branche** : renseignez la branche à utiliser pour l’importation de contenu.

1. Testez la connexion. Le bouton **Tester la connexion** n’est activé qu’après avoir saisi les détails requis. Si les détails de la connexion sont corrects, un message de réussite s’affiche. Dans le cas contraire, un message d’erreur s’affiche.

   ![](assets/git-connector-test-connection.png){width="600"}

1. Sélectionnez **Enregistrer** dans la partie supérieure pour enregistrer le connecteur.

   Le bouton Enregistrer n’est activé qu’une fois tous les détails requis saisis et la connexion établie. Si le connecteur est enregistré correctement, vous pouvez afficher le connecteur Github configuré sur la page **Sources de données**.

   ![](assets/git-connector-connected.png){width="600"}

