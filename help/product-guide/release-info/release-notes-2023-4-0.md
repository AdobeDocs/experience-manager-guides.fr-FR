---
title: Notes de mise à jour | Adobe Experience Manager Guides as a Cloud Service, version d’avril 2023
description: Version d’avril 2023 d’Adobe Experience Manager Guides as a Cloud Service
exl-id: fa339eab-d3d0-4763-adbf-6411e39aa213
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 0%

---

# Version d’avril 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cette note de mise à jour traite des instructions de mise à niveau, de la matrice de compatibilité et des problèmes résolus dans la version d’avril 2023 d’Adobe Experience Manager Guides (appelée ultérieurement *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés d’avril 2023 de la version AEM Guides as a Cloud Service](whats-new-2023-4-0.md).

## Mise à niveau vers la version d’avril 2023

Mettez à niveau votre configuration AEM Guides as a Cloud Service actuelle en procédant comme suit :

1. Extrayez le code Git des Cloud Service et passez à la branche configurée dans le pipeline Cloud Service correspondant à l’environnement que vous souhaitez mettre à niveau.
2. Mettez à jour la propriété `<dox.version>` dans le fichier `/dox/dox.installer/pom.xml` de votre code Git Cloud Service vers 2023.4.249.
3. Validez les modifications et exécutez le pipeline Cloud Service pour effectuer la mise à niveau vers la version d’avril 2023 d’AEM Guides as a Cloud Service.

## Procédure d’indexation du contenu existant (uniquement si vous utilisez une version antérieure à la version de septembre d’AEM Guides as a Cloud Service)

Effectuez les étapes suivantes pour indexer le contenu existant et utiliser le nouveau texte de recherche et de remplacement au niveau de la carte :

* Exécutez une requête de POST sur le serveur (avec l’authentification correcte) - `http://<server:port>/bin/guides/map-find/indexing`.
(Facultatif : vous pouvez transmettre des chemins spécifiques des cartes pour les indexer ; par défaut, toutes les cartes seront indexées. || Exemple : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Par exemple : http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Une fois la tâche terminée, la requête de GET ci-dessus répond avec succès et indique si une correspondance a échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par la version as a Cloud Service d’AEM Guides d’avril 2023.

### FrameMaker et FrameMaker Publishing Server

| Version AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.04.0 | Non compatible | 2022 ou version ultérieure |
| | | |


### Connecteur Oxygen

| Version AEM Guides as a Cloud | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.04.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |



## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :

* PDF natif | La publication de contenu comportant une classe de sortie avec crochets () entraîne un gel de publication. (11596)
* Le problème survient lors du déplacement (par glisser-déposer) à la place d’un élément de liste existant sur lequel le suivi des modifications est activé. (11570)
* Le problème se produit lors du déplacement (par glisser-déposer) en tant que nouvel élément de liste avec le suivi des modifications activé. (11569)
* Les éléments de la liste de retrait ou de retrait ne fonctionnent pas comme prévu lorsque le suivi des modifications est activé. (11568)
* L’ajout de contenu sur une ligne avec le suivi des modifications activé, puis la désactivation du suivi des modifications ne la désactive pas. (11567)
* Difficulté à faire glisser et déposer un élément de liste, le texte est déplacé à la place de l’élément de liste. (11566)
* La révision terminée ne s’ouvre pas en mode lecture seule. (11387)
* Le problème se produit dans AEM recherche de site (ne fonctionne pas au-delà des noeuds de 2 à 3 niveaux). (11352)
* Lors de la création dans l’élément affiché en vert (Suivi des modifications), le nouveau contenu s’affiche en tant que suivi des modifications, même si le suivi des modifications est désactivé. (7021)

### Problème connu avec la solution de contournement

Adobe a identifié le problème connu suivant pour la version as a Cloud Service d’avril 2023 d’AEM Guides.

* PDF natif | Les anciennes métadonnées ne sont pas renseignées tant que le paramètre prédéfini de sortie n’est pas ouvert explicitement.
