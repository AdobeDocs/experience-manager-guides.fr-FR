---
title: Configuration de la publication basée sur Microsoft avec l’authentification OAuth pour AEM Guides as a Cloud Service
description: Découvrez comment configurer la publication basée sur un microservice avec l’authentification OAuth pour AEM Guides.
feature: Microservice in AEM Guides
role: Admin
exl-id: db0c83c7-1ece-4010-b214-f8d806d26bc9
source-git-commit: c51a372dc44921a489219f5ac99e3ad180ccc91d
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 0%

---

# Configuration de la publication sur microservice avec authentification OAuth

Le microservice de publication vous permet d’exécuter simultanément des charges de travail de publication volumineuses sur Experience Manager Guides as a Cloud Service et de tirer parti de la plate-forme sans serveur Adobe I/O Runtime de pointe.

Pour chaque demande de publication, Experience Manager Guides as a Cloud Service exécute un conteneur distinct qui se met à l’échelle horizontalement en fonction des demandes de l’utilisateur. Cela permet d’exécuter plusieurs requêtes de publication et d’obtenir de meilleures performances que leurs serveurs Adobe Experience Manager On-premise volumineux.

>[!NOTE]
>
> La publication basée sur les microservices dans Experience Manager Guides prend en charge les types de paramètres prédéfinis de sortie PDF (natif et basé sur DITA-OT), HTML5, JSON et PERSONNALISÉS.

Comme le service de publication dans le cloud est sécurisé par l’authentification basée sur OAuth d’Adobe IMS, effectuez les étapes suivantes pour intégrer leurs environnements aux workflows d’authentification par jeton sécurisés d’Adobe et commencer à utiliser la solution de publication évolutive basée sur le cloud.


## Création de configurations IMS dans Adobe Developer Console

**Rôle requis pour créer les configurations** : administrateur système

Effectuez les étapes suivantes pour créer des configurations IMS dans **Adobe Developer Console** :

>[!NOTE]
>
>Si vous avez déjà créé un projet OAuth pour configurer les suggestions intelligentes optimisées par l’IA pour la création, vous pouvez ignorer les étapes suivantes pour créer le projet.

1. Ouvrez **Developer Console**: `https://developer.adobe.com/console`.

1. Passez à l’onglet **Projets** depuis le haut.

   <img src="assets/projects-tab.png" alt="onglet projets" width="500">

   *Sélectionnez l’onglet **Projets**sur **Adobe Developer Console***

1. Pour créer un projet vide, sélectionnez **Projet vide** dans la liste déroulante **Créer un projet** .

   <img src="assets/create-new-project.png" alt="créer un projet" width="500">

   *Créez un projet vide.*

1. Sélectionnez **API** dans la liste déroulante **Ajouter au projet** pour ajouter l’API IO Management à votre projet.

   <img src="assets/add-project.png" alt="ajouter un projet" width="300">

   *Sélectionnez un projet d’API dans la liste déroulante.*

   <img src="assets/io-management-api.png" alt="Gestion des io" width="500">

   *Ajoutez l’API de gestion I/O à votre projet.*

1. Créez des informations d’identification OAuth et enregistrez-les.

   <img src="assets/microservice-api-oauth.png" alt="générer une paire de clés" width="500">

   *Configurez les informations d’identification OAuth sur votre API.*


1. Revenez à l’onglet **Projets** et sélectionnez **Aperçu du projet** sur la gauche.

   <img src="assets/project-overview.png" alt="présentation du projet" width="500">

   *Commencez le nouveau projet.*

1. Cliquez sur le bouton **Télécharger** en haut pour télécharger le service JSON.

   <img src="assets/download-json.png" alt="télécharger json" width="500">

   *Téléchargez les détails du service JSON.*

Vous avez configuré les détails de l’authentification OAuth et téléchargé les détails du service JSON. Conservez ce fichier à portée de main, car cela est nécessaire dans la section suivante.


## Ajout de la configuration IMS à l’environnement

>[!NOTE]
>
>Si vous avez déjà créé un projet OAuth pour les suggestions intelligentes, vous pouvez réutiliser le même projet pour les microservices et ignorer les étapes suivantes pour ajouter la configuration IMS à l’environnement.

### Mise à jour de la configuration existante (JWT   vers OAuth shift )

