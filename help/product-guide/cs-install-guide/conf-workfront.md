---
title: Configuration d’Adobe Workfront dans Experience Manager Guides
description: Découvrez comment configurer Workfront dans Experience Manager Guides
feature: Authoring
role: Admin
level: Experienced
source-git-commit: 2748ecee0963028be5d9220f852f4dfbc122d4a0
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 2%

---

# Configuration d’Adobe Workfront

Adobe Workfront est une solution de gestion du travail cloud qui aide les équipes et les organisations à planifier, suivre et gérer efficacement leur travail. L’intégration entre Experience Manager Guides et Adobe Workfront vous donne accès à des fonctionnalités de gestion de projet fiables, en plus des fonctionnalités de base du système de gestion de contenu par composant (CCMS) de Experience Manager Guides, ce qui vous permet de planifier, d’affecter et de suivre les tâches efficacement.

En savoir plus sur l’[intégration d’Adobe Workfront](../user-guide/workfront-integration.md) dans Experience Manager Guides.

## Prérequis

Avant de commencer, assurez-vous des points suivants :

1. Vous disposez d’un accès standard à Adobe Workfront et d’un accès administrateur à Experience Manager Guides.
2. Vous [créez un formulaire personnalisé dans Adobe Workfront](https://experienceleague.adobe.com/fr/docs/workfront/using/administration-and-setup/customize/custom-forms/design-a-form/design-a-form) requis pour Experience Manager Guides en utilisant spécifiquement les champs suivants :

   | Type de champ | Libellé | Nom | Choix (Afficher les valeurs activées) |
   |------------|------|------|-------------------------------|
   | Liste déroulante à sélection unique | Type de tâche | task-type | Création (valeur = AUTEUR), Publication (valeur = PUBLIER), Traduction (valeur = TRADUCTION), Révision (valeur = RÉVISION) |
   | Liste déroulante à sélection unique | État de la tâche | état de la tâche | Création (valeur = AUTEUR), Révision (valeur = RÉVISION) |
   | Texte avec formatage | Liste d’auteurs | author-list | - |
   | Texte avec formatage | Liste des réviseurs | reviewer-list | - |
   | Texte monoligne | Vérifier l’URL | review-url | - |

>[!NOTE]
>
> Dans le tableau ci-dessus, les choix représentent les options disponibles sous le champ **Type de tâche**. Pour chaque option, vous devez fournir les valeurs **nom de la tâche** et **valeur de la tâche**. Le nom et les valeurs de chaque type de tâche doivent être identiques à ceux mentionnés dans le tableau ci-dessus. Par exemple, pour le type de tâche Auteur, indiquez **Création** comme nom et **AUTEUR** comme valeur correspondante.

## Commencer

Pour configurer Adobe Workfront dans Experience Manager Guides, procédez comme suit.

1. Ouvrez le panneau **Outils** et sélectionnez **Guides**.
2. Sélectionnez **Configurer Workfront**.

   La page de configuration **Workfront** s’affiche.

   ![](assets/configure-workfront-page.png)

3. Sur la page de configuration **Workfront**, saisissez l’URL complète du domaine Workfront de votre organisation, l’ID client et la clé secrète client.

   Pour accéder à la clé **ID client** et **Secret client** configurée dans votre configuration Adobe Workfront, accédez à `Setup >> Systems>> oAuth2 Applications`.

   Pour plus d’informations sur la configuration de votre domaine Adobe Workfront, consultez la section Flux de code d’autorisation dans [Création d’applications OAuth2 pour les intégrations Workfront](https://experienceleague.adobe.com/fr/docs/workfront/using/administration-and-setup/configure-integrations/create-oauth-application#create-an-oauth2-application-using-user-credentials-authorization-code-flow).

4. Sélectionnez **Connexion et vérification**.

   Vous êtes redirigé vers la page de connexion d’Adobe Workfront.
5. Connectez-vous à l’aide de votre adresse e-mail Adobe Workfront, puis sélectionnez **Autoriser l’accès** pour permettre à l’application Oauth2 d’accéder à votre compte Adobe Workfront respectif.

   Vous êtes automatiquement redirigé vers la page de configuration de Workfront sur Experience Manager Guides.

6. Dans la liste déroulante des formulaires personnalisés, sélectionnez le formulaire personnalisé Adobe Workfront que vous avez créé pour Experience Manager Guides. Afficher [Conditions préalables](#prerequisites).
7. Sélectionnez **Enregistrer et fermer** pour appliquer et enregistrer les modifications apportées à la configuration de Workfront.

Une fois la configuration effectuée, [ajoutez des utilisateurs à Adobe Workfront](https://experienceleague.adobe.com/fr/docs/workfront/using/administration-and-setup/add-users/create-manage-users/add-users) en utilisant les mêmes adresses e-mail que celles de Experience Manager Guides.



