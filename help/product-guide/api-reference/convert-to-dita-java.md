---
title: API Java pour le workflow de conversion
description: En savoir plus sur les API Java pour le workflow de conversion
exl-id: 807d9ffa-23e3-476c-992d-c1f495233892
feature: Java-Based API Conversion Workflow
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/gAntb7T-OGlwRNInxAsV8orxL3H9qL19Dsjwf5FZ14I
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552eid: c6d09140-3c91-45d3-b7ed-b681af752f43
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 324
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
