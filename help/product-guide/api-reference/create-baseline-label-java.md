---
title: API Java à utiliser avec les lignes de base et les libellés
description: Découvrez les API Java à utiliser avec les lignes de base et les libellés
exl-id: 0e2ba1bb-f5bf-44da-848a-a55385460c83
feature: Java-Based API Baseline
role: Developer
level: Experienced
source-git-commit: 8c80a4da8e61909aab0f2db81ef97149774b36c4
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 2%

---

# API Java à utiliser avec les lignes de base et les libellés {#id175UB30E05Z}

>[!NOTE]
>
> Vous pouvez utiliser des API Java disponibles dans Experience Manager Guides pour créer des modules externes personnalisés et étendre les processus prêts à l’emploi. Cet article sera archivé en novembre 2024.
> Affichez [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) pour obtenir la documentation la plus récente et détaillée sur l’utilisation de l’API Java.


Les API Java suivantes vous permettent de créer une ligne de base et d’ajouter des libellés aux fichiers d’une ligne de base. Ces API sont disponibles sous la forme d’un lot. Vous devez inclure ce lot dans votre code pour utiliser ces API.

Détails du lot :

- ID de groupe : **com.adobe.fmdita**

- ID d’artefact : **api**

- Version : **3.5**

- Package : **com.adobe.fmdita.api.baselines**

- Détails de la classe :

  ```JAVA
  public class BaselineUtils extends Object
  ```

  La classe **BaselineUtils** contient des méthodes pour créer des lignes de base et appliquer des étiquettes aux fichiers d’une ligne de base.


## Création d’une ligne de base

La méthode de création de ligne de base comporte deux versions : une pour la solution XML Documentation version 3.5 et une autre pour les versions antérieures à la version 3.5 \(qui inclut les versions 3.4, 3.3 et 3.2\). L’API version 3.5 permet la création d’une ligne de base à l’aide d’un libellé, de références directes et de références indirectes dans un fichier map.

L’autre version de l’API utilise la date et l’heure pour créer une ligne de base. Cette API est conservée à des fins de rétrocompatibilité avec les systèmes utilisant la solution XML Documentation 3.4, 3.3 ou 3.2.

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
| `session` | javax.jcr.Session | Session JCR valide. La session utilisateur doit disposer d’autorisations de lecture et d’écriture pour le mappage DITA et d’autorisations de lecture pour tous les fichiers de référence inclus dans la ligne de base. |
| `sourcePath` | Chaîne | Chemin d’accès absolu au fichier de mappage DITA dans AEM référentiel. |
| `baselineTitle` | Chaîne | Titre unique de la ligne de base. |
| `label` | Chaîne | Sélectionnez la version d’une rubrique à laquelle est appliqué le libellé donné. |
| `directContext` | LinkedHashMap&lt;String, Object\> | Les configurations sur la base desquelles la rubrique \(contenu\) directement référencée est sélectionnée, l’ordre mentionné dans la carte est suivi pour résoudre une version. <br> Si, après une itération sur toutes les clés de la carte, aucune version n’est trouvée, le processus de création de ligne de base échoue. <br> Si HashMap est vide \(envoyez une carte vide et non nulle pour la valeur par défaut\), par défaut, elle est renseignée comme suit : <br>`directContext.put("label", label);` <br> `directContext.put("latest", true);` <br> Si vous souhaitez que la création de la ligne de base ne sélectionne que la version d’une étiquette donnée et échoue en l’absence d’une telle version, placez la clé `label` et le libellé sur lequel vous souhaitez créer la ligne de base. |
| `indirectContext` | LinkedHashMap&lt;String, Object\> | Les configurations sur la base desquelles la rubrique référencée indirectement \(contenu référencé\) est sélectionnée, l’ordre mentionné dans la carte est suivi pour résoudre une version. <br> Si, après une itération sur toutes les clés de la carte, aucune version n’est trouvée, le processus de création de ligne de base échoue. <br> Si HashMap est vide \(envoyez un mappage vide et non nul par défaut\), il est renseigné par défaut comme suit : <br>`indirectContext.put("label", label);` <br>`indirectContext.put "pickAutomatically", null);` <br> Si vous souhaitez qu’il s’agisse de la dernière version au lieu de récupérer automatiquement une version, puis remplacez : <br>`indirectContext.put("pickAutomatically", null);` <br> _avec :_ <br>`indirectContext.put("latest", true)` |

