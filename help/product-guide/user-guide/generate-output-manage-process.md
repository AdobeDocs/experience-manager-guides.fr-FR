---
title: Génération de sortie
description: Gérez le processus de génération de sortie dans AEM Sites, PDF, HTML5, EPUB, personnalisé et JSON par le biais de plug-ins DITA-OT, de la publication Native PDF et de FMPS dans AEM Guides.
feature: Publishing
role: User
exl-id: 11bb3604-f45c-4df7-be74-588dbf8594af
TQID: 'https://experienceleague.adobe.com/hfJ-UrLwhOp0IFxw3vRpCgFU8eWkZCConfPlQfwL9V8'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
    internal-label: Native PDF publishing
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
    internal-label: Map console
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: 43e3af5a6d753e6124acf1d56e99497f6b9c4cd9
workflow-type: tm+mt
source-wordcount: '1296'
ht-degree: 0%
---
# Gérer le processus de génération de sortie

Adobe Experience Manager Guides permet de surveiller et de gérer les tâches de génération de sortie pour vos plans DITA. Vous pouvez consulter le statut des tâches de génération de sortie, annuler les tâches en cours et supprimer les entrées obsolètes de l&#39;historique de génération de sortie.

Une fois que vous avez lancé une tâche de génération de sortie pour un mappage ou que vous avez régénéré les rubriques sélectionnées, Experience Manager Guides envoie la tâche à la file d’attente de génération de sortie. Le statut de la tâche est mis à jour au fur et à mesure que le processus de génération de sortie progresse.

Vous pouvez afficher et gérer des tâches de génération de sortie à l’aide de l’onglet **Historique des sorties** de l’éditeur ou de l’onglet **SORTIES** de l’interface utilisateur d’Assets.


## Afficher et gérer les tâches de génération de sortie à partir de l’éditeur

Vous pouvez afficher et gérer les tâches de génération de sortie directement à partir de l’onglet **Historique de sortie** dans la console Mappage.

Ouvrez le plan DITA dans la console Map et générez la sortie à l’aide de l’un des paramètres prédéfinis de sortie disponibles dans Experience Manager Guides. Passez à l’onglet **Historique de sortie** pour afficher le statut de la tâche de génération de sortie et d’autres détails, comme illustré ci-dessous :

![](images/output-history-editor-view.png)

Pour chaque tâche de génération de sortie, vous pouvez visualiser les informations suivantes :

1. **Préréglage :** nom du paramètre prédéfini de sortie utilisé pour générer la sortie.
1. **Type de paramètre prédéfini :** type de paramètre prédéfini de sortie utilisé pour la génération de la sortie.
1. **Statut :** statut actuel de la tâche de génération de sortie, tel que En attente, Exécution, Terminé, Échec, Post-publication ou Annulé.
1. **Généré le :** date et heure de génération de la sortie.
1. **Durée :** temps nécessaire à la génération de la sortie.
1. **Généré par :** nom de l’utilisateur qui a lancé la tâche de génération de sortie.

>[!NOTE]
>
> Si une tâche de génération de sortie est en cours, le libellé **Exécution** dans la colonne **Statut** indique que la tâche est en cours de traitement. Utilisez l’option **Actualiser** pour afficher le dernier statut des tâches de génération de sortie.

Vous pouvez également annuler une tâche de génération de sortie en cours. Pour annuler une tâche en cours, pointez sur la ligne de la tâche et sélectionnez **Annuler la génération**.

![](images/cancel-generation-editor.png)

Une fois la tâche annulée, le libellé **Annulée** s&#39;affiche dans la colonne **Statut**.

Pour les tâches de génération de sortie terminées, passez la souris sur la ligne de tâche pour accéder aux actions suivantes, en fonction du statut de la tâche :

![](images/output-history-editor-actions.png)

- **Ouvrir la sortie :** permet d’afficher la sortie générée dans un nouvel onglet.
- **Afficher les journaux :** accédez aux journaux de génération de sortie pour consulter les détails de publication et résoudre les erreurs ou les avertissements.
- **Supprimer l’historique de sortie :** supprimez la tâche sélectionnée de l’historique de génération des sorties sans supprimer la sortie générée.

Vous pouvez également utiliser les options suivantes pour utiliser l’historique de génération de sortie :

- **Rechercher :** utilisez le champ de recherche pour rechercher des tâches de génération de sortie spécifiques dans l’historique.
- **Télécharger CSV :** sélectionnez **Télécharger CSV** pour télécharger l’historique de génération de sortie au format CSV.
- **Redimensionner la colonne :** sélectionnez la liste déroulante en regard d’un nom de colonne et sélectionnez **Redimensionner la colonne** pour ajuster la largeur de la colonne.
- **Filtre** : appliquez des filtres en fonction du type de paramètre prédéfini de sortie, du statut de la tâche, ainsi que de la période et de l’heure pour réduire l’historique de génération de sortie.

  ![](./images/output-history-filters.png)

En outre, les icônes à code de couleur indiquent l’état de chaque tâche : vert pour les tâches réussies, orange pour les tâches terminées avec des messages et rouge pour les tâches ayant échoué. Cela vous permet d’identifier rapidement les tâches qui nécessitent une attention particulière.

## Afficher et gérer les tâches de génération de sortie à partir de l’interface utilisateur d’Assets

À l’aide de l’API Assets, vous pouvez effectuer les actions suivantes sur la sortie générée :

