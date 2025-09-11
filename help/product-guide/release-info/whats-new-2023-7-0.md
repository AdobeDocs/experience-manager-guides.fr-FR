---
title: Notes de mise à jour | Nouveautés d’Adobe Experience Manager Guides version de juillet 2023
description: Découvrez les fonctionnalités nouvelles et améliorées de la version de juillet 2023 d’Adobe Experience Manager Guides as a Cloud Service
exl-id: 4b907729-4fbf-48ed-a2e1-014bd1101c73
feature: What's New
role: Leader
source-git-commit: 7d0ae0f13ab77a10beb89fcb0d8592b05c3828bd
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 0%

---

# Nouveautés de la version de juillet 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cet article couvre les nouvelles fonctionnalités et les fonctionnalités améliorées de la version de juillet 2023 d’Adobe Experience Manager Guides (plus tard appelée *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans cette version, voir [Notes de mise à jour](release-notes-2023-7-0.md).

## Se connecter à une source de données et insérer des données dans vos rubriques

Vous pouvez désormais vous connecter rapidement à vos sources de données à l’aide de connecteurs prêts à l’emploi d’AEM Guides. La connexion à une source de données vous permet de synchroniser vos informations avec la source et toutes les mises à jour des données sont répercutées automatiquement, ce qui fait d’AEM Guides un véritable hub de contenu. Cette fonctionnalité vous permet de gagner du temps et de limiter les efforts nécessaires pour ajouter ou copier manuellement les données.

Désormais, AEM Guides permet à votre administrateur de configurer les connecteurs prêts à l’emploi pour les bases de données JIRA et SQL (MySQL, PostgreSQL, SQL Server, SQLite). Ils peuvent également ajouter d’autres connecteurs en étendant les interfaces par défaut.

Une fois ajoutés, vous pouvez afficher les connecteurs configurés répertoriés sous le panneau **Sources de données** dans l’éditeur web.

![](assets/code-snippet-generator.png){width="300" align="left"}

Vous pouvez créer un générateur de fragments de contenu pour récupérer les données d’une source de données connectée. Vous pouvez ensuite insérer les données dans vos rubriques et les modifier.

Une fois que vous avez créé un générateur de fragment de contenu, vous pouvez le réutiliser pour insérer les données dans n’importe quelle rubrique. Pour plus d’informations, consultez la section [ Insérer un fragment de contenu à partir de votre source de données ](../user-guide/web-editor-content-snippet.md).



## Panneau de révision pour présenter les projets de révision et les tâches de révision actives

Désormais, AEM Guides rend vos avis plus transparents. Il fournit le panneau Révisions dans l’éditeur web. Le panneau Révisions affiche tous les projets de révision et les tâches de révision actives au sein des projets de révision dont vous faites partie.

En tant qu’auteur, cette fonctionnalité vous permet d’ouvrir facilement les tâches de révision, d’afficher les commentaires et d’adresser rapidement les commentaires dans une vue centralisée.
![](assets/active-review-task-comments.png){width="800" align="left"}
Pour plus d’informations, consultez la description de la fonctionnalité **Révision** dans la section [Panneau de gauche](../user-guide/web-editor-features.md#id2051EA0M0HS).


## Améliorations de la collection de cartes

Une collection de cartes permet d’organiser plusieurs cartes et de les publier par lots. De nombreuses nouvelles améliorations ont été apportées à la collection de cartes :

- Désormais, vous pouvez également ajouter des paramètres prédéfinis de sortie PDF natifs à une collection de mappages et les utiliser pour générer la sortie PDF.
- Vous pouvez afficher les paramètres prédéfinis de profil globaux et de dossier créés par votre administrateur et les utiliser pour générer la sortie PDF.
- Désormais, vous pouvez non seulement sélectionner un paramètre prédéfini individuel, mais vous pouvez également activer simultanément tous les paramètres prédéfinis de profil de dossier pour un plan DITA.
  ![](assets/edit-map-collection.png){width="800" align="left"}

Pour plus d’informations, consultez [Utilisation de la collecte de mappages pour la génération de sortie](../user-guide/generate-output-use-map-collection-output-generation.md).

## Possibilité d’accéder aux fichiers HTML temporaires lors de la génération de la sortie PDF native

Désormais, AEM Guides vous permet de télécharger les fichiers HTML temporaires créés lors de la génération de la sortie PDF native. Dans les paramètres prédéfinis de sortie , sélectionnez l’option pour télécharger les fichiers temporaires.  AEM Guides vous permet ensuite de télécharger les fichiers temporaires créés lors de la génération de la sortie à l’aide de ce paramètre prédéfini.

Cette fonctionnalité offre de meilleures informations sur le processus de génération avec un accès aux styles et mises en page intermédiaires. Elle vous aide également à corriger ou à modifier vos styles CSS en fonction de vos besoins.

![](assets/native-pdf-advanced-settings.png){width="800" align="left"}

Pour plus d’informations, voir [Création d’un paramètre prédéfini de sortie PDF](../web-editor/native-pdf-web-editor.md#create-output-preset).

## Publication basée sur les microservices pour générer une sortie HTML5 et personnalisée

Le nouveau microservice de publication vous permet d’exécuter simultanément d’importantes charges de travail de publication sur AEM Guides as a Cloud Service et d’exploiter la plateforme Adobe I/O Runtime sans serveur de pointe. Désormais, à l’aide du microservice, vous pouvez également générer la sortie HTML5 et la sortie personnalisée.
Vous pouvez exécuter plusieurs requêtes de publication et obtenir de meilleures performances pour générer ces formats de sortie.
Pour plus d’informations, consultez [Configuration de la publication basée sur les microservices pour AEM Guides as a Cloud Service](../knowledge-base/publishing/configure-microservices.md).

## Affichez les détails de la version d’AEM Guides dans la section À propos des informations

Désormais, avec les informations AEM **À propos**, vous pouvez également afficher les détails de la version d’AEM Guides. Vous pouvez afficher les détails de la version actuelle dans l’option **À propos** de l’**Aide** sur la page de navigation d’AEM.

![](assets/about-aem-help.png){width="800" align="left"}
