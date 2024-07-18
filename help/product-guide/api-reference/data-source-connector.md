---
title: API REST pour enregistrer un connecteur de source de données
description: Découvrez l’API REST pour enregistrer un connecteur de source de données
exl-id: e2811892-c3cf-41f5-94d8-c2b37823a53a
feature: Rest API Data Source
role: Developer
level: Experienced
source-git-commit: b4762314ec5269abe62b622184f1724762a6cfa0
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 7%

---

# API REST pour enregistrer un connecteur de source de données {#id236LG0Y0CXA}

L’API REST suivante vous permet d’enregistrer un connecteur de source de données.

## Enregistrement d’un connecteur de source de données

Méthode de GET qui enregistre un connecteur de source de données.

**Demander l’URL** :
`http://server:port/bin/guides/v1/konnect/config/register?path=<uploaded file path>`

**Paramètre** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `path` | Chaîne | Oui | Chaîne pointant vers un chemin d’accès dans le référentiel AEM. Il peut s’agir d’un chemin d’accès dans le `/content/dam or /var/dxml`. |

**Exemple** :\
`http://host:4502/bin/guides/v1/konnect/config/register?path=/var/dxml/konnect/jira.json`
