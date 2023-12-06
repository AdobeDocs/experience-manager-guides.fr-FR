---
title: Configuration de la nouvelle publication basée sur un microservice pour AEM Guides as a Cloud Service
description: Découvrez comment configurer une nouvelle publication basée sur un microservice pour AEM Guides.
exl-id: 92e3091d-6337-4dc6-9609-12b1503684cd
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 0%

---

# Configuration de la nouvelle publication basée sur un microservice pour AEM Guides as a Cloud Service

Le nouveau microservice de publication permet aux utilisateurs d’exécuter simultanément des charges de travail de publication volumineuses sur AEM Guides as a Cloud Service et d’exploiter la plate-forme Adobe I/O Runtime sans serveur de pointe.

Pour chaque demande de publication AEM Guides as a Cloud Service exécute un conteneur distinct qui se met à l’échelle horizontalement en fonction des demandes de l’utilisateur. Cela permet aux utilisateurs d’exécuter plusieurs requêtes de publication et d’obtenir de meilleures performances que leurs serveurs d’AEM on-premise volumineux.

>[!NOTE]
>
> La publication basée sur les microservices dans AEM Guides prend en charge les types de paramètres prédéfinis de sortie PDF (natifs et basés sur DITA-OT), HTML5, JSON et PERSONNALISÉS.

Comme le nouveau service de publication dans le cloud est sécurisé par l’authentification basée sur JWT d’Adobe IMS, les clients doivent suivre les étapes ci-dessous pour intégrer leurs environnements aux workflows d’authentification par jeton sécurisés d’Adobe et commencer à utiliser la nouvelle solution de publication évolutive basée sur le cloud.


## Création de configurations IMS dans la console Adobe Developer

**Rôle requis pour créer les configurations**: administrateur système

Effectuez les étapes suivantes pour créer des configurations IMS dans la console Adobe Developer :

1. Ouvrez Developer Console : `https://developer.adobe.com/console`.

1. Basculer vers **Projets** dans la partie supérieure.

   <img src="assets/projects-tab.png" alt="onglet projets" width="500">

1. Pour créer un projet vide, sélectionnez **Projet vide** de la **Créer un projet** menu déroulant.

   <img src="assets/create-new-project.png" alt="créer un projet" width="500">

1. Sélectionner **API** de la **Ajouter au projet** Liste déroulante pour ajouter l’API de gestion des entrées-sorties à votre projet.

   <img src="assets/add-project.png" alt="ajouter un projet" width="300">

   <img src="assets/io-management-api.png" alt="Gestion des io" width="500">

1. Créez une nouvelle paire de clés privée/publique lors de l’ajout de l’API. La clé privée sera alors automatiquement téléchargée sur votre système.

   <img src="assets/generate-key-pair.png" alt="générer une paire de clés" width="500">

1. Enregistrez l’API configurée.

   <img src="assets/save-api.png" alt="save api" width="600">

1. Revenir à **Projets** et cliquez sur **Présentation du projet** sur la gauche.

   <img src="assets/project-overview.png" alt="présentation du projet" width="500">

1. Cliquez sur **Télécharger** sur la partie supérieure pour télécharger le service JSON.

   <img src="assets/download-json.png" alt="télécharger json" width="500">

Vous avez maintenant configuré les détails de l’authentification JWT et téléchargé également la clé privée et les détails du service JSON. Conservez ces deux fichiers à portée de main, car ces fichiers sont requis dans la section suivante.

### Ajout de la configuration IMS à l’environnement

Effectuez les étapes suivantes pour ajouter la configuration IMS à l’environnement :

1. Ouvrez le gestionnaire d’expériences, puis sélectionnez le programme contenant l’environnement que vous souhaitez configurer.
1. Basculer vers **Environnements** .
1. Cliquez sur le nom de l’environnement que vous souhaitez configurer. Cela vous permet d’accéder à la page Informations sur l’environnement .
1. Basculer vers **Configuration** .
1. Téléchargez la clé privée et le fichier JSON du projet, comme illustré dans la capture d’écran ci-dessous. Veillez à utiliser les mêmes noms et configuration que ceux présentés ci-dessous.

   <img src="assets/ims-config-environment.png" alt="configurations ims" width="500">

>[!NOTE]
>
> Vous devez ouvrir, copier et coller le contenu du fichier JSON des détails de clé privée et de service dans la colonne des valeurs du panneau Configuration, comme illustré dans la capture d’écran ci-dessus.

Une fois que vous avez ajouté la configuration IMS à l’environnement, procédez comme suit pour lier ces propriétés à AEM Guides à l’aide d’OSGi :

1. Dans le code de projet Git de Cloud Manager, ajoutez les deux fichiers ci-dessous (pour le contenu du fichier, voir [Annexe](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`
1. Assurez-vous que les fichiers nouvellement ajoutés sont couverts par votre `filter.xml`.
1. Validez et poussez vos modifications Git.
1. Exécutez le pipeline pour appliquer les modifications à l’environnement.

Une fois cela fait, vous devriez pouvoir utiliser la nouvelle publication cloud basée sur un microservice.

## FAQ

1. Une seule clé peut-elle être utilisée dans plusieurs environnements cloud ?
   * Oui, vous pouvez générer une clé privée et l’utiliser pour tous les environnements, mais vous devez configurer des variables d’environnement pour tous les environnements et utiliser la même clé.
1. Si les configurations OSGi pour utiliser le microservice sont activées , le processus de publication fonctionnera-t-il sur le serveur d’AEM local avec la même base de code ?
   * Non, si l’indicateur `dxml.use.publish.microservice` est défini sur `true` puis il recherche toujours des configurations de microservice. Définir `dxml.use.publish.microservice` to `false` pour que la publication fonctionne sur votre site local.
1. Quelle quantité de mémoire est allouée au processus DITA lors de l’utilisation de la publication basée sur un microservice ? Est-ce piloté par les paramètres de fourmi de profil DITA ?
   * Avec la publication basée sur un microservice, l’allocation de mémoire n’est pas pilotée par les paramètres de fourmi de profil DITA. La mémoire totale disponible sur le conteneur de services est de 8 Go, dont 6 Go sont affectés au processus DITA-OT.


## Annexe {#appendix}

**Fichier**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Contenu**:

```
{
  "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
  "private.key": "$[secret:PRIVATE_KEY]"
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
