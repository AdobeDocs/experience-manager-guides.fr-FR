---
title: API Java à utiliser avec les lignes de base et les libellés
description: Découvrez les API Java à utiliser avec les lignes de base et les libellés
exl-id: 0e2ba1bb-f5bf-44da-848a-a55385460c83
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 0%

---

# API Java à utiliser avec les lignes de base et les libellés {#id175UB30E05Z}

Les API Java suivantes vous permettent de créer une ligne de base et d’ajouter des libellés aux fichiers d’une ligne de base. Ces API sont disponibles sous la forme d’un lot. Vous devez inclure ce lot dans votre code pour utiliser ces API.

Détails du lot :

- ID de groupe : **com.adobe.fmdita**

- ID d’artefact : **api**

- Version : **3,5**

- Package : **com.adobe.fmdita.api.baselines**

- Détails de la classe :

  ```JAVA
  public class BaselineUtils extends Object
  ```

  La variable **BaselineUtils** contient des méthodes pour créer des lignes de base et appliquer des libellés aux fichiers d’une ligne de base.


## Création d’une ligne de base

La méthode de création de ligne de base comporte deux versions : une pour la solution XML Documentation version 3.5 et une autre pour les versions antérieures à la version 3.5 \(qui inclut les versions 3.4, 3.3 et 3.2\). L’API version 3.5 permet la création d’une ligne de base à l’aide d’un libellé, de références directes et de références indirectes dans un fichier map.

L’autre version de l’API utilise la date et l’heure pour créer une ligne de base. Cette API est conservée à des fins de rétrocompatibilité avec les systèmes utilisant la solution XML Documentation 3.4, 3.3 ou 3.2.

**Syntaxe \(pour la version 3.5\)**:

```JAVA
public static String createBaseline(Session session, 
String sourcePath, 
String baselineTitle, 
String label, 
LinkedHashMap directContext, 
LinkedHashMap indirectContext) 
throws GuidesApiException
```

**Paramètres**: |Nom|Type|Description| |—|—|—| |`session`|javax.jcr.Session|Une session JCR valide. La session utilisateur doit disposer d’autorisations de lecture et d’écriture pour le mappage DITA et d’autorisations de lecture pour tous les fichiers de référence inclus dans la ligne de base.| |`sourcePath`|Chaîne|Chemin absolu du fichier de mappage DITA dans AEM référentiel.| |`baselineTitle`|Chaîne|Titre unique de la ligne de base.| |`label`|Chaîne|Sélectionnez la version d’une rubrique pour laquelle le libellé indiqué est appliqué.| |`directContext`|LinkedHashMap&lt;string object=&quot;&quot;>|Les configurations sur la base desquelles la rubrique référencée directement \(content\) est sélectionnée, l’ordre mentionné dans la carte est suivi pour résoudre une version. <br> Si, après une itération sur toutes les clés du mappage, aucune version n’est trouvée, le processus de création de ligne de base échoue. <br> Si HashMap est vide \(envoyez une carte vide et non nulle pour la valeur par défaut\), elle est renseignée par défaut comme suit : <br>`directContext.put("label", label);` <br> `directContext.put("latest", true);` <br> Si vous souhaitez que la création de la ligne de base ne sélectionne que la version d’un libellé donné et échoue si cette version n’existe pas, placez la variable `label` et le libellé sur lequel vous souhaitez créer la ligne de base.| |`indirectContext`|LinkedHashMap&lt;string object=&quot;&quot;>|Les configurations sur la base desquelles la rubrique référencée indirectement \(contenu référencé\) est sélectionnée, l’ordre mentionné dans la carte est suivi pour résoudre une version. <br> Si, après une itération sur toutes les clés du mappage, aucune version n’est trouvée, le processus de création de ligne de base échoue. <br> Si HashMap est vide \(envoyez une carte vide et non nulle pour la carte par défaut\), par défaut, elle est renseignée comme suit : <br>`indirectContext.put("label", label);` <br>`indirectContext.put "pickAutomatically", null);` <br> Si vous souhaitez qu’il s’agisse de la dernière version au lieu de récupérer automatiquement une version, remplacez : <br>`indirectContext.put("pickAutomatically", null);` <br> _par :_ <br>`indirectContext.put("latest", true)`|

