---
title: L’exportation des métadonnées échoue avec l’exception « Chaîne trop longue » dans Experience Manager Guides
description: Comprendre pourquoi l’exportation des métadonnées peut échouer pour le contenu Guides dans l’interface utilisateur d’Assets.
feature: Authoring, Publishing
role: User
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 1c61df4820e559417410d25c81800637481b040c
workflow-type: tm+mt
source-wordcount: 274
ht-degree: 0%

---

# Pourquoi l’exportation des métadonnées pour un dossier échoue-t-elle avec l’exception « Chaîne trop longue » ?

Lorsque vous [exportez des métadonnées](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/assets/using/metadata#export-metadata) pour un dossier à partir de l’interface utilisateur d’Assets, la tâche d’exportation peut échouer avec `String is too long` exception. Cela se produit généralement lorsque le dossier contient des propriétés spécifiques à Experience Manager Guides qui stockent des valeurs autres que des chaînes, telles que `baselineObj`.

**Pourquoi cela arrive-t-il ?**

Certaines propriétés stockées sous le nœud de métadonnées d’une ressource sont utilisées en interne par Experience Manager Guides et contiennent des données, telles que des objets JSON, plutôt que des valeurs de chaîne simples. Lors de l’exportation des métadonnées d’un dossier, si **Propriétés à exporter** est défini sur **Toutes**, la tâche d’exportation tente de convertir chaque propriété en chaîne et échoue sur les propriétés qui contiennent ce type de données.

**Comment empêcher cela ?**

Pour éviter cet échec, les propriétés suivantes sont exclues de l’exportation des métadonnées par défaut dans la **Configuration de l’exportateur de métadonnées de ressource** :

- `baseline`
- `namedoutputs`
- `conditionpresets`
- `nextgenbaselinestore`

**Puis-je toujours exporter ces propriétés ?**

Oui. Si vous avez besoin d’une ou de plusieurs de ces propriétés dans l’exportation, vous pouvez modifier la **Configuration de l’exportateur de métadonnées de ressource** et les supprimer de la liste d’exclusion.

La suppression d’une propriété de la liste d’exclusion ne garantit pas que l’exportation réussira. Selon la taille et le contenu des données sous-jacentes, la tâche peut toujours échouer avec la même exception. Si vous rencontrez ce problème après avoir réactivé une propriété, ajoutez-la à nouveau à la liste d’exclusion pour restaurer le comportement d’exportation fiable par défaut.
