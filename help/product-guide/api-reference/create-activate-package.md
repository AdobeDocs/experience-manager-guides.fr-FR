---
title: API REST pour la création et l’activation de packages
description: En savoir plus sur l’API REST pour la création et l’activation de packages
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
feature: Rest API Packages
role: Developer
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 0%

---

# API REST pour la création et l’activation de packages {#id198CF0260Y4}

L’API REST suivante vous permet de créer et d’activer des packages CRX.

## Créer et activer un package

Méthode de POST qui crée et active le package CRX.

**URL de la requête**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/activate

**Paramètres**: la requête de requête se compose de la chaîne de règles JSON. Le type de contenu de la demande de POST doit être défini sur `application/json; charset=UTF-8`.

**Exemple**: les exemples suivants présentent l’appel API à l’aide de la commande curl :

    &quot;
    curl -u &lt;*nom_utilisateur*>:&lt;*mot_de_passe*> -H &quot;Content-Type: application/json; charset=UTF-8&quot; -k -X POST -d &quot;{[chaîne de règles JSON](create-activate-package-java.md#example-create-activate-package-id198JH0B905em)}&quot; http://-guides-server*>:&lt;*numéro-port*>/bin/fmdita/activate
    &quot;
