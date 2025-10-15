---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides 5.1.0 Service Pack 1
description: Découvrez les correctifs de bugs dans la version 5.1.0 Service Pack 1 d’Adobe Experience Manager Guides
role: Leader
source-git-commit: 575488e1b378c17419add75876a8e7f7423d5116
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 1%

---

# Correction de problèmes dans la version 5.1.0 Service Pack 1 (octobre 2025)


Cet article couvre les bugs corrigés dans différentes zones de la version 5.1.0 Service Pack 1 d’Adobe Experience Manager Guides.

Découvrez les [instructions de mise à niveau pour la version 5.1.0 du pack de services 1](upgrade-instructions-5-1-0-sp1.md).


## Plateforme

- Lors de la migration de non-UUID vers UUID et de la mise à niveau vers la dernière version (5.0+), si vous déplacez les images référencées entre des dossiers, puis ramenez les fichiers DITA (où ces images ont été référencées) vers des versions précédentes, cela entraîne des références d&#39;image rompues. (GUIDES-34315)

## Publication

- Lors de la publication d&#39;un plan DITA à l&#39;aide de la ligne de base sur AEM Sites (avec le mappage de composant hérité), les éléments de plan avec l&#39;attribut `processing-role = resource-only` sont également publiés. (GUIDES-34298)
