---
title: API REST pour la gestion de sortie
description: En savoir plus sur les API REST pour la gestion de sortie
exl-id: dab654f5-555d-4a89-bc94-55b1e938f255
feature: Rest API Output Management
role: Developer
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1175'
ht-degree: 0%

---

# API REST pour la gestion de sortie {#id175UB30E05Z}

Les API REST suivantes sont disponibles pour la gestion des sorties dans AEM Guides.

## Obtention de tous les paramètres prédéfinis de sortie pour un mappage DITA {#get-output-presets-dita-map}

Méthode de POST qui récupère tous les paramètres prédéfinis de sortie configurés pour un mappage DITA.

**URL de la requête**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Paramètres**:\
|Nom|Type|Obligatoire|Description| |—|—|—|— |`:operation`|String|Yes|Nom de l’opération en cours d’appel. La valeur de ce paramètre est `getalloutputs`.<br> **Remarque :** La valeur n’est pas sensible à la casse.| |`sourcePath`|Chaîne|Oui|Chemin absolu du fichier de mappage DITA.|

**Valeurs de réponse**: renvoie un tableau d’objets JSON Output Preset, chaque objet contenant les éléments suivants :

| Elément | Description |
|-------|-----------|
| `outputName` | Nom du paramètre prédéfini de sortie. Les noms de sortie sont uniques dans la portée du mappage DITA dans lequel ils sont définis. |
| `outputType` | Type de sortie générée à l’aide de ce paramètre prédéfini, par exemple AEM Site, PDF, EPUB ou autre. Les options disponibles sont les suivantes :<br>- AEMSITE <br>- PDF <br>- HTML5 <br>- EPUB <br>- PERSONNALISÉ |
| `outputTitle` | Nom explicite des paramètres prédéfinis de sortie. Il est utilisé pour définir la valeur de la propriété Setting Name pour le paramètre prédéfini de sortie. |
| `ditaValPathList` | Tableau des chemins d’accès aux fichiers DITAVAL à utiliser pour générer la sortie souhaitée. |
| `targetPath` | Chemin où la sortie est publiée ou stockée. |
| `siteName` | *\(Pour AEM sortie du site\)* Nom du site AEM. |
| `templatePath` | *\(Pour AEM sortie du site\)* Chemin du noeud de modèle à utiliser pour générer la sortie souhaitée. |
| `searchScope` | Spécifiez la portée de l’opération de recherche. La valeur de ce paramètre doit être définie sur `local`. |
| `generateTOC` | *\(Pour AEM sortie du site\)* Indiquez si une table des matières est générée \(true\) ou non \(false\). |
| `generateBreadcrumbs` | *\(Pour AEM sortie du site\)* Indiquez si les chemins de navigation sont générés \(true\) ou non \(false\). |
| `overwriteStrategy` | *\(Pour AEM sortie du site\)* Indiquez si les fichiers de la destination sont écrasés \(true\) ou non \(false\). |
| `pdfGenerator` | Spécifiez le moteur de génération de PDF à utiliser. Les valeurs possibles sont les suivantes :<br>- DITA <br>- FMPS |

>[!NOTE]
>
> `DitaValPath` n’est plus prise en charge.

## Créer un paramètre prédéfini de sortie

Méthode de POST qui crée un nouveau paramètre prédéfini de sortie pour un mappage DITA.

**URL de la requête**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Paramètres**: |Nom|Type|Obligatoire|Description| |—|—|—|— |`:operation`|String|Yes|Nom de l’opération en cours d’appel. La valeur de ce paramètre est ``createoutput``.<br> **Remarque :** La valeur n’est pas sensible à la casse.| |`sourcePath`|String|Yes|Chemin absolu du fichier de mappage DITA.| |`outputTitle`|Chaîne|Oui|Un nom descriptif pour les paramètres prédéfinis de sortie. Il est utilisé pour définir la valeur de la propriété Setting Name pour le paramètre prédéfini de sortie.<br> **Remarque :** Lorsqu’un nouveau paramètre prédéfini de sortie est créé, le système principal génère un nom unique pour le paramètre prédéfini de sortie à partir du titre donné.| |`outputType`|String|Yes|Type de sortie générée à l’aide de ce paramètre prédéfini, par exemple AEM Site, PDF, EPUB ou autre. Les options disponibles sont les suivantes :<br>- AEMSITE <br>- PDF <br>- HTML5 <br>- EPUB <br>- PERSONNALISÉ|

**Valeurs de réponse**: |Elément|Description| |—|—| |`outputName`|Nom unique du paramètre prédéfini de sortie que vous venez de créer. Ce nom est dérivé de la valeur de la variable `outputTitle` parameter.|

## Enregistrer le paramètre prédéfini de sortie

Méthode de POST qui enregistre les modifications effectuées dans un paramètre prédéfini de sortie.

