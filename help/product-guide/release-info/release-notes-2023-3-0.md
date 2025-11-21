---
title: Notes de mise à jour | Adobe Experience Manager Guides as a Cloud Service, version de mars 2023
description: Version de mars d’Adobe Experience Manager Guides as a Cloud Service
exl-id: 6a0bba92-7d7d-4b20-ad46-0eacc91268da
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---

# Version de mars 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cette note de mise à jour couvre les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans la version de mars 2023 d’Adobe Experience Manager Guides (plus tard appelée *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version de mars 2023 d’AEM Guides as a Cloud Service](whats-new-2023-3-0.md).

## Mise à niveau vers la version de mars 2023

Mettez à niveau votre configuration AEM Guides as a Cloud Service actuelle en procédant comme suit :

1. Consultez le code Git des services cloud et passez à la branche configurée dans le pipeline des services cloud correspondant à l’environnement à mettre à niveau.
1. Mettez à jour `<dox.version>` propriété dans `/dox/dox.installer/pom.xml` fichier de votre code Git Cloud Services vers la version 2023.3.242.
1. Validez les modifications et exécutez le pipeline Cloud Services pour effectuer la mise à niveau vers la version de mars 2023 d’AEM Guides as a Cloud Service.

## Procédure à suivre pour indexer le contenu existant (uniquement si vous utilisez une version antérieure à la version de septembre d’AEM Guides as a Cloud Service)

Effectuez les étapes suivantes pour indexer le contenu existant et utiliser le nouveau texte de recherche et de remplacement au niveau du mappage :

* Exécutez une requête POST au serveur (avec l’authentification correcte) - `http://<server:port>/bin/guides/map-find/indexing`.
(Facultatif) Vous pouvez transmettre des chemins spécifiques des mappages pour les indexer. Par défaut, tous les mappages sont indexés || Exemple : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée : `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Par exemple : http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Une fois la tâche terminée, la requête GET ci-dessus répond avec succès et mentionne si des mappages ont échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par la version de mars 2023 d’AEM Guides as a Cloud Service.

### FrameMaker et FrameMaker Publishing Server

| Version d’AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.03.0 | Non compatible | 2022 ou version ultérieure |
| | | |


### Connecteur D&#39;Oxygène

| Version d’AEM Guides as a Cloud | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.03.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |  |

## Problèmes résolus

Les bogues corrigés dans différentes zones sont répertoriés ci-dessous :

* Le processus de téléchargement de PDF ne fonctionne pas correctement dans l’éditeur web. (11496)
* Sortie JSON | Mappez des métadonnées dont la valeur de propriété est `"value in spaces and double quotes"` entraîne une erreur de publication. (11438)
* L’insertion des fichiers multimédias audio et vidéo échoue au format YouTube sous l’icône **Insérer un fichier multimédia**. (11320)
* Une erreur de validation se produit lorsqu’une carte est créée à l’aide du modèle qui comporte un élément de titre spécialisé. (11212)
* PDF natif | la note de bas de page présente dans l’en-tête du tableau met le texte en gras et aligné au centre dans le pied de page correspondant dans la sortie PDF. (10610)
>[!NOTE]
>
>Pour prendre en compte la modification du PDF natif, supprimez le dossier PDF situé sous /content/dam/dita-templates, puis effectuez une mise à niveau vers le dernier build. (10610)

### Problème connu lié à la solution

Adobe a identifié le problème connu suivant pour la version de mars 2023 d’AEM Guides as a Cloud Service.

* Les utilisateurs ne peuvent pas enregistrer ni créer de version d’une ressource dupliquée.

**Solution** : avant d’apporter des modifications à la ressource en double, retraitez-la à partir de l’interface utilisateur d’Assets.
