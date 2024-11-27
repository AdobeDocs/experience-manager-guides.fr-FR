---
title: Gestion des tâches de publication à l’aide du tableau de bord Publish
description: Gérez les tâches de publication à l’aide du tableau de bord Publish dans AEM Guides. Découvrez comment accéder au tableau de bord de publication et annuler une tâche de publication.
feature: Publishing
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 0%

---

# Gestion des tâches de publication à l’aide du tableau de bord Publish {#id205CC08305Z}

Lorsque vous disposez d’un grand ensemble de tâches de publication s’exécutant sur votre système, il devient pratiquement impossible de vérifier chaque mappage DITA individuellement pour surveiller sa tâche de publication. AEM Guides offre aux administrateurs et aux éditeurs une vue unifiée de toutes les tâches de publication exécutées dans le système. Une liste de toutes les tâches de publication actives est disponible dans le tableau de bord Publish.

Le tableau de bord Publish donne un aperçu complet de toutes les tâches de publication en cours d’exécution dans le système.

![](images/publish-dashboard.png){width="800" align="left"}

Le tableau de bord Publish contient les détails suivants :

- **Titre de la carte** : titre d’un fichier de carte en cours de publication ou se trouve dans la file d’attente de publication.

- **Nom de fichier** - Nom de fichier du mappage DITA.

- **Paramètre prédéfini de sortie** : nom du paramètre prédéfini de sortie utilisé pour générer la sortie.

- **Initié par** - Nom d’utilisateur de l’utilisateur qui a initié la tâche de publication.

- **Démarré le** - Date et heure de début de la tâche de publication.

- **Temps écoulé** - Temps écoulé depuis l’exécution de la tâche de publication dans le système.

- **Icône Supprimer** - Annuler ou arrêter une tâche de publication.

Le panneau de gauche du tableau de bord Publish fournit les options de filtrage suivantes :

- **Paramètre prédéfini de sortie** : sélectionnez un ou plusieurs paramètres prédéfinis de sortie pour lesquels vous souhaitez afficher les tâches de publication actuellement actives. Dans la capture d’écran suivante, les tâches de publication sont filtrées afin de n’afficher que les tâches qui utilisent le paramètre prédéfini de sortie AEM site :

  ![](images/publish-dashboard-preset-filter.png){width="800" align="left"}

- **Initié par** - Sélectionnez un nom d’utilisateur dans la liste pour afficher les tâches de publication initiées par l’utilisateur sélectionné.

- **Carte** - Sélectionnez un fichier de mappage dans la liste pour afficher les tâches de publication exécutées pour la carte sélectionnée.

## Accès au tableau de bord Publish {#id205CC100DY4}

Effectuez les étapes suivantes pour accéder au tableau de bord Publish :

>[!NOTE]
>
> Seul un administrateur ou un éditeur peut accéder au tableau de bord Publish.

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et sélectionnez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils.

1. Cliquez sur la mosaïque **Tableau de bord Publish** .

   Le tableau de bord Publish s’ouvre avec une liste de toutes les tâches de publication actives du système.

   Si vous cliquez sur le lien Nom de fichier , la console de mappage DITA de la carte sélectionnée s’affiche.

   ![](images/publish-dashboard-click-filename-link.png){width="800" align="left"}


>[!NOTE]
>
> Vous pouvez également accéder au tableau de bord Publish à partir de l’onglet Sorties lorsque vous générez la sortie à partir du tableau de bord de la carte. Pour plus d’informations, voir [Affichage de l’état de la tâche de génération de sortie](generate-output-for-a-dita-map.md#viewing_output_history).

## Annulation d’une tâche de publication

Pour annuler une tâche de génération de sortie à partir du tableau de bord Publish, procédez comme suit :

1. [Accédez au tableau de bord Publish](#id205CC100DY4).

1. Dans la liste des tâches de publication actives, cliquez sur l’icône de suppression d’une tâche que vous souhaitez annuler.

   ![](images/publish-dashboard-cancel-task.png){width="800" align="left"}

1. Cliquez sur **Oui** dans l’invite de message Confirmer l’annulation .

   La commande d’annulation est acceptée et l’annulation est effectuée tant que la tâche reste active. Une fois la tâche terminée, elle est supprimée de la liste des tâches actives. L’état de la tâche est également mis à jour dans la console de mappage DITA sous la forme Annulé. Dans la capture d’écran suivante, la tâche *HTML5* est annulée à partir du tableau de bord Publish et son état est également modifié dans la console de mappage DITA.

   ![](images/cancelled-output-task.png){width="800" align="left"}


**Rubrique parente :**[ Génération de sortie](generate-output.md)