**URL de la requête**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Paramètres**: |Nom|Type|Obligatoire|Description| |—|—|—|— |`:operation`|String|Yes|Nom de l’opération en cours d’appel. La valeur de ce paramètre est ``saveoutput``.<br> **Remarque :** La valeur n’est pas sensible à la casse.| |`sourcePath`|String|Yes|Chemin absolu du fichier de mappage DITA.| |`outputObj`|String|Yes|Un objet JSON qui contient les propriétés du paramètre prédéfini de sortie en cours de mise à jour. La variable `outputObj.outputName` contient le nom du paramètre prédéfini de sortie à mettre à jour. Pour connaître le format de l’objet JSON, voir **Valeurs de réponse** dans [Obtention de tous les paramètres prédéfinis de sortie pour un mappage DITA](#get-output-presets-dita-map).

**Valeurs de réponse**: renvoie une réponse HTTP 200 \(réussie\).

## Obtenir un paramètre prédéfini de sortie spécifique

Méthode de POST qui récupère un paramètre prédéfini de sortie existant.

**URL de la requête**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Paramètres**: |Nom|Type|Obligatoire|Description| |—|—|—|— |`:operation`|String|Yes|Nom de l’opération en cours d’appel. La valeur de ce paramètre est `getoutput`. <br>**Remarque :** La valeur n’est pas sensible à la casse.| |`sourcePath`|String|Yes|Chemin absolu du fichier de mappage DITA.| |`outputName`|String|Yes|Nom du paramètre prédéfini de sortie pour lequel les détails doivent être récupérés.|

**Valeurs de réponse**: |Elément|Description| |—|—| |`outputName`|Nom du paramètre prédéfini de sortie. Les noms de sortie sont uniques dans la portée du mappage DITA dans lequel ils sont définis.| |`outputType`|Type de sortie généré à l’aide de ce paramètre prédéfini, par exemple AEM Site, PDF, EPUB ou autre. Les options disponibles sont les suivantes :<br>- AEMSITE <br>- PDF <br>- HTML5 <br>- EPUB <br>- PERSONNALISÉ <br>| |`outputTitle`|Un nom descriptif pour les paramètres prédéfinis de sortie. Il est utilisé pour définir la valeur de la propriété Setting Name pour le paramètre prédéfini de sortie.| |`ditaValPathList`|Tableau des chemins d’accès aux fichiers DITAVAL à utiliser pour générer la sortie souhaitée.| |`targetPath`|Chemin où la sortie est publiée ou stockée.| |`siteName`|\(Pour AEM sortie du site\) Nom du site AEM.| |`siteTitle`|\(Pour AEM sortie du site\) Titre du site AEM.| |`templatePath`|\(Pour AEM sortie Site\) Chemin du noeud de modèle à utiliser pour générer la sortie souhaitée.| |`searchScope`|Indiquez la portée de l’opération de recherche. La valeur de ce paramètre doit être définie sur `local`.| |`generateTOC`|\(Pour AEM sortie du site\) Indiquez si une table des matières est générée \(true\) ou non \(false\).| |`generateBreadcrumbs`|\(Pour AEM sortie du site\) Indiquez si les chemins de navigation sont générés \(true\) ou non \(false\).| |`overwriteFiles`|\(Pour AEM sortie du site\) Indiquez si les fichiers à la destination sont remplacés \(true\) ou non \(false\).| |`pdfGenerator`|Spécifiez le moteur de génération de PDF à utiliser. Les valeurs possibles sont les suivantes :<br>- DITA <br>- FMPS|

>[!NOTE]
>
> `DitaValPath` n’est plus prise en charge.

## Générer la sortie

Méthode de GET qui génère une sortie à l’aide d’un ou de plusieurs paramètres prédéfinis de sortie.

**URL de la requête**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Paramètres**: |Nom|Type|Obligatoire|Description| |—|—|—|— |`operation`|String|Yes|Nom de l’opération en cours d’appel. La valeur de ce paramètre est `GENERATEOUTPUT`.<br> **Remarque :** La valeur est sensible à la casse.| |`source`|String|Yes|Chemin absolu du fichier de mappage DITA.| |`outputName`|String|Yes|Nom du paramètre prédéfini de sortie\(s\) à utiliser pour générer la sortie. Plusieurs paramètres prédéfinis de sortie peuvent être spécifiés à l’aide d’un délimiteur barre verticale \(&quot;\|&quot;\), par exemple. `aemsite|pdfoutput`.

**Valeurs de réponse**: renvoie une réponse HTTP 200 \(réussie\).

## Générer une sortie incrémentielle

Méthode de GET qui génère une sortie incrémentielle pour un site AEM à l’aide d’un ou de plusieurs paramètres prédéfinis de sortie.

**URL de la requête**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Paramètres**: |Nom|Type|Obligatoire|Description| |—|—|—|— |`operation`|String|Yes|Nom de l’opération en cours d’appel. La valeur de ce paramètre est `INCREMENTALPUBLISH`. <br>**Remarque :** La valeur est sensible à la casse.| |`contentPath`|JSON|Oui|Chemin absolu du fichier de mappage DITA et des fichiers de rubrique avec le nom des paramètres prédéfinis de sortie. Utilisez l’exemple suivant comme bloc de création :|

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

- La variable `ditamap` prend le chemin d’accès absolu de la carte DITA utilisée pour générer la sortie.
- La variable `topics` prend un tableau de rubriques qui sont mises à jour et qui doivent être republiées.
- La variable `fullMaps` L’attribut contient le chemin d’accès des fichiers map \(comme les submaps découpés\) nécessaires, ainsi que leurs rubriques pour la génération de sortie incrémentielle.
- La variable `maps` contient le chemin d’accès des fichiers map \(pour résoudre les références d’espace-clé\) extraits sur le disque sans rubriques.
- La variable `outputs` prend un tableau de noms de paramètres prédéfinis de sortie utilisés pour générer la sortie.

**Valeurs de réponse**: renvoie une réponse HTTP 200 \(réussie\).

## Supprimer le paramètre prédéfini de sortie

Méthode de POST qui supprime un paramètre prédéfini de sortie.

**URL de la requête**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Paramètres**: |Nom|Type|Obligatoire|Description| |—|—|—|— |`:operation`|String|Yes|Nom de l’opération en cours d’appel. La valeur de ce paramètre est `deleteoutput`.<br> **Remarque :** La valeur n’est pas sensible à la casse.| |`sourcePath`|String|Yes|Chemin absolu du fichier de mappage DITA.| |`outputName`|String|Yes|Nom du paramètre prédéfini de sortie à supprimer.|

**Valeurs de réponse**: renvoie une réponse HTTP 200 \(réussie\).
