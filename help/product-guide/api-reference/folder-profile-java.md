---
title: API Java pour travailler avec des profils de dossier
description: Découvrez l’API Java pour utiliser les profils de dossier
exl-id: 388ae654-c4f9-4bb7-ba98-370b8919e3a6
feature: Java-Based API Folder Profiles
role: Developer
level: Experienced
source-git-commit: 8c80a4da8e61909aab0f2db81ef97149774b36c4
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 2%

---

# API Java pour travailler avec des profils de dossier {#id175UB30E05Z}

>[!NOTE]
>
> Vous pouvez utiliser des API Java disponibles dans Experience Manager Guides pour créer des modules externes personnalisés et étendre les processus prêts à l’emploi. Cet article sera archivé en novembre 2024.
> Affichez [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) pour obtenir la documentation la plus récente et détaillée sur l’utilisation de l’API Java.




L’API Java suivante vous permet d’ajouter des attributs conditionnels à un profil au niveau du dossier. Cette API est disponible sous la forme d’un lot. Vous devez inclure ce lot dans votre code pour utiliser ces API.

Détails du lot :

- ID de groupe : **com.adobe.fmdita**

- ID d’artefact : **api**

- Version : **3.2**

- Package : **com.adobe.fmdita.api.profiles**

- Détails de la classe :

  ```JAVA
  public class FolderProfileUtils extends Object
  ```

  La classe **`FolderProfileUtils`** contient une méthode pour ajouter des attributs conditionnels dans un profil de dossier.


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
| ``values`` | Chaîne | Liste de valeurs pour les attributs donnés. |
| `labels` | Chaîne | Liste des libellés pour les paires `attribute`- `value`. [1](#fntarg_1) |
| `profileName` | Chaîne | Nom du profil au niveau du dossier auquel ces attributs, valeurs et libellés doivent être appliqués. **Important :** Tous les attributs-valeurs-libellés existants définis dans le profil sont écrasés. |
| `session` | javax.jcr.Session | Session JCR valide. |

**Renvoie** :
`true` pour succès. En cas d’échec, il renvoie une exception.

**Exception** :
Lance ``java.lang.Exception`` dans les scénarios suivants :

- Si l’API n’a pas pu obtenir l’objet `resourceResolverFactory`. Dans ce cas, vous devez redémarrer le lot.
- Si les paramètres transmis à l’API ne sont pas valides.
- Si l’API est appelée par le biais d’une session utilisateur non autorisée, par exemple un utilisateur qui n’est pas administrateur pour le profil de dossier donné.

[1](#fnsrc_1) Les `attributeNames`, `values` et `labels` du même index dans une liste de tableaux doivent correspondre à la même entrée.
