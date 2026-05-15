---
title: API Java pour utiliser la ligne de base et les libellés
description: Découvrez les API Java utilisables avec les références et les libellés
exl-id: 0e2ba1bb-f5bf-44da-848a-a55385460c83
feature: Java-Based API Baseline
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/3vpR2zCp5a6dBn6RkSKgBeU7cS3Me-HE0KQxc-duYCk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 944
ht-degree: 2%

---

# API Java pour utiliser la ligne de base et les libellés {#id175UB30E05Z}

>[!NOTE]
>
> Vous pouvez utiliser les API Java disponibles dans Experience Manager Guides pour créer des modules externes personnalisés et étendre les workflows prêts à l’emploi. Cet article sera archivé en novembre 2024.
> Consultez [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) pour obtenir la documentation la plus récente et détaillée sur l’utilisation de l’API Java.


Les API Java suivantes vous permettent de créer une ligne de base et d’ajouter des libellés aux fichiers d’une ligne de base. Ces API sont disponibles sous la forme d’un lot. Vous devez inclure ce lot dans votre code pour utiliser ces API.

Détails du bundle :

- ID de groupe : **com.adobe.fmdita**

- ID d’artefact : **api**

- Version : **3.5**

- Package : **com.adobe.fmdita.api.baselines**

- Détails de la classe :

  ```JAVA
  public class BaselineUtils extends Object
  ```

  La classe **BaselineUtils** contient des méthodes permettant de créer des lignes de base et d&#39;appliquer des libellés aux fichiers d&#39;une ligne de base.


## Créer une ligne de base

La méthode Créer une ligne de base comporte deux versions : une pour la solution XML Documentation version 3.5 et d’autres pour les versions antérieures à la version 3.5 \(qui inclut les versions 3.4, 3.3 et 3.2\). L’API version 3.5 permet de créer une ligne de base à l’aide d’un libellé, de références directes et de références indirectes dans un fichier de mappage.

L’autre version de l’API utilise la date et l’heure pour créer une ligne de base. Cette API est conservée pour assurer la rétrocompatibilité avec les systèmes utilisant la solution XML Documentation 3.4, 3.3 ou 3.2.

**Syntaxe \(pour la version 3.5\)** :

```JAVA
public static String createBaseline(Session session, 
String sourcePath, 
String baselineTitle, 
String label, 
LinkedHashMap directContext, 
LinkedHashMap indirectContext) 
throws GuidesApiException
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `session` | javax.jcr.Session | Une session JCR valide. La session utilisateur doit disposer des autorisations de lecture et d&#39;écriture pour le plan DITA et des autorisations de lecture pour tous les fichiers de référence inclus dans la ligne de base. |
| `sourcePath` | Chaîne | Chemin d&#39;accès absolu au fichier de mappage DITA dans le référentiel AEM. |
| `baselineTitle` | Chaîne | Titre unique de la ligne de base. |
| `label` | Chaîne | Sélectionnez la version d&#39;une rubrique à laquelle est appliqué le libellé donné. |
| `directContext` | LinkedHashMap&lt;String, Object\> | Les configurations sur la base desquelles la rubrique directement référencée \(content\) est sélectionnée, l’ordre mentionné dans le mappage est suivi pour résoudre une version. <br> Si, après itération sur toutes les clés du mappage, aucune version n’est trouvée, le processus de création de la ligne de base échoue. <br> Si la carte de hachage est vide \(envoyez une carte vide et non nulle pour la valeur par défaut\), elle est renseignée par défaut comme suit : <br>`directContext.put("label", label);` <br> `directContext.put("latest", true);` <br> Si vous souhaitez que la création de la ligne de base ne sélectionne que la version d&#39;un libellé donné et échoue en l&#39;absence d&#39;une telle version, placez la clé `label` et le libellé sur lesquels vous souhaitez créer la ligne de base. |
| `indirectContext` | LinkedHashMap&lt;String, Object\> | Les configurations sur la base desquelles la rubrique indirectement référencée \(contenu référencé\) est sélectionnée, l’ordre mentionné dans le mappage est suivi pour résoudre une version. <br> Si, après itération sur toutes les clés du mappage, aucune version n’est trouvée, le processus de création de la ligne de base échoue. <br> Si la carte de hachage est vide \(envoyez une carte vide et non nulle pour la valeur par défaut\), elle est renseignée par défaut comme suit : <br>`indirectContext.put("label", label);` <br>`indirectContext.put "pickAutomatically", null);` <br> Si vous souhaitez qu’elle soit la dernière version au lieu de sélectionner automatiquement une version, remplacez : <br>`indirectContext.put("pickAutomatically", null);` <br> _par :_<br>`indirectContext.put("latest", true)` |

**Renvoie** :
Le nom de la ligne de base, qui est le nom de nœud de la ligne de base dans le référentiel JCR. Le titre de la nouvelle ligne de base s&#39;affiche pour l&#39;utilisateur sur la page Ligne de base du plan DITA.

**Exception** :
Renvoie ``ItemExistExceptiom`` si une ligne de base portant le même titre existe déjà.

**Syntaxe \(pour les versions 3.4, 3.3 et 3.2\)**

```JAVA
public static String createBaseline
(Session session, 
String sourcePath, 
String baselineTitle, 
Date versionDate) throws GuidesApiException
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `session` | javax.jcr.Session | Une session JCR valide. La session utilisateur doit disposer des autorisations de lecture et d&#39;écriture pour le plan DITA et des autorisations de lecture pour tous les fichiers de référence inclus dans la ligne de base. |
| ``sourcePath`` | Chaîne | Chemin d&#39;accès absolu au fichier de mappage DITA dans le référentiel AEM. |
| `baselineTitle` | Chaîne | Titre unique de la ligne de base. |
| `versionDate` | Date | La ligne de base est créée à l&#39;aide des versions des rubriques\(directement référencées à partir du plan DITA\) à cette date. Spécifiez la date au format `d-MM-yyyy H:mm`. |

