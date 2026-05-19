---
title: API Java pour la création et l’activation de packages
description: Découvrez l’API Java pour créer et activer des packages
exl-id: b801c2b3-445f-4aa7-a4f2-029563d7cb3a
feature: Java-Based API Packages
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/g5Mp7tMM9JaAYwNmMyPmaFEcI0fx66vrX8ry97lIUF8
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 618
ht-degree: 1%

---

# API Java pour la création et l’activation de packages {#id175UB30E05Z}

>[!NOTE]
>
> Vous pouvez utiliser les API Java disponibles dans Experience Manager Guides pour créer des modules externes personnalisés et étendre les workflows prêts à l’emploi. Cet article sera archivé en novembre 2024.
> Consultez [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) pour obtenir la documentation la plus récente et détaillée sur l’utilisation de l’API Java.


L’API Java suivante vous permet de créer et d’activer des packages CRX. Cette API est disponible sous la forme d’un lot. Vous devez inclure ce lot dans votre code pour utiliser ces API.

Détails du bundle :

- ID de groupe : **com.adobe.fmdita**

- ID d’artefact : **api**

- Version : **3.3**

- Package : **com.adobe.fmdita.api.crxactivate**

- Détails de la classe :

  ```JAVA
  public class CRXActivator
  ```

  La classe **`CRXActivator`** contient une méthode pour créer des packages CRX et les répliquer sur l’instance de publication.


## Créer et activer des packages

La méthode `activate` crée un package CRX sur l’instance de création et le réplique sur l’instance de publication, si nécessaire. On suppose que les paramètres de réplication AEM ont déjà été configurés sur l’instance de création. Cette méthode crée le package CRX à partir d’une liste de règles fournies en tant que paramètres d’entrée dans une chaîne JSON.
>[!NOTE]
>
> Les erreurs rencontrées lors du processus de création ou d’activation sont écrites dans le `outputstream`.

### Exemple avec deux paramètres

**Syntaxe**:


```JAVA
public static void activate
(
  String json, 
  OutputStream outputstream, 
  Session session
) 
throws GuidesApiException
```

### Exemple avec le troisième paramètre facultatif

```JAVA
public static void activate
(
  String json, 
  OutputStream outputstream,
  String activationTarget, 
  Session session
) 
throws GuidesApiException
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `json` | Chaîne | Chaîne JSON qui détermine le package CRX à créer. Utilisez le format suivant pour créer la chaîne JSON : <br>- `activate` : est de type Booléen \(`true`/`false`\). Détermine si le package CRX créé dans l’instance de création est répliqué sur l’instance de publication. <br> - `rules` : est de type tableau JSON. Tableau de règles JSON traitées de manière séquentielle pour créer le package CRX. <br> - `rootPath` : est de type chaîne. Chemin de base sur lequel les requêtes de nœud/propriété sont exécutées. Si aucune requête de nœud/propriété n’est présente, le chemin d’accès racine et tous les nœuds présents sous le chemin d’accès racine sont inclus dans le package CRX. <br> - `nodeQueries` : est de type Tableau Regex. Tableau d’expressions régulières utilisées pour inclure des fichiers spécifiques sous le chemin d’accès racine. <br> - `propertyQueries` : est de type tableau JSON. Un tableau d’objets JSON avec chaque objet JSON consistant en une requête XPath à exécuter sur le chemin racine et le nom d’une propriété présente dans chaque nœud JCR après l’exécution de la requête. La valeur de la propriété dans chaque nœud JCR doit être un chemin d’accès ou un tableau de chemins d’accès. Les chemins d’accès présents dans cette propriété sont ajoutés au package CRX. |
| `outputstream` | java.io.OutputStream | Il est utilisé pour écrire le résultat de différentes étapes, telles que l’exécution de la requête, l’inclusion de fichiers, la création de packages CRX ou l’activation. Toute erreur rencontrée lors du processus de création ou d’activation est enregistrée dans le `outputstream`. Cela s’avère utile pour le débogage. |
| `session` | Chaîne | Une session JCR valide avec l’autorisation d’activation. |
| `activationTarget` | Chaîne | (*Facultatif*) `preview` ou `publish` pour Cloud Service et `publish` pour les <br> de logiciels On-premise : pour Cloud Service, si le paramètre contient une valeur non valide, l’activation du package échoue. <br> - Pour le logiciel On-Premise, si le paramètre contient une valeur non valide, l’erreur est consignée et la publication est effectuée à l’aide de la valeur par défaut, `publish`. |

**Exception** :

Lance les `java.io.IOException` et les `java.io.IllegalArgumentException`


Si vous ne définissez pas le paramètre facultatif, `activationTarget`, il est activé à l’aide de l’agent de publication par défaut pour les logiciels Cloud Service et On-premise.


**Exemple** :
L’exemple suivant montre comment créer une requête JSON :

```JSON
{
  "activate": true,
  "rules": [
    {
      "rootPath": "/content/dam/nested",
      "nodeQueries": [
        ".*\\.jpg",
        ".*\\.png",
        ".*\\.gif"        
      ]
    },
    {
      "rootPath": "/content/output/sites/hierarchy_ditamap"
    },
    {
      "rootPath": "/content/output/sites/hierarchy_ditamap",
      "propertyQueries": [
        {
          "query": "//*[@fileReference]",
          "property": "fileReference"
        }
      ]
    }
  ]
}
```

L’exemple de requête JSON se compose des règles suivantes :

- Seules les images .png, .jpg et .gif situées sous /content/dam/nested path sont incluses dans le package.
- Tous les nœuds situés sous /content/output/sites/hierarchy\_ditamap sont inclus dans le package.
- Les chemins d’accès présents dans la propriété `fileReference` des nœuds sous /content/output/sites/hierarchy\_ditamap sont inclus dans le package.
