---
title: Créer un projet DITA
description: Créez un projet DITA à l'aide d'un modèle dans AEM Guides. Découvrez comment utiliser un projet DITA pour lancer les révisions.
exl-id: 0cd83fe3-1764-4f04-ae11-0b71b6ac576c
feature: Reviewing
role: User
source-git-commit: ae36a7fdff6ae147619340aa3a3d2bb6c7774fe0
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 0%

---

# Créer un projet DITA {#id1645HA00NM6}

Adobe Experience Manager Guides fournit un modèle de projet DITA que vous pouvez utiliser pour créer et gérer vos tâches de révision.

Vous pouvez créer un projet DITA, puis l&#39;utiliser pour lancer vos révisions. Un projet vous permet de définir une date limite et de contrôler les tâches et le temps requis pour terminer la tâche de révision pour laquelle vous avez créé le projet.

Vous pouvez ajouter des membres de l’équipe à un projet, qui pourront ensuite se voir attribuer différents rôles : Auteurs, Réviseurs et Éditeurs.

Une fois que vous avez créé votre projet DITA, vous pouvez lancer votre révision à partir de l&#39;éditeur ou de l&#39;interface utilisateur d&#39;Assets. Pour plus d’informations, voir [Envoyer les rubriques pour révision](review-send-topics-for-review.md#).

De même, chaque fois qu’un auteur lance un workflow de révision, les membres sélectionnés du projet reçoivent une notification par e-mail. Pour configurer les notifications par e-mail, consultez *Personnalisation des modèles d’e-mail* dans Installation et configuration d’Adobe Experience Manager Guides as a Cloud Service.

Pour créer un projet DITA, procédez comme suit :

1. Ouvrez la console Projets .

   Vous pouvez également accéder à la console Projets à l’aide de l’URL suivante :

   ```http
   http://<server name>:<port>/projects.html
   ```

1. Sélectionnez **Créer** \> **Projet** pour lancer l’assistant Créer un projet.

   ![](images/project-console-63.png){width="650" align="left"}

1. Sur la page Créer un projet , sélectionnez le modèle **Projet DITA** et sélectionnez **Suivant**.

1. Sur la page Propriétés du projet , saisissez les détails suivants :

   Informations de l’onglet **De base** :

   ![](images/create-project.png){width="650" align="left"}

   - Saisissez le **titre**, la **description** et la **date d’échéance** de votre projet.

   - Vous pouvez éventuellement choisir une miniature pour le projet.

   - Par défaut, vous êtes nommé propriétaire du projet. Pour ajouter d’autres utilisateurs à ce projet :

   1. Saisissez ou choisissez un utilisateur dans la liste déroulante **Utilisateur**.

   1. Choisissez un type d’utilisateur : Auteurs, Réviseurs ou Éditeurs.

      >[!NOTE]
      >
      >Vous verrez d&#39;autres types d&#39;utilisateurs dans cette liste déroulante, mais pour un projet DITA, vous ne devez choisir que parmi les types d&#39;utilisateurs Auteurs, Réviseurs ou Éditeurs. Même si vous ajoutez un utilisateur d&#39;un autre type, cet utilisateur ne pourra accéder à aucune fonctionnalité spécifique à DITA disponible dans Experience Manager Guides.

   1. Sélectionnez **Ajouter**.

      >[!NOTE]
      >
      >Si vous utilisez la version 3.5 ou antérieure de Experience Manager Guides, une option vous permettant de sélectionner un fichier de plan DITA s&#39;affiche pour résoudre les principales références relatives aux workflows de modification de rubrique, de prévisualisation et de révision. Dans la version 3.6 et les versions ultérieures, vous pouvez définir la carte racine via l’éditeur. Pour plus d’informations, consultez les [Préférences utilisateur](web-editor-features.md#id2087G0P40SB) dans l’éditeur. Vous pouvez également définir la carte racine en la configurant au niveau des profils globaux ou au niveau du dossier. Pour plus d’informations, consultez *Configuration de profils globaux ou de niveau dossier* dans le Guide d’installation et de configuration.

   Informations de l’onglet **Avancé** :

   - Saisissez un nom pour le projet. Ce nom est utilisé pour créer l’URL de ce projet.

1. Sélectionnez **Créer**.

   La boîte de dialogue Projet créé s’affiche.

1. Sélectionnez **Ouvrir** pour ouvrir la page de votre projet.


**Rubrique parente :**&#x200B;[ Présentation de la révision](review.md)
