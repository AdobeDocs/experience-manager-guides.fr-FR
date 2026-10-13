---
title: API REST pour utiliser des attributs conditionnels
description: Découvrez comment utiliser l’API REST avec des attributs conditionnels
exl-id: 1f0e023a-422c-47b9-917f-b0d80090471c
feature: Rest API Conditional Attributes
role: Developer
level: Experienced
TQID: 'https://experienceleague.adobe.com/qtmJN6jjCm3xeNYAaHTWr7G3SZFSOodcVqBOKctR3B8'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
    internal-label: APIs
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: d27d524e-c4e5-4b77-b86b-3db049db0b25
    internal-label: REST API Conditional Attributes
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 5%
---
# API REST pour utiliser des attributs conditionnels {#id175UB30E05Z}

L’API REST suivante vous permet d’ajouter des attributs conditionnels dans un profil de dossier.

## Ajout d’un attribut conditionnel dans un profil au niveau du dossier

Méthode POST qui ajoute des attributs conditionnels à un profil donné au niveau du dossier.

**URL de la requête** :\
*&lt;aem-guides-server\>* : *&lt;port-number\>*/bin/fmdita/folderprofiles

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
