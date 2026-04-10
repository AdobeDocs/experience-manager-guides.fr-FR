---
title: Déploiement de l’indexation personnalisée pour la configuration On-premise
description: Découvrez comment indexer le contenu personnalisé pour la configuration On-premise
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 0%

---

# Réindexation de la fonctionnalité de recherche et de remplacement (vue Source) pour On-Premise

La réindexation est nécessaire pour activer la fonction **Rechercher et remplacer (vue Source)** qui vous permet d’analyser l’ensemble du contenu visible dans la vue Auteur ainsi que le contenu Source sous-jacent (structure XML, y compris les éléments, les balises et les valeurs d’attribut) pour la chaîne recherchée.

## Réindexation

Pour les configurations on-premise, la définition d’index est incluse avec le package. Pour activer la fonctionnalité, vous devez réindexer le contenu.

Commencez la réindexation en définissant la propriété `reindex=true (Boolean)` sur le nœud : ` /oak:index/guidesAssetLucene` de réindexer le contenu précédemment capturé.

Le processus de réindexation se poursuit jusqu’à ce que le système redéfinisse automatiquement cette propriété sur false. Vous pouvez surveiller la progression de l’opération de réindexation dans les journaux système.
