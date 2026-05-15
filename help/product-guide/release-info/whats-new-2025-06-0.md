---
title: Notes de mise à jour | Nouveautés de la version Adobe Experience Manager Guides 2025.06.0
description: Découvrez les fonctionnalités nouvelles et améliorées de la version 2025.06.0 d’Adobe Experience Manager Guides
role: Leader
exl-id: 48f27aa6-d870-4228-8e62-db81699a25f7
TQID: https://experienceleague.adobe.com/Lu9Ebb7OEpxiRmjkho1KnXiry5Kz5kDwfAYbXJD8-uI
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 404
ht-degree: 3%

---

# Nouveautés de la version 2025.06.0 (juin 2025)

Cet article présente les nouvelles fonctionnalités améliorées introduites dans la version 2025.06.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour connaître la liste des problèmes résolus dans cette version, voir la section [Problèmes résolus dans la version 2025.06.0](fixed-issues-2025-06-0.md).

Découvrez les [instructions de mise à niveau pour la version 2025.06.0](../release-info/upgrade-instructions-2025-06-0.md).

## Invite de temporisation de session pour éviter la perte accidentelle de contenu

Un message pop-up vous avertit désormais lorsque votre session Adobe Experience Manager expire et que vous êtes déconnecté pour cause d’inactivité. Ce message est déclenché lorsque vous tentez de modifier du contenu dans Experience Manager Guides après la fin de la session. Cette fonctionnalité permet de réduire le risque de perdre du travail non enregistré et améliore la fiabilité et la fluidité globales de l’expérience, même pendant les périodes d’inactivité.

![](assets/sign-out-prompt.png)

En savoir plus sur l’[invite de temporisation de session](../user-guide/session-timeout-prompt.md) dans Experience Manager Guides.

## Amélioration des options de téléchargement des cartes dans l’éditeur

Experience Manager Guides introduit une nouvelle option **Utiliser les noms de fichiers réels** dans la boîte de dialogue **Télécharger le mappage**. Désormais, lorsque vous téléchargez des fichiers de mappage, vous pouvez choisir de conserver leurs noms de fichier d’origine au lieu des UUID par défaut, ce qui facilite la reconnaissance et la gestion de vos fichiers. Cette option n’est disponible que si vous sélectionnez **Conserver la hiérarchie de fichiers** et est désactivée lorsque vous choisissez **Aplatir la hiérarchie de fichiers**, ce qui vous offre davantage de flexibilité dans l’organisation des cartes téléchargées.

Pour plus d’informations, voir [Télécharger des fichiers](../user-guide/authoring-download-assets.md#download-a-dita-map-file-from-the-editor).

![](assets/download-map-dialog-new.png){width="300"}


## Amélioration de la gestion des `navref` dans l’éditeur

Les dernières améliorations apportées à l&#39;éditeur améliorent la gestion des éléments `navref` dans un plan DITA. Désormais, lorsque vous ajoutez un élément de `navref` à une carte, la boîte de dialogue **Sélectionner le chemin** s’ouvre, ce qui vous permet de choisir facilement les références de carte à inclure comme liens de navigation dans votre carte. Une fois ajouté, le titre de la carte ajoutée est affiché en mode Auteur et en mode Mise en page, ce qui offre une meilleure visibilité de la navigation incluse lors de la création.  En outre, l’élément `navref` ajouté est résolu automatiquement pour afficher la carte référencée dans l’éditeur.

Pour plus d’informations, voir [Ajouter des références de navigation](../user-guide/map-editor-other-features.md#add-navigation-references).

## Améliorations des performances de l’assistant AI

Cette version apporte des améliorations au moteur principal de l’assistant AI, offrant des performances accrues et une plus grande stabilité. Pour activer cette mise à jour et continuer à utiliser l’aide de l’assistant AI :

- Mettez à jour la configuration `chat.url` pour refléter la nouvelle URL de point d’entrée.
- Ajoutez un nouveau `GUIDES_AI_SITE_ID` de variable d’environnement dans Cloud Manager.

Pour plus d’informations, consultez [Configuration de l’assistant d’IA](../cs-install-guide/conf-smart-suggestions.md).

