---
title: Traitement de ressources
description: Découvrez comment traiter des ressources.
feature: Migration
role: Admin
level: Experienced
exl-id: 27786098-119c-4b7a-8275-8a89d435294f
source-git-commit: 62221031e445ccdbf1f2567f38fa888ff52017d4
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 0%

---

# Traitement des ressources

Dans les workflows gourmands en données tels que la publication, une gestion efficace des ressources est essentielle pour maintenir les performances et la fiabilité. Le workflow de traitement des ressources est conçu pour gérer les ressources spécifiques aux utilisateurs et utilisatrices nécessitant des opérations de données intensives. Elle traite principalement deux cas : lorsque le traitement initial échoue en raison d’erreurs ou lorsque les fichiers restent non traités car aucun déclencheur de traitement des ressources n’a été lancé. En activant le traitement ciblé au niveau du dossier, les utilisateurs et utilisatrices peuvent isoler et traiter uniquement les ressources nécessaires, évitant ainsi la surcharge de calculs inutiles. Cette approche sélective améliore considérablement les performances et réduit le temps nécessaire aux opérations critiques telles que la publication et la génération de rapports. Dans l’ensemble, il contribue à une plus grande efficacité et une plus grande rapidité dans la gestion des tâches de données complexes.

>[!NOTE]
>
> - Pour les jeux de données volumineux, il est préférable d’exécuter le traitement en dehors des heures de pointe afin d’éviter tout impact sur les performances du système. Une fois la tâche de traitement terminée, vous pouvez consulter les détails pour analyser les résultats.<br>
>- Le système déclenche le traitement des ressources pour le dossier `/content/dam` toutes les 15 minutes. Au cours de chaque cycle, les ressources qui ont été ajoutées récemment ou qui n’ont pas été traitées au cours des 15 dernières minutes sont récupérées et retraitées. Pour configurer la vue de la fonction de traitement automatique des ressources, [Configurer la fonction de traitement des ressources](../cs-install-guide/configure-asset-processing-cs.md).

## Traitement des ressources

Suivez les étapes mentionnées ci-dessous pour traiter les ressources :

1. Sélectionnez le logo Adobe Experience Manager en haut et choisissez **Outils**.
1. Dans le panneau **Outils**, sélectionnez **Guides**.
1. Sélectionnez la mosaïque **Processeur en bloc**.

   ![flow-asset-processor](images/flow-asset-processor.png){align="left"}

1. La fenêtre Guides Bulk Processor s’ouvre avec les détails affichés ci-dessous. En outre, seules les informations relatives aux cinq dernières migrations s’affichent dans cette fenêtre.

   - **Type de fonction** : affiche la fonction du processus en cours d’exécution.

   - **ID d’exécution** : il s’agit de l’ID unique pour chaque tâche de traitement que vous effectuez.

   - **Dossier** : affiche le dossier sélectionné pour le traitement.

   - **Dossiers exclus** : affiche le dossier exclu du traitement.

   - **Créé par** : indique qui a créé la tâche ou le processus. Il peut s’agir de vous ainsi que du système.

   - **Heure de début :** affiche la date et l’heure auxquelles le processus de traitement a été lancé.

   - **Heure de fin** : affiche la date et l’heure auxquelles le processus de traitement se termine.

   - **Statut** : affiche le statut du traitement comme étant En cours, Terminé ou Annulé.

   ![Guides-asset-processor](images/guides-asset-processor-new.png){align="left"}

1. Sélectionnez l’onglet **Nouveau processus** dans le coin supérieur droit de la fenêtre pour démarrer une nouvelle tâche de traitement.

   La boîte de dialogue **Nouveau processus** s’ouvre.

   ![Nouveau-processeur-de-ressource-processus](images/new-asset-processor.png){width="350" align="left"}

1. Fournissez les détails suivants dans la boîte de dialogue :

   1. **Type de fonction** : sélectionnez **Traitement des ressources** dans la liste déroulante.
   1. **Sélectionner des dossiers et des fichiers** : parcourez l’arborescence et sélectionnez un ou plusieurs dossiers et fichiers à traiter.
   1. **Sélectionner les dossiers à ignorer** : si vous le souhaitez, sélectionnez les sous-dossiers dans le dossier parent sélectionné à exclure du traitement.
   1. **Type de ressource** : dans la liste déroulante, sélectionnez le type de ressource spécifique à traiter (par exemple, rubrique DITA, plan DITA, Markdown, HTML/CSS, DITAVAL ou d’autres fichiers). Seul le type de ressource sélectionné est traité à partir du ou des dossiers que vous avez spécifiés précédemment.
Exemple : la sélection d&#39;une rubrique DITA traite uniquement les rubriques DITA du dossier sélectionné et active le filtrage ciblé.
   1. **Créé après/Créé avant** : appliquez des filtres de date pour traiter les ressources créées dans le délai spécifié.

   >[!NOTE]
   >
   > Si un processus est déjà en cours d’exécution pour un dossier, vous ne pouvez pas démarrer un nouveau processus pour le même dossier tant que la tâche en cours n’est pas terminée.

1. Sélectionnez **Créer**. Une fenêtre pop-up s’affiche **Succès et le Processus a été déclenché avec succès**. Vous pouvez voir le statut de la tâche de traitement sur la fenêtre.

   ![Message-asset-processor](images/message-asset-processor.png){width="350" align="left"}


## Options supplémentaires pour les tâches de traitement des ressources

D’autres options sont disponibles pour la tâche de traitement une fois qu’elle a été lancée. Vous pouvez accéder à ces options en pointant la souris sur l’ID d’exécution de la tâche. Vous trouverez ci-dessous des informations détaillées sur ces options :

- **Redémarrer** : redémarre la tâche de traitement des ressources ayant réussi précédemment.

  ![restart-asset-processor](images/restart-asset-processor.png){width="650" align="left"}

- **Reprendre** : reprend la tâche de traitement des ressources précédemment annulée ou ayant échoué.

  ![resume-asset-processor](images/resume-asset-processor.png){width="650" align="left"}

- **Annuler** : annule la tâche de traitement des ressources en cours.

  ![annuler-le-processeur-de-ressources](images/cancel-asset-processor.png){width="650" align="left"}

- **Afficher les journaux** : affiche les journaux de la tâche de traitement des ressources. Pour les tâches en cours, le journal affiche des informations détaillées sur le traitement, notamment le temps restant estimé et le statut de la ressource. Cette liste de journaux affiche jusqu’aux 500 dernières entrées. Le journal complet peut être téléchargé.

  ![logs-asset-processor](images/logs-asset-processor.png){width="650" align="left"}
