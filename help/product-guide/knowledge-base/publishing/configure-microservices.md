---
title: Configurer une nouvelle publication basée sur les microservices pour AEM Guides as a Cloud Service
description: Découvrez comment configurer une nouvelle publication basée sur un microservice pour AEM Guides.
exl-id: 92e3091d-6337-4dc6-9609-12b1503684cd
feature: Microservice in AEM Guides
role: User, Admin
TQID: https://experienceleague.adobe.com/1M-gDrJclVMkYHOo69FPmKqkJvzYaDHK0ljK5dIh-tA
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 740
ht-degree: 3%

---

# Configuration de la publication basée sur les microservices avec l’authentification JWT

[!BADGE ]{type=Informative}

>[!NOTE]
>
> Les informations d’identification du compte de service (JWT), ont été rendues obsolètes au profit des informations d’identification OAuth serveur à serveur. Vos applications utilisant les informations d’identification du compte de service (JWT) cesseront de fonctionner après le 1er janvier 2025. Vous devez migrer vers les nouvelles informations d’identification avant le 1er janvier 2025 pour vous assurer que votre application continue de fonctionner. En savoir plus sur la [migration des informations d’identification du compte de service (JWT) vers les informations d’identification OAuth de serveur à serveur](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/).



La publication basée sur les microservices dans pour Adobe Experience Manager Guides as a Cloud Service prend en charge les types de paramètres prédéfinis de sortie PDF (natifs et basés sur DITA-OT), HTML5, JSON et CUSTOM.

Comme les informations d’identification du compte de service (JWT) sont obsolètes, il est recommandé d’utiliser l’authentification OAuth d’Adobe IMS. Découvrez comment [configurer la publication basée sur un microservice avec l’authentification OAuth](configure-microservices-imt-config.md).

Pour le service de publication cloud sécurisé par l’authentification JWT d’Adobe IMS, les clients doivent suivre les étapes données ci-dessous pour intégrer leurs environnements aux workflows d’authentification basée sur les jetons sécurisés d’Adobe et commencer à utiliser la nouvelle solution de publication évolutive basée sur le cloud.


## Création de configurations IMS dans Adobe Developer Console

**Rôle requis pour créer les configurations** : administrateur système

Pour créer des configurations IMS dans Adobe Developer Console, procédez comme suit :

1. Ouvrez Developer Console : `https://developer.adobe.com/console`.

1. Basculez vers l’onglet **Projets** à partir du haut.

   <img src="assets/projects-tab.png" alt="onglet projets" width="500">

1. Pour créer un projet vide, sélectionnez **Projet vide** dans le menu déroulant **Créer un projet**.

   <img src="assets/create-new-project.png" alt="créer un projet" width="500">

1. Sélectionnez **API** dans le menu déroulant **Ajouter au projet** pour ajouter l’API IO Management à votre projet.

   <img src="assets/add-project.png" alt="ajouter un projet" width="300">

   <img src="assets/io-management-api.png" alt="gestion des e/s" width="500">

1. Créez une nouvelle paire de clés privée/publique lors de l’ajout de l’API . La clé privée sera automatiquement téléchargée sur votre système.

   <img src="assets/generate-key-pair.png" alt="générer une paire de clés" width="500">

1. Enregistrez l’API configurée.

   <img src="assets/save-api.png" alt="enregistrer l’api" width="600">

1. Revenez à l’onglet **Projets** et cliquez sur **Présentation du projet** sur la gauche.

   <img src="assets/project-overview.png" alt="présentation du projet" width="500">

1. Cliquez sur le bouton **Télécharger** en haut pour télécharger le fichier JSON du service.

   <img src="assets/download-json.png" alt="télécharger json" width="500">

Vous avez maintenant configuré les détails d’authentification JWT et téléchargé la clé privée et le fichier JSON des détails du service. Conservez ces deux fichiers à portée de main, car ils sont requis dans la section suivante.

### Ajouter la configuration IMS à l’environnement

Pour ajouter la configuration IMS à l’environnement, procédez comme suit :

1. Ouvrez Experience Manager, puis sélectionnez votre programme contenant l’environnement à configurer.
1. Basculez vers l’onglet **Environnements**.
1. Cliquez sur le nom de l’environnement à configurer. Vous devriez y accéder à la page Informations sur l’environnement.
1. Basculez vers l’onglet **Configuration**.
1. Chargez la clé privée et le projet JSON, comme illustré dans la capture d’écran ci-dessous. Assurez-vous d’utiliser les mêmes noms et la même configuration que ceux mis en surbrillance ci-dessous.

   <img src="assets/ims-config-environment.png" alt="configurations ims" width="500">

>[!NOTE]
>
> Vous devez ouvrir, copier et coller le contenu du fichier JSON des détails de la clé privée et du service dans la colonne de valeur du panneau Configuration comme illustré dans la capture d’écran ci-dessus.

Une fois que vous avez ajouté la configuration IMS à l’environnement, procédez comme suit pour lier ces propriétés à Experience Manager Guides à l’aide d’OSGi :

1. Dans le code de votre projet Git Cloud Manager, ajoutez les deux fichiers donnés ci-dessous (pour le contenu du fichier, voir [Annexe](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`
1. Assurez-vous que les fichiers nouvellement ajoutés sont couverts par votre `filter.xml`.
1. Validez et envoyez vos modifications Git.
1. Exécutez le pipeline pour appliquer les modifications à l’environnement.

Une fois cette opération effectuée, vous devriez être en mesure d’utiliser la nouvelle publication cloud basée sur les microservices.

## FAQ

1. Une seule clé peut-elle être utilisée sur plusieurs environnements cloud ?
   * Oui, vous pouvez générer une clé privée et l’utiliser pour tous les environnements, mais vous devez configurer les variables d’environnement pour tous les environnements et utiliser la même clé.
1. Si les configurations OSGi pour utiliser le microservice sont activées , le processus de publication fonctionnera-t-il sur le serveur AEM local avec la même base de code ?
   * Non, si l’indicateur `dxml.use.publish.microservice` est défini sur `true`, il recherche toujours les configurations de microservice. Définissez `dxml.use.publish.microservice` sur `false` pour que la publication fonctionne sur votre local.
1. Quelle quantité de mémoire est allouée au processus DITA lors de l&#39;utilisation de la publication basée sur les microservices ? Cela est-il piloté par le biais des paramètres de profil DITA ?
   * Avec la publication basée sur les microservices, l&#39;allocation de mémoire n&#39;est pas pilotée par les paramètres de profil DITA. La mémoire totale disponible sur le conteneur de services est de 8 Go, dont 6 Go sont alloués au processus DITA-OT.


## Annexe {#appendix}

**Fichier** :
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Contenu** :

```
{
  "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
  "private.key": "$[secret:PRIVATE_KEY]"
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
