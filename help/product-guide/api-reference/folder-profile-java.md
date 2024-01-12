---
title: API Java pour travailler avec des profils de dossier
description: Découvrez l’API Java pour utiliser les profils de dossier
exl-id: 388ae654-c4f9-4bb7-ba98-370b8919e3a6
feature: Java-Based API Folder Profiles
role: Developer
level: Experienced
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# API Java pour travailler avec des profils de dossier {#id175UB30E05Z}

L’API Java suivante vous permet d’ajouter des attributs conditionnels à un profil au niveau du dossier. Cette API est disponible sous la forme d’un lot. Vous devez inclure ce lot dans votre code pour utiliser ces API.

Détails du lot :

- ID de groupe : **com.adobe.fmdita**

- ID d’artefact : **api**

- Version : **3,2**

- Package : **com.adobe.fmdita.api.profiles**

- Détails de la classe :

  ```JAVA
  public class FolderProfileUtils extends Object
  ```

  La variable **`FolderProfileUtils`** contient une méthode permettant d’ajouter des attributs conditionnels dans un profil de dossier.


## Ajout d’attributs conditionnels à un profil de dossier

La variable ``addAttributeProfiles`` ajoute des attributs conditionnels à un profil au niveau du dossier.

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

**Paramètres**: |Nom|Type|Description| |—|—|—| |``attributeNames``|Chaîne|Une liste de noms d’attributs.| |``values``|Chaîne|Une liste de valeurs pour les attributs donnés.| |`labels`|Chaîne|Une liste de libellés pour le `attribute`- `value` paires. [1](#fntarg_1)| |`profileName`|String|Nom du profil au niveau du dossier auquel ces attributs, valeurs et libellés doivent être appliqués. **Important :** Tous les attributs-valeurs-libellés existants définis dans le profil sont écrasés.| |`session`|javax.jcr.Session|Une session JCR valide.|

**Renvoie**:
`true` pour la réussite. En cas d’échec, il renvoie une exception.

**Exception**: renvoie ``java.lang.Exception`` dans les scénarios suivants :

- Si l’API n’a pas pu obtenir `resourceResolverFactory` . Dans ce cas, vous devez redémarrer le lot.
- Si les paramètres transmis à l’API ne sont pas valides.
- Si l’API est appelée par le biais d’une session utilisateur non autorisée, par exemple un utilisateur qui n’est pas administrateur pour le profil de dossier donné.

[1](#fnsrc_1) La variable `attributeNames`, `values`, et `labels` au même index dans une liste de tableaux doit correspondre à la même entrée.
