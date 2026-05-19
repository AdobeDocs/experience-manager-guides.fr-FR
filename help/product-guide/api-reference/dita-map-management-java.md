---
title: API Java pour utiliser les plans DITA
description: En savoir plus sur les API Java pour utiliser les plans DITA
exl-id: bd91fc90-75f8-487c-99d1-2637e9cf9924
feature: Java-Based API Dita Map
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/XDVopMV3mqDipQ1P3FgfJPquykDrl1trrZYd2S-KLpw
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 1096
ht-degree: 3%

---

# API Java pour utiliser les plans DITA {#id175UB30E05Z}

>[!NOTE]
>
> Vous pouvez utiliser les API Java disponibles dans Experience Manager Guides pour créer des modules externes personnalisés et étendre les workflows prêts à l’emploi. Cet article sera archivé en novembre 2024.
> Consultez [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) pour obtenir la documentation la plus récente et détaillée sur l’utilisation de l’API Java.



Les API Java suivantes vous permettent d&#39;utiliser des plans DITA dans AEM Guides. Ces API sont disponibles sous la forme d’un lot. Vous devez inclure ce lot dans votre code pour utiliser ces API.

Détails du bundle :

- ID de groupe : **com.adobe.fmdita**

- ID d’artefact : **api**

- Version : **3.2**

- Package : **com.adobe.fmdita.api.maps**

- Détails de la classe :

  ```JAVA
  public class MapUtilities extends Object
  ```

  La classe MapUtilities contient des méthodes permettant de récupérer des informations de métadonnées à partir d&#39;un fichier de mappage DITA.


## Télécharger le plan DITA avec les personnes à charge

La méthode `zipMapWithDependents` crée un fichier .zip contenant un plan DITA avec toutes ses dépendances telles que les rubriques référencées, les sous-plans, les images et les DTD. Le fichier .zip du plan DITA est créé en fonction d&#39;une ligne de base donnée.

Il vous permet également de conserver la même structure \(dossiers parents et enfants\) ou de créer une structure de fichiers plats dans un seul dossier pour tous les fichiers dépendants.

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
| `session` | javax.jcr.Session | Une session JCR valide. |
| `sourcePath` | Chaîne | Chemin \(dans le référentiel AEM\) du fichier de mappage DITA à télécharger. |
| `outputStream` | java.io.OutputStream | Flux vers lequel écrire le fichier ZIP. |
| `baseline` | Chaîne | Titre de la ligne de base utilisée pour récupérer le contenu avec version. <br> **Remarque :** la valeur respecte la casse. |
| flatFS | Booléen | \(Facultatif\) Si cet attribut est défini sur true, une structure plate de fichiers est renvoyée dans le fichier ZIP. Par exemple, si votre plan DITA fait référence à du contenu situé dans plusieurs dossiers, tous les fichiers référencés sont extraits dans un seul dossier. Si des fichiers portent le même nom, ils sont renommés en ajoutant un suffixe numérique. Toutes les références \(dans plan DITA et rubriques\) sont gérées automatiquement, car elles sont mises à jour en fonction du nouvel emplacement des fichiers dans la structure de dossiers plate. Si cette valeur est définie sur false, la structure de dossiers est conservée telle quelle dans le fichier ZIP. Si le plan DITA fait référence à des fichiers provenant de plusieurs emplacements, tous ces emplacements sont également créés dans le fichier ZIP. Lorsque vous restaurez le fichier ZIP, la structure de dossiers exacte est créée à l’emplacement de destination. <br> La valeur par défaut de ce paramètre est false. |

**Renvoie** :
Le contenu du fichier ZIP est écrit dans le `outputStream`.

**Exception** :
Lance ``javax.jcr.RepositoryException``, `java.io.IOException`.

## Télécharger le plan DITA avec les dépendances \(de manière asynchrone\)

Vous pouvez également télécharger un plan DITA avec des dépendances en mode asynchrone. Cette approche est plus utile pour les plans DITA de plus grande taille.

La méthode `zipMapWithDependents` crée un fichier .zip contenant un plan DITA avec toutes ses dépendances telles que les rubriques référencées, les sous-plans, les images et les DTD. Le fichier .zip du plan DITA est créé en fonction d&#39;une ligne de base donnée.

Il vous permet également de conserver la même structure \(dossiers parents et enfants\) ou de créer une structure de fichiers plats dans un seul dossier pour tous les fichiers dépendants.

