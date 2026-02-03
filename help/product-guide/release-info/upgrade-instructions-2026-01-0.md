---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans Adobe Experience Manager Guides version 2026.01.0
description: Découvrez la matrice de compatibilité et comment effectuer une mise à niveau vers la version 2026.01.0 d’Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: e6dab21263731b42567729649a11e9d0a74f1dfd
workflow-type: tm+mt
source-wordcount: '1139'
ht-degree: 3%

---

# Instructions de mise à niveau pour la version 2026.01.0

Cet article couvre les instructions de mise à niveau et la matrice de compatibilité pour la version 2026.01.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2026.01.0](whats-new-2026-01-0.md).

Pour connaître la liste des problèmes résolus dans cette version, voir la section [Problèmes résolus dans la version 2026.01.0](fixed-issues-2026-01-0.md).

## Matrice de compatibilité

Cette section présente la matrice de compatibilité pour les applications logicielles prises en charge par la version 2026.01.0 de Experience Manager Guides as a Cloud Service.

### FrameMaker et FrameMaker Publishing Server

| Version de Experience Manager Guides as a Cloud | FMPS | FrameMaker | Oxygen Author |
| --- | --- | --- | --- |
| 2026.01.0 | Non compatible | 2022 ou version ultérieure | 26,1 |


### Connecteur D&#39;Oxygène

| Version de Experience Manager Guides as a Cloud | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2026.01.0 | 3.8 -uuid 1 | 3.8 -uuid 1 | 2,3 | 2,3 |


### Version du modèle de la base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu de composants Experience Manager Guides pour Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |


### Nouvelle version du modèle de site AEM

| Version des composants | Version du site |
|---|---|
| guides-components.all-1.4.0 | aemg-sites-template-1.3.0 |

## Conditions préalables

Conformément au comportement standard de DITA, l&#39;attribut scope=`external` ne doit pas être appliqué aux liens internes, car il est destiné uniquement aux références à des ressources externes. L’application de cet attribut aux liens internes et le déplacement de ces ressources peuvent perturber les workflows. Pour le contenu géré dans Experience Manager Guides, utilisez plutôt l’étendue par défaut=`local` ou les références basées sur les clés .

## Mise à niveau vers la version 2026.01.0

Experience Manager Guides est automatiquement mis à niveau lors de la mise à niveau vers la dernière version d’Experience Manager as a Cloud Service.

>[!NOTE]
>
> Cette version comprend des mises à jour des paramètres du profil de dossier (ui_config.json). Si vous utilisez des paramètres personnalisés, veillez à les sauvegarder avant de procéder à la mise à niveau. Après la mise à jour, vérifiez et ajustez vos paramètres pour vous aligner sur les modifications introduites dans la dernière version.

Effectuez les étapes suivantes pour Experience Manager Guides as a Cloud Service si vous ne l’avez pas déjà fait pour votre version existante :

### Procédure d’activation du déclenchement d’un script via une servlet

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 de Experience Manager Guides as a Cloud Service)

Une fois l’installation terminée, vous pouvez choisir d’APPUYER sur le déclencheur pour démarrer la tâche de traduction :

PUBLICATION :

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

1. Exécutez une requête POST au serveur (avec l’authentification correcte) - `http://<server>//bin/guides/reports/upgrade`.

1. L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée : `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(Par exemple : `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Une fois le traitement terminé, la requête GET précédente répond avec succès. Si la tâche échoue pour une raison quelconque, l’échec est visible dans les journaux du serveur.

1. Revenez à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifiée à l’étape 1.

### Procédure à suivre pour indexer le contenu existant afin d’utiliser la nouvelle liste de recherche et de remplacement et de rubriques sous l’onglet Rapports :

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 de Experience Manager Guides as a Cloud Service)

Effectuez les étapes suivantes pour indexer le contenu existant et utiliser le nouveau texte rechercher et remplacer au niveau du mappage et de la liste de rubriques sous l’onglet rapports :

1. Exécutez une requête POST au serveur (avec l’authentification correcte) - `http://<server:port>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des mappages pour les indexer. Par défaut, tous les mappages sont indexés.|| Exemple : `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. Vous pouvez également transmettre un dossier racine pour indexer les plans DITA d&#39;un dossier spécifique (et de ses sous-dossiers). Par exemple, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Notez que si le paramètre de chemins d’accès et le paramètre racine sont transmis, seul le paramètre de chemins d’accès est pris en compte.

1. L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée, `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}` (par exemple : `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`).

1. Une fois la tâche terminée, la requête GET précédente répond avec succès et mentionne si des mappages ont échoué. Les mappages correctement indexés peuvent être confirmés à partir des journaux du serveur.

### Procédure à suivre pour gérer le conflit de `'fmdita rewriter'`

Experience Manager Guides dispose d’un module [**custom sling rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter) qui gère les liens générés en cas de mappages croisés (liens entre les rubriques de deux mappages différents).

Si votre base de code contient un autre module de réécriture Sling personnalisé, utilisez une valeur de `'order'` supérieure à 50, car le module de réécriture Sling de Experience Manager Guides utilise `'order'` 50. Pour remplacer cela, vous avez besoin d’une valeur >50. Pour plus d’informations, consultez la section [Pipelines de réécriture de sortie](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Lors de cette mise à niveau, puisque la valeur `'order'` est modifiée de 1 000 à 50, vous devez fusionner le module de réécriture personnalisé existant, le cas échéant, avec `fmdita-rewriter`.

### Étapes de migration en arborescence B pour les fragments de contenu

Si les références ne s’affichent pas pour les fragments de contenu, vous pouvez choisir d’APPUYER sur le déclencheur pour démarrer la tâche de migration :

PUBLICATION :

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

### Étapes d’application des filtres de recherche sur les fichiers DITAVAL pour tous les paramètres prédéfinis de sortie

Pour garantir le bon fonctionnement des filtres, mettez à jour le fichier ui_config.json. Modifiez les propriétés répertoriées sous **browseFilters** > **Fichiers non-DITA** > **Fichiers Ditaval** comme illustré ci-dessous :

```
{
  "title": "Ditaval Files",
  "property": "LOWER_NAME",
  "operation": "like",
  "value": ".ditaval"
}
```
