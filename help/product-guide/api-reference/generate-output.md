---
title: API Java pour travailler avec la génération de sortie
description: En savoir plus sur l’API Java à utiliser avec la génération de sortie
exl-id: e19439df-39ec-47fd-9da5-24f51750a7e5
feature: Java-Based API Publishing
role: Developer
level: Experienced
source-git-commit: ee4eb829ebe215315b05cd1f376e934c02a73b1e
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 2%

---

# API Java pour travailler avec la génération de sortie {#id175UB30E05Z}

>[!NOTE]
>
> Vous pouvez utiliser des API Java disponibles dans Experience Manager Guides pour créer des modules externes personnalisés et étendre les processus prêts à l’emploi. Cet article sera archivé en novembre 2024.
> Affichez [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) pour obtenir la documentation la plus récente et détaillée sur l’utilisation de l’API Java.

L’API Java suivante vous permet de générer une sortie pour une carte DITA. Cette API est disponible sous la forme d’un lot. Vous devez inclure ce lot dans votre code pour utiliser ces API.

Détails du lot :

- ID de groupe : **com.adobe.fmdita**

- ID d’artefact : **api**

- Version : **3.4**

- Package : **&#x200B;**&#x200B;com.adobe.fmdita.api.maps&#x200B;**&#x200B;**

- Détails de la classe :

  ```JAVA
  public class **PublishUtils** extends Object
  ```

  La classe **`PublishUtils`** contient une méthode pour générer la sortie pour un ou plusieurs paramètres prédéfinis de sortie.


## Générer la sortie

La méthode ``generateOutput`` génère une sortie pour un fichier de mappage DITA à l’aide des paramètres prédéfinis de sortie spécifiés.

**Syntaxe**:

```JAVA
public static void generateOutput(Session session,
String sourcePath,
String outputName)
throws GuidesApiException
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `session` | javax.jcr.Session | Session JCR valide. |
| ``sourcePath`` | Chaîne | Chemin \(dans le référentiel AEM\) du fichier de mappage DITA pour lequel la sortie doit être générée. |
| ``outputName`` | Chaîne | Nom du paramètre prédéfini de sortie\(s\) à utiliser pour générer la sortie. Plusieurs paramètres prédéfinis de sortie peuvent être spécifiés à l’aide d’un délimiteur barre verticale \(&quot;\|&quot;\), par exemple `aemsite\|pdfoutput`. |

**Exception** :
Renvoie ``javax.jcr.RepositoryException``, `java.io.IOException` et `java.lang.Exception`.
