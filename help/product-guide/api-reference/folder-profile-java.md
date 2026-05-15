---
title: API Java pour l’utilisation des profils de dossier
description: Découvrez l’API Java permettant d’utiliser les profils de dossier
exl-id: 388ae654-c4f9-4bb7-ba98-370b8919e3a6
feature: Java-Based API Folder Profiles
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/-rZBkRHgOJDh0hpvpMgRx7jyvcYstElA4ztdjXmpATU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 315
ht-degree: 2%

---

# API Java pour l’utilisation des profils de dossier {#id175UB30E05Z}

>[!NOTE]
>
> Vous pouvez utiliser les API Java disponibles dans Experience Manager Guides pour créer des modules externes personnalisés et étendre les workflows prêts à l’emploi. Cet article sera archivé en novembre 2024.
> Consultez [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) pour obtenir la documentation la plus récente et détaillée sur l’utilisation de l’API Java.




L’API Java suivante vous permet d’ajouter des attributs conditionnels à un profil au niveau du dossier. Cette API est disponible sous la forme d’un lot. Vous devez inclure ce lot dans votre code pour utiliser ces API.

Détails du bundle :

- ID de groupe : **com.adobe.fmdita**

- ID d’artefact : **api**

- Version : **3.2**

- Package : **com.adobe.fmdita.api.profiles**

- Détails de la classe :

  ```JAVA
  public class FolderProfileUtils extends Object
  ```

  La classe **`FolderProfileUtils`** contient une méthode permettant d’ajouter des attributs conditionnels dans un profil de dossier.


## Ajout d’attributs conditionnels à un profil de dossier

La méthode ``addAttributeProfiles`` ajoute des attributs conditionnels à un profil au niveau du dossier.

**Syntaxe**:

```JAVA
public static boolean addAttributeProfiles
(List
<String> attributeNames, 
List
    <String> values, 
List
        <String> labels,
String profileName, 
Session session) throws GuidesApiException
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| ``attributeNames`` | Chaîne | Liste de noms d’attributs. |
| ``values`` | Chaîne | Une liste de valeurs pour les attributs donnés. |
| `labels` | Chaîne | Liste des libellés des paires `attribute`-`value`. [1](#fntarg_1) |
| `profileName` | Chaîne | Nom du profil au niveau du dossier auquel ces attributs, valeurs et libellés doivent être appliqués. **Important :** tous les attributs-values-labels existants définis dans le profil sont remplacés. |
| `session` | javax.jcr.Session | Une session JCR valide. |

**Renvoie** :
`true` pour réussir. En cas d’échec, il renvoie une exception.

**Exception** :
Lance des ``java.lang.Exception`` dans les scénarios suivants :

- Si l’API n’a pas pu obtenir `resourceResolverFactory` objet . Dans ce cas, vous devez redémarrer le lot.
- Si les paramètres transmis à l’API ne sont pas valides.
- Si l’API est appelée via une session utilisateur non autorisée, par exemple un utilisateur qui n’est pas administrateur pour le profil de dossier donné.

[1](#fnsrc_1) Les `attributeNames`, `values` et `labels` du même index dans une liste de tableau doivent correspondre à la même entrée.
