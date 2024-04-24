---
title: API REST pour la création et l’activation de modules
description: En savoir plus sur l’API REST pour la création et l’activation de packages
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
feature: Rest API Packages
role: Developer
level: Experienced
source-git-commit: 32da48d82b1267bb220424edf385035426293b66
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 0%

---

# API REST pour la création et l’activation de modules {#id198CF0260Y4}

L’API REST suivante vous permet de créer et d’activer des modules CRX.

## Créer et activer un module

Une méthode POST qui crée et active le package CRX.

**URL de** la demande :
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/activate&lt;/port-number\>&lt;/aem-guides-server\>

**Paramètres** :
La requête de requête est constituée de la chaîne de règles JSON. Le type de contenu de la requête de POST doit être défini sur `application/json; charset=UTF-8`.

**Par exemple** :
L’exemple suivant illustre l’appel d’API à l’aide de la commande curl :

```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate
```


**Paramètre facultatif**

`activationTarget`

**Valeurs valides**

`preview` ou `publish` pour Cloud Service et `publish` pour les logiciels sur site

Si le paramètre contient une valeur non valide, l’activation du package échoue. L’exemple suivant illustre l’appel d’API à l’aide de la commande curl avec le paramètre facultatif :


    &#39;&#39;&#39;XML
    
    curl -u &lt;*username*>:&lt;*password*> -H « Content-Type : application/json ; charset=UTF-8 » -k -X POST -d « {[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)} » http://&lt;*aem-guides-server*> :&lt;*port-number*>/bin/fmdita/activate ?activationTarget=&#39;&lt;validActivationTargetValue>&#39;
    &#39;
&lt;/validActivationTargetValue>&lt;/*port-number*>&lt;/*aem-guides-server*>&lt;/*password*>&lt;/*username*>