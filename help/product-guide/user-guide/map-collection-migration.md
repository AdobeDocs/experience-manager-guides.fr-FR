---
title: Migration d’anciennes collections de cartes vers de nouvelles collections de cartes
description: Découvrez comment migrer des collections de cartes de l’ancienne vers la nouvelle
source-git-commit: aa9f0768e2c6f23294f926c2ed9a1f7e51db7610
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 1%

---


# Migration d’anciennes collections de cartes vers de nouvelles collections de cartes

Si vous avez déjà configuré des collections de cartes dans l’ancien format, vous n’avez pas besoin de les recréer de zéro lors du passage à la nouvelle expérience . Vous pouvez les recréer manuellement ou utiliser l’outil de migration intégré pour tout déplacer en une seule étape.

L’outil de migration, ajouté en tant que nouveau type de processus dans le **processeur en bloc**, lit vos anciennes collections de mappages existantes et crée automatiquement de nouvelles collections de mappages correspondantes pour vous. Cet article vous guide tout au long de l’exécution de la migration et met en évidence quelques comportements clés à connaître avant de l’utiliser.

>[!NOTE]
>
> La fonctionnalité d’activation en bloc n’est pas migrée vers la nouvelle expérience de collecte de cartes. Recréez toutes les collections de mappages utilisées pour l’activation en bloc dans la nouvelle expérience de collection de mappages, si nécessaire.

## Migrer vers une nouvelle collection de cartes

Effectuez les étapes suivantes pour migrer les anciennes collections de cartes vers de nouvelles collections de cartes :

1. Sélectionnez le logo Adobe Experience Manager et choisissez **Outils**.
1. Dans le panneau **Outils**, sélectionnez **Guides**.
1. Sélectionnez la mosaïque **Processeur en bloc**.

   ![Met en surbrillance la mosaïque du processeur en bloc](images/flow-asset-processor.png)

1. La fenêtre Guides Bulk Processor s’ouvre avec les détails suivants :

   - **Type de fonction** : affiche la fonction du processus en cours d’exécution.

   - **ID d’exécution** : il s’agit de l’ID unique pour chaque tâche de migration que vous effectuez.

   - **Créé par** : indique qui a créé la tâche.

   - **Heure de début** : affiche la date et l’heure de début de la migration.

   - **Heure de fin** : affiche la date et l’heure de fin de la migration.

   - **Statut** : affiche le statut de la migration, à savoir En cours, Terminé ou En échec.

   ![Fenêtre Guides Bulk Processor](images/guides-asset-processor-migration.png)

1. Sélectionnez l’onglet **Nouveau processus** dans le coin supérieur droit de la fenêtre pour démarrer une nouvelle tâche de migration.

   La boîte de dialogue **Nouveau processus** s’ouvre.

   ![Boîte de dialogue Nouveau processus pour la migration](images/new-process-migration.png) {width="350"}

1. Sélectionnez **Collection de cartes** dans le menu déroulant **Type de fonction**.

   ![Fonctionnalité de collecte Map pour la tâche de migration](images/new-process.png) {width="350"}

1. Sélectionnez **Créer**.

Cette opération exécute une tâche unique qui migre toutes les anciennes collections de cartes existantes vers de nouvelles collections de cartes. Aucune configuration supplémentaire n’est nécessaire.

>[!NOTE]
>
> Si la tâche de migration échoue, vous pouvez vérifier l’option **Afficher les journaux** en pointant la souris sur l’ID d’exécution.

## Considérations importantes

- **Réexécution de la migration :** si le processus de migration est exécuté à nouveau, il ne vérifie pas les modifications apportées aux (anciennes) collections de mappages sources. Il migre à nouveau ou remplace inconditionnellement les nouvelles collections de cartes.
- **Horodatages et unicité :** chaque collection de mappages migrée stocke l’horodatage de la première migration. Cet horodatage est utilisé pour conserver l’unicité de l’enregistrement migré. Pour cette raison, la collection de mappages migrée ne reflète pas les mises à jour ultérieures apportées à la collection de mappages d’origine (source), seul l’état au moment de la migration est capturé.


