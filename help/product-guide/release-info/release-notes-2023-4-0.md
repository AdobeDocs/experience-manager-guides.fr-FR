---
title: Notes de mise à jour | Adobe Experience Manager Guides as a Cloud Service, version d’avril 2023
description: Version d’avril 2023 d’Adobe Experience Manager Guides as a Cloud Service
exl-id: fa339eab-d3d0-4763-adbf-6411e39aa213
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/tGOV1IcAL8f2B5ziGWPOMfkkPZGPlxcXSerTtAO3LW0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 602
ht-degree: 2%

---

# Version d’avril 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cette note de mise à jour couvre les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans la version d’avril 2023 d’Adobe Experience Manager Guides (plus tard appelée *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version d’avril 2023 d’AEM Guides as a Cloud Service](whats-new-2023-4-0.md).

## Mise à niveau vers la version d’avril 2023

Mettez à niveau votre configuration AEM Guides as a Cloud Service actuelle en procédant comme suit :

1. Consultez le code Git des services cloud et passez à la branche configurée dans le pipeline des services cloud correspondant à l’environnement à mettre à niveau.
2. Mettez à jour `<dox.version>` propriété dans `/dox/dox.installer/pom.xml` fichier de votre code Git Cloud Services vers la version 2023.4.249.
3. Validez les modifications et exécutez le pipeline Cloud Services pour effectuer la mise à niveau vers la version d’avril 2023 d’AEM Guides as a Cloud Service.

## Procédure à suivre pour indexer le contenu existant (uniquement si vous utilisez une version antérieure à la version de septembre d’AEM Guides as a Cloud Service)

Effectuez les étapes suivantes pour indexer le contenu existant et utiliser le nouveau texte de recherche et de remplacement au niveau du mappage :

* Exécutez une requête POST au serveur (avec l’authentification correcte) - `http://<server:port>/bin/guides/map-find/indexing`.
(Facultatif : vous pouvez transmettre des chemins spécifiques des mappages pour les indexer. Par défaut, tous les mappages sont indexés || Exemple : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Par exemple : http://&lt;_localhost:8080_/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Une fois la tâche terminée, la requête GET ci-dessus répond avec succès et mentionne si des mappages ont échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par la version d’avril 2023 d’AEM Guides as a Cloud Service.

### FrameMaker et FrameMaker Publishing Server

| Version d’AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.04.0 | Non compatible | 2022 ou version ultérieure |
| | | |


### Connecteur D&#39;Oxygène

| Version d’AEM Guides as a Cloud | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.04.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |  |



## Problèmes résolus

Les bogues corrigés dans différentes zones sont répertoriés ci-dessous :

* Native PDF | La publication de contenu ayant une classe de sortie avec des crochets() entraîne un gel de la publication. (11596)
* Le problème se produit lors du déplacement (glisser-déposer) à la place d’un élément de liste existant avec le suivi des modifications activé. (11570)
* Le problème se produit lors du déplacement (glisser-déposer) en tant que nouvel élément de liste avec le suivi des modifications activé. (11569)
* Le retrait ou le retrait négatif d’éléments de liste ne fonctionne pas comme prévu lorsque le suivi des modifications est activé. (11568)
* L’ajout de contenu sur une ligne avec le suivi des modifications activé puis la désactivation du suivi des modifications ne le désactive pas réellement. (11567)
* Difficulté à faire glisser et à déposer un élément de liste, le texte est déplacé à la place de l’élément de liste. (11566)
* La révision terminée ne s’ouvre pas en mode lecture seule. (11387)
* Le problème se produit dans la recherche de site AEM (ne fonctionne pas au-delà de 2 à 3 nœuds de niveau). (11352)
* Lors de la création dans l’élément affiché en vert (Suivi des modifications), le nouveau contenu s’affiche en tant que suivi des modifications même si ce dernier est désactivé. (7021)

### Problème connu lié à la solution

Adobe a identifié le problème connu suivant pour la version d’avril 2023 d’AEM Guides as a Cloud Service.

* PDF natif | Les anciennes métadonnées ne sont pas renseignées tant que le paramètre prédéfini de sortie n’est pas explicitement ouvert.
