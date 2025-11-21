---
title: API REST pour la gestion des sorties
description: En savoir plus sur les API REST pour la gestion des sorties
exl-id: dab654f5-555d-4a89-bc94-55b1e938f255
feature: Rest API Output Management
role: Developer
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1175'
ht-degree: 6%

---

# API REST pour la gestion des sorties {#id175UB30E05Z}

Les API REST suivantes sont disponibles pour gérer les sorties dans AEM Guides.

## Obtention de tous les paramètres prédéfinis de sortie pour un plan DITA {#get-output-presets-dita-map}

Méthode POST qui récupère tous les paramètres prédéfinis de sortie configurés pour un plan DITA.

**URL de la requête** :
http://*&lt;aem-guides-server\>* : *&lt;port-number\>*/bin/publishlistener

**Paramètres** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `:operation` | Chaîne | Oui | Nom de l’opération appelée. La valeur de ce paramètre est `getalloutputs`.<br> **Remarque :** la valeur ne respecte pas la casse. |
| `sourcePath` | Chaîne | Oui | Chemin d&#39;accès absolu au fichier de mappage DITA. |

**Valeurs de réponse** :
Renvoie un tableau d’objets de paramètre prédéfini de sortie JSON, chaque objet contenant les éléments suivants :

| Elément | Description |
|-------|-----------|
| `outputName` | Nom du préréglage de sortie. Les noms de sortie sont uniques dans l&#39;étendue du plan DITA dans lequel ils sont définis. |
| `outputType` | Type de sortie générée à l’aide de ce préréglage, par exemple AEM Site, PDF, EPUB ou autre. Les options disponibles sont les suivantes : <br>-   AEMSITE <br>-   PDF <br>-   HTML5 <br>-   EPUB <br>-   PERSONNALISÉ |
| `outputTitle` | Nom descriptif pour les paramètres prédéfinis de sortie. Il est utilisé pour définir la valeur de la propriété Nom du paramètre pour le paramètre prédéfini de sortie. |
| `ditaValPathList` | Tableau de chemins d’accès aux fichiers DITAVAL à utiliser pour générer la sortie souhaitée. |
| `targetPath` | Chemin où publier ou stocker la sortie. |
| `siteName` | *\(Pour la sortie du site AEM\)* Nom du site AEM. |
| `templatePath` | *\(Pour la sortie de site AEM\)* chemin d’accès du nœud de modèle à utiliser pour générer la sortie souhaitée. |
| `searchScope` | Spécifiez la portée de l’opération de recherche. La valeur de ce paramètre doit être définie sur `local`. |
| `generateTOC` | *\(Pour la sortie de site AEM\)* Spécifiez si une table des matières est générée \(true\) ou non \(false\). |
| `generateBreadcrumbs` | *\(Pour la sortie de site AEM\)* indiquez si les chemins de navigation sont générés \(true\) ou non \(false\). |
| `overwriteStrategy` | *\(Pour la sortie de site AEM\)* Spécifiez si les fichiers de la destination sont remplacés \(true\) ou non \(false\). |
| `pdfGenerator` | Spécifiez le moteur de génération PDF à utiliser. Les valeurs possibles sont les suivantes : <br>-   DITAOT <br>-   FMPS |

>[!NOTE]
>
> `DitaValPath` élément n’est plus pris en charge.

## Créer un paramètre prédéfini de sortie

Méthode POST qui crée un nouveau paramètre prédéfini de sortie pour un plan DITA.

**URL de la requête** :
http://*&lt;aem-guides-server\>* : *&lt;port-number\>*/bin/publishlistener

**Paramètres** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `:operation` | Chaîne | Oui | Nom de l’opération appelée. La valeur de ce paramètre est ``createoutput``.<br> **Remarque :** la valeur ne respecte pas la casse. |
| `sourcePath` | Chaîne | Oui | Chemin d&#39;accès absolu au fichier de mappage DITA. |
| `outputTitle` | Chaîne | Oui | Nom descriptif pour les paramètres prédéfinis de sortie. Il est utilisé pour définir la valeur de la propriété Nom du paramètre pour le paramètre prédéfini de sortie.<br> **Remarque :** lorsqu’un nouveau paramètre prédéfini de sortie est créé, le système principal attribue un nom unique au paramètre prédéfini de sortie à partir du titre donné. |
| `outputType` | Chaîne | Oui | Type de sortie générée à l’aide de ce préréglage, par exemple AEM Site, PDF, EPUB ou autre. Les options disponibles sont les suivantes : <br>-   AEMSITE <br>-   PDF <br>-   HTML5 <br>-   EPUB <br>-   PERSONNALISÉ |

