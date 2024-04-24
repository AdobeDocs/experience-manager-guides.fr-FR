---
title: Configuration de la publication basée sur Microservice avec l’authentification OAuth pour AEM Guides as a Cloud Service
description: Découvrez comment configurer la publication basée sur un microservice avec l’authentification OAuth pour AEM Guides.
feature: Microservice in AEM Guides
role: User, Admin
source-git-commit: 4c7421391922d276ef82515fb4b1cbdc2397e4ce
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 0%

---

# Configuration de la publication sur microservice avec authentification OAuth

Le microservice de publication vous permet d’exécuter simultanément des charges de travail de publication volumineuses sur Experience Manager Guides as a Cloud Service et de tirer parti de la plate-forme sans serveur Adobe I/O Runtime de pointe.

Pour chaque demande de publication, les guides du Experience Manager as a Cloud Service exécutent un conteneur distinct qui se met à l’échelle horizontalement en fonction des demandes de l’utilisateur. Cela permet d’exécuter plusieurs requêtes de publication et d’obtenir de meilleures performances que leurs serveurs Adobe Experience Manager On-premise volumineux.

>[!NOTE]
>
> La publication basée sur les microservices dans les guides de Experience Manager prend en charge les types de paramètres prédéfinis de sortie PDF (natifs et basés sur DITA-OT), HTML5, JSON et PERSONNALISÉS.

Comme le service de publication dans le cloud est sécurisé par l’authentification basée sur OAuth d’Adobe IMS, effectuez les étapes suivantes pour intégrer leurs environnements aux workflows d’authentification par jeton sécurisés d’Adobe et commencer à utiliser la solution de publication évolutive basée sur le cloud.


## Création de configurations IMS dans la console Adobe Developer

**Rôle requis pour créer les configurations**: administrateur système

Effectuez les étapes suivantes pour créer des configurations IMS dans **Console Adobe Developer**:

>[!NOTE]
>
>Si vous avez déjà créé un projet OAuth pour configurer les suggestions intelligentes optimisées par l’IA pour la création, vous pouvez ignorer les étapes suivantes pour créer le projet.

1. Ouvrir **Developer Console**: `https://developer.adobe.com/console`.

1. Basculez vers le **Projets** dans la partie supérieure.

   <img src="assets/projects-tab.png" alt="onglet projets" width="500">

   *Sélectionnez la variable **Projets**sur l’**Console Adobe Developer***

1. Pour créer un projet vide, sélectionnez **Projet vide** de la **Créer un projet** menu déroulant.

   <img src="assets/create-new-project.png" alt="créer un projet" width="500">

   *Créez un projet vide.*

1. Sélectionner **API** de la **Ajouter au projet** pour ajouter l’API de gestion des E/S à votre projet.

   <img src="assets/add-project.png" alt="ajouter un projet" width="300">

   *Sélectionnez un projet API dans la liste déroulante.*

   <img src="assets/io-management-api.png" alt="Gestion des io" width="500">

   *Ajoutez l’API de gestion I/O à votre projet.*

1. Créez des informations d’identification OAuth et enregistrez-les.

   <img src="assets/microservice-api-oauth.png" alt="générer une paire de clés" width="500">

   *Configurez les informations d’identification OAuth sur votre API.*


1. Revenez au **Projets** et sélectionnez **Présentation du projet** sur la gauche.

   <img src="assets/project-overview.png" alt="présentation du projet" width="500">

   *Commencez le nouveau projet.*

1. Cliquez sur le bouton **Télécharger** sur la partie supérieure pour télécharger le service JSON.

   <img src="assets/download-json.png" alt="télécharger json" width="500">

   *Téléchargez les détails du service JSON.*

Vous avez configuré les détails de l’authentification OAuth et téléchargé les détails du service JSON. Conservez ce fichier à portée de main, car cela est nécessaire dans la section suivante.


## Ajout de la configuration IMS à l’environnement

>[!NOTE]
>
>Si vous avez déjà créé un projet OAuth pour les suggestions intelligentes, vous pouvez réutiliser le même projet pour les microservices et ignorer les étapes suivantes pour ajouter la configuration IMS à l’environnement.

