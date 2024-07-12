---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans la version 2024.06.0 d’Adobe Experience Manager Guides
description: Découvrez la matrice de compatibilité et comment effectuer la mise à niveau vers la version 2024.06.0 d’Adobe Experience Manager Guides as a Cloud Service.
exl-id: 6895357a-cfd1-4e6a-aec1-8870db8054fb
source-git-commit: d525775afeeb89754762ff514126b1c3a3307b3f
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 4%

---

# Instructions de mise à niveau de la version 2024.06.0

Cet article décrit les instructions de mise à niveau et la matrice de compatibilité de la version 2024.06.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2024.06.0](whats-new-2024-06-0.md).

Pour connaître la liste des problèmes résolus dans cette version, voir la section [Problèmes résolus dans la version 2024.06.0](fixed-issues-2024-06-0.md).

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité des applications logicielles prises en charge par la version 2024.06.0 d’Experience Manager Guides as a Cloud Service.

### FrameMaker et FrameMaker Publishing Server

| Version de Experience Manager Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2024.06.0 | Non compatible | 2022 ou version ultérieure |
| | | |


### Connecteur Oxygen

| Version de Experience Manager Guides as a Cloud | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2024.06.0 | 3.5-uuid 1 | 3.5-uuid 1 | 2,3 | 2,3 |
|  |  |  |  |


### Version du modèle de base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu des composants Experience Manager Guides pour Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.16 |

## Mise à niveau vers la version 2024.06.0

Experience Manager Guides est automatiquement mis à niveau lors de la mise à niveau de la version actuelle (la plus récente) de l’as a Cloud Service Experience Manager.

>[!NOTE]
>
> Une fois que vous avez commencé à utiliser la version actuelle (la plus récente), comparez les configurations remplacées aux dernières pour obtenir les dernières fonctionnalités :
>- ui_config.json (peut avoir été défini dans les profils de dossier)


Effectuez les étapes suivantes pour Experience Manager Guides as a Cloud Service si vous ne l’avez pas fait auparavant pour votre version existante :

### Procédure d’activation du déclencheur d’un script via un servlet

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 de Experience Manager Guides as a Cloud Service)

Une fois l’installation terminée, vous pouvez choisir d’ACCÉDER au déclencheur pour lancer la tâche de traduction :

POST :

```
http://localhost:4503/bin/guides/script/start?jobType=translation-map-upgrade
```

Réponse :

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/translation-map-upgrade/1683190032886",
"status": "SCHEDULED"
}
```

Dans la réponse précédente JSON, la clé `lockNodePath` contient le chemin d’accès au noeud créé dans le référentiel pointant vers la tâche envoyée. Il est automatiquement supprimé une fois la tâche terminée, puis vous pouvez vous référer à ce noeud pour connaître le statut de la tâche.

Patientez jusqu’à ce que cette tâche soit terminée avant de passer aux étapes suivantes.

>[!NOTE]
>
> Vérifiez si le noeud est toujours présent et l’état de la tâche.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

### Étapes de post-traitement du contenu existant pour utiliser le rapport de lien rompu

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 de Experience Manager Guides as a Cloud Service)

Effectuez les étapes suivantes pour post-traiter le contenu existant et utiliser le nouveau rapport de lien rompu :

1. (Facultatif) S’il existe plus de 100 000 fichiers DITA dans le système, mettez à jour les `queryLimitReads` et `queryLimitInMemory` sous `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` vers une valeur plus grande (toute valeur supérieure au nombre de ressources présentes, par exemple 200 000), puis redéployez.

   - Suivez les instructions de la section *Remplacements de configuration* dans Installation et configuration de l’as a Cloud Service Adobe Experience Manager Guides pour créer le fichier de configuration.
   - Dans le fichier de configuration, fournissez les détails (propriété) suivants pour configurer l’option `queryLimitReads` et `queryLimitInMemory` :

     | PID | Clé de propriété | Valeur de la propriété |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valeur : 200000 Valeur par défaut : 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Valeur : 200000 Valeur par défaut : 100000 |

1. Exécutez une requête de POST sur le serveur (avec l’authentification correcte) - `http://<server>//bin/guides/reports/upgrade`.

1. L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison - `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(Par exemple : `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Une fois la tâche terminée, la requête de GET précédente répond avec succès. Si la tâche échoue pour une raison quelconque, l’échec est visible à partir des journaux du serveur.

1. Revenez à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifiée à l’étape 1.

### Étapes pour indexer le contenu existant afin d’utiliser la nouvelle liste de rubrique et de recherche sous l’onglet Rapports :

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 de Experience Manager Guides as a Cloud Service)

Effectuez les étapes suivantes pour indexer le contenu existant et utilisez le nouveau texte de recherche et de remplacement au niveau de la carte et de la liste des rubriques sous l’onglet rapports :

1. Exécutez une requête de POST sur le serveur (avec l’authentification correcte) - `http://<server:port>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des cartes pour les indexer, toutes les cartes sont par défaut indexées|| Par exemple : `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. Vous pouvez également transmettre un dossier racine pour indexer les mappages DITA d’un dossier spécifique (et de ses sous-dossiers). Par exemple, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Notez que si les paramètres paths et root sont transmis, seul le paramètre paths est pris en compte.

1. L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(Par exemple : `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Une fois la tâche terminée, la requête de GET précédente répond avec succès et indique si une correspondance a échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

### Procédure de gestion du conflit `'fmdita rewriter'`

Experience Manager Guides dispose d’un module [**de réécriture sling personnalisée**](../cs-install-guide/conf-output-generation.md#custom-rewriter) pour gérer les liens générés en cas de mappage croisé (liens entre les rubriques de deux cartes différentes).

Si votre code base comporte un autre module de réécriture sling personnalisé, utilisez une valeur `'order'` supérieure à 50, car Experience Manager Guides sling rewriter utilise `'order'` 50. Pour le remplacer, vous devez disposer d’une valeur supérieure à 50. Pour plus d’informations, voir [ Pipelines de réécriture de sortie](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Pendant cette mise à niveau, puisque la valeur `'order'` est passée de 1000 à 50, vous devez fusionner le module de réécriture personnalisé existant, le cas échéant, avec `fmdita-rewriter`.



### Procédure de migration de l’arborescence B pour les fragments de contenu

Si les références ne s’affichent pas pour les fragments de contenu, vous pouvez choisir d’ACCÉDER au déclencheur pour lancer la tâche de migration :

POST :

```
http://localhost:4503/bin/guides/script/start?jobType=cf-reference-store-btree-migration
```


Réponse :

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/cf-reference-store-btree-migration/1683190032886",
"status": "SCHEDULED"
}
```

Dans la réponse précédente, JSON, la clé `lockNodePath` contient le chemin d’accès au noeud créé dans le référentiel, qui pointe vers la tâche envoyée. Il sera automatiquement supprimé une fois la tâche terminée. Vous pouvez vous reporter à ce noeud pour connaître l’état de la tâche.

Patientez jusqu’à ce que cette tâche soit terminée avant de passer aux étapes suivantes.

>[!NOTE]
>
>Vérifiez si le noeud est toujours présent et l’état de la tâche.

GET :

```
http://<aem_domain>/var/dxml/executor-locks/cf-reference-store-btree-migration/1683190032886.json
```