**Renvoie** :
Le nom de la ligne de base, qui est le nom de nœud de la ligne de base dans le référentiel JCR. Le titre de la nouvelle ligne de base s&#39;affiche pour l&#39;utilisateur sur la page Ligne de base du plan DITA.

**Exception** :
Throws ``RepositoryException.``

## Appliquer des libellés

La méthode ``applyLabel`` applique un ou plusieurs libellés aux fichiers d&#39;une ligne de base.

**Syntaxe**:

```JAVA
public static void applyLabel(Session session,
                  String sourcePath,
                  String baselineName,
                  String label)
                  throws RepositoryException, WorkflowException, Exception
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `session` | javax.jcr.Session | Une session JCR valide. |
| `sourcePath` | Chaîne | Chemin d&#39;accès absolu au fichier de mappage DITA dans le référentiel AEM. |
| ``baselineName`` | Chaîne | Nom du nœud de base sur lequel le libellé doit être appliqué. Pour obtenir le nom du nœud de ligne de base, vous pouvez utiliser la méthode [\#id185NFF0085Z](#id185NFF0085Z) ou vérifier le nœud de lignes de base du plan DITA dans CRXDE.<br> **Remarque :** le libellé est appliqué aux versions des fichiers qui sont directement référencées à partir du fichier de mappage dans la ligne de base. |
| `label` | Chaîne | Libellé appliqué aux fichiers de la ligne de base. Assurez-vous que le libellé ne contient pas les caractères suivants : &sol; &comma; &colon; &comma; &lbrack; &comma; &rbrack; &comma; &vert; &comma; &ast; <br> Si vous souhaitez définir plusieurs libellés, séparez les libellés par une virgule ; par exemple, Libellé1, Libellé2. |

**Exception** :
Lance `RepositoryException`.

## Supprimer les libellés

La méthode ``deleteLabel`` supprime un ou plusieurs libellés des fichiers d&#39;une ligne de base.

**Syntaxe**:

```JAVA
public static Map
<String, String> deleteLabel(Session session, 
String sourcePath, 
String baselineName, 
String label) throws GuidesApiException
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `session` | javax.jcr.Session | Une session JCR valide. |
| `sourcePath` | Chaîne | Chemin d&#39;accès absolu au fichier de mappage DITA dans le référentiel AEM. |
| `baselineName` | Chaîne | Nom de la ligne de base dont le libellé doit être supprimé. <br> **Remarque :** libellé est supprimé de la version des fichiers directement référencés à partir du fichier de mappage dans la ligne de base. |
| `label` | Chaîne | Libellé à supprimer des fichiers de la ligne de base. <br> Si vous souhaitez supprimer plusieurs libellés, séparez-les par une virgule ; par exemple, Libellé1, Libellé2. |

**Renvoie** :
Mappage avec paire de `path:deletedlabels` *clé:value* pour tous les fichiers de la ligne de base.

**Exception** :
Lance ``RepositoryException`, `VersionException`, `Exception``.
