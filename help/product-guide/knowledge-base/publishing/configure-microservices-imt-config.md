---
title: Configuration de la publication basée sur les microservices avec l’authentification OAuth pour AEM Guides as a Cloud Service
description: Découvrez comment configurer la publication basée sur un microservice avec l’authentification OAuth pour AEM Guides.
feature: Microservice in AEM Guides
role: Admin
exl-id: db0c83c7-1ece-4010-b214-f8d806d26bc9
TQID: https://experienceleague.adobe.com/iAlQIB0z2bxI-BaOXp62M6YJjzS-RzGfJaJbl8BWNUc
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 850
ht-degree: 0%

---

# Configuration de la publication basée sur les microservices avec l’authentification OAuth

Le microservice de publication vous permet d’exécuter simultanément d’importantes charges de travail de publication sur Experience Manager Guides as a Cloud Service et de tirer parti de la plateforme Adobe I/O Runtime sans serveur leader du secteur.

Pour chaque demande de publication, Experience Manager Guides as a Cloud Service exécute un conteneur distinct qui est mis à l’échelle horizontalement en fonction des demandes des utilisateurs. Vous pouvez ainsi exécuter plusieurs requêtes de publication et obtenir de meilleures performances que leurs serveurs On-premise Adobe Experience Manager volumineux.

>[!NOTE]
>
> La publication basée sur les microservices dans Experience Manager Guides prend en charge les types de paramètres prédéfinis de sortie PDF (natif et basé sur DITA-OT), HTML5, JSON et CUSTOM.

Comme le service de publication cloud est sécurisé par l’authentification OAuth d’Adobe IMS, procédez comme suit pour intégrer leurs environnements aux workflows d’authentification basée sur les jetons sécurisés d’Adobe et commencer à utiliser la solution de publication évolutive basée sur le cloud.


## Création de configurations IMS dans Adobe Developer Console

**Rôle requis pour créer les configurations** : administrateur système

Pour créer des configurations IMS dans ****, procédez comme suit :

>[!NOTE]
>
>Si vous avez déjà créé un projet OAuth pour configurer les suggestions intelligentes optimisées par l’IA pour la création, vous pouvez ignorer les étapes suivantes pour créer le projet.

1. Ouvrez **** : `https://developer.adobe.com/console`.

1. Accédez à l’onglet **Projets** à partir du haut.

   <img src="assets/projects-tab.png" alt="onglet projets" width="500">

   *Sélectionnez l’onglet **Projets**dans le **Adobe Developer Console***

1. Pour créer un projet vide, sélectionnez **Projet vide** dans le menu déroulant **Créer un projet**.

   <img src="assets/create-new-project.png" alt="créer un projet" width="500">

   *Créer un nouveau projet vide.*

1. Sélectionnez **API** dans le menu déroulant **Ajouter au projet** pour ajouter l’API IO Management à votre projet.

   <img src="assets/add-project.png" alt="ajouter un projet" width="300">

   *Sélectionnez un projet d’API dans la liste déroulante.*

   <img src="assets/io-management-api.png" alt="gestion des e/s" width="500">

   *Ajoutez l’API I/O Management à votre projet.*

1. Créez des informations d’identification OAuth et enregistrez-les.

   <img src="assets/microservice-api-oauth.png" alt="générer une paire de clés" width="500">

   *Configurer les informations d’identification OAuth dans votre API.*


1. Revenez à l’onglet **Projets** et sélectionnez **Présentation du projet** sur la gauche.

   <img src="assets/project-overview.png" alt="présentation du projet" width="500">

   *Commencer le nouveau projet.*

1. Cliquez sur le bouton **Télécharger** en haut pour télécharger le fichier JSON du service.

   <img src="assets/download-json.png" alt="télécharger json" width="500">

   *Téléchargez les détails du service JSON.*

Vous avez configuré les détails d’authentification OAuth et téléchargé les détails du service JSON. Gardez ce fichier à portée de main car il est requis dans la section suivante.


## Ajouter la configuration IMS à l’environnement

