---
title: Guides de publication de références sur AEMaaCS
description: Comprenez les limites du système sur la publication sur AEM Cloud.
feature: Publishing
role: User, Admin
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 21%
---
# Références de publication AEM Guides sur AEMaaCS

Ce test comparatif évalue les performances des nouvelles API de publication sur différents paramètres prédéfinis de sortie et l’augmentation des tailles de mappage dans AEM Guides as a Cloud Service. L’objectif est de comprendre le comportement en matière d’évolutivité et d’identifier les goulots d’étranglement en termes de performances.

Le service de publication utilise une [architecture basée sur microservice](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/kb-articles/publishing/publish-microservice-architecture-and-performance) avec mise à l’échelle automatique, ce qui permet de gérer des charges de travail plus importantes grâce à des capsules supplémentaires.

## Environnement d’exécution

- **Version d’**:2026.4.25322.20260407T085152Z
- **Version du module complémentaire Guides** : 2026.5.0
- **Nombre initial de capsules** : 2 capsules
- **Comportement de mise à l’échelle automatique** : mise à l’échelle de 4 capsules sur 4 nœuds à mesure que la charge augmentait
- **processeurs virtuels** : 10
- **RAM par pod** : 8 Go
- **Utilisateurs simultanés** : 1 utilisateur

>[!NOTE]
>
> Cet exercice s’est concentré sur le comportement de la publication à mesure que la taille des mappages augmente, soulignant l’impact des mappages plus volumineux sur le débit, la latence et la fin globale de la publication sous charge.


## Numéros de génération de sortie

**Site AEM natif**

| MapSize | Heure(s) d’exécution | Microservice |
| ------- | ------------------ | ------------ |
| 10 | 62.378 | Oui |
| 100 | 64.27 | Oui |
| 1000 | 93.091 | Oui |
| 5000 | 496.319 | Oui |
| 10000 | 922.602 | Oui |

PDF natif ****

| MapSize | Heure(s) d’exécution | Microservice |
| ------- | ------------------ | ------------ |
| 10 | 62.302 | Oui |
| 100 | 62.431 | Oui |
| 1000 | 108.666 | Oui |
| 5000 | 201.379 | Oui |
| 10000 | 1170.689 | Oui |

**PDF**

| MapSize | Heure(s) d’exécution | Microservice |
| ------- | ------------------ | ------------ |
| 10 | 30.926 | Oui |
| 100 | 30.987 | Oui |
| 1000 | 77.007 | Oui |
| 5000 | 247.505 | Oui |
| 10000 | 686.61 | Oui |

**HTML5**

| MapSize | Heure(s) d’exécution | Microservice |
| ------- | ------------------ | ------------ |
| 10 | 30.844 | Oui |
| 100 | 30.834 | Oui |
| 1000 | 77.384 | Oui |
| 5000 | 170.237 | Oui |
| 10000 | 419.166 | Oui |


## Principales observations

- Le temps de génération du site AEM dépend du modèle utilisé. Le temps d’exécution peut augmenter si un modèle complexe est utilisé.
- Le temps d’exécution de la publication personnalisée repose sur un exemple de sortie personnalisée. Le temps de publication personnalisé dépend uniquement de la logique de transformation du client ou de la cliente.