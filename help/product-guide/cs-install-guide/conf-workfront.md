---
title: Configuration d’Adobe Workfront dans Experience Manager Guides
description: Découvrez comment configurer Workfront dans Experience Manager Guides
feature: Authoring
role: Admin
level: Experienced
exl-id: 1f72642c-e694-47cd-9182-f4f4aaf69655
TQID: https://experienceleague.adobe.com/Yua4Y6xsnec3O-hpTNhSmK4HvsCwaGYbLTxUxEeQAKY
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: ae478996-b206-4712-9b0c-dc78a2644453
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: f7774ebe-aec9-42b6-97e4-5002acdc712e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 600
ht-degree: 2%

---

# Configuration d’Adobe Workfront

Adobe Workfront est une solution de gestion du travail cloud qui aide les équipes et les organisations à planifier, suivre et gérer efficacement leur travail. L’intégration entre Experience Manager Guides et Adobe Workfront vous donne accès à des fonctionnalités de gestion de projet fiables, en plus des fonctionnalités de base du système de gestion de contenu par composant (CCMS) de Experience Manager Guides, ce qui vous permet de planifier, d’affecter et de suivre les tâches efficacement.

En savoir plus sur l’[intégration d’](../user-guide/workfront-integration.md) dans Experience Manager Guides.

## Conditions préalables

Avant de commencer, assurez-vous des points suivants :

1. Vous disposez d’un accès standard à Adobe Workfront et d’un accès administrateur à Experience Manager Guides.
2. Vous [créez un formulaire personnalisé dans Adobe Workfront](https://experienceleague.adobe.com/fr/docs/workfront/using/administration-and-setup/customize/custom-forms/design-a-form/design-a-form) requis pour Experience Manager Guides en utilisant spécifiquement les champs suivants :

   | Type de champ | Libellé | Nom | Choix (Afficher les valeurs activées) |
   |------------|------|------|-------------------------------|
   | Liste déroulante à sélection unique | Type de tâche | task-type | Création (valeur = AUTEUR), Publication (valeur = PUBLIER), Traduction (valeur = TRADUCTION), Révision (valeur = RÉVISION) |
   | Liste déroulante à sélection unique | État de la tâche | état de la tâche | Création (valeur = AUTEUR), Publication (valeur = PUBLIER), Traduction (valeur = TRADUCTION), Révision (valeur = RÉVISION) |
   | Texte avec formatage | Liste d’auteurs | author-list | - |
   | Texte avec formatage | Liste des réviseurs | reviewer-list | - |
   | Texte monoligne | Vérifier l’URL | review-url | - |
   | Texte monoligne | URL de la tâche | task-url | - |
   | Une seule ligne de texte | Objet de l’e-mail | email-subject | - |

>[!NOTE]
>
> * Dans le tableau ci-dessus, les choix représentent les options disponibles sous le champ **Type de tâche**. Pour chaque option, vous devez fournir les valeurs **nom de la tâche** et **valeur de la tâche**. Le nom et les valeurs de chaque type de tâche doivent être identiques à ceux mentionnés dans le tableau ci-dessus. Par exemple, pour le type de tâche Auteur, indiquez **Création** comme nom et **AUTEUR** comme valeur correspondante.
> * Lorsque vous utilisez des services on-prem, assurez-vous toujours que `localhost` est remplacé par l’adresse de serveur correcte dans la configuration **Day CQ Link Externalizer** pour recevoir correctement le lien de la tâche résolue dans les notifications par e-mail.
> * Lors de la création d’une tâche de révision dans Workfront, les utilisateurs (auteurs ou réviseurs) doivent faire partie du groupe **workflow-users**. En outre, en tant que **Auteur** vous devez faire partie du groupe **content-authors** et **authors**, tandis qu’en tant que **Réviseur** vous devez faire partie du groupe **réviseurs**.


## Commencer

Pour configurer Adobe Workfront dans Experience Manager Guides, procédez comme suit.

1. Ouvrez le panneau **Outils** et sélectionnez **Guides**.
2. Sélectionnez **Configurer Workfront**.

   La page de configuration **&#x200B;**&#x200B;s’affiche.

   ![](assets/configure-workfront-page.png)

3. Sur la page de configuration **&#x200B;**, saisissez l’URL complète du domaine Workfront de votre organisation, l’ID client et la clé secrète client.

   Pour accéder à la clé **ID client** et **Secret client** configurée dans votre configuration Adobe Workfront, accédez à `Setup >> Systems>> oAuth2 Applications`.

   Pour plus d’informations sur la configuration de votre domaine Adobe Workfront, consultez la section Flux de code d’autorisation dans [Création d’applications OAuth2 pour les intégrations Workfront](https://experienceleague.adobe.com/fr/docs/workfront/using/administration-and-setup/configure-integrations/create-oauth-application#create-an-oauth2-application-using-user-credentials-authorization-code-flow).

4. Sélectionnez **Connexion et vérification**.

   Vous êtes redirigé vers la page de connexion d’Adobe Workfront.
5. Connectez-vous à l’aide de votre adresse e-mail Adobe Workfront, puis sélectionnez **Autoriser l’accès** pour permettre à l’application Oauth2 d’accéder à votre compte Adobe Workfront respectif.

   Vous êtes automatiquement redirigé vers la page de configuration de Workfront sur Experience Manager Guides.

6. Dans la liste déroulante des formulaires personnalisés, sélectionnez le formulaire personnalisé Adobe Workfront que vous avez créé pour Experience Manager Guides. Afficher [Conditions préalables](#prerequisites).
7. Sélectionnez **Enregistrer et fermer** pour appliquer et enregistrer les modifications apportées à la configuration de Workfront.

Une fois la configuration effectuée, [ajoutez des utilisateurs à Adobe Workfront](https://experienceleague.adobe.com/fr/docs/workfront/using/administration-and-setup/add-users/create-manage-users/add-users) en utilisant les mêmes adresses e-mail que celles de Experience Manager Guides.
