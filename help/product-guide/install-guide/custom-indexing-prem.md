---
title: Déploiement de l’indexation personnalisée pour la configuration On-premise
description: Découvrez comment indexer le contenu personnalisé pour la configuration On-premise
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 5b9e4936-f674-41d3-a7b2-3d42a2523693
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
source-wordcount: '132'
ht-degree: 0%
---
# Réindexation de la fonction Rechercher et remplacer (vue Source)

La réindexation est nécessaire pour activer la fonction **Rechercher et remplacer (vue Source)** qui vous permet d’analyser l’ensemble du contenu visible dans la vue Auteur ainsi que le contenu Source sous-jacent (structure XML, y compris les éléments, les balises et les valeurs d’attribut) pour la chaîne recherchée.

## Réindexation

Pour les configurations on-premise, la définition d’index est incluse avec le package. Pour activer la fonctionnalité, vous devez réindexer le contenu.

Commencez la réindexation en définissant la propriété `reindex=true (Boolean)` sur le nœud : ` /oak:index/guidesAssetLucene` de réindexer le contenu précédemment capturé.

Le processus de réindexation se poursuit jusqu’à ce que le système redéfinisse automatiquement cette propriété sur false. Vous pouvez surveiller la progression de l’opération de réindexation dans les journaux système.
