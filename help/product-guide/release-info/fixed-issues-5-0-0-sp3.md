---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides 5.0.0 Service Pack 3
description: Découvrez les correctifs de bugs dans la version 5.0.0 Service Pack 3 d’Adobe Experience Manager Guides
role: Leader
exl-id: ba915d58-4de8-4c4f-b338-29b64451d60d
TQID: https://experienceleague.adobe.com/qENxN8e84lkLpfHhXwIDcAGINdcqqs4eOZhpiV3DKxA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 128
ht-degree: 0%

---

# Correction de problèmes dans la version 5.0.0 Service Pack 3 (février 2026)


Cet article couvre les bugs corrigés dans différentes zones de la version 5.0.0 Service Pack 3 d’Adobe Experience Manager Guides.

Découvrez les [instructions de mise à niveau pour la version 5.0.0 du pack de services 3](upgrade-instructions-5-0-0-sp3.md).

## Traduction

- Lorsqu’une image initialement gérée en tant que ressource spécifique à la langue avec une version spécifique (par exemple, sous `/en/`) est déplacée vers un dossier global avec une version mise à jour et que l’exportation de la ligne de base est effectuée, la nouvelle ligne de base continue à référencer des versions obsolètes spécifiques à la langue de cette image, ce qui entraîne l’échec de l’exportation de la ligne de base. (GUIDES-39394)
