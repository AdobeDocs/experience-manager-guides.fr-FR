---
title: Configuration de l’assistant Guides pour la recherche de contenu
description: Découvrez comment configurer l’assistant de guides pour rechercher du contenu
source-git-commit: 8ac0ed6b867a3efdef750cb19ed4955a67def9ee
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 0%

---


# Configuration de l’assistant de guides optimisé par l’IA pour rechercher du contenu

En tant qu’administrateur, vous pouvez configurer la fonction de l’assistant de Guides pour les auteurs. Le service d’assistant de guides est sécurisé par l’authentification basée sur l’authentification Adobe IMS. Intégrez votre environnement aux processus d’authentification sécurisés par jeton d’Adobe et commencez à utiliser la nouvelle fonctionnalité de l’assistant de guides. Les configurations suivantes vous permettent d’ajouter la variable **Configuration de l’IA** à un profil de dossier. Une fois l’ajout effectué, vous pouvez utiliser la fonction de l’assistant de Guides dans l’éditeur web.

## Création de configurations IMS dans la console Adobe Developer

Effectuez les étapes suivantes pour créer des configurations IMS dans la console Adobe Developer :

>[!NOTE]
>
>Si vous avez déjà créé un projet OAuth pour configurer la fonction de suggestions intelligentes ou la publication basée sur un microservice, vous pouvez ignorer les étapes suivantes pour créer le projet.

1. Launch [Console Adobe Developer](https://developer.adobe.com/console).
1. Une fois connecté à Developer Console, vous verrez le **Accueil** écran. La variable **Accueil** vous permet de trouver facilement des informations et des liens rapides, y compris des liens de navigation supérieure vers Projets et téléchargements.
1. Pour créer un projet vide, sélectionnez **Créer un projet** de la **Démarrage rapide** liens.
   ![Liens de démarrage rapide](assets/conf-ss-quick-start.png) {width="550" align="left"}
   *Créez un projet.*

1. Sélectionner **Ajouter une API** de la **Projets** écran.  La variable **Ajout d’une API** s’affiche. Cet écran affiche toutes les API, événements et services disponibles pour les produits et technologies d’Adobe avec lesquels vous pouvez développer des applications.

1. Sélectionnez la variable **API de gestion I/O** pour l’ajouter à votre projet.
   ![API IO Management](assets/confi-ss-io-management.png)
   *Ajoutez l’API de gestion I/O à votre projet.*

1. Créer **Informations d’identification OAuth** et enregistrez-le.
   ![Mosaïque Informations d’identification OAuth dans la configuration de l’API](assets/conf-ss-OAuth-credential.png) {width="3000" align="left"}
   *Configurez les informations d’identification OAuth sur votre API.*

1. Dans le  **Projets** , choisissez la variable **Serveur OAuth vers serveur** puis sélectionnez les informations d’identification nouvellement créées.

1. Sélectionnez la variable **OAuth serveur à serveur** lien pour afficher les informations d’identification de votre projet.

   ![identifiants connectés](assets/conf-ss-connected-credentials.png) {width="800" align="left"}

   *Connectez-vous au projet pour afficher les informations d’identification.*

1. Revenez au **Projets** et sélectionnez **Présentation du projet** sur la gauche.

   <img src="assets/project-overview.png" alt="présentation du projet" width="500">

   *Commencez le nouveau projet.*

1. Cliquez sur le bouton **Télécharger** sur la partie supérieure pour télécharger le service JSON.

   <img src="assets/download-json.png" alt="télécharger json" width="500">

   *Téléchargez les détails du service JSON.*

Vous avez configuré les détails de l’authentification OAuth et téléchargé les détails du service JSON. Conservez ce fichier à portée de main, car cela est nécessaire dans la section suivante.

### Ajout de la configuration IMS à l’environnement

Effectuez les étapes suivantes pour ajouter la configuration IMS à l’environnement :

1. Ouvrez Experience Manager, puis sélectionnez votre programme, qui contient l’environnement que vous souhaitez configurer.
1. Basculez vers le **Environnements** .
1. Sélectionnez le nom de l&#39;environnement que vous souhaitez configurer. Cela devrait vous permettre d’accéder au **Informations sur l’environnement** page.
1. Basculez vers le **Configuration** .
1. Mettez à jour le champ JSON SERVICE_ACCOUNT_DETAILS . Assurez-vous d’utiliser le même nom et la même configuration que ceux indiqués dans la capture d’écran suivante.

![configuration du compte de service ims](assets/ims-service-account-config.png){width="800" align="left"}


*Ajoutez les détails de configuration de l’environnement.*




Une fois que vous avez ajouté la configuration IMS à l’environnement, procédez comme suit pour lier ces propriétés à AEM Guides à l’aide d’OSGi :

1. Dans le code de votre projet Git Cloud Manager, ajoutez les deux fichiers ci-dessous (pour le contenu du fichier, consultez [Annexe](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

1. Assurez-vous que les fichiers nouvellement ajoutés sont couverts par votre `filter.xml`.
1. Validez et poussez vos modifications Git.
1. Exécutez le pipeline pour appliquer les modifications à l’environnement.

Une fois cette opération effectuée, vous devriez pouvoir utiliser la variable **Assistant de guides** fonction .



## Annexe {#appendix}

**Fichier**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Contenu**:

```
{
 "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
}
```


Une fois que vous avez configuré la variable **Assistant de guides** ![Assistant de guides](assets/guides-assistant-icon.svg) s’affiche dans le panneau de droite de l’éditeur Web. Sélectionnez l’icône pour afficher le **Assistant de guides** du panneau.
Pour plus d’informations, voir la [Assistant de guides optimisé par l’IA pour la recherche de contenu](../user-guide/ai-based-guides-assistant.md) dans le Guide de l’utilisateur de Experience Manager.
