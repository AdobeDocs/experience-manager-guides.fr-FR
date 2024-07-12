---
title: API REST pour la création et l’activation de packages
description: En savoir plus sur l’API REST pour la création et l’activation de packages
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
feature: Rest API Packages
role: Developer
level: Experienced
source-git-commit: b95a64ca2e8ebffebec3d8ff8704f76f7faceca2
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# API REST pour la création et l’activation de packages {#id198CF0260Y4}

L’API REST suivante vous permet de créer et d’activer des packages CRX.

## Créer et activer un package

Méthode de POST qui crée et active le package CRX.

**Demander l’URL** :
http://*&lt;aem-guides-server\>* : *&lt;port-number\>*/bin/fmdita/activate

**Paramètres** :
La requête de requête se compose de la chaîne de règles JSON. Le type de contenu de la requête du POST doit être défini sur `application/json; charset=UTF-8`.

**Exemple** :
L’exemple suivant illustre l’appel API à l’aide de la commande curl :

```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate
```


**Paramètre facultatif**

`activationTarget`

**Valeurs valides**

`preview` ou `publish` pour Cloud Service et `publish` pour le logiciel On-premise

- Pour Cloud Service, si le paramètre contient une valeur non valide, l’activation du package échoue.

- Pour le logiciel On-premise, si le paramètre contient une valeur non valide, l’erreur est consignée et la publication est effectuée à l’aide de la valeur par défaut, `publish`.

Si vous ne définissez pas le paramètre facultatif, `activationTarget`, il s’active à l’aide de l’agent de publication par défaut pour le Cloud Service et le logiciel On-premise.



L’exemple suivant illustre l’appel API à l’aide de la commande curl avec le paramètre facultatif :


    &quot;XML
    
    curl -u &lt;*nom d’utilisateur*>:&lt;*mot de passe*> -H &quot;Type de contenu : application/json; charset=UTF-8&quot; -k -X POST -d &quot;{[chaîne de règles JSON](create-activate-package-java.md#example-create-activate-package-id198JH0B9055000500000000)}&quot; http://&lt;*aem-guides-server*>:&lt;*port-number*>/bin/fmdita/activate?activationTarget=&lt;validActivationTargetValue>`
    &quot;
&quot;