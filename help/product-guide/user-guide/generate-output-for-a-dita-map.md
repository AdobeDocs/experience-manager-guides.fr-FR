---
title: Générer la sortie d’un mappage DITA à partir de la console de mappage
description: Générez la sortie d’un mappage DITA à partir de la console de mappage dans AEM Guides. Découvrez la génération incrémentale de sortie et comment afficher l’état, annuler et supprimer une tâche de sortie.
exl-id: d6cbd44c-e74c-4192-bcc4-fb7752c59508
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 0%

---

# Générer la sortie d’un mappage DITA à partir de la console de mappage {#id1825FG00UHT}

Effectuez les étapes suivantes pour générer la sortie pour un mappage DITA :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de mappage DITA à publier, puis cliquez dessus.

   La console de mappage DITA s’affiche avec la liste des paramètres prédéfinis de sortie disponibles pour générer la sortie.

1. Sélectionnez un ou plusieurs paramètres prédéfinis de sortie à utiliser pour générer la sortie.

   ![](images/generate-multiple-outputs-uuid.png){width="800" align="left"}

   >[!NOTE]
   >
   > Si vous générez la sortie Site AEM, le processus de publication utilise la structure définie dans la variable `.ditamap` pour créer AEM structure du site.

1. Cliquez sur l&#39;icône Générer pour lancer le processus de génération de sortie.


