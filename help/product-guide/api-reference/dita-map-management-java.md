---
title: API Java pour travailler avec des mappages DITA
description: En savoir plus sur les API Java à utiliser avec les mappages DITA
exl-id: bd91fc90-75f8-487c-99d1-2637e9cf9924
feature: Java-Based API Dita Map
role: Developer
level: Experienced
source-git-commit: 8c80a4da8e61909aab0f2db81ef97149774b36c4
workflow-type: tm+mt
source-wordcount: '1068'
ht-degree: 3%

---

# API Java pour travailler avec des mappages DITA {#id175UB30E05Z}

>[!NOTE]
>
> Vous pouvez utiliser des API Java disponibles dans Experience Manager Guides pour créer des modules externes personnalisés et étendre les processus prêts à l’emploi. Cet article sera archivé en novembre 2024.
> Affichez [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) pour obtenir la documentation la plus récente et détaillée sur l’utilisation de l’API Java.



Les API Java suivantes vous permettent d’utiliser des mappages DITA dans AEM Guides. Ces API sont disponibles sous la forme d’un lot. Vous devez inclure ce lot dans votre code pour utiliser ces API.

Détails du lot :

- ID de groupe : **com.adobe.fmdita**

- ID d’artefact : **api**

- Version : **3.2**

- Package : **com.adobe.fmdita.api.maps**

- Détails de la classe :

  ```JAVA
  public class MapUtilities extends Object
  ```

  La classe MapUtilities contient des méthodes pour récupérer des informations de métadonnées d’un fichier de mappage DITA.


## Téléchargement du mappage DITA avec des dépendances

La méthode `zipMapWithDependents` crée un fichier .zip contenant un mappage DITA avec toutes ses dépendances telles que les rubriques référencées, les sous-cartes, les images et les DTD. Le fichier .zip pour le mappage DITA est créé en fonction d’une ligne de base donnée.

Il vous permet également de conserver la même structure \(dossiers parents et enfants\) ou de créer une structure de fichiers plate dans un seul dossier pour tous les fichiers dépendants.

>[!IMPORTANT]
>
> L’API renvoie une exception et ne parvient pas à créer un fichier .zip si l’un des fichiers dépendants est manquant.

**Syntaxe**:

```JAVA
public static void zipMapWithDependents(Session session, 
                     String sourcePath, 
                     String baseline, 
                     OutputStream outputStream,
                     boolean flatFS) 
                     throws RepositoryException, IOException
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `session` | javax.jcr.Session | Session JCR valide. |
| `sourcePath` | Chaîne | Chemin \(dans le référentiel AEM\) du fichier de mappage DITA qui doit être téléchargé. |
| `outputStream` | java.io.OutputStream | Flux vers lequel écrire le fichier ZIP. |
| `baseline` | Chaîne | Titre de la ligne de base utilisée pour récupérer le contenu versionné. <br> **Remarque :** La valeur est sensible à la casse. |
| platFS | Booléen | \(Facultatif\) Si la valeur est définie sur true, une structure plate des fichiers est renvoyée dans le fichier ZIP. Par exemple, si votre mappage DITA fait référence au contenu de plusieurs dossiers, tous les fichiers référencés sont extraits dans un seul dossier. S’il existe des fichiers portant le même nom, ces fichiers sont renommés en ajoutant un suffixe numérique. Toutes les références \(dans le mappage DITA et les rubriques\) sont gérées automatiquement, car elles sont mises à jour en fonction du nouvel emplacement des fichiers dans la structure de dossiers plate. S’il est défini sur false, la structure de dossiers est conservée telle quelle dans le fichier ZIP. Si le mappage DITA fait référence à des fichiers provenant de plusieurs emplacements, tous ces emplacements sont également créés dans le fichier ZIP. Lorsque vous restaurez le fichier ZIP, la structure exacte des dossiers est créée à l’emplacement de destination. <br> La valeur par défaut de ce paramètre est false. |

**Renvoie** :
Le contenu du fichier ZIP est écrit sur le `outputStream`.

**Exception** :
Lance ``javax.jcr.RepositoryException``, `java.io.IOException`.

## Télécharger le mappage DITA avec les dépendances \(Asynchrone\)

Vous pouvez également télécharger le mappage DITA avec les dépendances en mode asynchrone. Cette approche est plus utile pour les mappages DITA plus volumineux.

La méthode `zipMapWithDependents` crée un fichier .zip contenant un mappage DITA avec toutes ses dépendances telles que les rubriques référencées, les sous-cartes, les images et les DTD. Le fichier .zip pour le mappage DITA est créé en fonction d’une ligne de base donnée.

Il vous permet également de conserver la même structure \(dossiers parents et enfants\) ou de créer une structure de fichiers plate dans un seul dossier pour tous les fichiers dépendants.

>[!NOTE]
>
> Ce noeud est automatiquement supprimé après un certain temps en fonction de la configuration output.history.purgetime si elle est définie, ou pendant 5 jours par défaut.

**Syntaxe**:

```JAVA
public static CompletableFuture<Node> zipMapWithDependencies(Session session,
                     String sourcePath, 
                     String baseline, 
                     boolean flatFS) 
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `session` | javax.jcr.Session | Session JCR valide. |
| `sourcePath` | Chaîne | Chemin \(dans le référentiel AEM\) du fichier de mappage DITA qui doit être téléchargé. |
| `baseline` | Chaîne | Titre de la ligne de base utilisée pour récupérer le contenu versionné. <br> **Remarque :** La valeur est sensible à la casse. |
| platFS | Booléen | \(Facultatif\) Si la valeur est définie sur true, une structure plate des fichiers est renvoyée dans le fichier ZIP. Par exemple, si votre mappage DITA fait référence au contenu de plusieurs dossiers, tous les fichiers référencés sont extraits dans un seul dossier. S’il existe des fichiers portant le même nom, ces fichiers sont renommés en ajoutant un suffixe numérique. Toutes les références \(dans le mappage DITA et les rubriques\) sont gérées automatiquement, car elles sont mises à jour en fonction du nouvel emplacement des fichiers dans la structure de dossiers plate. S’il est défini sur false, la structure de dossiers est conservée telle quelle dans le fichier ZIP. Si le mappage DITA fait référence à des fichiers provenant de plusieurs emplacements, tous ces emplacements sont également créés dans le fichier ZIP. Lorsque vous restaurez le fichier ZIP, la structure exacte des dossiers est créée à l’emplacement de destination.<br> La valeur par défaut de ce paramètre est false. |

