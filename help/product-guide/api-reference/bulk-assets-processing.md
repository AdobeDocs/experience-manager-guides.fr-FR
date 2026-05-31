---
title: API pour démarrer le traitement en bloc des ressources
description: En savoir plus sur l’API permettant de démarrer le traitement en bloc des ressources
feature: Post-Processing Event Handler
role: Developer
level: Experienced
exl-id: feba6d8e-c363-4360-af33-92a01dcf6672
TQID: https://experienceleague.adobe.com/rGPpMIf5X5lfZZy2ZWk9lizd2E7UyRT8BLkSBb0o320
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: a13143053c75ab65cbcd20a52c8ca3fb953edecf
workflow-type: tm+mt
source-wordcount: 639
ht-degree: 11%

---

# API pour démarrer le traitement en bloc des ressources

>[!NOTE]
>
> Pour connaître les dernières définitions de point d’entrée de l’API REST et les détails associés, consultez la documentation Swagger à l’adresse `https://<aem-author-url>/libs/fmdita/clientlibs/api-docs/index.html` (remplacez `<aem-author-url>` par l’URL de votre serveur AEM). Comme cet article doit être archivé en octobre 2026, nous vous recommandons d’utiliser à l’avenir la documentation Swagger pour obtenir les informations d’API les plus récentes.

Méthode POST qui lance le traitement des ressources en bloc pour un chemin d’accès spécifié. Cette API prend en charge le traitement des ressources basé sur JCR et sur la base de données. Il lance une tâche asynchrone qui traite toutes les ressources du chemin donné et de ses sous-chemins. Lors du lancement, l’API renvoie un ID de traitement unique, qui peut être utilisé pour suivre le statut de la tâche.

**URL de la demande**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process`

**Paramètres de requête**

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `path` | Chaîne | Oui | Chemin d’accès absolu du dossier ou de la ressource dans le référentiel AEM à traiter. |
| `excludedPaths` | Chaîne | Non | Liste des chemins à exclure du traitement |
| `type` | Chaîne | Oui | Type de traitement à effectuer. Par exemple : ASSET_PROCESSING. |
| `filter` | Objet | Non | Filtres appliqués aux ressources sélectionnées |

**Filtrer les champs d’objet**

| Nom | Type | Description |
|----|----|-----------|
| fileTypes | Chaîne | Types de ressources à traiter. Valeurs autorisées : DITATOPIC, DITAMAP, MARKDOWN, HTML/CSS, DITAVAL, AUTRES. |
| heure de début | Entier | Limite inférieure pour l’heure de création de la ressource |
| heure de fin | Entier | Limite supérieure pour l’heure de création de la ressource |

**Exemple de requête**

```JSON
{
  "path": "/content/dam/status-fetch1",
  "excludedPaths": [
    "content/dam/status-fetch1/excluded-folder"
  ],
  "type": "ASSET_PROCESSING",
  "filter": {
        "fileTypes": ["DITAMAP", "DITATOPIC"],
        "startTime": 1758876933000
        "endTime": 1764932039000
    }
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
