---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides, version 2026.11.0 Service Pack 1
description: Découvrez les correctifs de bugs de la version 2026.11.0 du Service Pack 1 d’Adobe Experience Manager Guides as a Cloud Service.
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 8821e671951d83439688aa33f88ac1f91f0919eb
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%
---
# Correction de problèmes dans la version 2026.11.0 Service Pack 1

Cet article couvre les bugs corrigés dans la version 2026.11.0 du Service Pack 1 d’Adobe Experience Manager Guides as a Cloud Service.

## Publication

Les problèmes suivants se produisent lors de la publication sur AEM Sites (avec le mappage des composants composites) :

- La régénération des rubriques sélectionnées ou d&#39;une sous-carte avec publication `microservice-based` prend à peu près autant de temps que la génération de la carte complète. (GUIDES-59322)
- La régénération d’une sous-carte contenant des rubriques tronquées entraîne l’affichage de titres et de liens incorrects dans la table des matières. Chaque entrée de rubrique segmentée affiche le titre de la dernière rubrique segmentée. (GUIDES-58650)

Les problèmes suivants se produisent lors de la publication dans AEM Sites à l’aide d’une ligne de base dynamique, ligne de base (héritée) ou nouvelle ligne de base :

- La ligne de base est recréée plusieurs fois au cours de la même opération de publication, ce qui allonge le temps de publication et, dans certains cas, bloque la reconstruction. Avec la nouvelle ligne de base, la publication incrémentielle utilise également une ligne de base obsolète au lieu de la ligne de base actuelle, de sorte que la sortie peut ne pas refléter le contenu le plus récent. (GUIDES-60189)
- Certains problèmes de performances sont observés lors de l’utilisation du tableau de bord des cartes. (GUIDES-60189, GUIDES-55646)

## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 2026.11.0 du Service Pack 1 :

- Lors de l’utilisation de Experience Manager Guides as a Cloud Service version 2026.11.0 ou ultérieure, la publication échoue avec une erreur d’application si AEM redémarre certains services internes pendant le processus de publication, par exemple lorsqu’une instance de serveur démarre. (GUIDES-60804)<br>**Solution de contournement :** Pour résoudre le problème, relancez la publication.
- Lors de la génération d’une sortie pour plusieurs paramètres prédéfinis AEM Sites (à l’aide du mappage de composants composites) ou PDF natifs via **Collection de mappages** ou l’API, la génération de la sortie échoue avec une exception `Rebuild the Baseline`. <br>**Solution :** publiez les paramètres prédéfinis de manière séquentielle plutôt que simultanément pour éviter le problème.