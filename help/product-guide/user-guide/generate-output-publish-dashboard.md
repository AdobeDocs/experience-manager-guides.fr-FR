---
title: Gérer les tâches de publication à l’aide du tableau de bord de publication
description: Gérez les tâches de publication à l’aide du tableau de bord de publication dans AEM Guides. Savoir comment accéder au tableau de bord de publication et annuler une tâche de publication.
exl-id: d9e25e52-ba9d-4088-ac95-8df76b69f5d3
feature: Publishing
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 0%

---

# Gérer les tâches de publication à l’aide du tableau de bord de publication {#id205CC08305Z}

Lorsqu&#39;un grand nombre de tâches de publication sont exécutées sur votre système, il devient pratiquement impossible de vérifier chaque plan DITA individuellement pour surveiller sa tâche de publication. Adobe Experience Manager Guides offre aux administrateurs et aux éditeurs une vue unifiée de toutes les tâches de publication exécutées dans le système. Une liste de toutes les tâches de publication actives est disponible dans le tableau de bord de publication.

Le tableau de bord de publication donne un aperçu complet de toutes les tâches de publication actuellement en cours d’exécution dans le système.

![](images/publish-dashboard.png){align="left"}

Le tableau de bord de publication contient les détails suivants :

- **Titre du mappage** - Titre d’un fichier de mappage en cours de publication ou se trouvant dans la file d’attente de publication.

- **Nom de fichier** - Nom de fichier du plan DITA.

- **Paramètre prédéfini de sortie** - Nom du paramètre prédéfini de sortie utilisé pour générer la sortie.

- **Déclenché par** - Nom d’utilisateur de l’utilisateur qui a lancé la tâche de publication.

- **Démarré le** - Date et heure de début de la tâche de publication.

- **Temps écoulé** - Temps écoulé depuis le moment où la tâche de publication est en cours d’exécution dans le système.

- **Icône Supprimer** - Annulez ou mettez fin à une tâche de publication.

Le panneau de gauche du tableau de bord de publication propose les options de filtrage suivantes :

- **Paramètre prédéfini de sortie** - Sélectionnez un ou plusieurs paramètres prédéfinis de sortie pour lesquels vous souhaitez afficher les tâches de publication actuellement actives. Dans la capture d’écran suivante, les tâches de publication sont filtrées afin d’afficher uniquement les tâches qui utilisent le paramètre prédéfini de sortie du site AEM :

  ![](images/publish-dashboard-preset-filter.png){align="left"}

- **Initié par** - Sélectionnez un nom d’utilisateur dans la liste pour afficher les tâches de publication initiées par l’utilisateur sélectionné.

- **Mapper** - Sélectionnez un fichier de mappage dans la liste pour afficher les tâches de publication exécutées pour le mappage sélectionné.

## Accès au tableau de bord de publication

Vous pouvez accéder au tableau de bord **Publication** directement à partir de la page d’accueil de Experience Manager Guides [&#128279;](./intro-home-page.md). Ouvrez la page d’accueil et sélectionnez l’option **File d’attente de publication** dans le panneau de gauche.

>[!NOTE]
>
> Seul un administrateur ou un éditeur peut accéder au tableau de bord de publication.

Vous pouvez également accéder au tableau de bord **Publication** à partir de la page Adobe Experience Manager **Outils**. Pour utiliser cette méthode, procédez comme suit :

1. Sélectionnez le logo Adobe Experience Manager en haut de l’écran, puis sélectionnez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils.

1. Sélectionnez la mosaïque **Publier le tableau de bord**.

   Le tableau de bord de publication s’ouvre avec une liste de toutes les tâches de publication actives dans le système.

   Si vous sélectionnez le lien Nom de fichier, le tableau de bord du plan DITA du plan sélectionné s&#39;affiche.

   ![](images/publish-dashboard-click-filename-link.png){align="left"}


>[!NOTE]
>
> Vous pouvez également accéder au tableau de bord de publication à partir de l’onglet **Sorties** tout en générant une sortie à partir du tableau de bord de mappage. Pour plus d’informations, voir [Affichage de l’état de la tâche de génération de sortie](generate-output-for-a-dita-map.md#viewing_output_history).

## Annuler une tâche de publication

Pour annuler une tâche de génération de sortie à partir du tableau de bord de publication, procédez comme suit :

1. [Accédez au tableau de bord de publication](#access-the-publish-dashboard).

1. Dans la liste des tâches de publication actives, sélectionnez l’icône de suppression d’une tâche à annuler.

   ![](images/publish-dashboard-cancel-task.png){align="left"}

1. Sélectionnez **Oui** dans l’invite de message **Confirmer l’annulation**.

   La commande d’annulation est acceptée et une tentative d’annulation est effectuée tant que la tâche reste active. Une fois la tâche terminée, elle est supprimée de la liste des tâches actuellement actives. Le statut de la tâche est également mis à jour dans le tableau de bord du plan DITA comme Annulé. Dans la capture d&#39;écran suivante, la tâche *HTML5* est annulée à partir du tableau de bord de publication et son statut est également modifié dans le tableau de bord du plan DITA.

   ![](images/cancelled-output-task.png){align="left"}


**Rubrique parente :**&#x200B;[&#x200B; Génération de sortie](generate-output.md)
