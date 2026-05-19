---
title: Notes de mise à jour | Correction de problèmes dans la version Adobe Experience Manager Guides 4.3.1.5
description: Découvrez les correctifs de bugs dans la version 4.3.1.5 d’Adobe Experience Manager Guides
role: Leader
exl-id: 082dca28-15da-417c-b511-74eb5ac68078
TQID: https://experienceleague.adobe.com/ujQFyhAp5bIB1OJnmqvbHCaiDip7T2qsjlVAWevykK8
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 130
ht-degree: 6%

---

# Correction de problèmes dans la version 4.3.1.5


Cet article couvre les bugs corrigés dans diverses zones de 4.3.1.5 version d’Adobe Experience Manager Guides.



Découvrez les [instructions de mise à niveau pour la version 4.3.1.5](../release-info/upgrade-instructions-4-3-1-5.md).


## Création

- L’ajout d’espaces entre les éléments intégrés dans `<codeblock>` entraîne un saut de ligne dans la sortie générée. (15247)
- Des problèmes d’expérience se produisent lors de l’ajout d’éléments à partir de la boîte de dialogue « Insérer un élément ». (15108)

## Publication

- Les journaux d’erreurs affichent des informations incorrectes sur la publication de contenu avec des portées externes. (15242)
- Les liens internes vers des fichiers DITA commençant par `HTTP` sont traités comme des liens externes et provoquent des erreurs d&#39;étendue. (15155)
- La régénération du site AEM échoue pour les plans DITA. (14369)

## Gestion

- La propriété **fmditaTopicrefs** affiche les chemins relatifs au lieu des chemins absolus. (15341)
