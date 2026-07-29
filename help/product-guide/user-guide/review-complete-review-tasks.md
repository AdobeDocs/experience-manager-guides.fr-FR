---
title: Terminer la tâche de révision en tant que réviseur
description: Savoir comment marquer une tâche comme terminée en tant que réviseur dans AEM Guides.
feature: Reviewing
role: User
exl-id: 99b64fb5-c509-41cf-b091-ba78b90db481
TQID: https://experienceleague.adobe.com/Ttty7SNmwHvrs-Ma5SN0JqjQRR3Y6yM-W-ozgQ3Vcyg
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: eb30be6342a50ba52e8afd8b4a31148b3ad9c340
workflow-type: tm+mt
source-wordcount: 854
ht-degree: 0%

---

# Terminer la tâche de révision en tant que réviseur

En tant que réviseur ou réviseuse, vous pouvez marquer une tâche de révision comme terminée une fois que vous avez révisé tout le contenu et que vous souhaitez en informer l’auteur ou l’autrice. Vous pouvez également laisser des commentaires finaux à ce stade.

Effectuez les étapes suivantes pour terminer une tâche de révision :

1. Ouvrez la tâche de révision qui vous a été assignée.
2. Sélectionnez **Marquer comme terminé** dans la partie supérieure, comme illustré ci-dessous :

   ![](images/review-task-mark-as-done.png){width="350"}

   La boîte de dialogue **Terminer la tâche** s’affiche.
3. Dans la boîte de dialogue **Terminer la tâche**, ajoutez les commentaires finaux pour l’auteur et sélectionnez **Terminer**.

   >[!NOTE]
   >
   > Les commentaires au niveau de la tâche servent de résumé ou de commentaires finaux et sont distincts des commentaires au niveau du texte ajoutés lors de la révision de la rubrique. Dans cette boîte de dialogue, vous pouvez indiquer les mesures de suivi, par exemple demander à l’auteur de répondre à des commentaires spécifiques et de renvoyer la tâche pour révision, ou indiquer que la révision est terminée.

   Par exemple, en tant que réviseur ou réviseuse, vous pouvez ajouter un commentaire en tant qu’action de suivi pour l’auteur :

   ![](images/complete-task-dialog-followup.png){width="350"}

   Vous pouvez également ajouter un commentaire pour indiquer que la tâche est terminée, comme illustré ci-dessous :

   ![](images/complete-task-dialog.png){width="350"}


Vous avez marqué la tâche comme terminée et son état est maintenant défini sur **Terminé**. Aucune autre action n’est autorisée une fois la tâche marquée comme terminée. Une notification est envoyée à l’auteur ou à l’initiateur de la tâche de révision pour attirer leur attention immédiate. Pour plus d’informations sur le déclenchement des notifications de révision, voir [Présentation des notifications de révision](./review-understanding-review-notifications.md).

![](images/task-completed-status.png){width="350"}

En fonction des commentaires, si l’auteur ou l’initiateur de la tâche décide de [fermer la tâche de révision](./review-close-review-task.md), le statut de la tâche dans l’interface utilisateur de révision devient **Fermée**.

![](images/review-status-closed-review-ui.png){width="350"}

>[!NOTE]
>
> La synchronisation des tâches entre l’interface utilisateur de révision et la boîte de réception AEM est disponible et activée par défaut. Lorsqu’un réviseur ou une réviseuse marque une tâche de révision comme **Terminée** dans l’interface utilisateur de révision, la tâche correspondante est automatiquement terminée et supprimée de la boîte de réception AEM du réviseur ou de la réviseuse. De même, l’accomplissement d’une tâche à partir de la boîte de réception AEM la marque automatiquement comme terminée dans l’interface utilisateur de révision.
>
> L’auteur ou l’initiateur de la tâche peut toujours consulter les commentaires et réaffecter la tâche si une révision supplémentaire est nécessaire. Lorsqu’une tâche est réaffectée, une nouvelle notification de boîte de réception AEM est générée pour le réviseur, ce qui permet à la tâche d’être à nouveau révisée.
>
> Si vous souhaitez utiliser le comportement précédent, où les tâches de révision terminées restent dans la boîte de réception AEM du réviseur jusqu’à ce que l’auteur ou l’initiateur de la tâche examine les commentaires et ferme la tâche de révision, contactez votre équipe du succès client pour désactiver la synchronisation des tâches.



