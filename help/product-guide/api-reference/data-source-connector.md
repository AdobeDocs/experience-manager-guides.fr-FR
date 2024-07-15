---
title: API REST pour enregistrer un connecteur de source de données
description: Découvrez l’API REST pour enregistrer un connecteur de source de données
exl-id: e2811892-c3cf-41f5-94d8-c2b37823a53a
feature: Rest API Data Source
role: Developer
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 0%

---

# API REST pour enregistrer un connecteur de source de données {#id236LG0Y0CXA}

L’API REST suivante vous permet d’enregistrer un connecteur de source de données.

## Enregistrement d’un connecteur de source de données

Méthode de GET qui enregistre un connecteur de source de données.

**Demander l’URL** :
`http://server:port/bin/guides/v1/konnect/config/register?path=<uploaded file path>`

**Paramètre** :
|Nom|Type|Obligatoire|Description|
|----|----|--------|-----------|
|`path`|String|Yes|A string which points to a path in the AEM repository. It can be a path in the `/content/dam or /var/dxml`.|

**Exemple** :\
`http://host:4502/bin/guides/v1/konnect/config/register?path=/var/dxml/konnect/jira.json`
