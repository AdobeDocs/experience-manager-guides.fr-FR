---
title: Connexion d’AEM Guides à Guides Knowledge AI
description: Découvrez comment connecter AEM Guides à Guides Knowledge AI
feature: Introduction
role: Admin
level: Experienced
source-git-commit: 05976e2a408e57256a454f181bb93d900dc091ab
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 2%
---

# Connecter Adobe Experience Manager Guides à Guides Knowledge AI (Beta)

>[!IMPORTANT]
>
> Cette fonction est désactivée par défaut. Pour activer la fonctionnalité d’IA dédiée à la connaissance de Guides, contactez votre équipe du succès client.

Cet article fournit aux administrateurs et aux ingénieurs de contenu le processus de bout en bout pour configurer l’accès à Guides Knowledge AI et charger le contenu Experience Manager Guides pour sa consommation dans Knowledge AI.

## Présentation du processus

| Étape | Ce que vous ferez |
|---|---|
| 1 | Créez un compte de service dans Adobe Developer Console et configurez-le pour votre environnement. |
| 2 | Récupérez l’e-mail du compte technique à partir du fichier des informations d’identification du compte de service. |
| 3 | Accordez l’accès au compte de service dans l’IA dédiée aux connaissances en créant un rôle et en ajoutant l’utilisateur. |
| 4 | Configurez un paramètre prédéfini de sortie de l’IA dédiée aux connaissances dans Experience Manager Guides et chargez du contenu. |


## Prérequis

Assurez-vous de disposer des autorisations et des droits d’accès suivants avant de commencer :

| Condition requise | Objectif |
|---|---|
| Console de développeur Adobe | Créez le compte de service et téléchargez ses informations d’identification JSON. |
| Adobe Experience Manager Guides | Créez du contenu et configurez le paramètre prédéfini de sortie pour l’IA dédiée à la connaissance. |
| [IA dédiée à la connaissance](https://guidesai.adobe.io/) | Gérez les rôles et les utilisateurs, et recevez le contenu chargé. |
| Autorisation : Créer Des Comptes De Service | Requis dans Adobe Developer Console pour créer un compte de service. |
| Autorisation : gérer les utilisateurs et les rôles dans l’IA dédiée à la connaissance | Obligatoire pour accorder l’accès au compte de service dans l’IA dédiée aux connaissances. |

## Créer un compte de service

L’IA dédiée aux connaissances utilise un compte de service pour s’authentifier en toute sécurité et accéder au contenu.

1. Suivez les instructions de la section [Configurer l’IMT des microservices](https://experienceleague.adobe.com/fr/docs/experience-manager-guides/using/knowledge-base/kb-articles/publishing/configure-microservices-imt-config).

1. Créez un compte de service et téléchargez le fichier d’informations d’identification JSON généré.

1. Configurez les paramètres d’environnement requis à l’aide des informations d’identification téléchargées.

Une fois l’opération terminée, le compte de service doit être correctement associé à votre environnement.

>[!NOTE]
>
> Si vous avez déjà créé et configuré un compte de service pour votre environnement, vous pouvez passer à l’étape suivante.


## Récupérer l’e-mail du compte technique

Pour accorder l’accès à l’IA dédiée aux connaissances, identifiez le compte de service.

1. Ouvrez le fichier JSON du compte de service téléchargé.
1. Recherchez l’`technical_account_email` du nom du champ. Affichez une valeur similaire à la suivante :

   ```json
   {
   "technical_account_email": "a1b2c3d4e5f6@techacct.adobe.com"
   }
   ```

1. Copiez l’adresse e-mail associée à `technical_account_email`. Vous utiliserez cette adresse e-mail à l’étape suivante.

## Accorder l’accès dans l’IA dédiée aux connaissances

Pour permettre au compte de service de gérer et de charger du contenu, ajoutez-le à l’IA dédiée aux connaissances avec les autorisations appropriées.

1. Ouvrez [Knowledge AI](https://guidesai.adobe.io/).
1. Accédez à **Sécurité > Rôles** et créez un rôle avec les autorisations minimales requises.
1. Accédez à **Sécurité > Utilisateurs > Ajouter un utilisateur**. Ajoutez un nouvel utilisateur à l’aide du `technical_account_email` copié à partir du fichier JSON du compte de service, sélectionnez les domaines dans la liste déroulante **Domaines** et attribuez le rôle créé à l’étape précédente.

Le compte de service est désormais autorisé à effectuer des opérations d’administration et de chargement de contenu.

## Configuration du préréglage de l’IA dédiée à la connaissance et chargement de contenu

Pour publier du contenu sur l’IA dédiée aux connaissances, configurez Experience Manager Guides une fois que vous avez configuré les autorisations.

1. Ouvrez la console **Map** dans Experience Manager Guides.
1. Accédez à l’onglet **Paramètres prédéfinis de sortie**.
1. Sélectionnez l’icône + pour créer un paramètre prédéfini de sortie.
1. Sélectionnez **Knowledge AI** dans la liste déroulante **Type** de la boîte de dialogue **Nouveau paramètre prédéfini de sortie**. Saisissez un **Nom** et sélectionnez **Ajouter au profil du dossier actuel** pour créer un paramètre prédéfini de sortie dans le profil du dossier actuel.

   ![création-de-préréglage-ia-de-connaissances](assets/knowledge-ai-preset.png)

1. Sélectionnez **Ajouter**. Le paramètre prédéfini de l’IA dédiée à la connaissance est créé.
1. Ouvrez le paramètre prédéfini de l’IA dédiée à la connaissance configuré.
1. Sélectionnez le domaine pour lequel le rôle a été accordé au `technical_account_email`, puis sélectionnez **Charger le contenu**. Cela déclenche le workflow de chargement de contenu vers l’IA dédiée aux connaissances. Attendez la fin du processus de chargement.

   ![domaine-ia-des-connaissances](assets/knowledge-ai-domain.png)

1. Une fois le chargement terminé, sélectionnez **Ouvrir dans l’IA dédiée aux connaissances**. Cela ouvre la conversation de l’IA dédiée aux connaissances dans le domaine, à l’aide du contenu chargé.

   ![Knowledge-ai-open](assets/open-knowledge-ai.png)

Vous avez correctement configuré le compte de service, attribué les autorisations requises et rendu votre contenu Experience Manager Guides disponible dans l’IA dédiée aux connaissances. Chaque fois que vous souhaitez publier du contenu mis à jour, créez un nouveau paramètre prédéfini de l’IA dédiée à la connaissance et suivez les étapes décrites dans la section [configurer le paramètre prédéfini de l’IA dédiée à la connaissance et charger votre contenu](#configure-knowledge-ai-preset-and-upload-content) ci-dessus.



