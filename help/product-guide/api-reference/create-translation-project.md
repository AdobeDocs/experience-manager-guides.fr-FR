---
title: Créer un projet de traduction
description: En savoir plus sur la création de projet de traduction d’API
feature: Post-Processing Event Handler
role: Developer
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: e0bef973-8c57-4760-9b12-ec950a3c7247
    internal-label: Post processing event handler
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 15%
---

# Créer un projet de traduction

>[!NOTE]
>
> Pour connaître les dernières définitions de point d’entrée de l’API REST et les détails associés, consultez la documentation Swagger à l’adresse `https://<aem-author-url>/libs/fmdita/clientlibs/api-docs/index.html` (remplacez `<aem-author-url>` par l’URL de votre serveur AEM). Comme cet article doit être archivé en octobre 2026, nous vous recommandons d’utiliser à l’avenir la documentation Swagger pour obtenir les informations d’API les plus récentes.

Une méthode POST qui vous permet de créer un projet de traduction en acceptant les détails du projet requis.

## URL de la requête

`http://<aem-guides-server>:<port-number>/bin/guides/v1/translation/project/create`

## Type de demande

POST

## Paramètres de la requête

| Nom | Type | Description |
|----|----|-----------|
| `type` | Chaîne | newTranslationProject, xliffTranslationProject, newMultiLanguageTranslationProject, addToExistingProject, newScopingTranslationProject |
| `versionDetails`, `versionSelector` | Chaîne | Ligne de base, latestVersion, versionAsOfDate |
| `language` | Chaîne | Langues séparées par des virgules « de », « fr » |
| `map.id` | Chaîne | GUID du mappage source à traduire |
| `map.path` | Chaîne | Chemin du mapping source à traduire |
| `referenceType` | Chaîne | Indirect, direct |
| `fileType` | Chaîne | Carte, Sujet, Autres |
| `documentState` | Chaîne | peut être l&#39;une des listes affectées par l&#39;utilisateur sur le profil de map |
| `translationStatus` | Chaîne | Désynchronisé, Synchronisé, À jour, Obsolète, En cours, Copie manquante, AUCUN, S/O |

>[!NOTE]
>
>Vous pouvez utiliser `map.id` ou `map.path` lors de la création d’un projet de traduction.

## Exemple de requête

```JSON
{
  "title": "Test Project 1 on Dec 5",
  "type": "newTranslationProject",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en",
      "path": "/content/dam/ajay-test/lang/en/m2.ditamap"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "latestVersion"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": [] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
   ]
```

## Valeurs de réponse

```JSON
{
  "executionId": "5c13c571-3407-46d5-8f45-50ea9e05a212",
  "path": "/content/projects/test_project_1_ondec5"
}
```

**Codes de réponse**

- 200 Succès
- 400 Entrée non valide
- 401 Accès non autorisé
- Erreur de serveur interne 500

## Exemples de requêtes

### Ajouter à un projet existant

```json
{
  "title": "Add to existing Project",
  "type": "addToExistingProject",
  "path": "/content/projects/test_project_1_existing",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "versionAsOfDate",
      "version": "2025-12-05T10:30:00+01:30"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": [] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
  ]
}
```

### Ajouter à un projet existant avec une ligne de base

```json
{
  "title": "Add to existin project Project with baseline",
  "type": "addToExistingProject",
  "path": "/content/projects/existing_project_path",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "baseline",
      "version": "test1"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": ["Direct"] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
  ]
}
```

## Statut de création du projet de traduction

Une API GET qui suit le statut de traduction d’un nouveau projet de traduction.

## URL de la requête

`http://<aem-guides-server>:<port-number>/bin/guides/v1/translation/project/creationstatus`

## Type de demande

GET

## Paramètres de la requête

| Nom | Type | Description |
|----|----|-----------|
| `path` | Chaîne | Chemin du projet |
| `languageStatusMap` | Chaîne | Pour chaque langue demandée, renvoie l’état d’achèvement : En cours, Terminé, Échec, Ignoré |


## Exemple de requête

```json
{
  "path": "/content/projects/test_project_1_ondec5",
  "languageStatusMap": {
    "de": "Completed"
  }
}
```