Vous pouvez afficher l’état actuel de la requête de génération de sortie en cliquant sur Sorties. Pour plus d’informations, voir [Afficher l&#39;état de la tâche de génération de sortie](#viewing_output_history)

>[!IMPORTANT]
>
> Si un processus de génération de sortie pour un paramètre prédéfini se trouve dans la file d’attente ou est en cours, vous ne pouvez pas lancer une autre tâche de génération de sortie pour le même paramètre prédéfini.

Vous pouvez générer la sortie du PDF pour un ou plusieurs paramètres prédéfinis de sortie créés pour un mappage DITA à partir de l’éditeur web. Pour plus d’informations, voir [Utilisez le panneau Génération rapide pour générer et afficher la sortie des paramètres prédéfinis.](web-editor-quick-generate-panel.md#).

Vous pouvez également générer la sortie AEM Site pour une ou plusieurs rubriques, ou l’ensemble du mappage DITA à partir de l’éditeur web. Pour plus d’informations, voir [Publication basée sur des articles à partir de l’éditeur web](web-editor-article-publishing.md#id218CK0U019I).

## Génération incrémentielle de sortie {#generating_standalone_topic}

>[!NOTE]
>
> La génération de sortie incrémentielle s’applique uniquement à la sortie AEM site. En outre, vous pouvez uniquement générer des rubriques DITA \(.dita/.xml\) à partir d’un mappage ou de sous-mappages DITA. Si vous sélectionnez un mappage DITA, un sous-mappage, un groupe de rubriques ou une rubrique avec `@processing-role="resource-only"`, l’option de régénération n’est pas disponible.

Il peut y avoir un certain nombre d’instances où vous ne mettriez à jour que quelques rubriques dans votre carte DITA et ne repoussez que ces rubriques mises à jour en direct. Pour gérer ces scénarios, AEM Guides vous permet de créer des sorties incrémentielles. Si vous avez mis à jour quelques rubriques, vous n’avez pas besoin de régénérer l’ensemble du mappage DITA. Vous pouvez sélectionner uniquement les rubriques mises à jour et les régénérer.

Si votre carte est tronquée et que vous avez mis à jour une seule rubrique dans cette carte, vous devez régénérer la carte entière pour la rubrique ou le contenu mis à jour à refléter dans la sortie. Vous n’obtiendrez pas l’option de régénération de sortie au niveau de la rubrique. Elle n’est disponible qu’au niveau de la carte \(découpé\). Cela s’applique à la carte parent et à toutes les sous-cartes.

Effectuez les étapes suivantes pour générer à nouveau une sortie pour une rubrique ou un groupe de rubriques spécifique :

>[!IMPORTANT]
>
> Lorsque vous régénérez la sortie Site AEM, la sortie est créée à l’aide de la version actuelle des fichiers et non de la ligne de base jointe.

1. Dans l’interface utilisateur d’Assets, accédez à et cliquez sur le fichier de mappage DITA.

   La console de mappage DITA s’affiche avec la liste des paramètres prédéfinis de sortie disponibles pour générer la sortie.

1. Sélectionnez la variable **Sujets** .

   Une liste des rubriques disponibles dans le mappage DITA s’affiche.

1. Sélectionnez les rubriques que vous souhaitez régénérer.

   >[!NOTE]
   >
   > Si vous avez ajouté de nouvelles rubriques au mappage DITA, vous ne pourrez pas générer ces nouvelles rubriques à partir de cet emplacement. Vous devez d’abord publier les rubriques nouvellement ajoutées à l’aide de la fonction de publication de mappage DITA.

   ![](images/regenerate-topics.png){width="800" align="left"}

1. Cliquez sur **Régénérer**.

   La page Régénérer les rubriques sélectionnées s’affiche.

1. Sélectionnez le paramètre prédéfini de sortie à utiliser pour régénérer les rubriques sélectionnées.

1. Cliquez sur **Régénérer** pour lancer le processus de génération de sortie.


>[!IMPORTANT]
>
> Si vous renommez un titre de rubrique et régénérez la rubrique, le titre de rubrique mis à jour ne se reflète pas dans la table des matières du mappage DITA. Pour mettre à jour le titre de la rubrique dans la table des matières, vous devez générer le mappage DITA entier.

Vous pouvez afficher l’état actuel de la requête de génération de sortie en cliquant sur Sorties. Pour plus d’informations, voir [Afficher l&#39;état de la tâche de génération de sortie](#viewing_output_history).

## Afficher l&#39;état de la tâche de génération de sortie {#viewing_output_history}

Une fois que vous avez lancé la tâche de génération de sortie pour une carte ou que vous avez régénéré les rubriques sélectionnées, AEM Guides envoie cette tâche à la file d’attente de génération de sortie. Cette file d’attente est mise à jour en temps réel, indiquant l’état de chaque tâche de génération de sortie dans la file d’attente.

Effectuez les étapes suivantes pour afficher la file d’attente de génération de sortie :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de mappage pour lequel vous souhaitez vérifier l’état de génération de la sortie, puis cliquez dessus.

1. Cliquez sur **Sorties**.

   ![](images/output-queued.png){width="800" align="left"}

   La page Sorties est divisée en deux parties :

   - **Sorties en file d’attente :**

     Répertorie les sorties en attente de génération ou en cours de processus de génération. Les tâches en file d’attente ou en cours s’affichent avec une icône de couleur bleue devant le nom du paramètre prédéfini. Vous pouvez également trouver le paramètre de génération de sortie ou le paramètre prédéfini utilisé pour la tâche en file d’attente, le type, l’utilisateur qui a lancé la tâche, le temps écoulé depuis que la tâche est en file d’attente et l’état actuel.

     Cliquez sur le lien pour accéder au **Publier le tableau de bord** et afficher l’état actuel de l’exécution. Une liste de toutes les tâches de publication actives est disponible dans le tableau de bord de publication. La variable **Sorties en file d’attente** et la variable **Publier le tableau de bord** ne s’affichent que lorsqu’il existe des sorties en attente de génération ou en cours de processus de génération. Elles n’apparaissent pas une fois les tâches de sortie terminées. Pour plus d’informations sur le tableau de bord de publication, voir [Gestion des tâches de publication à l’aide du tableau de bord de publication](generate-output-publish-dashboard.md#).

   - **Sorties générées**

     Répertorie les tâches de sortie terminées. Là encore, les informations affichées ici sont similaires à la section Sorties en file d’attente avec quelques différences. Vous disposez d’un nouvel ensemble d’informations sous la forme d’une icône de résultat de sortie et de la durée de génération de la sortie.

     Dans cette liste, vous pouvez avoir des tâches qui ont été exécutées avec succès, des tâches qui ont été exécutées avec un message ou des tâches qui ont échoué. Les tâches réussies sont affichées avec une icône en couleur verte, les tâches avec un message ont une icône en couleur orange et les tâches ayant échoué sont affichées avec une icône en couleur rouge.

     Pour toutes les tâches, le processus de publication crée un fichier journal \(logs.txt\) accessible en cliquant sur le lien dans la colonne Généré à. Pour les tâches ayant échoué ou comportant des messages, vous pouvez vérifier le fichier journal, qui est expliqué dans la section . [Afficher et vérifier le fichier journal](generate-output-basic-troubleshooting.md#id1822G0P0CHS).

     >[!NOTE]
     >
     > Lorsque vous cliquez sur un lien de la sortie de PDF générée, vous êtes invité à télécharger le PDF. Il s’agit du comportement par défaut dans AEM 6.5 et 6.4.


## Annulation d’une tâche de génération de sortie {#id2061H100T5Z}

AEM Guides offre aux éditeurs un moyen simple et facile d’annuler toute tâche de publication en cours. En tant qu’éditeur, vous pouvez annuler une tâche de publication en cours à partir de la console de mappage DITA ou de la [Publier le tableau de bord](generate-output-publish-dashboard.md#).

Pour annuler une tâche de génération de sortie à partir de la console de mappage DITA, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de mappage pour lequel vous souhaitez annuler une tâche de génération de sortie en cours, puis cliquez dessus.

1. Cliquez sur **Sorties**.

1. Dans la liste Sorties en file d’attente, placez le pointeur de la souris sur une tâche que vous souhaitez annuler.

1. Cliquez sur le bouton *Annuler Cette Tâche* Icône

   ![](images/cancel-publish-task-map-console.png){width="800" align="left"}

1. Cliquez sur **Oui** dans l’invite de message Confirmer l’annulation .

   ![](images/confirm-cancel-output-map-condole.png){width="800" align="left"}

   Si la tâche n’a pas encore commencé, la commande d’annulation est exécutée sur la tâche. Pour une tâche en cours d’annulation, l’état est défini sur Annuler.

   Une fois la tâche annulée, elle est déplacée vers la **Sorties générées** avec une liste **Annulé** statut. Lorsque vous passez la souris sur la tâche annulée, le nom de l’utilisateur qui a annulé la tâche s’affiche. Dans la capture d’écran suivante, la variable *HTML5* la tâche est annulée.

   ![](images/cancelled-output-task.png){width="800" align="left"}


## Suppression d’une tâche de sortie de la console de mappage DITA

Lorsque vous générez plusieurs sorties pour un mappage DITA, la liste des sorties générées d’un tel mappage devient très longue sur une période donnée. En tant qu’éditeur, vous pouvez effacer l’historique de sortie d’un fichier de mappage en supprimant les tâches obsolètes du *Sorties générées* liste. Notez que la sortie n’est pas supprimée du système, seule l’entrée de la sortie générée est supprimée de la variable *Sorties générées* liste.

Effectuez les étapes suivantes pour supprimer une tâche de sortie de la liste Sortie générée :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de mappage à partir duquel vous souhaitez supprimer les tâches, puis cliquez dessus.

1. Cliquez sur **Sorties**.

1. Dans la liste Sorties générées , placez le pointeur de la souris sur une tâche à supprimer.

1. Cliquez sur l’icône de suppression.

   ![](images/delete-output-task.png){width="800" align="left"}

1. Cliquez sur **Oui** dans l’invite de message Confirmer la suppression .

   La tâche est supprimée de la liste Sorties générées .


**Rubrique parente :**[ Génération de sortie](generate-output.md)
