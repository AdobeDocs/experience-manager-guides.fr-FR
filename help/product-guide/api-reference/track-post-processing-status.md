---
title: API pour effectuer le suivi du post-traitement d’un dossier ou d’une ressource
description: Découvrez l’API permettant d’effectuer le suivi du post-traitement d’un dossier ou d’une ressource
feature: Post-Processing Event Handler
role: Developer
level: Experienced
exl-id: f902fac1-2717-4696-a835-c4b0bb8add3d
TQID: https://experienceleague.adobe.com/Lyv-S5o-Z40bMqqIHhbxKrsmn9CCqHRnqnpiq91EjGU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: a13143053c75ab65cbcd20a52c8ca3fb953edecf
workflow-type: tm+mt
source-wordcount: 198
ht-degree: 10%

---

# API pour effectuer le suivi de l’état de post-traitement d’un dossier ou d’une ressource

>[!NOTE]
>
> Pour connaître les dernières définitions de point d’entrée de l’API REST et les détails associés, consultez la documentation Swagger à l’adresse `https://<aem-author-url>/libs/fmdita/clientlibs/api-docs/index.html` (remplacez `<aem-author-url>` par l’URL de votre serveur AEM). Comme cet article doit être archivé en octobre 2026, nous vous recommandons d’utiliser à l’avenir la documentation Swagger pour obtenir les informations d’API les plus récentes.

Voici une méthode POST qui démarre une tâche asynchrone pour obtenir le statut des ressources.

## Recherche du statut des ressources dans les guides

**URL de la demande**

`http://<aem-guides-server>:<port-number>bin/guides/v1/assets/status `

**Paramètres**

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `path` | Chaîne | Oui | Chemin d’accès au dossier ou à la ressource pour lequel le statut doit être récupéré. |
| `excludedPaths` | Chaîne | Non | Chemins d’accès aux dossiers à exclure de la liste ci-dessus. |

```JSON
{ 

    "paths": [ 

        "/content/dam/status-fetch1", 

        "/content/dam/status-fetch2" 

    ], 

    "excludedPaths": [ 

        "content/dam/status-fetch1/excluded-folder" 

    ] 

} 
```

**Valeurs de réponse**
jobId à interroger pour obtenir le statut d&#39;une tâche asynchrone.

```JSON
{ 

  "jobId": "akjhdfalkj1132", 

  "status": "WAITING", 

 

} 
```

## API Poller

Une méthode GET qui obtient le statut d’une tâche asynchrone exécutée par l’API ci-dessus.

**URL de la demande**

`http://<aem-guides-server>:<port-number>bin/guides/v1/assets/status`

**Paramètres**

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `jobId` | Chaîne | Oui | Identifiant du traitement renvoyé par l’API ci-dessus . |

**Valeurs de réponse**

Liste des ressources et de leur statut.

```JSON
{ 

  "jobId": " akjhdfalkj1132", 

  "status": "SUCCESS", 

  "assets": [ 

    { 

      "path": "/content/dam/status-fetch1/a.dita", 

      "uuid": "GUID-1293914ansd", 

      "status": "SUCCESS", 

      "exists": true 

    }, 

    { 

      "path": "/content/dam/status-fetch1/b.dita", 

      "uuid": "GUID-1883241", 

      "status": "FAILURE", 

      "exists": true 

    } 

 

  ] 

} 
```

**Valeurs de statut :** SUCCÈS, ÉCHEC, TRAITEMENT, EN ATTENTE
