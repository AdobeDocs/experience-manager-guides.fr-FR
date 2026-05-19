---
title: API Java pour travailler avec la génération de sortie
description: Découvrez l’API Java permettant d’utiliser la génération de sortie
exl-id: e19439df-39ec-47fd-9da5-24f51750a7e5
feature: Java-Based API Publishing
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/i5mTM1VtBg3QFUa-sBmF2pH8BITRn9j-efw2dr8VwCU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 225
ht-degree: 2%

---

# API Java pour travailler avec la génération de sortie {#id175UB30E05Z}

>[!NOTE]
>
> Vous pouvez utiliser les API Java disponibles dans Experience Manager Guides pour créer des modules externes personnalisés et étendre les workflows prêts à l’emploi. Cet article sera archivé en novembre 2024.
> Consultez [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) pour obtenir la documentation la plus récente et détaillée sur l’utilisation de l’API Java.

L&#39;API Java suivante vous permet de générer une sortie pour un plan DITA. Cette API est disponible sous la forme d’un lot. Vous devez inclure ce lot dans votre code pour utiliser ces API.

Détails du bundle :

- ID de groupe : **com.adobe.fmdita**

- ID d’artefact : **api**

- Version : **3.4**

- Package : **&#x200B;**&#x200B;com.adobe.fmdita.api.maps&#x200B;**&#x200B;**

- Détails de la classe :

  ```JAVA
  public class **PublishUtils** extends Object
  ```

  La classe **`PublishUtils`** contient une méthode permettant de générer une sortie pour un ou plusieurs paramètres prédéfinis de sortie.


## Générer la sortie

La méthode ``generateOutput`` génère une sortie pour un fichier de mappage DITA à l&#39;aide des paramètres prédéfinis de sortie spécifiés.

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
| `session` | javax.jcr.Session | Une session JCR valide. |
| ``sourcePath`` | Chaîne | Chemin \(dans le référentiel AEM\) du fichier map DITA pour lequel la sortie doit être générée. |
| ``outputName`` | Chaîne | Nom du ou des préréglages de sortie à utiliser pour générer la sortie. Plusieurs paramètres prédéfinis de sortie peuvent être spécifiés à l’aide d’un délimiteur de barre verticale \(« \|« \), par exemple `aemsite\|pdfoutput`. |

**Exception** :
Renvoie ``javax.jcr.RepositoryException``, `java.io.IOException` et `java.lang.Exception`.