### Mettre à jour la configuration existante

Si vous utilisez déjà un microservice pour la publication à l’aide de JWT (obsolète), effectuez les étapes suivantes pour mettre à jour les configurations :



1. Ouvrir **Experience Manager** et sélectionnez le programme contenant l&#39;environnement que vous souhaitez configurer.
1. Basculez vers le **Environnements** .
1. Sélectionnez le nom de l’environnement que vous souhaitez configurer. Cela devrait vous permettre d’accéder au **Informations sur l’environnement** page.
1. Basculez vers le **Configuration** .

1. Mettez à jour le champ JSON SERVICE_ACCOUNT_DETAILS avec le nouveau fichier JSON OAuth que vous avez téléchargé.
1. Supprimez le champ PRIVATE_KEY .



   <img src="assets/ims-service-account-config.png" alt="configuration du compte de service ims" width="500">

   *Mettez à jour les configurations d’environnement JWT existantes.*

### Première configuration

Pour utiliser un microservice de publication pour la première fois, mettez à jour les paramétrages selon les étapes suivantes :
1. Ouvrir **Experience Manager** et sélectionnez le programme contenant l&#39;environnement que vous souhaitez configurer.
1. Basculez vers le **Environnements** .
1. Sélectionnez le nom de l’environnement que vous souhaitez configurer. Cela devrait vous permettre d’accéder au **Informations sur l’environnement** page.
1. Basculez vers le **Configuration** .

1. Mettez à jour le champ JSON SERVICE_ACCOUNT_DETAILS . Assurez-vous d’utiliser le même nom et la même configuration que ceux indiqués dans la capture d’écran suivante.


<img src="assets/jws-service-account-config.png" alt="configuration du compte de service ims" width="500">

*Configurez l’environnement pour la première fois.*


### Utilisation de la publication sur microservice pour la première fois

>[!NOTE]
>
> Ignorez les étapes suivantes si vous utilisez déjà la publication basée sur un microservice :

Une fois que vous avez ajouté la configuration IMS à l’environnement, procédez comme suit pour lier ces propriétés à des guides du Experience Manager à l’aide d’OSGi :

1. Dans le code de votre projet Git Cloud Manager, ajoutez les deux fichiers suivants (pour le contenu du fichier, affichez [Annexe](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`
1. Assurez-vous que les fichiers nouvellement ajoutés sont couverts par votre `filter.xml`.
1. Validez et poussez vos modifications Git.
1. Exécutez le pipeline pour appliquer les modifications à l’environnement.

Une fois cette opération effectuée, vous pouvez utiliser la publication cloud basée sur un microservice.

## FAQ


1. Si les configurations OSGi pour utiliser le microservice sont activées, le processus de publication fonctionnera-t-il sur le serveur Experience Manager local avec la même base de code ?
   * Non, si l’indicateur `dxml.use.publish.microservice` est défini sur `true`, il recherche toujours les configurations de microservice. Définir `dxml.use.publish.microservice` to `false` pour que la publication fonctionne sur votre serveur local.
1. Quelle quantité de mémoire est allouée au processus DITA lors de l’utilisation de la publication basée sur un microservice ? Est-ce piloté par le profil et les paramètres DITA ?
   * Avec la publication basée sur un microservice, l’allocation de mémoire n’est pas pilotée par le profil et les paramètres DITA. La mémoire totale disponible sur le conteneur de services est de 8 Go, dont 6 Go sont attribués au processus DITA-OT.


## Annexe {#appendix}

**Fichier**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Contenu**:

```
{
"service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
}
```

**Fichier**: `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`

**Contenu**:
* `dxml.use.publish.microservice`: basculez pour activer la publication basée sur un microservice à l’aide de DITA-OT
* `dxml.use.publish.microservice.native.pdf`: basculez pour activer la publication de PDF natifs en fonction du microservice.

```
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          jcr:primaryType="sling:OsgiConfig"
          dxml.publish.microservice.url="https://adobeioruntime.net/api/v1/web/543112-guidespublisher/default/publishercaller.json"
          dxml.use.publish.microservice="{Boolean}true"
          dxml.use.publish.microservice.native.pdf="{Boolean}true"
/>
```
