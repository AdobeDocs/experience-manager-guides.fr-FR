---
title: Installation et configuration de GitLab pour Edge Delivery Services
description: Découvrez comment configurer les référentiels GitLab, les jetons d’accès, Cloud Manager, les webhooks et Bring Your Own Git pour publier du contenu de Experience Manager Guides vers Edge Delivery Services.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: e5721ff1d6e2322213ac7bc988fb1d7e721cd148
workflow-type: tm+mt
source-wordcount: '1256'
ht-degree: 3%
---

# Installation et configuration de GitLab pour Edge Delivery Services

Pour publier du contenu de Experience Manager Guides vers Edge Delivery Services (EDS) à l’aide de GitLab, connectez un référentiel GitLab à votre site EDS à l’aide de la fonctionnalité Cloud Manager *Apporter votre propre Git* (BYOG). Cet article répertorie les étapes dans l’ordre. Pour plus d’informations sur chaque étape, consultez la documentation associée.

## Fonctionnement

- Un **référentiel GitHub** crée le site EDS via l’application de synchronisation de code AEM.
- Un **référentiel GitLab** stocke le contenu publié à partir de Experience Manager Guides.
- **&#x200B;**&#x200B;relie les deux en recevant les événements push GitLab (webhook) et en les synchronisant avec le site EDS.

## Conditions préalables

