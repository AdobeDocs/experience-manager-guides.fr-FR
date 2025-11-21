---
title: API REST pour utiliser des attributs conditionnels
description: Découvrez comment utiliser l’API REST avec des attributs conditionnels
exl-id: 1f0e023a-422c-47b9-917f-b0d80090471c
feature: Rest API Conditional Attributes
role: Developer
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 6%

---

# API REST pour utiliser des attributs conditionnels {#id175UB30E05Z}

L’API REST suivante vous permet d’ajouter des attributs conditionnels dans un profil de dossier.

## Ajout d’un attribut conditionnel dans un profil au niveau du dossier

Méthode POST qui ajoute des attributs conditionnels à un profil donné au niveau du dossier.

**URL de la requête** :\
http://*<aem-guides-server\>* : *<port-number\>*/bin/fmdita/folderprofiles

**Paramètres** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `:operation` | Chaîne | Oui | Nom de l’opération appelée. La valeur de ce paramètre est ``ADDATTRIBUTEPROFILES``. <br> **Remarque :** la valeur ne respecte pas la casse. |
| `profilename` | Chaîne | Oui | Nom d’affichage du profil au niveau du dossier dans lequel les attributs conditionnels doivent être ajoutés. |
| `conditionalprofiles` | Tableau JSON | Oui | Un tableau JSON composé du nom et des valeurs d’attribut conditionnel. L’exemple de fragment de code suivant illustre le tableau JSON avec deux attributs : `platform` et `product`, auxquels plusieurs valeurs sont affectées. |

```JSON
[  {    name: "platform",    
        values: [       
                {value: "win", label: "Windows"},       
                {value: "mac", label: "Mac OS"}    
                ]},
                {    
                    name: "product",    
                    values: [      
                        {value: "aem_1", label: "AEM 6.1"},     
                        {value: "aem_4,  label: "AEM 6.4"}  
                        ]  
                }]
```

**Valeurs de réponse** :\
Renvoie une réponse HTTP 200 \(Successful\).
