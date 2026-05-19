---
title: Notes de mise à jour | Nouveautés d’Adobe Experience Manager Guides 5.1.0 Service Pack 3
description: Découvrez les fonctionnalités nouvelles et améliorées de la version 5.1.0 Service Pack 3 d’Adobe Experience Manager Guides
role: Leader
exl-id: 1b2e45a8-bea6-4b78-bd2e-cc02df86f40a
TQID: https://experienceleague.adobe.com/dXXQ1YvVduT11vvF5qyXHLqnuo1xMKkAb5I-EoD2JAA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 176
ht-degree: 0%

---

# Nouveautés de la version 5.1.0 Service Pack 3 (décembre 2025)

Cet article présente les nouvelles fonctionnalités améliorées introduites dans la version 5.1.0 du Service Pack 3 d’Adobe Experience Manager Guides.

Pour obtenir la liste des problèmes qui ont été résolus dans cette version, voir [Problèmes résolus dans le pack de services 3 d’ 5.1.0](fixed-issues-5-1-0-sp3.md).

Découvrez les [instructions de mise à niveau pour la version 5.1.0 du pack de services 3](../release-info/upgrade-instructions-5-1-0-sp3.md).


## Configuration de rendus d’image personnalisés pour des paramètres prédéfinis de sortie spécifiques

Vous pouvez désormais configurer différents rendus d’image pour les paramètres prédéfinis de sortie individuels sous le même type de sortie à l’aide de l’attribut `outputName` dans `renditionmapping.xml`. Cette amélioration vous offre une plus grande flexibilité lors de la publication de contenu qui nécessite différentes résolutions d’image selon les scénarios. Par exemple, vous pouvez souhaiter une image haute résolution pour votre sortie HTML5 principale tout en utilisant une miniature plus petite pour un paramètre prédéfini léger.

Pour plus d’informations, consultez la section [Gérer le rendu d’image dans la génération de sortie](../install-guide/conf-output-generation.md#handle-image-rendition-during-output-generation).
