---
title: Configuration de l’aide dynamique pour rechercher du contenu
description: Découvrez comment configurer l’aide dynamique pour rechercher du contenu.
exl-id: b5836c02-027e-459a-a7f0-f7d631f999dc
TQID: https://experienceleague.adobe.com/CVY-v5lrpyLwIjmcxA6-p-4E0OuKZM14cvJomBqADz4
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 619
ht-degree: 0%

---

# Configurer l’aide intelligente optimisée par l’IA pour rechercher du contenu

En tant qu’administrateur, vous pouvez configurer la fonction d’aide dynamique pour les auteurs. Le service d’aide dynamique est sécurisé par l’authentification basée sur l’authentification Adobe IMS. Intégrez votre environnement aux workflows d’authentification basée sur les jetons sécurisés d’Adobe et commencez à utiliser la nouvelle fonctionnalité d’aide dynamique. Les configurations suivantes vous aident à ajouter l’onglet **Configuration de l’IA** à un profil de dossier. Une fois l’ajout effectué, vous pouvez utiliser la fonction Aide dynamique dans l’éditeur web.

## Création de configurations IMS dans Adobe Developer Console

Pour créer des configurations IMS dans Adobe Developer Console, procédez comme suit :

>[!NOTE]
>
>Si vous avez déjà créé un projet OAuth pour configurer la fonctionnalité de suggestions intelligentes ou la publication basée sur un microservice, vous pouvez ignorer les étapes suivantes pour créer le projet. Vous pouvez commencer par l’étape 8.

1. Lancer [&#128279;](https://developer.adobe.com/console).
1. Une fois la connexion à Developer Console établie, l’écran **Accueil** s’affiche. L’écran **Accueil** vous permet de trouver facilement des informations et des liens rapides, y compris des liens de navigation supérieure vers les projets et les téléchargements.
1. Pour créer un projet vide, sélectionnez **Créer un projet** parmi les liens **Démarrage rapide**.
   ![Liens de démarrage rapide &#x200B;](assets/conf-ss-quick-start.png) {width="550"}
   *Créer un projet.*

1. Sélectionnez **Ajouter une API** dans l’écran **Projets**.  L’écran **Ajouter une API** s’affiche. Cet écran affiche tous les API, événements et services disponibles pour les produits et technologies Adobe avec lesquels vous pouvez développer des applications.

1. Sélectionnez l’**API I/O Management** pour l’ajouter à votre projet.
   API ![IO Management](assets/confi-ss-io-management.png)
   *Ajoutez l’API I/O Management à votre projet.*

1. Créez des informations d’identification **OAuth** et enregistrez-les.
   ![&#x200B; Mosaïque d’informations d’identification OAuth dans la configuration de l’API &#x200B;](assets/conf-ss-OAuth-credential.png) {width="3000"}
   *Configurer les informations d’identification OAuth dans votre API.*

1. Dans l’onglet **Projets**, choisissez l’option **OAuth de serveur à serveur** puis sélectionnez les informations d’identification nouvellement créées.

1. Cliquez sur le lien **OAuth de serveur à serveur** pour afficher les informations d’identification de votre projet.

   ![&#x200B; informations d’identification connectées &#x200B;](assets/conf-ss-connected-credentials.png) {width="800"}

   *Connectez-vous au projet pour afficher les informations d’identification.*

1. Revenez à l’onglet **Projets** et sélectionnez **Présentation du projet** sur la gauche.

   <img src="assets/project-overview.png" alt="présentation du projet" width="500">

   *Commencer le nouveau projet.*

1. Cliquez sur le bouton **Télécharger** en haut pour télécharger le fichier JSON du service.

   <img src="assets/download-json.png" alt="télécharger json" width="500">

   *Téléchargez les détails du service JSON.*

Vous avez configuré les détails d’authentification OAuth et téléchargé les détails du service JSON. Gardez ce fichier à portée de main car il est requis dans la section suivante.

### Ajouter la configuration IMS à l’environnement

Pour ajouter la configuration IMS à l’environnement, procédez comme suit :

1. Ouvrez Experience Manager, puis sélectionnez votre programme, qui contient l’environnement à configurer.
1. Passez à l’onglet **Environnements**.
1. Sélectionnez le nom de l’environnement à configurer. Vous devriez y accéder à la page **Informations sur l’environnement**.
1. Passez à l’onglet **Configuration**.
1. Mettez à jour le champ JSON SERVICE_ACCOUNT_DETAILS . Assurez-vous que vous utilisez le même nom et la même configuration que dans la capture d’écran suivante.

![configuration du compte de service ims](assets/ims-service-account-config.png){width="800"}


*Ajoutez les détails de la configuration de l’environnement.*




Une fois que vous avez ajouté la configuration IMS à l’environnement, procédez comme suit pour lier ces propriétés à AEM Guides à l’aide d’OSGi :

1. Dans le code de votre projet Git Cloud Manager, ajoutez les deux fichiers ci-dessous (pour le contenu des fichiers, consultez l’[Annexe](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

1. Assurez-vous que les fichiers nouvellement ajoutés sont couverts par votre `filter.xml`.
1. Validez et envoyez vos modifications Git.
1. Exécutez le pipeline pour appliquer les modifications à l’environnement.

Une fois cette opération effectuée, vous devriez être en mesure d’utiliser la fonctionnalité **Aide intelligente**.



## Annexe {#appendix}

**Fichier** :
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Contenu** :

```
{
 "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
}
```


Une fois la configuration effectuée, l’icône **Aide dynamique** ![Aide dynamique](assets/smart-help-icon.svg) s’affiche dans le panneau droit de l’éditeur web. Sélectionnez l’icône pour afficher le panneau **Aide dynamique**.
Pour plus d’informations, consultez la section Aide intelligente optimisée par [IA pour rechercher du contenu](../user-guide/ai-based-smart-help.md) dans le Guide de l’utilisateur d’Experience Manager.
