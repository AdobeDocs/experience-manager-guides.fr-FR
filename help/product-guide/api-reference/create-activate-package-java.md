---
title: API Java pour la création et l’activation de packages
description: En savoir plus sur l’API Java pour la création et l’activation de packages
exl-id: b801c2b3-445f-4aa7-a4f2-029563d7cb3a
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 0%

---

# API Java pour la création et l’activation de packages {#id175UB30E05Z}

L’API Java suivante vous permet de créer et d’activer des packages CRX. Cette API est disponible sous la forme d’un lot. Vous devez inclure ce lot dans votre code pour utiliser ces API.

Détails du lot :

- ID de groupe : **com.adobe.fmdita**

- ID d’artefact : **api**

- Version : **3,3**

- Package : **com.adobe.fmdita.api.crxactivate**

- Détails de la classe :

  ```JAVA
  public class CRXActivator
  ```

  La variable **`CRXActivator`** contient une méthode pour créer des modules CRX et les répliquer sur l’instance de publication.


## Créer et activer des packages

La variable `activate` crée un package CRX sur l’instance d’auteur et le réplique sur l’instance de publication, si nécessaire. On suppose que les paramètres de réplication AEM ont déjà été configurés sur l’instance de création. Cette méthode crée le package CRX à partir d’une liste de règles fournies en tant que paramètres d’entrée dans une chaîne JSON.
>[!NOTE]
>
> Les erreurs rencontrées lors du processus de création ou d’activation sont écrites dans la variable `outputstream`.

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

**Paramètres**: |Nom|Type|Description| |—|—|—| |`json`|Chaîne|Chaîne JSON qui détermine le package CRX à créer. Utilisez le format suivant pour créer la chaîne JSON : <br>- `activate`: est de type Booléen \(`true`/`false`\). Détermine si le package CRX créé dans l’instance de création est répliqué vers l’instance de publication. <br> - `rules`: est de type JSON Array. Tableau de règles JSON qui sont traitées de manière séquentielle pour créer le package CRX. <br> - `rootPath`: est de type Chaîne. Chemin d’accès de base sur lequel les requêtes de noeud/propriété sont exécutées. Si aucune requête de noeud/propriété n’est présente, le chemin d’accès racine et tous les noeuds présents sous le chemin d’accès racine sont inclus dans le package CRX. <br> - `nodeQueries`: est de type Regex Array. Tableau d’expressions régulières utilisées pour inclure des fichiers spécifiques sous le chemin racine. <br> - `propertyQueries`: est de type JSON Array. Tableau d’objets JSON comportant chaque objet JSON constitué d’une requête XPath à exécuter sur le chemin racine et le nom d’une propriété présente dans chaque noeud JCR après l’exécution de la requête. La valeur de la propriété dans chaque noeud JCR doit être un chemin d’accès ou un tableau de chemins d’accès. Les chemins d’accès présents dans cette propriété sont ajoutés au package CRX.| |`outputstream`|java.io.OutputStream|Permet d’écrire le résultat de différentes étapes, telles que l’exécution de requêtes, l’inclusion de fichiers, la création de packages CRX ou l’activation. Toute erreur rencontrée lors de la création ou du processus d’activation est écrite dans la variable `outputstream`. Cela s’avère utile pour le débogage.| |`session`|Chaîne|Une session JCR valide avec autorisation d’activation.|

**Exception**: renvoie ``java.io.IOException``.

**Exemple**: l’exemple suivant montre comment créer une requête JSON :

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
- Les chemins d’accès présents dans la variable `fileReference` La propriété des noeuds sous /content/output/sites/hierarchy\_ditamap est incluse dans le package.
