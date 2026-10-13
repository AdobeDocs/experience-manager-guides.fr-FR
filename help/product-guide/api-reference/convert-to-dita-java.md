---
title: API Java pour le workflow de conversion
description: En savoir plus sur les API Java pour le workflow de conversion
exl-id: 807d9ffa-23e3-476c-992d-c1f495233892
feature: Java-Based API Conversion Workflow
role: Developer
level: Experienced
TQID: 'https://experienceleague.adobe.com/gAntb7T-OGlwRNInxAsV8orxL3H9qL19Dsjwf5FZ14I'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
    internal-label: APIs
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: c2674c69-1bed-41fa-ba40-ab1a5382af59
    internal-label: Java Based API Conversion Workflow
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 4%
---
# API Java pour le workflow de conversion {#id175UB30E05Z}

>[!NOTE]
>
> Vous pouvez utiliser les API Java disponibles dans Experience Manager Guides pour créer des modules externes personnalisés et étendre les workflows prêts à l’emploi. Cet article sera archivé en novembre 2024.
> Consultez [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) pour obtenir la documentation la plus récente et détaillée sur l’utilisation de l’API Java.




Les API Java suivantes vous permettent de convertir des documents HTML et Word au format DITA. Ces API sont disponibles sous la forme d’un lot. Vous devez inclure ce lot dans votre code pour utiliser ces API.

**Détails de l’offre groupée** :

- ID de groupe : **com.adobe.fmdita**

- ID d’artefact : **api**

- Version : **3.2**

- Package : **com.adobe.fmdita.api.conversion**

- Détails de la classe :

  ```JAVA
  public class ConversionUtils extends Object
  ```

  La classe **ConversionUtils** contient des méthodes pour convertir des documents HTML et Word au format DITA.


## Convertir des documents HTML

La méthode `convertHtmlToDita` convertit des documents HTML au format DITA.

**Syntaxe**:

```JAVA
public static void convertHtmlToDita(Session session, 
                  String inputFile, 
                  String destPath, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `session` | javax.jcr.Session | Une session JCR valide. |
| `inputFile` | Chaîne | Chemin d’accès absolu aux fichiers HTML sources dans le référentiel AEM. |
| `destPath` | Chaîne | Chemin d&#39;accès absolu à l&#39;emplacement de destination où les fichiers DITA convertis seront enregistrés. |
| `createRev` | Booléen | Indiquez si une révision des fichiers est créée \( `true`\) à la destination spécifiée ou non \( `false`\). Cela n’est pris en compte que lorsque l’emplacement de destination contient une version existante des fichiers convertis. |

**Exception** :
Lance `RepositoryException`.

## Convertir des documents Word

La méthode ``convertWordToDita`` convertit des documents Word au format DITA.

**Syntaxe**:

```JAVA
public static void convertWordToDita(Session session, 
                  String inputFile,
                  String destPath, 
                  String style2tagMap, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `session` | javax.jcr.Session | Une session JCR valide. |
| `inputFile` | Chaîne | Chemin d’accès absolu aux fichiers Word sources dans le référentiel AEM. |
| `destPath` | Chaîne | Chemin d&#39;accès absolu à l&#39;emplacement de destination où les fichiers DITA convertis seront enregistrés. |
| `style2tagMap` | Chaîne | Chemin d’accès absolu au fichier de mappage de style qui sera utilisé pour la conversion. |
| `createRev` | Booléen | Indiquez si une révision des fichiers est créée \( `true`\) à la destination spécifiée ou non \( `false`\). Cela n’est pris en compte que lorsque l’emplacement de destination contient une version existante des fichiers convertis. |

**Exception** :
Lance `RepositoryException`.