## Afficher les commentaires au niveau de la tâche

Tous les commentaires au niveau de la tâche sont affichés dans la boîte de dialogue **Commentaires des tâches**, disponible en mode lecture seule. Lorsque vous terminez une tâche de révision avec un commentaire final, votre saisie est enregistrée dans cette boîte de dialogue pour référence ultérieure.

Pour accéder aux commentaires au niveau de la tâche à partir de l’interface utilisateur de révision, accédez au panneau de gauche et sélectionnez l’icône **Commentaires sur la tâche**.

![](images/task-comments-icon.png){width="350"}

La boîte de dialogue **Commentaires de la tâche** s’affiche à droite.

![](images/task-comments-reviewer.png){width="350"}

Les commentaires de la boîte de dialogue s’affichent dans l’ordre chronologique, les commentaires récents apparaissant en premier et les commentaires les plus anciens en dernier. Cet ordre vous aide à suivre la conversation au fil du temps.

La boîte de dialogue **Commentaires sur la tâche** est accessible à tous les utilisateurs impliqués dans la tâche de révision, y compris l’auteur ou l’initiateur de la tâche de révision et les autres réviseurs. Par conséquent, les commentaires des autres réviseurs (le cas échéant) peuvent également apparaître dans la boîte de dialogue Commentaires sur la tâche. Cela permet d’assurer une communication claire et traçable tout au long du processus d’examen.

Après avoir consulté les commentaires au niveau de la tâche, l’auteur peut demander une révision ou fermer la tâche de révision. Dans les deux cas, tous les commentaires capturés au cours du processus de révision restent disponibles à titre de référence dans la boîte de dialogue **Commentaires de la tâche**.

## Déléguer une tâche de révision à un autre réviseur

>[!IMPORTANT]
>
> Cette fonctionnalité est activée par défaut. Si vous préférez ne pas utiliser cette fonctionnalité dans votre environnement, contactez votre équipe du succès client.

En tant que réviseur, vous pouvez parfois souhaiter qu’un autre utilisateur intervienne dans une révision avant qu’elle ne revienne à l’auteur. Par exemple, si une partie du contenu ne relève pas de votre compétence ou si vous souhaitez obtenir un deuxième avis avant de marquer la tâche comme **Terminée**. Au lieu de le router par l’intermédiaire d’un administrateur de projet, vous pouvez recommander un réviseur directement à partir de la tâche de révision à l’aide de l’option **Déléguer**.

Sélectionner **Déléguer** ne termine pas la tâche de révision pour vous. Il envoie votre recommandation à l’auteur (initiateur de la tâche), qui décide d’ajouter ou non le réviseur recommandé à la tâche.

Effectuez les étapes suivantes pour déléguer une tâche de révision :

1. Ouvrez la tâche de révision qui vous a été assignée.
2. Une fois que vous avez révisé le contenu, sélectionnez **Déléguer**, en regard de **Marquer comme terminé**.

   ![](./images/review-delegate-option.png){width="350"}

3. La boîte de dialogue **Recommander le réviseur** s’affiche. Sélectionnez dans la liste déroulante un utilisateur à recommander comme réviseur pour cette tâche.

   ![](./images/recommend-reviewer-dialog.png){width="350"}

4. *(Facultatif)* Ajoutez un commentaire pour l’auteur, pour le contexte.
5. Sélectionnez **Déléguer**.

Une notification est envoyée à l’auteur pour indiquer que vous avez demandé l’ajout d’un réviseur à la tâche. Pour plus d’informations sur la manière dont l’auteur répond à cette demande, consultez la section [Demander une révision ou fermer une tâche de révision en tant qu’auteur](./review-close-review-task.md).