>[!NOTE]
>
>Si vous avez déjà créé un projet OAuth pour les suggestions intelligentes, vous pouvez réutiliser le même projet pour les microservices et ignorer les étapes suivantes pour ajouter une configuration IMS à l’environnement.

### Mise à jour de la configuration existante (passage de JWT à OAuth )

Si vous utilisez déjà un microservice pour la publication à l’aide de JWT (obsolète), procédez comme suit pour mettre à jour les configurations :



1. Ouvrez **** et sélectionnez le programme contenant l’environnement à configurer.
1. Passez à l’onglet **Environnements**.
1. Sélectionnez le nom de l’environnement à configurer. Vous devriez y accéder à la page **Informations sur l’environnement**.
1. Passez à l’onglet **Configuration**.

1. Mettez à jour le champ JSON SERVICE_ACCOUNT_DETAILS avec le nouveau fichier JSON OAuth que vous avez téléchargé.
1. Supprimez le champ PRIVATE_KEY.



   <img src="assets/ims-service-account-config.png" alt="configuration du compte de service ims" width="500">

   *Mettez à jour les configurations d’environnement JWT existantes.*

### Première configuration

Pour utiliser un microservice de publication pour la première fois, mettez à jour les configurations en procédant comme suit :
1. Ouvrez **** et sélectionnez le programme contenant l’environnement à configurer.
1. Passez à l’onglet **Environnements**.
1. Sélectionnez le nom de l’environnement à configurer. Vous devriez y accéder à la page **Informations sur l’environnement**.
1. Passez à l’onglet **Configuration**.

1. Créez une configuration nommée SERVICE_ACCOUNT_DETAILS. Dans la valeur , ajoutez le contenu du fichier JSON OAuth que vous avez téléchargé à partir de Developer Console .


<img src="assets/jws-service-account-config.png" alt="configuration du compte de service ims" width="500">

*Configurez l’environnement pour la première fois.*


### Premières modifications du code pour l’activation de la publication basée sur les microservices

>[!NOTE]
>
> Ignorez les étapes suivantes si vous utilisez déjà la publication basée sur les microservices :

Une fois que vous avez ajouté la configuration IMS à l’environnement, procédez comme suit pour lier ces propriétés à Experience Manager Guides à l’aide d’OSGi :

1. Dans le code de votre projet Git Cloud Manager, ajoutez les deux fichiers suivants dans `/apps/fmditaCustom/config` (pour le contenu des fichiers, consultez [Annexe](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`
1. Assurez-vous que les fichiers nouvellement ajoutés sont couverts par votre `filter.xml`.
1. Validez et envoyez vos modifications Git.
1. Exécutez le pipeline pour appliquer les modifications à l’environnement.

Une fois cette opération effectuée, vous pouvez utiliser la publication cloud basée sur les microservices.

## FAQ


1. Si les configurations OSGi pour utiliser le microservice sont activées, le processus de publication fonctionnera-t-il sur le serveur Experience Manager local avec la même base de code ?
   * Non, si l’indicateur `dxml.use.publish.microservice` est défini sur `true`, il recherche toujours les configurations de microservice. Définissez `dxml.use.publish.microservice` sur `false` pour que la publication fonctionne sur votre serveur local.
1. Quelle quantité de mémoire est allouée au processus DITA lors de l&#39;utilisation de la publication basée sur les microservices ? Cela est-il piloté par le biais du profil et des paramètres DITA ?
   * Avec la publication basée sur les microservices, l&#39;allocation de mémoire n&#39;est pas pilotée par le profil et les paramètres DITA. La mémoire totale disponible sur le conteneur de services est de 8 Go, dont 6 Go sont alloués au processus DITA-OT.


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
* `dxml.use.publish.microservice` : activer la publication basée sur les microservices à l’aide de DITA-OT
* `dxml.use.publish.microservice.native.pdf` : activer la publication native PDF basée sur les microservices

```
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          jcr:primaryType="sling:OsgiConfig"
          dxml.publish.microservice.url="https://adobeioruntime.net/api/v1/web/543112-guidespublisher/default/publishercaller.json"
          dxml.use.publish.microservice="{Boolean}true"
          dxml.use.publish.microservice.native.pdf="{Boolean}true"
/>
```
