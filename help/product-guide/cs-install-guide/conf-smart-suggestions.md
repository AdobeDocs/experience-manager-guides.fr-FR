---
title: Configuration des suggestions intelligentes pour la création
description: Découvrez comment configurer les suggestions intelligentes pour la création
source-git-commit: 1cdad275651b78d794ebc3f4ad9ead266ebeb0bd
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# Configuration des suggestions intelligentes optimisées par l’IA pour la création

En tant qu’administrateur, vous pouvez configurer la fonction Suggestions intelligentes pour les auteurs. Le service de suggestion dynamique est sécurisé par l’authentification basée sur l’authentification Adobe IMS. Intégrez votre environnement aux processus d’authentification sécurisés par jeton d’Adobe et commencez à utiliser la nouvelle fonctionnalité de suggestion dynamique. La configuration suivante vous aide à ajouter la variable **Configuration de l’IA** d’un onglet à un profil de dossier. Une fois l’ajout effectué, vous pouvez utiliser la fonction de suggestions intelligentes dans l’éditeur web.

## Création de configurations IMS dans la console Adobe Developer

Effectuez les étapes suivantes pour créer des configurations IMS dans la console Adobe Developer :
1. Launch [Console Adobe Developer](https://developer.adobe.com/console).
1. Une fois connecté à Developer Console, vous verrez le **Accueil** écran. La variable **Accueil** vous permet de trouver facilement des informations et des liens rapides, y compris des liens de navigation supérieure vers Projets et téléchargements.
1. Pour créer un projet vide, sélectionnez  **Créer un projet** de la  **Démarrage rapide** liens.
   ![Liens de démarrage rapide](assets/conf-ss-quick-start.png) {width="550" align="left"}
   *Créez un projet.*

1. Sélectionner  **Ajouter une API**  de la  **Projets** écran.  La variable **Ajout d’une API** s’affiche. Cet écran affiche toutes les API, événements et services disponibles pour les produits et technologies d’Adobe avec lesquels vous pouvez développer des applications.

1. Sélectionnez la variable **API de gestion I/O** pour l’ajouter à votre projet.
   ![API IO Management](assets/confi-ss-io-management.png)
   *Ajoutez l’API de gestion I/O à votre projet.*

1. Créer **Informations d’identification OAuth** et enregistrez-le.
   ![Mosaïque Informations d’identification OAuth dans la configuration de l’API](assets/conf-ss-OAuth-credential.png) {width="3000" align="left"}
   *Configurez les informations d’identification OAuth sur votre API.*

1. Dans le  **Projets** , choisissez **Serveur OAuth vers serveur** puis sélectionnez les informations d’identification nouvellement créées.

1. Sélectionnez la variable **OAuth serveur à serveur** lien pour afficher les informations d’identification de votre projet.

   ![identifiants connectés](assets/conf-ss-connected-credentials.png) {width="800" align="left"}

   *Connectez-vous au projet pour afficher les informations d’identification.*
1. Copiez les clés CLIENT_ID et CLIENT_SECRET .

Vous avez maintenant configuré les détails de l’authentification OAuth. Conservez ces deux clés à portée de main, car elles sont requises dans la section suivante.

### Ajout de la configuration IMS à l’environnement

Effectuez les étapes suivantes pour ajouter la configuration IMS à l’environnement :

1. Ouvrez Experience Manager, puis sélectionnez le programme contenant l&#39;environnement que vous souhaitez configurer.
1. Basculez vers le **Environnements** .
1. Sélectionnez le nom de l&#39;environnement que vous souhaitez configurer. Cela vous permet d’accéder à la page Informations sur l’environnement .
1. Basculez vers le **Configuration** .
1. Ajoutez les clés CLIENT_ID et CLIENT_SECRET comme illustré dans la capture d’écran suivante. Veillez à utiliser les mêmes noms et configuration que ceux présentés ci-dessous.
   ![Configuration de l’environnement](assets/conf-ss-environment.png) {width="800" align="left"}
   *Ajoutez les détails de configuration de l’environnement.*




Une fois que vous avez ajouté la configuration IMS à l’environnement, procédez comme suit pour lier ces propriétés à AEM Guides à l’aide d’OSGi :

1. Dans le code de projet Git de Cloud Manager, ajoutez les deux fichiers ci-dessous (pour le contenu du fichier, consultez [Annexe](#appendix)).

   * `com.adobe.fmdita.ims.service.ImsOauthUserAccountHeadersImpl.cfg.json`
   * `com.adobe.fmdita.smartsuggest.service.SmartSuggestConfigurationConsumer.cfg.json`
1. Assurez-vous que les fichiers nouvellement ajoutés sont couverts par votre `filter.xml`.
1. Validez et poussez vos modifications Git.
1. Exécutez le pipeline pour appliquer les modifications à l’environnement.

Une fois cette opération effectuée, vous devriez pouvoir utiliser la fonction de suggestions intelligentes .



## Annexe {#appendix}

**Fichier**:
`com.adobe.fmdita.ims.service.ImsOauthUserAccountHeadersImpl.cfg.json`

**Contenu**:

```
{
  "client.id": "$[secret:CLIENT_ID]",
  "client.secret": "$[secret:CLIENT_SECRET]",
  "ims.url": "https://ims-na1.adobelogin.com"
}
```

**Fichier**: `com.adobe.fmdita.smartsuggest.service.SmartSuggestConfigurationConsumer.cfg.json`

**Contenu**:

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
| instance.type | Type de l’instance AEM. Assurez-vous que cette valeur est unique pour chaque instance AEM sur laquelle les suggestions intelligentes sont configurées. Un cas d’utilisation serait de tester la fonctionnalité dans l’environnement intermédiaire avec &quot;instance.type&quot; = &quot;stage&quot; alors qu’en même temps, la fonctionnalité est également configurée sur &quot;prod&quot;. | Toute clé unique identifiant l’environnement. Uniquement *alphanumérique* sont autorisées. &quot;dev&quot;/&quot;stage&quot;/&quot;prod&quot;/&quot;test1&quot;/&quot;stage2&quot; | &quot;prod&quot; |

Une fois que vous avez configuré , l’icône de suggestions intelligentes s’affiche dans le panneau droit de l’éditeur web. Vous pouvez afficher la liste des suggestions intelligentes lorsque vous modifiez vos rubriques. Pour plus d’informations, voir [Suggestions intelligentes basées sur l’IA pour la création](../user-guide/authoring-ai-based-smart-suggestions.md) dans le Guide de l’utilisateur de Experience Manager.
