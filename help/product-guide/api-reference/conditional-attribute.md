---
title: API REST pour travailler avec des attributs conditionnels
description: En savoir plus sur l’API REST pour utiliser les attributs conditionnels
exl-id: 1f0e023a-422c-47b9-917f-b0d80090471c
feature: Rest API Conditional Attributes
role: Developer
level: Experienced
source-git-commit: 6184bb98c9897e980a6fba2f97476570228188af
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 6%

---

# API REST pour travailler avec des attributs conditionnels {#id175UB30E05Z}

L’API REST suivante vous permet d’ajouter des attributs conditionnels dans un profil de dossier.

## Ajout d’un attribut conditionnel dans un profil au niveau du dossier

Méthode de POST qui ajoute des attributs conditionnels à un profil donné au niveau du dossier.

**Demander l’URL** :\
http://*&lt;aem-guides-server\>* : *&lt;port-number\>*/bin/fmdita/folderprofiles

**Paramètres** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `:operation` | Chaîne | Oui | Nom de l’opération en cours d’appel. La valeur de ce paramètre est ``ADDATTRIBUTEPROFILES``. <br> **Remarque :** La valeur n’est pas sensible à la casse. |
| `profilename` | Chaîne | Oui | Nom d’affichage du profil au niveau du dossier dans lequel les attributs conditionnels doivent être ajoutés. |
| `conditionalprofiles` | Tableau JSON | Oui | Tableau JSON constitué du nom et des valeurs de l’attribut conditionnel. L’exemple de fragment de code suivant montre le tableau JSON avec deux attributs : `platform` et `product` avec plusieurs valeurs qui leur sont affectées. |

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
Renvoie une réponse HTTP 200 \(Succès\).