**Valeurs de réponse** :

| Elément | Description |
|-------|-----------|
| `outputName` | Nom unique du paramètre prédéfini de sortie nouvellement créé. Ce nom est dérivé de la valeur du paramètre `outputTitle` . |

## Enregistrer le paramètre prédéfini de sortie

Méthode POST qui enregistre les modifications apportées à un paramètre prédéfini de sortie.

**URL de la requête** :
http://*&lt;aem-guides-server\>* : *&lt;port-number\>*/bin/publishlistener

**Paramètres** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `:operation` | Chaîne | Oui | Nom de l’opération appelée. La valeur de ce paramètre est ``saveoutput``.<br> **Remarque :** la valeur ne respecte pas la casse. |
| `sourcePath` | Chaîne | Oui | Chemin d&#39;accès absolu au fichier de mappage DITA. |
| `outputObj` | Chaîne | Oui | Objet JSON contenant les propriétés du paramètre prédéfini de sortie en cours de mise à jour. La propriété `outputObj.outputName` contient le nom du paramètre prédéfini de sortie à mettre à jour. Pour le format de l&#39;objet JSON, consultez le tableau **Valeurs de réponse** dans [Obtention de tous les paramètres prédéfinis de sortie pour un plan DITA](#get-output-presets-dita-map). |

**Valeurs de réponse** :
Renvoie une réponse HTTP 200 \(Successful\).

## Obtention d’un paramètre prédéfini de sortie spécifique

Une méthode POST qui récupère un paramètre prédéfini de sortie existant.

**URL de la requête** :
http://*&lt;aem-guides-server\>* : *&lt;port-number\>*/bin/publishlistener

**Paramètres** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `:operation` | Chaîne | Oui | Nom de l’opération appelée. La valeur de ce paramètre est `getoutput`. <br>**Remarque :** la valeur ne respecte pas la casse. |
| `sourcePath` | Chaîne | Oui | Chemin d&#39;accès absolu au fichier de mappage DITA. |
| `outputName` | Chaîne | Oui | Nom du préréglage de sortie pour lequel les détails doivent être récupérés. |

**Valeurs de réponse** :

| Elément | Description |
|-------|-----------|
| `outputName` | Nom du préréglage de sortie. Les noms de sortie sont uniques dans l&#39;étendue du plan DITA dans lequel ils sont définis. |
| `outputType` | Type de sortie générée à l’aide de ce préréglage, par exemple AEM Site, PDF, EPUB ou autre. Les options disponibles sont les suivantes : <br>-   AEMSITE <br>-   PDF <br>-   HTML5 <br>-   EPUB <br>-   <br> PERSONNALISÉ |
| `outputTitle` | Nom descriptif pour les paramètres prédéfinis de sortie. Il est utilisé pour définir la valeur de la propriété Nom du paramètre pour le paramètre prédéfini de sortie. |
| `ditaValPathList` | Tableau de chemins d’accès aux fichiers DITAVAL à utiliser pour générer la sortie souhaitée. |
| `targetPath` | Chemin où publier ou stocker la sortie. |
| `siteName` | \(Pour la sortie du site AEM\) Nom du site AEM. |
| `siteTitle` | \(Pour la sortie du site AEM\) Titre du site AEM. |
| `templatePath` | \(Pour la sortie de site AEM\) Chemin d’accès du nœud de modèle à utiliser pour générer la sortie souhaitée. |
| `searchScope` | Spécifiez la portée de l’opération de recherche. La valeur de ce paramètre doit être définie sur `local`. |
| `generateTOC` | \(Pour la sortie de site AEM\) Spécifiez si une table des matières est générée \(true\) ou non \(false\). |
| `generateBreadcrumbs` | \(Pour la sortie du site AEM\) Spécifiez si les chemins de navigation sont générés \(true\) ou non \(false\). |
| `overwriteFiles` | \(Pour la sortie de site AEM\) Spécifiez si les fichiers de la destination sont remplacés \(true\) ou non \(false\). |
| `pdfGenerator` | Spécifiez le moteur de génération PDF à utiliser. Les valeurs possibles sont les suivantes : <br>-   DITAOT <br>-   FMPS |

