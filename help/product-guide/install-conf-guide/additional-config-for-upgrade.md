---
title: Configuration supplémentaire pour la mise à niveau du service cloud
description: Découvrez la configuration supplémentaire pour mettre à niveau le service cloud
source-git-commit: 453da51a42984b912547570f2e1de70806b41171
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 0%

---

# Configuration supplémentaire pour la mise à niveau d’AEM Guides as a Cloud Service

>[!INFO]
>
>Cet article s’applique si vous avez configuré des paramètres de profil de dossier personnalisés (`ui_config.json`). Après chaque mise à niveau, vérifiez et modifiez vos paramètres selon les besoins pour garantir la compatibilité avec les dernières modifications.

Selon la version à partir de laquelle vous effectuez la mise à niveau, des étapes de configuration supplémentaires peuvent être nécessaires pour intégrer les modifications introduites dans les versions Cloud Service plus récentes.

Certaines configurations s’appliquent uniquement à des versions spécifiques. Veillez à vous référer aux sections de configuration ci-dessous et à appliquer les configurations requises applicables à votre configuration.

## Étapes d’application de filtres de recherche sur les fichiers DITAVAL pour tous les paramètres prédéfinis de sortie

Pour garantir le bon fonctionnement des filtres, mettez à jour le fichier ui_config.json. Modifiez les propriétés répertoriées sous **browseFilters** > **Fichiers non-DITA** > **Fichiers Ditaval** comme illustré ci-dessous :

```
{
  "title": "Ditaval Files",
  "property": "LOWER_NAME",
  "operation": "like",
  "value": ".ditaval"
}
```

## Étapes de migration en arborescence B pour les fragments de contenu

Si les références ne s’affichent pas pour les fragments de contenu, vous pouvez choisir d’exécuter la tâche de migration :

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

## Procédure à suivre pour gérer le conflit de `'fmdita rewriter'`

Experience Manager Guides dispose d’un module [**custom sling rewriter**](../install-conf-guide/conf-output-generation.md#custom-rewriter) qui gère les liens générés en cas de mappages croisés (liens entre les rubriques de deux mappages différents).

Si votre base de code contient un autre module de réécriture Sling personnalisé, utilisez une valeur de `'order'` supérieure à 50, car le module de réécriture Sling de Experience Manager Guides utilise `'order'` 50. Pour remplacer cela, vous avez besoin d’une valeur >50. Pour plus d’informations, consultez la section [Pipelines de réécriture de sortie](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Lors de cette mise à niveau, puisque la valeur `'order'` est modifiée de 1 000 à 50, vous devez fusionner le module de réécriture personnalisé existant, le cas échéant, avec `fmdita-rewriter`.

## Configurations applicables pour les versions antérieures à juin 2023

Les configurations suivantes ne sont requises que si vous utilisez une version de Experience Manager Guides as a Cloud Service publiée avant juin 2023. Développez les sections pertinentes ci-dessous pour appliquer les paramètres nécessaires et assurer la compatibilité avec les mises à jour nécessaires.

+++Procédure d’indexation du contenu existant afin d’utiliser la nouvelle liste de recherche et de remplacement et de rubriques sous l’onglet Rapports
Effectuez les étapes suivantes pour indexer le contenu existant et utiliser le nouveau texte rechercher et remplacer au niveau du mappage et de la liste de rubriques sous l’onglet rapports :

1. Exécutez une requête POST au serveur (avec l’authentification correcte) - `http://<server:port>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des mappages pour les indexer. Par défaut, tous les mappages sont indexés.|| Exemple : `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. Vous pouvez également transmettre un dossier racine pour indexer les plans DITA d&#39;un dossier spécifique (et de ses sous-dossiers). Par exemple, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Notez que si le paramètre de chemins d’accès et le paramètre racine sont transmis, seul le paramètre de chemins d’accès est pris en compte.

1. L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée, `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}` (par exemple : `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`).

1. Une fois la tâche terminée, la requête GET précédente répond avec succès et mentionne si des mappages ont échoué. Les mappages correctement indexés peuvent être confirmés à partir des journaux du serveur.

+++

+++Étapes de post-traitement du contenu existant pour utiliser le rapport de lien rompu 
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

+++

+++Procédure d’activation du déclenchement d’un script via une servlet
Une fois l’installation terminée, vous pouvez choisir de démarrer la tâche de traduction :

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

+++
