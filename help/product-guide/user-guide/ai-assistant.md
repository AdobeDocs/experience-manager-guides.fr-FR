---
title: Utiliser l’assistant AI pour créer des documents de manière intelligente « »
description: Découvrez comment utiliser l’assistant d’IA pour rechercher et créer des documents intelligemment dans Adobe Experience Manager Guides.
exl-id: c18e8761-333e-40ef-9e16-e71a194a754a
TQID: https://experienceleague.adobe.com/pg9zeEg8m3NeDbN-j945SqPbaMX0GgBmuquAsQcrjOM
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: ec4263d9-bf7c-44c7-b3f1-3e664861c8f2
    internal-label: Generative AI
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
    internal-label: Content reuse
source-git-commit: 71ddd55d2a6848449d5810701b60e9f69a29112b
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 0%
---
# Assistant AI (Beta)

L’**assistant AI** d’Adobe Experience Manager Guides est un puissant outil piloté par l’IA qui a été conçu pour améliorer votre productivité grâce à des fonctionnalités intelligentes d’aide, de création et de balisage. En mode **Standard**, il rassemble deux puissantes fonctionnalités d’IA : **Création** et **Aide** dans l’interface de Experience Manager Guides, ce qui vous permet de créer du contenu et d’accéder plus rapidement et plus efficacement aux informations de la documentation de Experience Manager Guides. En mode **Agentic**, l’assistant AI propose plutôt le **balisage intelligent**, qui vous permet de demander, par le biais d’une fenêtre d’invite de conversation, des recommandations de balises pour votre contenu et de les appliquer à une ou plusieurs rubriques.

>[!NOTE]
>
> La fonctionnalité Assistant AI est actuellement disponible pour Adobe Experience Manager Guides as a Cloud Service.

## Modes de l’assistant AI

>[!NOTE]
>
>Pour activer l’assistant AI en mode Agence pour votre environnement, contactez l’équipe du succès client.

AI Assistant est disponible dans deux modes : **Agentic** et **Standard**. Les administrateurs peuvent choisir entre les deux modes dans la section **Assistant IA** de l’onglet **Général** dans les paramètres de **Workspace**. Le panneau de l’assistant d’IA reste le même dans les deux modes de l’éditeur, mais les fonctionnalités disponibles diffèrent :

* Le mode **Agentic** utilise les compétences **Balisage intelligent** d’Adobe CX Enterprise Coworker pour analyser votre contenu et recommander des balises pertinentes en fonction de la taxonomie de votre organisation.
* Le mode **Standard** fournit l’expérience de l’assistant AI existant, avec les onglets **Aide** et **Création** dans le panneau de l’assistant AI.

## Mode agent

### Balisage intelligent

L’assistant d’IA en mode Agence accélère et facilite le balisage de votre contenu par le biais d’une fenêtre d’invite de conversation. Grâce aux compétences de balisage intelligent dynamique d’Adobe CX Enterprise Coworker, l’assistant AI recommande des balises pertinentes pour votre contenu lorsque vous le demandez. Pour garder le contrôle, examinez les balises suggérées et choisissez de les appliquer à une ou plusieurs rubriques, y compris plusieurs rubriques dans une carte.

Pour plus d’informations, consultez la section [Prise en main de l’assistant IA dédiée aux agences](./ai-assistant-agentic.md).

![assistant ia - Balisage intelligent](./images/suggested-prompts.png)

## Mode standard

### Création

Lorsque l’assistant AI est configuré en mode **Standard**, la fonctionnalité **Création** de l’assistant AI rend votre processus de création plus intelligent et plus rapide. Il propose des fonctionnalités telles que la génération de suggestions intelligentes pour la réutilisation du contenu, la traduction du contenu, l’amélioration de la qualité du contenu, etc., le tout en fonction du contenu que vous avez sélectionné. Cette fonctionnalité améliore l’expérience globale de création et la productivité des créateurs et des créatrices.

Pour plus d’informations, voir [Création](./ai-assistant-right-panel.md).

![assistant ia](./images/ai-assistant-panel.png)

### Aide

Lorsque l’assistant AI est configuré en mode **Standard**, la fonctionnalité **Aide** offre une expérience intuitive basée sur les conversations qui vous aide à comprendre Experience Manager Guides, à résoudre les problèmes et à trouver des informations dans la documentation d’Adobe Experience Manager Guides. Au lieu d’effectuer des recherches dans des guides de l’utilisateur et des documents de référence, vous pouvez utiliser la fonction **Aide** pour trouver rapidement des réponses pertinentes à vos requêtes. Cela vous permet de gagner du temps et de vous concentrer sur la création de contenu, ce qui se traduit par une productivité et une efficacité accrues.

Pour plus d’informations, voir [Aide](./ai-based-smart-help.md).


![Panneau d’aide dynamique](images/smart-help-panel.png)

## Prise en main de l’assistant AI en mode standard

Lorsque vous utilisez l’assistant **AI** en mode standard pour la première fois, vous êtes invité à envoyer votre consentement avant d’utiliser les fonctionnalités de l’IA générative Experience Manager Guides.

Pour lancer l’assistant AI, procédez comme suit :

1. Connectez-vous à Experience Manager Guides.
1. Sur la page d’accueil, sélectionnez **Assistant AI** dans la partie supérieure. Assurez-vous que votre administrateur a activé la fonction Assistant AI dans le mode souhaité.

L’assistant AI affiche les fonctionnalités clés, un lien destiné aux utilisateurs et un bouton **Commencer**.

![Panneau d’aide dynamique](images/get-started-ai.png)

Lisez attentivement les directives d’utilisation, puis sélectionnez **Commencer** pour lancer l’assistant d’IA.

**Rubriques connexes**

[FAQ sur la sécurité de l’assistant AI](./ai-assistant-faq.md)

[Divulgations d’Adobe Experience Manager Guides Generative AI](./adobe-generative-ai-disclosures.md)

[Configurer l’assistant AI pour l’aide et la création intelligentes](../cs-install-guide/conf-smart-suggestions.md)
