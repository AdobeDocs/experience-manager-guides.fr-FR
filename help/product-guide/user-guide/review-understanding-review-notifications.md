---
title: Comprendre les notifications de révision
description: Découvrez les différents types de notifications de révision et leur déclenchement lors des différentes phases du workflow de révision dans Experience Manager Guides.
feature: Reviewing
role: User
source-git-commit: b7648fe1d36de3c243ca5a55f42a41f7523056ce
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 0%

---

# Comprendre les notifications de révision

>[!IMPORTANT]
>
> Les nouvelles fonctionnalités décrites dans cet article sont activées par défaut avec la version 2508 de Experience Manager Guides as a Cloud Services. Les révisions créées avant la migration ne sont pas affectées et continueront à utiliser le workflow précédent. Si vous préférez continuer à utiliser les fonctionnalités existantes sans ces mises à jour, contactez votre équipe du succès client pour que les nouvelles fonctionnalités soient désactivées.

Experience Manager Guides simplifie la collaboration entre les auteurs et les réviseurs par le biais d’un workflow de révision structuré. Dans le cadre de ce workflow, les notifications jouent un rôle essentiel pour tenir tous les participants à une tâche de révision informés et réactifs aux modifications.

Chaque fois qu’une action liée à la révision est effectuée, comme l’affectation d’une tâche, l’achèvement d’une tâche ou les mises à jour des commentaires, une notification est automatiquement envoyée aux utilisateurs concernés par la tâche de révision afin d’attirer leur attention immédiate. Ces notifications sont diffusées dans deux formats :

- **Notifications AEM** : affichées dans l’interface d’AEM.
- **Notifications par e-mail** : envoyées directement dans la boîte de réception de l’utilisateur.

Le tableau ci-dessous présente un aperçu des différents types de notifications de révision, des actions qui les déclenchent et de leur apparence dans différents formats :


## Vérifier les formats de notification avec des exemples de valeurs

| **Action de révision** | **Titre de la notification (AEM)** | **Texte de notification (AEM)** | **Objet de l’e-mail** | **Texte de notification électronique** | **Destinataire** |
|-----------------------------|--------------------------------------------------|-------------------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------|-----------------------------|
| Tâche de révision créée | Tâche de révision affectée : **Révision de la page d’accueil** | Affecté par **auteur** | Tâche de révision affectée : **Révision de la page d’accueil** | **Auteur** a créé une tâche de révision **Révision de la page d’accueil** dans le projet **Révision de WebDocs** avec une date d’échéance de **15 août 2025**. Vous avez été affecté en tant que réviseur/réviseuse. | **Réviseur** |
| Retour d’informations envoyé | Consulter les commentaires reçus pour **Examen de la page d’accueil** | Retour d’informations du **réviseur** | Consulter les commentaires reçus pour **Examen de la page d’accueil** | **Reviewer** a soumis des commentaires pour la tâche **Homepage Review** dans le projet **WebDocs Revamp**. Veuillez vérifier et effectuer les mises à jour nécessaires bien avant la date d’échéance **15 août 2025**. | **Auteur** ou **Initiateur de la tâche** |
| Révision demandée | Révision demandée pour **Homepage Review** | Demande par **auteur** | Révision demandée pour **Homepage Review** par **Author** | **Auteur** a mis à jour le document pour la tâche **Révision de la page d’accueil** en fonction de vos commentaires et demande à être révisé. Veuillez vérifier bien avant la date d’échéance **15 août 2025**. | **Réviseur** |
| Révision terminée | Tâche de révision close : **Révision de la page d’accueil** | Fermée par **auteur** | Tâche de révision close : **Révision de la page d’accueil** | La tâche de révision **Révision de la page d’accueil** sous le projet **Réorganisation des WebDocs** a été fermée par **Auteur**. | **Auteur** ou **Initiateur de la tâche** , **Réviseur** |
| Réviseur non affecté | Affectation annulée de la tâche de révision **Révision de la page d’accueil** | Non affecté par **auteur** | Affectation annulée de la tâche de révision **Révision de la page d’accueil** | L’affectation de vous a été annulée pour la tâche de révision **Révision de la page d’accueil** dans le projet **Réorganisation des WebDocs** par **Auteur**. | **Réviseur** |
| Mention de balise | Mentionné dans le commentaire de tâche de révision pour **Révision de page d’accueil** | Mentionné par **auteur** | Mentionné dans le commentaire de tâche de révision pour **Révision de page d’accueil** | Vous avez été mentionné dans un commentaire sur la tâche **Révision de la page d’accueil** sous **Réorganisation des WebDocs** par **Auteur**. **Extrait de commentaire :** *« Veuillez mettre à jour la structure d’en-tête pour respecter les directives d’accessibilité. »* | **Utilisateur mentionné** |
| Contenu mis à jour lors de la révision | Rubrique mise à jour dans la tâche de révision **Révision de la page d’accueil** | Mise à jour par **auteur** | Rubrique mise à jour dans la tâche de révision **Révision de la page d’accueil** | **Auteur** a mis à jour les versions de rubrique pour la tâche de révision **Révision de la page d’accueil**. Veuillez vérifier bien avant la date d’échéance **15 août 2025**. | **Réviseur** |


Dans le tableau ci-dessus, le **texte en gras** représente des exemples de valeurs et est piloté par des variables prédéfinies qui peuvent être utilisées dans les notifications.


Par exemple :

- **Révision de la page d’accueil** est un exemple de nom de tâche.
- **Priya** (auteur) et **John** (réviseur) sont des exemples de noms d’utilisateur.
- **WebDocs Revamp** est un exemple de nom de projet.
- **15 août 2025** est un exemple de date d’échéance.

En outre, si une tâche contient des commentaires, un extrait de commentaire ( une partie du commentaire complet) est inclus dans l’e-mail de notification. L&#39;extrait est affiché dans les cas suivants :

- Lorsque vous êtes identifié dans un commentaire, un extrait du commentaire identifié s’affiche dans l’e-mail de notification.
- Lorsqu’un commentaire au niveau de la tâche est ajouté à une tâche de révision dont vous faites partie, un extrait de ce commentaire apparaît dans l’e-mail de notification.

Pour obtenir une liste complète des variables prédéfinies et consulter la personnalisation des notifications, reportez-vous à la section [Configurer et personnaliser des workflows](../cs-install-guide/customize-workflows.md#customize-email-and-aem-notification-templates).




**Rubrique parente :**[ Présentation de la révision](review.md)
