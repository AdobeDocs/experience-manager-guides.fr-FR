---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans Adobe Experience Manager Guides version 2024.12.0
description: Découvrez la matrice de compatibilité et comment effectuer une mise à niveau vers la version 2024.12.0 d’Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: f643a4a22151af2ff14288ab3885c1a6657a80ca
workflow-type: tm+mt
source-wordcount: '1016'
ht-degree: 2%

---

# Instructions de mise à niveau pour la version 2024.12.0

Cet article couvre les instructions de mise à niveau et la matrice de compatibilité pour la version 2024.12.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour connaître la liste des problèmes résolus dans cette version, voir la section [Problèmes résolus dans la version 2024.12.0](fixed-issues-2024-12-0.md).

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par la version 2024.12.0 de Experience Manager Guides as a Cloud Service.

### FrameMaker et FrameMaker Publishing Server

| Version de Experience Manager Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2024.12.0 | Non compatible | 2022 ou version ultérieure |
| | | |


### Connecteur D&#39;Oxygène

| Version de Experience Manager Guides as a Cloud | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2024.12.0 | 3.7-uuid 2 | 3.7-uuid 2 | 2,3 | 2,3 |
|  |  |  |  |


### Version du modèle de la base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu de composants Experience Manager Guides pour Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.16 |

### Nouvelle version du modèle AEM Sites

| Version des composants | Version Sites |
|---|---|
| guides-components.all-1.0.0 | daemg-sites-template-1.0.0 |

## Mise à niveau vers la version 2024.12.0

Experience Manager Guides est mis à niveau automatiquement lors de la mise à niveau de la version actuelle (la plus récente) d’Experience Manager as a Cloud Service.

>[!NOTE]
>
> Une fois que vous avez commencé à utiliser la version actuelle (la plus récente), comparez toutes les configurations remplacées avec les dernières pour obtenir les dernières fonctionnalités :
>- ui_config.json (peut avoir été défini dans les profils de dossier)


Pour Experience Manager Guides as a Cloud Service, procédez comme suit si vous ne l’avez pas déjà fait pour votre version existante :

### Procédure d’activation du déclenchement d’un script via une servlet

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 de Experience Manager Guides as a Cloud Service)

Une fois l’installation terminée, vous pouvez choisir d’APPUYER sur le déclencheur pour démarrer la tâche de traduction :

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

Dans la réponse précédente JSON, la clé `lockNodePath` contient le chemin d’accès au nœud créé dans le référentiel pointant vers la tâche envoyée. Il est automatiquement supprimé une fois la tâche terminée. Vous pouvez alors vous référer à ce nœud pour connaître le statut de la tâche.

Patientez jusqu’à ce que ce traitement soit terminé avant de passer aux étapes suivantes.

>[!NOTE]
>
> Vous devez vérifier si le nœud est toujours présent, ainsi que le statut de la tâche.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

### Étapes de post-traitement du contenu existant pour utiliser le rapport de lien rompu

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 de Experience Manager Guides as a Cloud Service)

Effectuez les étapes suivantes pour post-traiter le contenu existant et utiliser le nouveau rapport de lien rompu :

1. (Facultatif) Si le système contient plus de 100 000 fichiers DITA, mettez à jour les `queryLimitReads` et `queryLimitInMemory` sous `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` avec une valeur plus élevée (toute valeur supérieure au nombre de ressources présentes, par exemple 200 000), puis redéployez.

   - Suivez les instructions de la section *Remplacements de configuration* dans Installation et configuration d’Adobe Experience Manager Guides as a Cloud Service pour créer le fichier de configuration.
   - Dans le fichier de configuration, fournissez les détails (propriété) suivants pour configurer les options `queryLimitReads` et `queryLimitInMemory` :

     | PID | Clé de la propriété | Valeur de la propriété |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valeur : 200000 Valeur par défaut : 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Valeur : 200000 Valeur par défaut : 100000 |

1. Exécutez une requête de POST au serveur (avec l’authentification correcte) - `http://<server>//bin/guides/reports/upgrade`.

1. L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une demande de GET avec l’ID de tâche au même point d’entrée : `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(Par exemple : `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Une fois le traitement terminé, la requête de GET précédente répond avec succès. Si la tâche échoue pour une raison quelconque, l’échec est visible dans les journaux du serveur.

1. Revenez à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifiée à l’étape 1.

### Procédure à suivre pour indexer le contenu existant afin d’utiliser la nouvelle liste de recherche et de remplacement et de rubriques sous l’onglet Rapports :

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 de Experience Manager Guides as a Cloud Service)

Effectuez les étapes suivantes pour indexer le contenu existant et utiliser le nouveau texte rechercher et remplacer au niveau du mappage et de la liste de rubriques sous l’onglet rapports :

1. Exécutez une requête de POST au serveur (avec l’authentification correcte) - `http://<server:port>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des mappages pour les indexer. Par défaut, tous les mappages sont indexés.|| Exemple : `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. Vous pouvez également transmettre un dossier racine pour indexer les plans DITA d&#39;un dossier spécifique (et de ses sous-dossiers). Par exemple, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Notez que si le paramètre de chemins d’accès et le paramètre racine sont transmis, seul le paramètre de chemins d’accès est pris en compte.

1. L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une demande de GET avec l’ID de tâche au même point d’entrée, `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}` (par exemple : `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`).

1. Une fois la tâche terminée, la requête de GET précédente répond avec succès et mentionne si des mappages ont échoué. Les mappages correctement indexés peuvent être confirmés à partir des journaux du serveur.

### Procédure à suivre pour gérer le conflit de `'fmdita rewriter'`

Experience Manager Guides dispose d’un module [**custom sling rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter) qui gère les liens générés en cas de mappages croisés (liens entre les rubriques de deux mappages différents).

Si votre base de code contient un autre module de réécriture Sling personnalisé, utilisez une valeur de `'order'` supérieure à 50, car le module de réécriture Sling de Experience Manager Guides utilise `'order'` 50. Pour remplacer cela, vous avez besoin d’une valeur >50. Pour plus d’informations, consultez la section [Pipelines de réécriture de sortie](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Lors de cette mise à niveau, puisque la valeur `'order'` est modifiée de 1 000 à 50, vous devez fusionner le module de réécriture personnalisé existant, le cas échéant, avec `fmdita-rewriter`.

### Étapes de migration en arborescence B pour les fragments de contenu

Si les références ne s’affichent pas pour les fragments de contenu, vous pouvez choisir d’APPUYER sur le déclencheur pour démarrer la tâche de migration :

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

Dans la réponse précédente, JSON, la clé `lockNodePath` contient le chemin d’accès au nœud créé dans le référentiel, qui pointe vers la tâche envoyée. Il sera automatiquement supprimé une fois le traitement terminé. Vous pouvez vous reporter à ce nœud pour connaître le statut du traitement.

Patientez jusqu’à ce que ce traitement soit terminé avant de passer aux étapes suivantes.

>[!NOTE]
>
>Vous devez vérifier si le nœud est toujours présent, ainsi que le statut de la tâche.

GET :

```
http://<aem_domain>/var/dxml/executor-locks/cf-reference-store-btree-migration/1683190032886.json
```