**Renvoie** :
Le noeud du fichier zip est encapsulé dans la classe `CompletableFuture`. L’utilisateur peut continuer à le gérer de manière asynchrone et utiliser la méthode `.get()`future pour bloquer le thread lorsque le noeud est nécessaire. La valeur renvoyée peut également se terminer par une erreur et elle peut être traitée avec la méthode `.exceptionally()`.

## Obtention d’une liste des lignes de base

La méthode ``getBaselineList`` récupère une liste de toutes les lignes de base qui existent pour un mappage DITA donné.

**Syntaxe**:

```JAVA
public static List<HashMap<String,String>> getBaselineList( 
                  javax.jcr.Session session, 
                  String sourcePath)
                  throws javax.jcr.RepositoryException
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `session` | javax.jcr.Session | Session JCR valide. |
| `sourcePath` | Chaîne | Chemin \(dans le référentiel AEM\) du fichier de mappage DITA pour lequel les informations de base doivent être récupérées. |

**Renvoie** :
Liste d’objets `HashMap`. Chaque objet `HashMap` représente une ligne de base et contient le nom et le titre de la ligne de base.

**Exception** :
Lance ``javax.jcr.RepositoryException``.

## Obtenir la liste des paramètres prédéfinis conditionnels

La méthode ``getConditionalPresetList`` récupère une liste de tous les paramètres prédéfinis conditionnels qui existent pour un mappage DITA donné.

**Syntaxe**:

```JAVA
public static List<HashMap<String,String>> getConditionalPresetList (
                  javax.jcr.Session session,
                  String sourcePath)
                  throws javax.jcr.RepositoryException
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `session` | javax.jcr.Session | Session JCR valide. |
| `sourcePath` | Chaîne | Chemin \(dans le référentiel AEM\) du fichier de mappage DITA pour lequel les informations de paramètre prédéfini conditionnel doivent être récupérées. |

**Renvoie** :
Liste d’objets `HashMap`. Chaque objet `HashMap` représente un paramètre prédéfini conditionnel et contient le nom et le titre du paramètre prédéfini conditionnel.

**Exception** :
Lance ``javax.jcr.RepositoryException``.

## Obtention des informations du fichier DITAVAL pour un paramètre prédéfini conditionnel

La méthode ``getDitavalFromConditionalPreset`` récupère le chemin d’accès du fichier DITAVAL correspondant à un paramètre prédéfini conditionnel pour un mappage DITA donné.

**Syntaxe**:

```JAVA
public static String getDitavalFromConditionalPreset
    (Session session,
    String sourcePath, 
    String cpName) throws RepositoryException
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `session` | javax.jcr.Session | Session JCR valide. |
| `sourcePath` | Chaîne | Chemin \(dans le référentiel AEM\) du fichier de mappage DITA pour lequel le fichier DITAVAL doit être récupéré. |
| `cpName` | Chaîne | Nom du paramètre prédéfini conditionnel dans le mappage DITA pour lequel le fichier DITAVAL doit être récupéré. |

**Renvoie** :
Chemin d’accès du fichier DITAVAL correspondant au paramètre prédéfini conditionnel défini dans le fichier de mappage DITA.

## Obtention de toutes les dépendances d’un noeud

La méthode ``getAllDependencies`` renvoie toutes les dépendances d’un noeud donné.

**Syntaxe**:

```JAVA
public static List
<Node> getAllDependencies 
(Node rootNode) throws GuidesApiException
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `rootNode` | javax.jcr.Node | Noeud racine pour lequel toutes les dépendances doivent être récupérées. |

**Renvoie** :
Liste de noeuds contenant toutes les dépendances du noeud racine.
