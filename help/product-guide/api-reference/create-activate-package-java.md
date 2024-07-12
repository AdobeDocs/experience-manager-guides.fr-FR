---
title: API Java pour la création et l’activation de packages
description: En savoir plus sur l’API Java pour la création et l’activation de packages
exl-id: b801c2b3-445f-4aa7-a4f2-029563d7cb3a
feature: Java-Based API Packages
role: Developer
level: Experienced
source-git-commit: 4ce78061ddb193d3c16241ff32fa87060c9c7bd6
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 0%

---

# API Java pour la création et l’activation de packages {#id175UB30E05Z}

L’API Java suivante vous permet de créer et d’activer des modules CRX. Cette API est disponible sous la forme d’un lot. Vous devez inclure ce lot dans votre code pour utiliser ces API.

Détails du lot :

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

La méthode `activate` crée un package CRX sur l’instance d’auteur et le réplique sur l’instance de publication, si nécessaire. On suppose que les paramètres de réplication AEM ont déjà été configurés sur l’instance de création. Cette méthode crée le package CRX à partir d’une liste de règles fournies en tant que paramètres d’entrée dans une chaîne JSON.
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

### Exemple avec troisième paramètre facultatif

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
|Nom|Type|Description|
|—|—|—|
|`json`|Chaîne|JSON qui détermine le package CRX à créer. Utilisez le format suivant pour créer la chaîne JSON : <br>- `activate` : est de type booléen \(`true`/`false`\). Détermine si le package CRX créé dans l’instance d’auteur est répliqué vers l’instance de publication. <br> - `rules` : est de type JSON Array. Tableau de règles JSON, qui sont traitées de manière séquentielle pour créer le module CRX. <br> - `rootPath` : est de type Chaîne. Chemin d’accès de base sur lequel les requêtes de noeud/propriété sont exécutées. Si aucune requête de noeud/propriété n’est présente, le chemin d’accès racine et tous les noeuds présents sous le chemin d’accès racine sont inclus dans le package CRX. <br> - `nodeQueries` : est de type Regex Array. Tableau d’expressions régulières utilisées pour inclure des fichiers spécifiques sous le chemin racine. <br> - `propertyQueries` : est de type JSON Array. Tableau d’objets JSON comportant chaque objet JSON constitué d’une requête XPath à exécuter sur le chemin racine et le nom d’une propriété présente dans chaque noeud JCR après l’exécution de la requête. La valeur de la propriété dans chaque noeud JCR doit être un chemin d’accès ou un tableau de chemins d’accès. Les chemins d’accès présents dans cette propriété sont ajoutés au package CRX.|
|`outputstream`|java.io.OutputStream|Il est utilisé pour écrire le résultat de diverses étapes, telles que l’exécution de requêtes, l’inclusion de fichiers, la création de packages CRX ou l’activation. Toute erreur rencontrée lors de la création ou du processus d&#39;activation est écrite dans le `outputstream`. Cela s’avère utile pour le débogage.|
|`session`|String|Une session JCR valide avec autorisation d’activation.|
|`activationTarget`|Chaîne|(*Facultatif*) `preview` ou `publish` pour Cloud Service et `publish` pour le logiciel On-premise <br> - Pour Cloud Service, si le paramètre contient une valeur non valide, l’activation du module échoue. <br> - Pour le logiciel On-Premise, si le paramètre contient une valeur non valide, l’erreur est consignée et la publication est effectuée à l’aide de la valeur par défaut, `publish`. |

**Exception** :

Throws `java.io.IOException` et `java.io.IllegalArgumentException`


Si vous ne définissez pas le paramètre facultatif, `activationTarget`, il s’active à l’aide de l’agent de publication par défaut pour les logiciels de Cloud Service et On-premise.


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

- Seules les images .png, .jpg et .gif sous /content/dam/nested path sont incluses dans le package.
- Tous les noeuds situés sous /content/output/sites/hierarchy\_ditamap sont inclus dans le package.
- Les chemins d’accès présents dans la propriété `fileReference` des noeuds sous /content/output/sites/hierarchy\_ditamap sont inclus dans le package.
