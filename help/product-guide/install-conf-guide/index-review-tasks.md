---
title: Exécution de l’indexation pour inclure toutes les tâches de révision dans le panneau Commentaires
description: Découvrez comment indexer les tâches de révision existantes afin qu’elles apparaissent aux côtés des nouvelles dans le menu déroulant Tâche de révision du panneau Commentaires .
feature: Web Editor Configuration
role: Admin
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%
---
# Exécution de l’indexation pour inclure toutes les tâches de révision d’une rubrique dans le panneau Commentaires

La fonction [Afficher toutes les tâches de révision pour une rubrique](../user-guide/review-address-review-comments.md#view-all-review-tasks-for-a-topic), disponible dans le panneau Commentaires, permet aux auteurs de sélectionner n’importe quelle tâche de révision (ouverte ou fermée) associée à la rubrique actuellement ouverte, sans changer de projet de révision. Lorsqu’il est activé, le panneau **Commentaires** de l’éditeur inclut une liste déroulante répertoriant chaque tâche de révision à laquelle le sujet fait partie, ainsi que l’état de chaque tâche et le projet auquel elle appartient.

Par défaut, lorsque cette fonctionnalité est activée sur une instance, les tâches de révision sont indexées au fur et à mesure de leur création, elles sont donc automatiquement disponibles dans cette liste déroulante.

Cependant, si la fonction est désactivée au moment du déploiement de Experience Manager Guides sur une instance, les tâches de révision créées alors qu’elle reste désactivée ne sont pas indexées. En tant qu’administrateur, si vous activez la fonctionnalité après que de telles tâches de révision existent déjà, ces tâches n’apparaissent pas dans la liste déroulante tant qu’elles ne sont pas indexées. Pour les rendre disponibles, vous devez exécuter un script unique pour indexer les tâches de révision existantes.

Exécutez la commande cURL suivante une fois pour indexer les tâches de révision existantes :

```bash
curl --location 'http://<host>:<port>/bin/guides/script/start' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Basic <base64-encoded-credentials>' \
--header 'Cookie: cq-authoring-mode=TOUCH' \
--data-urlencode 'jobType=review-topic-guids-migration'
```