**Renvoie**: nom de la ligne de base, qui est le nom de noeud de la ligne de base dans le référentiel JCR. Le titre de la ligne de base nouvellement créée s’affiche pour l’utilisateur sur la page Ligne de base pour le mappage DITA.

**Exception**: renvoie ``ItemExistExceptiom`` s’il existe déjà une ligne de base portant le même titre.

**Syntaxe \(pour les versions 3.4, 3.3 et 3.2\)**

```JAVA
public static String createBaseline
(Session session, 
String sourcePath, 
String baselineTitle, 
Date versionDate) throws GuidesApiException
```

**Paramètres**: |Nom|Type|Description| |—|—|—| |`session`|javax.jcr.Session|Une session JCR valide. La session utilisateur doit disposer d’autorisations de lecture et d’écriture pour le mappage DITA et d’autorisations de lecture pour tous les fichiers de référence inclus dans la ligne de base.| |``sourcePath``|Chaîne|Chemin absolu du fichier de mappage DITA dans AEM référentiel.| |`baselineTitle`|Chaîne|Titre unique de la ligne de base.| |`versionDate`|Date|La ligne de base est créée à l’aide des versions des rubriques\ (directement référencée à partir du mappage DITA\) telles que à cette date. Indiquez la date indiquée dans `d-MM-yyyy H:mm` format.|

**Renvoie**: nom de la ligne de base, qui est le nom de noeud de la ligne de base dans le référentiel JCR. Le titre de la ligne de base nouvellement créée s’affiche pour l’utilisateur sur la page Ligne de base pour le mappage DITA.

**Exception**: renvoie ``RepositoryException.``

## Application de libellés

La variable ``applyLabel`` applique une ou plusieurs étiquettes aux fichiers d’une ligne de base.

**Syntaxe**:

```JAVA
public static void applyLabel(Session session,
                  String sourcePath,
                  String baselineName,
                  String label)
                  throws RepositoryException, WorkflowException, Exception
```

**Paramètres**: |Nom|Type|Description| |—|—|—| |`session`|javax.jcr.Session|Une session JCR valide.| |`sourcePath`|Chaîne|Chemin absolu du fichier de mappage DITA dans AEM référentiel.| |``baselineName``|Chaîne|Nom du noeud de ligne de base sur lequel le libellé doit être appliqué. Pour obtenir le nom du noeud de ligne de base, vous pouvez utiliser la variable [\#id185NFF0085Z](#id185NFF0085Z) ou vérifiez le noeud des lignes de base du mappage DITA dans CRXDE.<br> **Remarque :** Le libellé est appliqué à la version des fichiers qui sont directement référencés à partir du fichier map dans la ligne de base.| |`label`|Chaîne|Libellé appliqué aux fichiers de la ligne de base. Assurez-vous que le libellé ne contient pas les caractères suivants : &amp;sol; &amp;virgule; &amp;deux-points; &amp;virgule; &amp;lbrack; &amp;virgule; &amp;brack; &amp;virgule; &amp;vert; &amp;virgule; &amp;ast; <br> Si vous souhaitez définir plusieurs étiquettes, séparez-les par une virgule ; par exemple, Libellé1, Libellé2.|

**Exception**: renvoie `RepositoryException`.

## Supprimer des étiquettes

La variable ``deleteLabel`` supprime une ou plusieurs étiquettes des fichiers d’une ligne de base.

**Syntaxe**:

```JAVA
public static Map
<String, String> deleteLabel(Session session, 
String sourcePath, 
String baselineName, 
String label) throws GuidesApiException
```

**Paramètres**: |Nom|Type|Description| |—|—|—| |`session`|javax.jcr.Session|Une session JCR valide.| |`sourcePath`|Chaîne|Chemin absolu du fichier de mappage DITA dans AEM référentiel.| |`baselineName`|Chaîne|Nom de la ligne de base à partir de laquelle le libellé doit être supprimé. <br> **Remarque :** Le libellé est supprimé de la version des fichiers qui sont directement référencés à partir du fichier map dans la ligne de base.| |`label`|Chaîne|Une étiquette à supprimer des fichiers de la ligne de base. <br> Si vous souhaitez supprimer plusieurs étiquettes, séparez-les par une virgule ; par exemple, Libellé1, Libellé2.|

**Renvoie**: la carte avec *key:value* paire de `path:deletedlabels` pour tous les fichiers de la ligne de base.

**Exception**: renvoie ``RepositoryException`, `VersionException`, `Exception``.
