---
title: API REST pour créer et activer des packages
description: Découvrez l’API REST pour créer et activer des packages
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
feature: Rest API Packages
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/cJUVS3QdzVhnZjFF7uoHfpOSBefgm5W2jh-kWM1PvmE
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552eid: a3bd6397-2eb2-4908-a61c-226e26855dcaid: c6d09140-3c91-45d3-b7ed-b681af752f43
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 181
ht-degree: 0%

---

# API REST pour créer et activer des packages {#id198CF0260Y4}

L’API REST suivante vous permet de créer et d’activer des packages CRX.

## Créer et activer un package

Méthode POST de création et d’activation du package CRX.

**URL de la requête** :
*&lt;aem-guides-server\>* : *&lt;port-number\>*/bin/fmdita/activate

**Paramètres** :
La requête de requête se compose de la chaîne de règles JSON . Le type de contenu de la requête POST doit être défini sur `application/json; charset=UTF-8`.

**Exemple** :
L’exemple suivant illustre l’appel API à l’aide de la commande curl :

```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate
```


**Paramètre facultatif**

`activationTarget`

**Valeurs valides**

`preview` ou `publish` pour Cloud Service et `publish` pour les logiciels On-Premise

- Pour Cloud Service, si le paramètre contient une valeur non valide, l’activation du package échoue.

- Pour les logiciels On-premise, si le paramètre contient une valeur non valide, l’erreur est consignée et la publication est effectuée à l’aide de la valeur par défaut, `publish`.

Si vous ne définissez pas le paramètre facultatif, `activationTarget`, il est activé à l’aide de l’agent de publication par défaut pour les logiciels Cloud Service et On-premise.



L’exemple suivant illustre l’appel API à l’aide de la commande curl avec le paramètre facultatif :


```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate?activationTarget=`<validActivationTargetValue>`
```
