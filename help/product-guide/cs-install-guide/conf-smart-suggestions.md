---
title: Configuration des suggestions intelligentes pour la création
description: Découvrez comment configurer les suggestions intelligentes pour la création
exl-id: a595ca1f-0123-40d3-a79c-a066bc6517b4
source-git-commit: d3e0c475ebd50a2664ea45c293d34b3a10772633
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 1%

---

# Configuration des suggestions intelligentes optimisées par l’IA pour la création

En tant qu’administrateur, vous pouvez configurer la fonction Suggestions intelligentes pour les auteurs. Le service de suggestion dynamique est sécurisé par l’authentification basée sur l’authentification Adobe IMS. Intégrez votre environnement aux processus d’authentification sécurisés par jeton d’Adobe et commencez à utiliser la nouvelle fonctionnalité de suggestion dynamique. La configuration suivante vous aide à ajouter l’onglet **Configuration de l’IA** au profil de dossier. Une fois l’ajout effectué, vous pouvez utiliser la fonction de suggestions intelligentes dans l’éditeur web.

## Création de configurations IMS dans Adobe Developer Console

Effectuez les étapes suivantes pour créer des configurations IMS dans Adobe Developer Console :

>[!NOTE]
>
>Si vous avez déjà créé un projet OAuth pour configurer la publication basée sur un microservice, vous pouvez ignorer les étapes suivantes pour créer le projet.