>[!NOTE]
>
> Ce nœud est automatiquement supprimé après un certain temps en fonction de la configuration output.history.purgetime, si elle est définie, ou 5 jours par défaut.

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
| `session` | javax.jcr.Session | Une session JCR valide. |
| `sourcePath` | Chaîne | Chemin \(dans le référentiel AEM\) du fichier de mappage DITA à télécharger. |
| `baseline` | Chaîne | Titre de la ligne de base utilisée pour récupérer le contenu avec version. <br> **Remarque :** la valeur respecte la casse. |
| flatFS | Booléen | \(Facultatif\) Si cet attribut est défini sur true, une structure plate de fichiers est renvoyée dans le fichier ZIP. Par exemple, si votre plan DITA fait référence à du contenu situé dans plusieurs dossiers, tous les fichiers référencés sont extraits dans un seul dossier. Si des fichiers portent le même nom, ils sont renommés en ajoutant un suffixe numérique. Toutes les références \(dans plan DITA et rubriques\) sont gérées automatiquement, car elles sont mises à jour en fonction du nouvel emplacement des fichiers dans la structure de dossiers plate. Si cette valeur est définie sur false, la structure de dossiers est conservée telle quelle dans le fichier ZIP. Si le plan DITA fait référence à des fichiers provenant de plusieurs emplacements, tous ces emplacements sont également créés dans le fichier ZIP. Lorsque vous restaurez le fichier ZIP, la structure de dossiers exacte est créée à l’emplacement de destination.<br> La valeur par défaut de ce paramètre est false. |

**Renvoie** :
Le nœud du fichier zip est encapsulé dans la classe `CompletableFuture`. L’utilisateur peut continuer à le gérer de manière asynchrone et peut utiliser la méthode `.get()` du futur pour bloquer le thread lorsque le nœud est nécessaire. La valeur renvoyée peut également se terminer par une erreur, qui peut être traitée par `.exceptionally()` méthode .

## Obtention d’une liste de lignes de base

La méthode ``getBaselineList`` récupère une liste de toutes les lignes de base qui existent pour un plan DITA donné.

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
| `session` | javax.jcr.Session | Une session JCR valide. |
| `sourcePath` | Chaîne | Chemin \(dans le référentiel AEM\) du fichier de mappage DITA pour lequel les informations de base doivent être récupérées. |

**Renvoie** :
Liste d’objets `HashMap`. Chaque objet `HashMap` représente une ligne de base et contient son nom et son titre.

**Exception** :
Lance ``javax.jcr.RepositoryException``.

## Obtention d’une liste de paramètres prédéfinis conditionnels

La méthode ``getConditionalPresetList`` récupère une liste de tous les paramètres prédéfinis conditionnels qui existent pour un plan DITA donné.

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
| `session` | javax.jcr.Session | Une session JCR valide. |
| `sourcePath` | Chaîne | Chemin \(dans le référentiel AEM\) du fichier de mappage DITA pour lequel les informations de paramètre prédéfini conditionnel doivent être récupérées. |

**Renvoie** :
Liste d’objets `HashMap`. Chaque objet `HashMap` représente un paramètre prédéfini conditionnel et contient le nom et le titre du paramètre prédéfini conditionnel.

**Exception** :
Lance ``javax.jcr.RepositoryException``.

## Obtention des informations du fichier DITAVAL pour un préréglage conditionnel

La méthode ``getDitavalFromConditionalPreset`` récupère le chemin d&#39;accès du fichier DITAVAL correspondant à un paramètre prédéfini conditionnel pour un plan DITA donné.

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
| `session` | javax.jcr.Session | Une session JCR valide. |
| `sourcePath` | Chaîne | Chemin \(dans le référentiel AEM\) du fichier de mappage DITA pour lequel le fichier DITAVAL doit être récupéré. |
| `cpName` | Chaîne | Nom du paramètre prédéfini conditionnel dans le plan DITA pour lequel le fichier DITAVAL doit être récupéré. |

**Renvoie** :
Chemin d&#39;accès au fichier DITAVAL correspondant au paramètre prédéfini conditionnel défini dans le fichier de mappage DITA.

## Obtention de toutes les dépendances pour un nœud

La méthode ``getAllDependencies`` renvoie toutes les dépendances d’un nœud donné.

**Syntaxe**:

```JAVA
public static List
<Node> getAllDependencies 
(Node rootNode) throws GuidesApiException
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `rootNode` | javax.jcr.Node | Nœud racine pour lequel toutes les dépendances doivent être récupérées. |

**Renvoie** :
Liste de nœuds contenant toutes les dépendances du nœud racine.