Si vous utilisez déjà un microservice pour la publication à l’aide de JWT (obsolète), effectuez les étapes suivantes pour mettre à jour les configurations :



1. Ouvrez **Experience Manager** et sélectionnez le programme contenant l&#39;environnement que vous souhaitez configurer.
1. Passez à l’onglet **Environnements** .
1. Sélectionnez le nom de l’environnement que vous souhaitez configurer. Cela devrait vous permettre d’accéder à la page **Environment Information**.
1. Passez à l’onglet **Configuration** .

1. Mettez à jour le champ JSON SERVICE_ACCOUNT_DETAILS avec le nouveau fichier JSON OAuth que vous avez téléchargé.
1. Supprimez le champ PRIVATE_KEY .



   <img src="assets/ims-service-account-config.png" alt="configuration du compte de service ims" width="500">

   *Mettez à jour les configurations d’environnement JWT existantes.*

### Première configuration

Pour utiliser un microservice de publication pour la première fois, mettez à jour les paramétrages selon les étapes suivantes :
1. Ouvrez **Experience Manager** et sélectionnez le programme contenant l&#39;environnement que vous souhaitez configurer.
1. Passez à l’onglet **Environnements** .
1. Sélectionnez le nom de l’environnement que vous souhaitez configurer. Cela devrait vous permettre d’accéder à la page **Environment Information**.
1. Passez à l’onglet **Configuration** .

1. Créez une configuration nommée SERVICE_ACCOUNT_DETAILS. Dans la valeur , ajoutez le contenu du fichier JSON OAuth que vous avez téléchargé à partir de la console de développement .


<img src="assets/jws-service-account-config.png" alt="configuration du compte de service ims" width="500">

*Configurez l&#39;environnement pour la première fois.*


### Modifications du code pour la première fois pour l’activation de publication basée sur un microservice

>[!NOTE]
>
> Ignorez les étapes suivantes si vous utilisez déjà la publication basée sur un microservice :

Une fois la configuration IMS ajoutée à l’environnement, procédez comme suit pour lier ces propriétés à Experience Manager Guides à l’aide d’OSGi :

1. Dans le code de votre projet Git Cloud Manager, ajoutez les deux fichiers suivants dans `/apps/fmditaCustom/config` (pour le contenu des fichiers, consultez [Annexe](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`
1. Assurez-vous que les fichiers nouvellement ajoutés sont couverts par votre `filter.xml`.
1. Validez et poussez vos modifications Git.
1. Exécutez le pipeline pour appliquer les modifications à l’environnement.

Une fois cette opération effectuée, vous pouvez utiliser la publication cloud basée sur un microservice.

## FAQ


1. Si les configurations OSGi pour utiliser le microservice sont activées, le processus de publication fonctionnera-t-il sur le serveur Experience Manager local avec la même base de code ?
   * Non, si l’indicateur `dxml.use.publish.microservice` est défini sur `true`, il recherche toujours des configurations de microservice. Définissez `dxml.use.publish.microservice` sur `false` pour que la publication fonctionne sur votre serveur local.
1. Quelle quantité de mémoire est allouée au processus DITA lors de l’utilisation de la publication basée sur un microservice ? Est-ce piloté par le profil et les paramètres DITA ?
   * Avec la publication basée sur un microservice, l’allocation de mémoire n’est pas pilotée par le profil et les paramètres DITA. La mémoire totale disponible sur le conteneur de services est de 8 Go, dont 6 Go sont attribués au processus DITA-OT.


## Annexe {#appendix}

**Fichier** :
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Contenu** :

```
{
"service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
}
```

**Fichier** : `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`

**Contenu** :
* `dxml.use.publish.microservice` : basculez pour activer la publication sur microservice à l’aide de DITA-OT
* `dxml.use.publish.microservice.native.pdf` : basculez pour activer la publication de PDF natifs en fonction du microservice.

```
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          jcr:primaryType="sling:OsgiConfig"
          dxml.publish.microservice.url="https://adobeioruntime.net/api/v1/web/543112-guidespublisher/default/publishercaller.json"
          dxml.use.publish.microservice="{Boolean}true"
          dxml.use.publish.microservice.native.pdf="{Boolean}true"
/>
```