- [Afficher le statut de la tâche de génération de sortie](#view-the-status-of-the-output-generation-task)
- [Annuler une tâche de génération de sortie](#cancel-an-output-generation-task)
- [Supprimer une tâche de sortie](#delete-an-output-task)

### Afficher le statut de la tâche de génération de sortie

Une fois que vous avez lancé la tâche de génération de sortie pour un mappage ou que vous avez régénéré les rubriques sélectionnées, Experience Manager Guides envoie cette tâche à la file d’attente de génération de sortie. Cette file d’attente est mise à jour en temps réel, affichant le statut de chaque tâche de génération de sortie dans la file d’attente.

1. Dans l’interface utilisateur d’Assets, accédez au fichier de mappage pour lequel vous souhaitez vérifier le statut de génération de sortie et ouvrez-le.

1. Sélectionnez **SORTIES**.

   ![](images/output-queued.png)

   La page Sorties est divisée en deux parties :

   - **Sorties mises en file d’attente :**

     Répertorie les sorties qui sont en attente de génération ou qui sont en cours de génération. Les tâches en file d’attente ou en cours s’affichent avec une icône de couleur bleue devant le nom du paramètre prédéfini. Vous pouvez également trouver le paramètre ou le préréglage de génération de sortie utilisé pour la tâche mise en file d’attente, le type, l’utilisateur qui a initié la tâche, la durée écoulée depuis la mise en file d’attente de la tâche et le statut actuel.

     Sélectionnez le lien pour accéder au tableau de bord **Publication** et afficher le statut d’exécution actuel. Une liste de toutes les tâches de publication actives est disponible dans le tableau de bord de publication. Les liens **Sorties mises en file d’attente** et **Tableau de bord de publication** ne s’affichent que lorsque des sorties sont en attente de génération ou en cours de génération. Elles n’apparaissent pas une fois les tâches de sortie terminées.Pour plus d’informations sur le tableau de bord de publication, consultez la section [Gérer les tâches de publication à l’aide du tableau de bord de publication](generate-output-publish-dashboard.md#).

   - **Sorties générées**

     Répertorie les tâches de sortie qui ont été terminées. Là encore, les informations affichées ici sont similaires à la section Sorties mises en file d’attente avec quelques différences. Vous disposez d’un nouvel ensemble d’informations sous la forme d’une icône de résultat de sortie et de l’heure de génération de la sortie.

     Dans cette liste, vous pouvez avoir des tâches qui se sont exécutées avec succès, des tâches qui se sont exécutées avec un message ou des tâches ayant échoué. Les tâches réussies s’affichent avec une icône de couleur verte, les tâches comportant un message avec une icône de couleur orange et les tâches ayant échoué s’affichent avec une icône de couleur rouge.

     Pour toutes les tâches, le processus de publication crée un fichier journal \(logs.txt\) accessible en sélectionnant le lien dans la colonne **Date de génération**. Pour les tâches ayant échoué ou contenant des messages, vous pouvez vérifier le fichier journal, comme expliqué dans la section [Afficher et vérifier le fichier journal](generate-output-basic-troubleshooting.md#id1822G0P0CHS).

     >[!NOTE]
     >
     > Lorsque vous sélectionnez le lien de la sortie PDF générée, vous êtes invité à télécharger le PDF.


### Annuler une tâche de génération de sortie

Experience Manager Guides offre aux éditeurs un moyen simple et facile d’annuler toute tâche de publication en cours. En tant qu&#39;éditeur, vous pouvez annuler une tâche de publication en cours à partir de la console de plan DITA ou du tableau de bord [Publication](generate-output-publish-dashboard.md#).

Effectuez les étapes suivantes pour annuler une tâche de génération de sortie à partir de la console de mappage DITA :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de mappage pour lequel vous souhaitez annuler une tâche de génération de sortie en cours, puis ouvrez-le.

1. Sélectionnez **SORTIES**.

1. Dans la liste **Sorties mises en file d’attente**, placez le pointeur sur une tâche à annuler.

1. Sélectionnez l’icône **Annuler ce traitement**.

   ![](images/cancel-publish-task-map-console.png)

1. Sélectionnez **Oui** dans l’invite de message **Confirmer l’annulation**.

   ![](images/confirm-cancel-output-map-console.png)

   Si la tâche n&#39;est pas encore démarrée, la commande d&#39;annulation est exécutée sur la tâche. Pour une tâche en cours d&#39;annulation, le Statut est défini sur Annulation.

   Une fois la tâche annulée, elle est déplacée vers la liste **Sorties générées** avec un statut **Annulé**. Lorsque vous pointez sur la tâche annulée, le nom de l’utilisateur qui a annulé la tâche s’affiche. Dans la capture d’écran suivante, la tâche *HTML5* est annulée.

   ![](images/cancelled-output-task.png)


### Supprimer une tâche de sortie

Lorsque vous générez plusieurs sorties pour un plan DITA, la liste des sorties générées pour un tel plan devient très longue au fil du temps. En tant qu’éditeur, vous pouvez nettoyer l’historique de sortie de n’importe quel fichier de mappage en supprimant les tâches obsolètes de la liste *Sorties générées*. Notez que la sortie n’est pas supprimée du système, seule l’entrée de la sortie générée est supprimée de la liste *Sorties générées*.

Effectuez les étapes suivantes pour supprimer une tâche de sortie de la liste Sortie générée :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de mappage à partir duquel vous souhaitez supprimer les tâches, puis ouvrez-le.

1. Sélectionnez **SORTIES**.

1. Dans la liste **Sorties générées**, placez le pointeur sur une tâche à supprimer.

1. Sélectionnez l’icône de suppression.

   ![](images/delete-output-task.png)

1. Sélectionnez **Oui** dans l’invite de message **Confirmer la suppression**.

   La tâche est supprimée de la liste des Sorties générées .

















