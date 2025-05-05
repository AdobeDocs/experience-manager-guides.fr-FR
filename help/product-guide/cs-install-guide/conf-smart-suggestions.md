---
title: Configurer l’assistant AI pour l’aide et la création intelligentes
description: Découvrez comment configurer l’assistant AI dans Experience Manager Guides
exl-id: a595ca1f-0123-40d3-a79c-a066bc6517b4
source-git-commit: 018bd7c7bc3bb9161e5bedd42d50a5c501ca2919
workflow-type: tm+mt
source-wordcount: '880'
ht-degree: 0%

---

# Configuration de l’assistant d’IA

En tant qu’administrateur, vous pouvez configurer la fonctionnalité Assistant AI dans Experience Manager Guides. L’assistant AI est sécurisé par l’authentification basée sur l’authentification Adobe IMS. Intégrez votre environnement aux workflows d’authentification sécurisés basés sur les jetons d’Adobe et commencez à utiliser la fonctionnalité Assistant IA. La configuration suivante vous permet d’ajouter l’onglet **Configuration de l’IA** au profil de dossier. Une fois l’ajout effectué, vous pouvez utiliser la fonction Assistant AI dans Experience Manager Guides.

Effectuez les étapes suivantes pour configurer l’assistant AI :

1. [Création d’une configuration IMS dans Adobe Developer Console](#create-ims-configurations-in-adobe-developer-console).
2. [Ajout de configurations IMS à l’environnement](#add-ims-configuration-to-the-environment)
3. [Activer l’indicateur d’IA dans l’environnement](#enable-ai-flag-in-the-environment)
4. [Application des modifications à l’environnement](#apply-changes-to-the-environment)
5. [Activer l’assistant AI dans le profil de dossier](#enable-ai-assistant-in-folder-profile)
6. [Configuration des suggestions intelligentes dans le profil de dossier](./conf-folder-level.md#configure-ai-assistant-for-smart-help-and-authoring)

## Création de configurations IMS dans Adobe Developer Console

Pour créer des configurations IMS dans Adobe Developer Console, procédez comme suit :

>[!NOTE]
>
>Si vous avez déjà créé un projet OAuth pour configurer la publication basée sur un microservice, vous pouvez ignorer les étapes suivantes pour créer le projet.

1. Lancer [Adobe Developer Console](https://developer.adobe.com/console).
1. Une fois la connexion à Developer Console établie, l’écran **Accueil** s’affiche. L’écran **Accueil** vous permet de trouver facilement des informations et des liens rapides, y compris des liens de navigation supérieure vers les projets et les téléchargements.
1. Pour créer un projet vide, sélectionnez **Créer un projet** parmi les liens **Démarrage rapide**.
   ![Liens de démarrage rapide](assets/conf-ss-quick-start.png) {width="550" align="left"}
   *Créer un projet.*

1. Sélectionnez **Ajouter une API** dans l’écran **Projets**.  L’écran **Ajouter une API** s’affiche. Cet écran affiche tous les API, événements et services disponibles pour les produits et technologies Adobe avec lesquels vous pouvez développer des applications.

1. Sélectionnez l’**API I/O Management** pour l’ajouter à votre projet.
   ![API IO Management](assets/confi-ss-io-management.png)
   *Ajoutez l’API I/O Management à votre projet.*

1. Créez des informations d’identification **OAuth** et enregistrez-les.

   ![ Mosaïque d’informations d’identification OAuth dans la configuration de l’API ](assets/conf-ss-OAuth-credential.png)

   *Configurer les informations d’identification OAuth dans votre API.*

1. Dans l’onglet **Projets**, choisissez l’option **OAuth de serveur à serveur** puis sélectionnez les informations d’identification nouvellement créées.

1. Cliquez sur le lien **OAuth de serveur à serveur** pour afficher les informations d’identification de votre projet.

   ![ informations d’identification connectées ](assets/conf-ss-connected-credentials.png) {width="800" align="left"}

   *Connectez-vous au projet pour afficher les informations d’identification.*

1. Revenez à l’onglet **Projets** et sélectionnez **Présentation du projet** sur la gauche.

   <img src="assets/project-overview.png" alt="présentation du projet" width="500">

   *Commencer le nouveau projet.*

1. Sélectionnez le bouton **Télécharger** en haut pour télécharger le fichier JSON du service.

   <img src="assets/download-json.png" alt="télécharger json" width="500">

   *Téléchargez les détails du service JSON.*

Vous avez configuré les détails d’authentification OAuth et téléchargé les détails du service JSON. Gardez ce fichier à portée de main car il est requis dans la section suivante.

## Ajouter la configuration IMS à l’environnement

Pour ajouter la configuration IMS à l’environnement, procédez comme suit :

1. Ouvrez Experience Manager, puis sélectionnez votre programme contenant l’environnement à configurer.
1. Passez à l’onglet **Environnements**.
1. Sélectionnez le nom de l’environnement à configurer. Vous devriez y accéder à la page **Informations sur l’environnement**.
1. Passez à l’onglet **Configuration**.
1. Mettez à jour le champ JSON SERVICE_ACCOUNT_DETAILS . Assurez-vous que vous utilisez le même nom et la même configuration que dans la capture d’écran suivante.

   ![configuration du compte de service ims](assets/ims-service-account-config.png){width="800" align="left"}

## Activer l’indicateur d’IA dans l’environnement

Pour activer la fonctionnalité Assistant d’IA dans l’interface utilisateur de Experience Manager Guides, ajoutez l’indicateur `ENABLE_GUIDES_AI` dans l’environnement.

Assurez-vous d’utiliser le même nom et la même configuration que ceux fournis dans la capture d’écran suivante.

![](assets/conf-folder-ai-assistant-enable.png){width="800" align="left"}

Définir l’indicateur sur **true** active la fonctionnalité, tandis que le définir sur **false** la désactive.

## Application des modifications à l’environnement

Une fois que vous avez ajouté la configuration IMS et activé l’indicateur de l’assistant AI à l’environnement, procédez comme suit pour lier ces propriétés à AEM Guides à l’aide d’OSGi :

1. Dans le code de votre projet Git Cloud Manager, ajoutez les deux fichiers ci-dessous (pour le contenu des fichiers, consultez l’[Annexe](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.guides.ai.config.service.AiConfigImpl.cfg.json`
1. Assurez-vous que les fichiers nouvellement ajoutés sont couverts par votre `filter.xml`.
1. Validez et envoyez vos modifications Git.
1. Exécutez le pipeline pour appliquer les modifications à l’environnement.

## Activer l’assistant AI dans le profil de dossier

Une fois les modifications de configuration appliquées, activez la fonction Assistant AI pour le profil de dossier souhaité.

Pour plus d’informations, consultez la section [Connaître les fonctionnalités de l’éditeur](../user-guide/web-editor-features.md).

![](assets/conf-folder-ai-assistant-enable-settings.png){width="300" align="left"}

## Configuration des suggestions intelligentes dans le profil de dossier

Après avoir activé la fonction Assistant d’IA, configurez la fonctionnalité Suggestions intelligentes dans le profil de dossier.

Pour plus d’informations, voir [Configuration des suggestions intelligentes dans le profil de dossier](./conf-folder-level.md#configure-ai-assistant-for-smart-help-and-authoring).


## Annexe {#appendix}

**Fichier** :
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Contenu** :

```
{
 "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]"
}
```

**Fichier** : `com.adobe.guides.ai.config.service.AiConfigImpl.cfg.json`

**Contenu** :

```
{
  "conref.inline.threshold":0.6,
  "conref.block.threshold":0.7,
  "related.link.threshold":0.5,
  "emerald.url":"https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1",
  "instance.type":"prod",
  "chat.url":"https://aem-guides-ai.adobe.io"
}
```

## Détails de configuration de l’assistant AI

| Clé | Description | Valeurs autorisées | Valeur par défaut |
|---|---|---|---|
| conref.inline.threshold | Seuil qui contrôle la précision/le rappel des suggestions récupérées pour la balise que l’utilisateur saisit actuellement. | Toute valeur comprise entre -1.0 et 1.0. | 0,6 |
| conref.block.threshold | Seuil qui contrôle la précision/le rappel des suggestions récupérées pour les balises dans l’ensemble du fichier. | Toute valeur comprise entre -1.0 et 1.0. | 0,7 |
| emerald.url | Point d’entrée de la base de données vectorielle de suggestions intelligentes | [https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1](https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1) | [https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1](https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1) |
| chat.url | Point d’entrée du service d’assistant d’IA | [https://aem-guides-ai.adobe.io](https://aem-guides-ai.adobe.io) | [https://aem-guides-ai.adobe.io](https://aem-guides-ai.adobe.io) |
| instance.type | Type de l’instance AEM. Assurez-vous qu’il est unique pour chaque instance AEM sur laquelle les suggestions intelligentes sont configurées. Un cas d’utilisation consisterait à tester la fonctionnalité dans un environnement d’évaluation avec « instance.type » = « stage », tandis qu’en même temps, la fonctionnalité serait également configurée sur « prod ». | Toute clé unique identifiant l’environnement. Seules les valeurs *alphanumériques* sont autorisées. « dev »/« stage »/« prod »/« test1 »/« stage2 » | « prod » |

Une fois que vous avez configuré, l’icône de l’assistant AI s’affiche sur la page d’accueil et dans l’éditeur du Experience Manager Guides. Pour plus d’informations, consultez la section [Assistant AI](../user-guide/ai-assistant.md) dans le Guide de l’utilisateur d’Experience Manager.
