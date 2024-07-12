---
title: Notes de mise à jour | Adobe Experience Manager Guides as a Cloud Service, version de mars 2023
description: Version de mars d’Adobe Experience Manager Guides as a Cloud Service
exl-id: 6a0bba92-7d7d-4b20-ad46-0eacc91268da
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 0%

---

# Version d’Adobe Experience Manager Guides as a Cloud Service de mars 2023

Cette note de mise à jour traite des instructions de mise à niveau, de la matrice de compatibilité et des problèmes résolus dans la version de mars 2023 d’Adobe Experience Manager Guides (appelée ultérieurement *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de mars 2023 de la version AEM Guides as a Cloud Service](whats-new-2023-3-0.md).

## Mise à niveau vers la version de mars 2023

Mettez à niveau votre configuration AEM Guides as a Cloud Service actuelle en procédant comme suit :

1. Extrayez le code Git des Cloud Service et passez à la branche configurée dans le pipeline Cloud Service correspondant à l’environnement que vous souhaitez mettre à niveau.
1. Mettez à jour la propriété `<dox.version>` dans le fichier `/dox/dox.installer/pom.xml` de votre code Git Cloud Service vers 2023.3.242.
1. Validez les modifications et exécutez le pipeline Cloud Service pour effectuer la mise à niveau vers la version de mars 2023 d’AEM Guides as a Cloud Service.

## Procédure d’indexation du contenu existant (uniquement si vous utilisez une version antérieure à la version de septembre d’AEM Guides as a Cloud Service)

Effectuez les étapes suivantes pour indexer le contenu existant et utiliser le nouveau texte de recherche et de remplacement au niveau de la carte :

* Exécutez une requête de POST sur le serveur (avec l’authentification correcte) - `http://<server:port>/bin/guides/map-find/indexing`.
(Facultatif : vous pouvez transmettre des chemins spécifiques des cartes pour les indexer ; par défaut, toutes les cartes seront indexées. || Exemple : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Par exemple : http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Une fois la tâche terminée, la requête de GET ci-dessus répond avec succès et indique si une correspondance a échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par la version as a Cloud Service d’AEM Guides de mars 2023.

### FrameMaker et FrameMaker Publishing Server

| Version AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.03.0 | Non compatible | 2022 ou version ultérieure |
| | | |


### Connecteur Oxygen

| Version AEM Guides as a Cloud | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.03.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |

## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :

* Le processus du PDF de téléchargement ne fonctionne pas correctement dans l’éditeur web. (11496)
* Sortie JSON | Les métadonnées de mappage dont la valeur de propriété est `"value in spaces and double quotes"` entraînent une erreur de publication. (11438)
* L’insertion des fichiers multimédia audio et vidéo échoue au format YouTube sous l’icône **Insérer le multimédia** . (11320)
* Une erreur de validation se produit lorsqu’une map est créée à l’aide du modèle qui comporte un élément de titre spécialisé. (11212)
* PDF natif | la note de bas de page présente dans l’en-tête du tableau pour afficher le texte en gras aligné au centre dans le pied de page correspondant dans la sortie du PDF. (10610)
>[!NOTE]
>
>Pour refléter la modification du PDF natif, supprimez le dossier du PDF situé à l’emplacement /content/dam/dita-templates, puis effectuez la mise à niveau vers le dernier build. (10610)

### Problème connu avec la solution de contournement

Adobe a identifié le problème connu suivant pour la version as a Cloud Service mars 2023 d’AEM Guides.

* Les utilisateurs ne peuvent pas enregistrer ni créer de version d’une ressource dupliquée.

**Solution** : avant d’apporter des modifications à la ressource en double, retraitez-la à partir de l’interface utilisateur d’Assets.