1. Lancez [Adobe Developer Console](https://developer.adobe.com/console).
1. Après vous être connecté à Developer Console, vous verrez l’écran **Accueil**. L’écran **Accueil** vous permet de trouver facilement des informations et des liens rapides, y compris des liens de navigation supérieure vers Projets et téléchargements.
1. Pour créer un projet vide, sélectionnez **Créer un projet** à partir des liens **Démarrage rapide**.
   ![Liens de démarrage rapide](assets/conf-ss-quick-start.png) {width="550" align="left"}
   *Créez un projet.*

1. Sélectionnez **Ajouter une API** dans l’écran **Projets** .  L’écran **Ajouter une API** s’affiche. Cet écran affiche toutes les API, événements et services disponibles pour les produits et technologies d’Adobe avec lesquels vous pouvez développer des applications.

1. Sélectionnez l’ **API de gestion I/O** pour l’ajouter à votre projet.
   ![API de gestion des E/S](assets/confi-ss-io-management.png)
   *Ajoutez l’API de gestion I/O à votre projet.*

1. Créez un nouveau **OAuth credential** et enregistrez-le.

   ![Mosaïque d’informations d’identification OAuth dans la configuration de l’API](assets/conf-ss-OAuth-credential.png)

   *Configurez les informations d’identification OAuth sur votre API.*

1. Dans l’onglet **Projets** , sélectionnez l’option **OAuth Server to Server** , puis sélectionnez les informations d’identification nouvellement créées.

1. Sélectionnez le lien **OAuth Server-to-Server** pour afficher les informations d’identification de votre projet.

   ![informations d’identification connectées](assets/conf-ss-connected-credentials.png) {width="800" align="left"}

   *Connectez-vous au projet pour afficher les informations d’identification.*

1. Revenez à l’onglet **Projets** et sélectionnez **Aperçu du projet** sur la gauche.

   <img src="assets/project-overview.png" alt="présentation du projet" width="500">

   *Commencez le nouveau projet.*

1. Cliquez sur le bouton **Télécharger** en haut pour télécharger le service JSON.

   <img src="assets/download-json.png" alt="télécharger json" width="500">

   *Téléchargez les détails du service JSON.*

Vous avez configuré les détails de l’authentification OAuth et téléchargé les détails du service JSON. Conservez ce fichier à portée de main, car cela est nécessaire dans la section suivante.

### Ajout de la configuration IMS à l’environnement

Effectuez les étapes suivantes pour ajouter la configuration IMS à l’environnement :

1. Ouvrez Experience Manager, puis sélectionnez le programme contenant l&#39;environnement que vous souhaitez configurer.
1. Passez à l’onglet **Environnements** .
1. Sélectionnez le nom de l&#39;environnement que vous souhaitez configurer. Cela devrait vous permettre d’accéder à la page **Environment Information**.
1. Passez à l’onglet **Configuration** .
1. Mettez à jour le champ JSON SERVICE_ACCOUNT_DETAILS . Assurez-vous d’utiliser le même nom et la même configuration que ceux indiqués dans la capture d’écran suivante.

![Configuration du compte de service ims](assets/ims-service-account-config.png){width="800" align="left"}


*Ajoutez les détails de configuration de l&#39;environnement.*




Une fois la configuration IMS ajoutée à l’environnement, procédez comme suit pour lier ces propriétés à AEM Guides à l’aide d’OSGi :

1. Dans le code de projet Git de votre gestionnaire de cloud, ajoutez les deux fichiers ci-dessous (pour le contenu du fichier, consultez [Annexe](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.smartsuggest.service.SmartSuggestConfigurationConsumer.cfg.json`
1. Assurez-vous que les fichiers nouvellement ajoutés sont couverts par votre `filter.xml`.
1. Validez et poussez vos modifications Git.
1. Exécutez le pipeline pour appliquer les modifications à l’environnement.

Une fois cette opération effectuée, vous devriez pouvoir utiliser la fonction de suggestions intelligentes .



## Annexe {#appendix}

**Fichier** :
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Contenu** :

```
{
 "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
}
```

**Fichier** : `com.adobe.fmdita.smartsuggest.service.SmartSuggestConfigurationConsumer.cfg.json`

**Contenu** :

```
{
  "smart.suggestion.flag":true,
  "conref.inline.threshold":0.6,
  "conref.block.threshold":0.7,
  "emerald.url":"https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1",
  "instance.type":"prod"
}
```

## Détails de la configuration des suggestions intelligentes

| Clé | Description | Valeurs autorisées | Valeur par défaut |
|---|---|---|---|
| smart.suggestion.flag | Contrôle si les suggestions intelligentes sont activées ou non | true/false | false |
| conref.inline.threshold | Seuil contrôlant la précision/le rappel des suggestions récupérées pour la balise que l’utilisateur saisit actuellement. | Toute valeur comprise entre -1.0 et 1.0. | 0,6 |
| conref.block.threshold | Seuil contrôlant la précision/le rappel des suggestions récupérées pour les balises dans l’ensemble du fichier. | Toute valeur comprise entre -1.0 et 1.0. | 0,7 |
| emerald.url | Point de terminaison de la base de données vectorielle Emerald | [https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1](https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1) | [https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1](https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1) |
| instance.type | Type de l’instance AEM. Assurez-vous que cette valeur est unique pour chaque instance AEM sur laquelle les suggestions intelligentes sont configurées. Un cas d’utilisation serait de tester la fonctionnalité dans l’environnement intermédiaire avec &quot;instance.type&quot; = &quot;stage&quot; alors qu’en même temps, la fonctionnalité est également configurée sur &quot;prod&quot;. | Toute clé unique identifiant l’environnement. Seules les valeurs *alphanumérique* sont autorisées. &quot;dev&quot;/&quot;stage&quot;/&quot;prod&quot;/&quot;test1&quot;/&quot;stage2&quot; | &quot;prod&quot; |

Une fois que vous avez configuré , l’icône de suggestions intelligentes s’affiche dans le panneau droit de l’éditeur web. Vous pouvez afficher la liste des suggestions intelligentes lorsque vous modifiez vos rubriques. Pour plus d’informations, consultez la section [Suggestions intelligentes basées sur l’IA pour la création](../user-guide/authoring-ai-based-smart-suggestions.md) du Guide de l’utilisateur Experience Manager.