>[!NOTE]
>
> `DitaValPath` élément n’est plus pris en charge.

## Générer la sortie

Méthode GET qui génère une sortie à l’aide d’un ou de plusieurs paramètres prédéfinis de sortie.

**URL de la requête** :
http://*&lt;aem-guides-server\>* : *&lt;port-number\>*/bin/publishlistener

**Paramètres** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `operation` | Chaîne | Oui | Nom de l’opération appelée. La valeur de ce paramètre est `GENERATEOUTPUT`.<br> **Remarque :** la valeur respecte la casse. |
| `source` | Chaîne | Oui | Chemin d&#39;accès absolu au fichier de mappage DITA. |
| `outputName` | Chaîne | Oui | Nom du ou des préréglages de sortie à utiliser pour générer la sortie. Plusieurs paramètres prédéfinis de sortie peuvent être spécifiés à l’aide d’un délimiteur de barre verticale \(« \|« \), par exemple `aemsite\|pdfoutput`. |

**Valeurs de réponse** :
Renvoie une réponse HTTP 200 \(Successful\).

## Générer une sortie incrémentielle

Méthode GET qui génère une sortie incrémentielle pour un site AEM à l’aide d’un ou de plusieurs paramètres prédéfinis de sortie.

**URL de la requête** :
http://*&lt;aem-guides-server\>* : *&lt;port-number\>*/bin/publishlistener

**Paramètres** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `operation` | Chaîne | Oui | Nom de l’opération appelée. La valeur de ce paramètre est `INCREMENTALPUBLISH`. <br>**Remarque :** la valeur respecte la casse. |
| `contentPath` | JSON | Oui | Chemin d&#39;accès absolu du fichier de plan DITA et des fichiers de rubrique avec le nom des paramètres prédéfinis de sortie. Utilisez l’exemple suivant comme bloc de création : |

```XML
{
   {   
   "ditamap": 
      "/content/dam/sample/sample.ditamap",   
   "topics": [     
      "/content/dam/sample/topic1.xml",     
      "/content/dam/sample/topic2.xml"   
         ],   
   "fullMaps": [     
      "/content/dam/sample/submap.ditamap"   
      ],   
   "maps": [     
      "/content/dam/sample/keyspace.ditamap"   
      ],   
   "outputs": [     
      "aemsite"   
      ] 
   }
}
```

- L&#39;attribut `ditamap` utilise le chemin d&#39;accès absolu du plan DITA utilisé pour générer la sortie.
- L’attribut `topics` prend un tableau de rubriques qui sont mises à jour et doivent être republiées.
- L’attribut `fullMaps` contient le chemin des fichiers de mappage \(comme les sous-mappages segmentés\) nécessaires avec leurs rubriques pour la génération de sortie incrémentielle.
- L’attribut `maps` contient le chemin des fichiers de mappage \(pour résoudre les références d’espace clé\) extraits sur le disque sans rubriques.
- L’attribut `outputs` prend un tableau de noms de paramètres prédéfinis de sortie utilisés pour générer la sortie.

**Valeurs de réponse** :
Renvoie une réponse HTTP 200 \(Successful\).

## Supprimer le paramètre prédéfini de sortie

Méthode POST qui supprime un paramètre prédéfini de sortie.

**URL de la requête** :
http://*&lt;aem-guides-server\>* : *&lt;port-number\>*/bin/publishlistener

**Paramètres** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `:operation` | Chaîne | Oui | Nom de l’opération appelée. La valeur de ce paramètre est `deleteoutput`.<br> **Remarque :** la valeur ne respecte pas la casse. |
| `sourcePath` | Chaîne | Oui | Chemin d&#39;accès absolu au fichier de mappage DITA. |
| `outputName` | Chaîne | Oui | Nom du préréglage de sortie à supprimer. |

**Valeurs de réponse** :
Renvoie une réponse HTTP 200 \(Successful\).