- Accès à GitHub et GitLab (GitLab.com ou auto-hébergé) pour créer des référentiels et des jetons.
- Accès à Cloud Manager, avec un rôle qui permet d’ajouter des référentiels (Responsable de déploiement ou Propriétaire de l’entreprise).
- Rôle d’administrateur système ou de développeur d’API dans votre organisation Adobe pour créer l’intégration de l’API Cloud Manager.
- Organisation `aem.live` enregistrée dans le service de configuration. En savoir plus dans [Configuration du service de configuration](https://www.aem.live/docs/config-service-setup).

## Ordre de configuration

1. [Créer le site EDS à l’aide de GitHub](#1-create-the-eds-site-using-github)
2. [Création du référentiel GitLab](#2-create-the-gitlab-repository)
3. [Configurer l’URL du point de montage](#3-configure-the-mountpoint-url)
4. [Création de jetons d’accès GitLab](#4-create-gitlab-access-tokens)
5. [Ajout du référentiel GitLab à Cloud Manager](#5-add-the-gitlab-repository-to-cloud-manager)
6. [Générer une clé API Cloud Manager](#6-generate-a-cloud-manager-api-key)
7. [Configuration du webhook GitLab](#7-configure-the-gitlab-webhook)
8. [Ajout du site EDS à Cloud Manager](#8-add-the-eds-site-to-cloud-manager)
9. [Connecter le référentiel à l’aide de l’option Apporter votre propre Git](#9-connect-the-repository-using-bring-your-own-git)
10. [Configuration du site EDS pour utiliser Cloud Manager](#10-configure-the-eds-site-to-use-cloud-manager)
11. [Synchroniser et vérifier](#11-sync-and-verify)
12. [Publier à partir de Experience Manager Guides](#12-publish-from-experience-manager-guides)

### &#x200B;1. Créer le site EDS à l’aide de GitHub

Créez un référentiel GitHub à partir du standard AEM Guides et installez-y l’application de synchronisation du code AEM. Enregistrez l’**URL en direct** (`https://<branch>--<github-repo>--<github-username>.aem.live`) générée pour plus tard.

Pour connaître les étapes, voir [Création d’un référentiel GitHub pour EDS](./configure-eds.md#create-a-github-repository-for-eds) et [Connexion de GitHub à Adobe via la synchronisation de code AEM](./configure-eds.md#connect-github-to-adobe-via-aem-code-sync).

>[!IMPORTANT]
>
> Ne créez pas le site EDS à l’aide de l’option en un clic dans Cloud Manager. Les sites créés de cette manière ne vous donnent pas les autorisations d’administrateur requises pour les étapes suivantes. En savoir plus dans la section [Préparation de votre site Edge Delivery Services](https://www.aem.live/developer/byo-git#1.-prepare-your-edge-delivery-services-site).

### &#x200B;2. Création du référentiel GitLab

Créez un référentiel GitLab distinct (par exemple, `my-eds-gitlab`) à partir de la même norme standard AEM Guides. Experience Manager Guides publie la sortie générée dans ce référentiel. EDS attend une branche `main`.

Pour créer le référentiel, créez un projet vierge et transmettez-y le contenu du [aem-guides-boilerplate](https://github.com/adobe/aem-guides-boilerplate) ou importez-le dans un nouveau projet. Pour connaître les étapes, voir [Créer un projet](https://docs.gitlab.com/user/project/) et [Importer votre projet de GitHub vers GitLab](https://docs.gitlab.com/user/project/import/github/) dans la documentation GitLab.

### &#x200B;3. Configurer l’URL du point de montage

Dans le référentiel GitHub, mettez à jour `fstab.yaml` afin que la source de contenu pointe vers le référentiel GitLab, puis validez la modification dans `main`.

```text
https://<worker URL>/gitlab/<git acc domain>/<git username>/<git repo>/main/docs
```

| Paramètre | Description |
|---|---|
| `<worker URL>` | URL du nœud collaborateur fournie par Adobe. |
| `<git acc domain>` | Domaine GitLab, tel que `gitlab.com`, ou votre domaine auto-hébergé. |
| `<git username>` | Votre nom d’utilisateur GitLab. |
| `<git repo>` | Nom du référentiel GitLab. |
| `main` / `docs` | Branche et dossier racine. Valeurs par défaut pour Experience Manager Guides. |

### &#x200B;4. Création de jetons d’accès GitLab

Créez le ou les jetons d’accès requis pour :

- **&#x200B;**, pour valider et accéder au référentiel. Pour en savoir plus, consultez la section [Ajouter des référentiels externes dans Cloud Manager](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager/content/managing-code/external-repositories).
- **Profil de publication**, pour valider la sortie publiée. Créez un jeton d’accès au projet GitLab avec le rôle **Développeur** et la portée `api`. Pour en savoir plus, consultez la [documentation GitLab](https://docs.gitlab.com/ee/user/project/settings/project_access_tokens.html).

>[!NOTE]
>
> Renouveler les jetons avant leur expiration. La publication échoue si le jeton dans le profil de publication a expiré. Pour mettre à jour un jeton utilisé par Cloud Manager, consultez [Gérer les jetons d’accès pour les référentiels externes](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager/content/managing-code/manage-access-tokens).

### &#x200B;5. Ajout du référentiel GitLab à Cloud Manager

Dans Cloud Manager, accédez à **Référentiels** > **Ajouter un référentiel**, sélectionnez **Référentiel privé** et validez la propriété à l’aide du jeton d’accès. Patientez jusqu’à ce que le statut du référentiel soit **Prêt**. L’option BYOG n’est disponible qu’une fois qu’au moins un référentiel externe est Prêt.

Pour connaître les étapes, voir [Ajouter des référentiels externes dans Cloud Manager](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager/content/managing-code/external-repositories).

### &#x200B;6. Générer une clé API Cloud Manager

Créez une intégration d’API dans Adobe Developer Console (**API Cloud Manager**, **OAuth de serveur à serveur**) et copiez l’**ID client (clé API)**.

Pour connaître les étapes, voir [Création d’un projet d’intégration d’API](https://developer.adobe.com/experience-cloud/cloud-manager/guides/getting-started/create-api-integration).

### &#x200B;7. Configuration du webhook GitLab

Dans Cloud Manager, sélectionnez **Configurer le Webhook** pour le référentiel et copiez les **URL du Webhook** et **Secret**. Ajoutez la clé API à l’URL (`<webhook URL>&api-key=<CLIENT_ID>`). Dans GitLab, accédez à **Paramètres** > **Webhooks**, ajoutez l’URL et le secret, sélectionnez la branche `main` et activez **Événements push**.

Pour plus d’informations, consultez [Configuration de votre référentiel externe dans Cloud Manager](https://www.aem.live/developer/byo-git#2.-configure-your-external-repository-in-cloud-manager).

### &#x200B;8. Ajout du site EDS à Cloud Manager

Dans Cloud Manager, accédez à **Edge Delivery** > **Ajouter un site Edge Delivery** et saisissez l’URL en direct enregistrée à l’étape 1. Effectuez la validation de la propriété.

Pour connaître les étapes, voir [Ajouter un site Edge Delivery](https://experienceleague.adobe.com/fr/docs/experience-manager-cloud-service/content/implementing/using-cloud-manager/edge-delivery-sites/add-edge-delivery-site).

### &#x200B;9. Connecter le référentiel à l’aide de l’option Apporter votre propre Git

Sur le site EDS de Cloud Manager, sélectionnez **Apporter votre propre Git (BYOG)**, choisissez le référentiel GitLab, puis confirmez. Copiez et stockez en toute sécurité le secret généré. Il n’est affiché qu’une seule fois et un nouveau secret est généré si vous reconfigurez le site.

Pour plus d’informations, consultez [Configuration de votre site Edge Delivery dans Cloud Manager](https://www.aem.live/developer/byo-git#3.-configure-your-edge-delivery-site-in-cloud-manager).

### &#x200B;10. Configuration du site EDS pour utiliser Cloud Manager

Définissez la source de code du site EDS sur le référentiel Cloud Manager, à l’aide des **ID de programme** (`/program/<PROGRAM_ID>/`) et **ID de référentiel** (`/repo/<REPO_ID>/`) de l’URL du webhook. Créez ensuite un secret nommé exactement `cm-byog` avec le secret de l’étape 9.

Pour les appels d’API d’administration, consultez [Configuration de votre site AEM pour utiliser Cloud Manager](https://www.aem.live/developer/byo-git#4.-configure-your-aem-site-to-use-cloud-manager).

### &#x200B;11. Synchroniser et vérifier

Dans Cloud Manager, sélectionnez **Code de synchronisation** dans le menu du site et choisissez la branche `main`. Ouvrez ensuite `https://main--<site>--<org>.aem.page` pour vérifier le site.

Pour plus d’informations, consultez les sections [Déclencher votre première synchronisation](https://www.aem.live/developer/byo-git#5.-trigger-your-first-sync) et [Vérifier votre site AEM](https://www.aem.live/developer/byo-git#6.-verify-your-aem-site).

### &#x200B;12. Publier à partir de Experience Manager Guides

Créez un profil de publication EDS avec le **type de compte Git** défini sur **GitLab**, à l’aide du jeton d’accès au projet de l’étape 4. Sélectionnez ensuite ce profil dans un paramètre prédéfini de sortie EDS et générez la sortie. La sortie est validée dans le dossier `docs` du référentiel GitLab.

Pour connaître les étapes, consultez les sections [Créer le profil de publication EDS](./configure-eds.md#create-the-eds-publish-profile-for-github-or-gitlab) et [Créer un paramètre prédéfini de sortie pour EDS et générer une sortie](./configure-eds.md#create-an-output-preset-for-eds-and-generate-output).

## Résolution des problèmes

- **Le site affiche l’ancien contenu après une notification push :** vérifiez que le webhook diffuse les événements vers Cloud Manager, puis vérifiez le statut de la dernière tâche de synchronisation.
- **Erreur de synchronisation `Unable to fetch hlxignore: 401` :** le secret `cm-byog` est incorrect. Recréez-le avec le secret de l’étape 9.
- **Référentiel lié à un autre site :** un référentiel Cloud Manager ne peut être lié qu’à un seul site à la fois. Pour partager un référentiel sur plusieurs sites, utilisez [Repoless](https://www.aem.live/docs/repoless).

Pour plus d’informations, consultez la section [Dépannage dans Apporter votre propre Git](https://www.aem.live/developer/byo-git#troubleshooting).
