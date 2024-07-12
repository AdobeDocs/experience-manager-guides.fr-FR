---
title: Notes de mise à jour | Correction de problèmes dans la version 4.3.1.5 d’Adobe Experience Manager Guides
description: En savoir plus sur les correctifs de la version 4.3.1.5 d’Adobe Experience Manager Guides
role: Leader
exl-id: 082dca28-15da-417c-b511-74eb5ac68078
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 2%

---

# Correction de problèmes dans la version 4.3.1.5


Cet article couvre les bogues corrigés dans différentes zones de la version 4.3.1.5 d’Adobe Experience Manager Guides.



Découvrez les [instructions de mise à niveau pour la version 4.3.1.5](../release-info/upgrade-instructions-4-3-1-5.md).


## Création

- L’ajout d’espaces entre les éléments intégrés dans `<codeblock>` provoque un saut de ligne dans la sortie générée. (15247)
- Des problèmes d’expérience se produisent lors de l’ajout d’éléments à partir de la boîte de dialogue &quot;Insérer un élément&quot;. (15108)

## Publication

- Les journaux d’erreurs affichent des informations incorrectes sur la publication de contenu avec des portées externes. (15242)
- Les liens internes vers les fichiers DITA commençant par `HTTP` sont traités comme des liens externes et entraînent des erreurs de portée. 15155
- La régénération du site AEM échoue pour les mappages DITA. (14369)

## Gestion

- La propriété **fmditaTopicrefs** affiche des chemins relatifs plutôt que des chemins absolus. 15341
