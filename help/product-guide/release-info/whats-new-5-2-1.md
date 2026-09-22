---
title: Notes de mise à jour | Nouveautés d’Adobe Experience Manager Guides 5.2.0 Service Pack 1
description: Découvrez les fonctionnalités nouvelles et améliorées de la version 5.2.0 Service Pack 1 d’Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/dXXQ1YvVduT11vvF5qyXHLqnuo1xMKkAb5I-EoD2JAA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: 788d0b9a2e2f07d2990bcc4f984f3ba4a4aabf17
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 0%
---
# Nouveautés de la version 5.2.0 Service Pack 1 (septembre 2026)

Cet article présente les nouvelles fonctionnalités améliorées introduites dans la version 5.2.0 du Service Pack 1 d’Adobe Experience Manager Guides.

Pour obtenir la liste des problèmes qui ont été résolus dans cette version, voir [Problèmes résolus dans le pack de services 1 d’ 5.2.0](fixed-issues-5-2-0-sp1.md).

Découvrez les [instructions de mise à niveau pour la version 5.2.0 du Service Pack 1](../release-info/upgrade-instructions-5-2-0-sp1.md).


## Experience Manager Guides ajoute la prise en charge de MCP

Experience Manager Guides prend désormais en charge le protocole MCP (Model Context Protocol). Vous pouvez connecter vos outils d’IA tels que Claude, Cursor et d’autres à Guides sans avoir à effectuer de travail personnalisé. Grâce à un seul point d’entrée MCP, dans cette version, les utilisateurs authentifiés peuvent utiliser Guides en tant que système découplé et gérer les rubriques et les cartes, créer et exporter des lignes de base et générer des rapports, tout en utilisant leurs autorisations AEM existantes. Cela permet aux équipes de documentation de travailler plus efficacement à l’aide des applications et des agents d’IA.

Pour plus d’informations, consultez la section [Utilisation du serveur Adobe Experience Manager Guides MCP](../install-conf-guide/conf-aem-guides-mcp.md).


## Prise en charge des sources de données externes et des citations désormais disponibles dans le nouvel éditeur

Le nouvel éditeur prend désormais en charge deux fonctionnalités Experience Manager Guides existantes : la possibilité de se connecter à des sources de données externes et d’utiliser des citations dans les documents.

Les auteurs peuvent continuer à utiliser les sources de données externes configurées lors de la création ou de la mise à jour de contenu dans le nouvel éditeur. Les citations sont également prises en charge, de sorte que les auteurs peuvent ajouter et gérer des références dans leur contenu sans changer d’éditeur.

## Prise en charge du style de citation AMA

Experience Manager Guides prend désormais en charge le style de citation de l’American Medical Association (AMA), en étendant le cadre de citation existant pour répondre aux normes de documentation requises par les clients des secteurs de la santé, de la réglementation et des sciences de la vie.

Lorsque AMA est sélectionné comme style de citation dans les paramètres **&#x200B;**, les citations sont automatiquement formatées conformément aux directives AMA, y compris le rendu numérique d&#39;exposant, la numérotation séquentielle et l&#39;ordre précis de la liste de référence. L’option **Analyser les citations** dans l’éditeur de texte enrichi est disponible exclusivement lorsque l’option AMA est sélectionnée, ce qui permet aux auteurs d’ajouter et d’analyser les citations sans changer de contexte.

Le style de citation AMA est pris en charge dans les formats de sortie Native PDF et AEM Sites. Pour configurer le style de citation, accédez aux paramètres de **&#x200B;**&#x200B;puis sélectionnez AMA dans les options de style de citation. Pour plus d’informations, consultez la section [Utilisation de citations](../user-guide/web-editor-apply-citations.md).


