---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides 5.1.0 Service Pack 1
description: Découvrez les correctifs de bugs dans la version 5.1.0 Service Pack 1 d’Adobe Experience Manager Guides
role: Leader
exl-id: 4b51085b-1f71-41e2-b0a9-88a12990fc97
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 144
ht-degree: 1%

---

# Correction de problèmes dans la version 5.1.0 Service Pack 1 (octobre 2025)


Cet article couvre les bugs corrigés dans différentes zones de la version 5.1.0 Service Pack 1 d’Adobe Experience Manager Guides.

Découvrez les [instructions de mise à niveau pour la version 5.1.0 du pack de services 1](upgrade-instructions-5-1-0-sp1.md).


## Plateforme

- Lors de la migration de non-UUID vers UUID et de la mise à niveau vers la dernière version (5.0+), si vous déplacez les images référencées entre des dossiers, puis ramenez les fichiers DITA (où ces images ont été référencées) vers des versions précédentes, cela entraîne des références d&#39;image rompues. (GUIDES-34315)

## Publication

- Lors de la publication d&#39;un plan DITA à l&#39;aide de la ligne de base sur AEM Sites (avec le mappage de composant hérité), les éléments de plan avec l&#39;attribut `processing-role = resource-only` sont également publiés. (GUIDES-34298)
