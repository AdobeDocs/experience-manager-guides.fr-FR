---
title: API pour démarrer le traitement en bloc des ressources
description: En savoir plus sur l’API permettant de démarrer le traitement en bloc des ressources
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: e2eca63a5dd56e358aeea047b37f4b0f88dc720b
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 11%

---

# API pour démarrer le traitement en bloc des ressources

Méthode POST qui lance le traitement des ressources en bloc pour un chemin d’accès spécifié. Cette API prend en charge le traitement des ressources basé sur JCR et sur la base de données. Il lance une tâche asynchrone qui traite toutes les ressources du chemin donné et de ses sous-chemins. Lors du lancement, l’API renvoie un ID de traitement unique, qui peut être utilisé pour suivre le statut de la tâche.

**URL de la demande**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process`

**Paramètres de requête**

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `path` | Chaîne | Oui | Chemin d’accès absolu du dossier ou de la ressource dans le référentiel AEM à traiter. |
| `excludedPaths` | Chaîne | Non | Liste des chemins à exclure du traitement |
| `type` | Chaîne | Oui | Type de traitement à effectuer. Par exemple : ASSET_PROCESSING. |

**Exemple de requête**

```JSON
{
  "path": "/content/dam/status-fetch1",
  "excludedPaths": [
    "content/dam/status-fetch1/excluded-folder"
  ],
  "type": "ASSET_PROCESSING"
}
```

**Valeurs de réponse**

processingId à interroger pour obtenir le statut du traitement asynchrone.

```JSON
{
  "processingId": "akjhdfalkj1132"
}
```

**Codes de réponse**

- 200 Succès
- 400 Entrée non valide
- 401 Accès non autorisé
- Erreur de serveur interne 500

## Vérifier le statut du traitement

Une méthode GET qui récupère le statut actuel d’une tâche de traitement des ressources démarrée précédemment.

**URL de la demande**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/status`

**Paramètres de requête**

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `processingId` | Chaîne | Oui | ID unique du traitement dont l’état fait l’objet d’une requête. |

**Exemple de réponse**

```JSON
{
  "processingId": "string",
  "path": "string",
  "excludedPaths": ["string"],
  "status": "WAITING",
  "triggeredCount": 0,
  "startedAt": 0,
  "completedAt": 0,
  "hasLogs": true,
  "createdBy": "string",
  "type": "ASSET_PROCESSING",
  "migrationSet": {
    "totalFiles": 0,
    "calculationStatus": "WAITING"
  },
  "eta": {
    "value": 0,
    "unit": "string"
  },
  "comments": "string",
  "restartable": true,
  "resumable": true,
  "cancellable": true
}
```

**Codes de réponse**

- 200 Succès
- 400 Entrée non valide
- 401 Accès non autorisé
- Erreur de serveur interne 500

## Affichage des journaux de tâches

Méthode GET qui récupère les journaux d’un ID de tâche donné. Cette API récupère les journaux de la tâche de traitement des ressources. L’ID de traitement est obligatoire. L’API fournit des paramètres de décalage et de limite, ainsi qu’une stratégie de fin.

**URL de la demande**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/logs`

**Paramètres de requête**

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `processingId` | Chaîne | Oui | ID unique du traitement dont les journaux doivent être affichés. |
| `offset` | Entier | Non | Point de départ (numéro de ligne) à partir duquel les journaux doivent être lus. Utilisé pour la pagination pour ignorer les N premières lignes. |
| `limit` | Entier | Non | Nombre maximal de lignes de journal à récupérer. |
| `tail` | Entier | Non | Nombre de lignes de log à récupérer depuis la fin. |


**Exemple de réponse**

```JSON
{
  "lines": [
    "string"
  ],
  "limit": 0,
  "offset": 0,
  "hasMore": true
}
```

**Codes de réponse**

- 200 Succès
- 400 Entrée non valide
- 401 Accès non autorisé
- 500 Internal server error


## Télécharger les journaux de tâches

Méthode GET qui télécharge le fichier journal d’une tâche donnée au format ZIP.

**URL de la demande**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/logs/download`

**Paramètres de requête**

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `processingId` | Chaîne | Oui | ID unique de la tâche dont le fichier journal doit être téléchargé. |


**Exemple de réponse**

```JSON
{
  "logFilePaths": [
    "string"
  ]
}
 
```

**Codes de réponse**

- 400 Entrée non valide
- 401 Accès non autorisé
- 500 Internal server error

## Annuler le traitement

Une API POST qui annule une requête de traitement des ressources en bloc en cours. Si la tâche est introuvable, l’API renvoie une erreur.

**URL de la demande**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/cancel`

**Paramètres de requête**

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `processingId` | Chaîne | Oui | ID unique du traitement dont l’état fait l’objet d’une requête. |


**Codes de réponse**

- 200 Succès
- 400 Entrée non valide
- 401 Accès non autorisé
- 500 Internal server error


## Reprendre la tâche

Une API POST qui redémarre une requête de traitement des ressources en bloc précédemment annulée ou ayant échoué. Le traitement reprend à partir du dernier point de contrôle. Si la tâche est introuvable ou est en cours d’exécution, l’API renvoie une erreur.

**URL de la demande**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/resume`

**Paramètres de requête**

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `processingId` | Chaîne | Oui | ID unique du traitement dont l’état fait l’objet d’une requête. |


**Codes de réponse**

- 200 Succès
- 400 Entrée non valide
- 401 Accès non autorisé
- 500 Internal server error

## Afficher l’historique des tâches

Une API GET qui renvoie les « N » dernières exécutions de post-traitement des ressources.

**URL de la demande**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/history`

**Paramètres de requête**

Aucune. Cette requête GET récupère l’historique des tâches sans nécessiter de paramètres d’entrée.

**Exemple de réponse**

```JSON
{
  "executionHistory": [
    {
      "processingId": "165f1de6-68c4-4dcd-9223-2b7242b62306",
      "path": "/content/dam/22858",
      "status": "SUCCESS",
      "triggeredCount": 6,
      "startedAt": 1761291362776,
      "completedAt": 1761291364026,
      "hasLogs": true,
      "createdBy": "user",
      "type": "ASSET_PROCESSING",
      "migrationSet": {
        "totalFiles": 6,
        "calculationStatus": "SUCCESS"
      },
      "eta": {
        "value": 0,
        "unit": "SECONDS"
      },
      "comments": "",
      "filter": {
        "fileTypes": [],
        "filterProcessedAssets": false
      },
      "cancellable": false,
      "resumable": false,
      "restartable": true
    }
  ]
}
```



