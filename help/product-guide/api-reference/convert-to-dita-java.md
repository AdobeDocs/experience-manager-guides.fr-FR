---
title: API Java pour le workflow de conversion
description: En savoir plus sur les API Java pour le workflow de conversion
exl-id: 807d9ffa-23e3-476c-992d-c1f495233892
feature: Java-Based API Conversion Workflow
role: Developer
level: Experienced
source-git-commit: 8c80a4da8e61909aab0f2db81ef97149774b36c4
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 5%

---

# API Java pour le workflow de conversion {#id175UB30E05Z}

>[!NOTE]
>
> Vous pouvez utiliser des API Java disponibles dans Experience Manager Guides pour créer des modules externes personnalisés et étendre les processus prêts à l’emploi. Cet article sera archivé en novembre 2024.
> Affichez [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) pour obtenir la documentation la plus récente et détaillée sur l’utilisation de l’API Java.




Les API Java suivantes vous permettent de convertir des documents HTML et Word au format DITA. Ces API sont disponibles sous la forme d’un lot. Vous devez inclure ce lot dans votre code pour utiliser ces API.

**Détails du lot** :

- ID de groupe : **com.adobe.fmdita**

- ID d’artefact : **api**

- Version : **3.2**

- Package : **com.adobe.fmdita.api.conversion**

- Détails de la classe :

  ```JAVA
  public class ConversionUtils extends Object
  ```

  La classe **ConversionUtils** contient des méthodes pour convertir des documents HTML et Word au format DITA.


## Convertir des documents d’HTML

La méthode `convertHtmlToDita` convertit les documents d’HTML au format DITA.

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
| `session` | javax.jcr.Session | Session JCR valide. |
| `inputFile` | Chaîne | Chemin d’accès absolu aux fichiers d’HTML source dans le référentiel AEM. |
| `destPath` | Chaîne | Chemin absolu de l’emplacement de destination où les fichiers DITA convertis seront enregistrés. |
| `createRev` | Booléen | Indiquez si une révision des fichiers est créée \( `true`\) à la destination spécifiée ou non \( `false`\). Cela n’est pris en compte que lorsque l’emplacement de destination contient une version existante des fichiers convertis. |

**Exception** :
Lance `RepositoryException`.

## Conversion de documents Word

La méthode ``convertWordToDita`` convertit les documents Word au format DITA.

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
| `session` | javax.jcr.Session | Session JCR valide. |
| `inputFile` | Chaîne | Chemin d’accès absolu aux fichiers Word source dans AEM référentiel. |
| `destPath` | Chaîne | Chemin absolu de l’emplacement de destination où les fichiers DITA convertis seront enregistrés. |
| `style2tagMap` | Chaîne | Chemin d’accès absolu au fichier de mappage de style qui sera utilisé pour la conversion. |
| `createRev` | Booléen | Indiquez si une révision des fichiers est créée \( `true`\) à la destination spécifiée ou non \( `false`\). Cela n’est pris en compte que lorsque l’emplacement de destination contient une version existante des fichiers convertis. |

**Exception** :
Lance `RepositoryException`.
