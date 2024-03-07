---
title: Notes de mise à jour | Correction de problèmes dans la version 4.3.1.5 des guides Adobe Experience Manager
description: Découvrez les correctifs de bogues de la version 4.3.1.5 des Guides Adobe Experience Manager.
role: Leader
source-git-commit: 485f88e2e8724d1dc28deac13d677734fcc15c25
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 2%

---


# Correction de problèmes dans la version 4.3.1.5


Cet article couvre les bogues corrigés dans différentes zones de la version 4.3.1.5 des Guides Adobe Experience Manager.



En savoir plus [instructions de mise à niveau de la version 4.3.1.5](../release-info/upgrade-instructions-4-3-1-5.md).


## Création

- Ajout d’espaces entre les éléments intégrés dans `<codeblock>` provoque un saut de ligne dans la sortie générée. (15247)
- Des problèmes d’expérience se produisent lors de l’ajout d’éléments à partir de la boîte de dialogue &quot;Insérer un élément&quot;. (15108)

## Publication

- Les journaux d’erreurs affichent des informations incorrectes sur la publication de contenu avec des portées externes. (15242)
- Liens internes vers les fichiers DITA commençant par `HTTP` sont traités comme des liens externes et provoquent des erreurs de portée. 15155
- La régénération du site AEM échoue pour les mappages DITA. (14369)

## Gestion

- **fmditaTopicrefs** affiche les chemins relatifs plutôt que les chemins absolus. 15341

