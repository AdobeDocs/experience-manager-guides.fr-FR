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
source-git-commit: b3c2c68321080aa4dde16befe4bfd0022bf9f61c
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 0%
---
# Assistant IA

>[!NOTE]
>
> La fonctionnalité Assistant AI est actuellement disponible pour Adobe Experience Manager Guides as a Cloud Service.

L’assistant AI d’Adobe Experience Manager Guides est un outil optimisé par l’IA conçu pour améliorer la productivité en simplifiant les workflows de création, de gestion et de création de contenu. Il propose deux modes : Agentic et Standard. En **mode Agence**, l’assistant d’IA vous permet d’effectuer des tâches liées au contenu par le biais d’interactions en langage naturel, avec des compétences telles que l’importation, la création et le balisage intelligent afin de rationaliser la création de contenu, l’organisation et la gestion des métadonnées. En **mode standard**, l’assistant AI fournit une aide à la création qui vous permet de créer, d’affiner et de gérer le contenu plus efficacement.

## Modes de l’assistant AI

AI Assistant est disponible dans deux modes : **Agentic** et **Standard**. Les administrateurs peuvent sélectionner ce mode dans la section **Fonctionnalités d’IA** de l’onglet **Général** dans les paramètres de **Workspace**. Le panneau de l’assistant d’IA dans l’éditeur reste le même dans les deux modes, mais les fonctionnalités disponibles diffèrent :

- **Mode agent :** utilise des compétences **Importer**, **Créer** et **Balisage intelligent** pour convertir des fichiers en rubriques structurées, créer un premier brouillon de contenu et recommander des balises pertinentes en fonction de la taxonomie de votre entreprise.
- **Mode standard :** fournit une aide à la création optimisée par l’IA au moyen d’actions contextuelles, telles que la réutilisation du contenu, la traduction et l’amélioration de la qualité du contenu, afin de rationaliser les workflows de création.

## Mode agent

>[!NOTE]
>
> Pour utiliser l’assistant AI en mode Agence, votre entreprise doit être intégrée à Adobe CX Enterprise Coworker et disposer de crédits disponibles. Une fois l’intégration effectuée, contactez votre équipe du succès client pour activer la fonctionnalité. Pour plus d’informations sur la configuration, voir [Configurer l’assistant AI en mode agent](../install-conf-guide/configure-ai-assistant-agentic-mode-cs.md).

Le mode Agent de l’assistant AI vous permet d’effectuer un large éventail de tâches liées au contenu par le biais d’interactions en langage naturel, telles que la création et l’importation de contenu, la synthèse des rubriques, l’ajout de rubriques aux cartes et la gestion des métadonnées. Vous pouvez décrire vos besoins dans le panneau de conversation. L’assistant AI planifie et exécute des tâches tout en offrant une visibilité sur leur progression. Le mode Agence permet d’accéder rapidement aux compétences suivantes :

- **Importer** : permet de convertir des fichiers PDF, Word ou Markdown de votre appareil ou référentiel de contenu en rubriques structurées. Pour plus d’informations, consultez [Importer du contenu avec l’assistant AI](./import-ai-assistant.md).

- **Créer** : génère des brouillons de rubriques et de cartes à partir de matériaux d’entrée tels que des spécifications, des images de tableau blanc, des captures d’écran et d’autres contenus de référence, avec la possibilité d’utiliser du contenu existant pour le ton et le style. Pour plus d’informations, voir [Créer du contenu avec l’assistant AI](./create-ai-assistant.md).

- **Balisage intelligent** : recommande des balises pertinentes pour les rubriques en fonction de la taxonomie de votre organisation afin d’améliorer la cohérence des métadonnées. Pour plus d’informations, consultez la section [Balisage intelligent avec l’assistant AI](./ai-assistant-agentic.md).

Les composants suivants du panneau de l’assistant d’IA vous permettent d’ajouter du contenu, de saisir des invites et de démarrer des tâches :

![assistant ia - Balisage intelligent](./images/panel-new-agentic.png)

- **(A)** Historique des conversations : affichez et rouvrez les conversations précédentes pour consulter les demandes et réponses précédentes.
- **(B)** Plein écran : développe le panneau de l’assistant d’IA en plein écran.
- **(C)** Espace d’invite : saisissez une demande d’invite ou saisissez `/` pour ajouter des fichiers et générer des balises.
- **(D)** Joindre des fichiers ou ajouter du contexte : permet d’ajouter des rubriques, des cartes ou des fichiers à partir de votre système local pour fournir le contenu avec lequel l’assistant AI travaille.
- **(E)** Envoyer : envoyez votre invite et le contenu joint à l’assistant AI.
- **(F)** Actions rapides : démarrez une tâche directement à partir de l’un des raccourcis suivants : **Importer**, **Créer** ou **Balise**.

## Mode standard

Le mode standard rend votre processus de création plus intelligent et plus rapide. Lorsque vous sélectionnez du texte dans l’éditeur, l’assistant d’IA propose des actions rapides, telles que la génération de suggestions intelligentes pour la réutilisation du contenu, la traduction du contenu, l’amélioration de la qualité du contenu, etc., le tout en fonction du contenu que vous avez sélectionné. Cela améliore l’expérience globale de création et la productivité des créateurs et des créatrices.

Pour plus d’informations, consultez la section [Créer des documents avec l’assistant AI](./ai-assistant-right-panel.md).

![assistant ia](./images/ai-assistant-panel.png)


## Commencer avec l’assistant IA

Lorsque vous utilisez l’assistant **AI** pour la première fois, vous êtes invité à envoyer votre consentement avant d’utiliser les fonctionnalités de l’IA générative Experience Manager Guides.

Pour lancer l’assistant AI, procédez comme suit :

1. Connectez-vous à Experience Manager Guides.
1. Sur la page d’accueil, sélectionnez **Assistant AI** dans la partie supérieure. Assurez-vous que votre administrateur a activé la fonction Assistant AI dans le mode souhaité.
L’assistant AI affiche les fonctionnalités clés, un lien destiné aux utilisateurs et un bouton **Commencer**.
1. Lisez attentivement les directives d’utilisation, puis sélectionnez **Commencer** pour lancer l’assistant d’IA.

>[!NOTE]
>
>Si vous avez déjà consenti aux instructions pour l’utilisation de la fonctionnalité d’assistant d’aide, vous ne serez pas invité à donner à nouveau votre consentement et vous pourrez continuer à utiliser la fonctionnalité d’assistant d’IA.

**Rubriques connexes**

[FAQ sur la sécurité de l’assistant AI](./ai-assistant-faq.md)

[Divulgations d’Adobe Experience Manager Guides Generative AI](./adobe-generative-ai-disclosures.md)

[Configurer l’assistant AI pour l’aide et la création intelligentes](../cs-install-guide/conf-smart-suggestions.md)