**Renvoie** :
Nom de la ligne de base, qui est le nom de noeud de la ligne de base dans le référentiel JCR. Le titre de la ligne de base nouvellement créée s’affiche pour l’utilisateur sur la page Ligne de base pour le mappage DITA.

**Exception** :
Renvoie ``ItemExistExceptiom`` s’il existe déjà une ligne de base portant le même titre.

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
| `session` | javax.jcr.Session | Session JCR valide. La session utilisateur doit disposer d’autorisations de lecture et d’écriture pour le mappage DITA et d’autorisations de lecture pour tous les fichiers de référence inclus dans la ligne de base. |
| ``sourcePath`` | Chaîne | Chemin d’accès absolu au fichier de mappage DITA dans AEM référentiel. |
| `baselineTitle` | Chaîne | Titre unique de la ligne de base. |
| `versionDate` | Date | La ligne de base est créée à l’aide des versions des rubriques\ (directement référencées à partir du mappage DITA\) telles que à cette date. Spécifiez la date au format `d-MM-yyyy H:mm`. |

**Renvoie** :
Nom de la ligne de base, qui est le nom de noeud de la ligne de base dans le référentiel JCR. Le titre de la ligne de base nouvellement créée s’affiche pour l’utilisateur sur la page Ligne de base pour le mappage DITA.

**Exception** :
Throws ``RepositoryException.``

## Application de libellés

La méthode ``applyLabel`` applique une ou plusieurs étiquettes aux fichiers d’une ligne de base.

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
| `session` | javax.jcr.Session | Session JCR valide. |
| `sourcePath` | Chaîne | Chemin d’accès absolu au fichier de mappage DITA dans AEM référentiel. |
| ``baselineName`` | Chaîne | Nom du noeud de ligne de base sur lequel le libellé doit être appliqué. Pour obtenir le nom du noeud de ligne de base, vous pouvez utiliser la méthode [\#id185NFF0085Z](#id185NFF0085Z) ou vérifier le noeud de lignes de base du mappage DITA dans CRXDE.<br> **Remarque :** Le libellé est appliqué à la version des fichiers directement référencés à partir du fichier map dans la ligne de base. |
| `label` | Chaîne | Libellé appliqué aux fichiers de la ligne de base. Assurez-vous que le libellé ne contient pas les caractères suivants : &amp;sol; &amp;virgua; &amp;deux; &amp;virgule; &amp;loc; &amp;virgule; &amp;joker; &amp;virgule; &amp;virgule; &amp;vert; &amp;virgule; &amp;ast; <br> Si vous souhaitez définir plusieurs libellés, séparez-les par une virgule, par exemple, Libellé2. |

**Exception** :
Lance `RepositoryException`.

## Supprimer des étiquettes

La méthode ``deleteLabel`` supprime une ou plusieurs étiquettes des fichiers d’une ligne de base.

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
| `session` | javax.jcr.Session | Session JCR valide. |
| `sourcePath` | Chaîne | Chemin d’accès absolu au fichier de mappage DITA dans AEM référentiel. |
| `baselineName` | Chaîne | Nom de la ligne de base à partir de laquelle le libellé doit être supprimé. <br> **Remarque :** Le libellé est supprimé de la version des fichiers qui sont directement référencés à partir du fichier map dans la ligne de base. |
| `label` | Chaîne | Libellé à supprimer des fichiers de la ligne de base. <br> Si vous souhaitez supprimer plusieurs étiquettes, séparez-les par une virgule ; par exemple, Libellé1, Libellé2. |

**Renvoie** :
La carte avec la paire *key:value* de `path:deletedlabels` pour tous les fichiers de la ligne de base.

**Exception** :
Lance ``RepositoryException`, `VersionException`, `Exception``.
