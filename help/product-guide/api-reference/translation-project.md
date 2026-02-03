---
title: Créer un projet de traduction
description: En savoir plus sur la création de projet de traduction d’API
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: 41dd3dee5f9d64fb5c58b5b302cc9759e48e3631
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 18%

---

# Créer un projet de traduction

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

Une API GET qui effectue le suivi du statut de traduction d’un nouveau projet de traduction.

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



