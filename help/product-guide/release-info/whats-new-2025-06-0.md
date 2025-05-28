---
title: Notes de mise à jour | Nouveautés de la version Adobe Experience Manager Guides 2025.06.0
description: Découvrez les fonctionnalités nouvelles et améliorées de la version 2025.06.0 d’Adobe Experience Manager Guides
role: Leader
source-git-commit: 147bd8cce875178f94dae5742bc6573b51f24d3a
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 3%

---

# Nouveautés de la version 2025.06.0 (juin 2025)

Cet article présente les nouvelles fonctionnalités améliorées introduites dans la version 2025.06.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour connaître la liste des problèmes résolus dans cette version, voir la section [Problèmes résolus dans la version 2025.06.0](fixed-issues-2025-06-0.md).

Découvrez les [instructions de mise à niveau pour la version 2025.06.0](../release-info/upgrade-instructions-2025-06-0.md).

## Les fichiers temporaires pour la sortie publiée incluent désormais les URL de création et de publication dans un nouveau fichier de configuration

Les dernières améliorations de publication apportées à Experience Manager Guides ajoutent désormais un nouveau fichier `system_config.json` aux fichiers temporaires générés lors de la publication des sorties HTML, PDF et JSON à l’aide de DITA-OT, ainsi que la sortie Native PDF. Ce fichier est automatiquement inclus dans la tâche de publication et également accessible par le biais de fichiers temporaires lorsque vous activez l’option **Conserver les fichiers temporaires** pour les paramètres prédéfinis et que vous générez la sortie.

Le fichier `system_config.json` contient des détails clés sur l’instance, notamment l’URL de création, l’URL locale et l’URL de publication, qui fournissent un contexte plus clair et améliorent la traçabilité des URL téléchargées.

Pour plus d’informations, consultez la section [Présentation des paramètres prédéfinis de sortie](../user-guide/generate-output-understand-presets.md).

## Invite de temporisation de session pour éviter la perte accidentelle de contenu

Un message pop-up vous avertit désormais lorsque votre session Adobe Experience Manager expire et que vous êtes déconnecté pour cause d’inactivité. Ce message est déclenché lorsque vous tentez de modifier du contenu dans Experience Manager Guides après la fin de la session. Cette fonctionnalité permet de réduire le risque de perdre du travail non enregistré et améliore la fiabilité et la fluidité globales de l’expérience, même pendant les périodes d’inactivité.

![](assets/sign-out-prompt.png)

En savoir plus sur l’[invite de temporisation de session](../user-guide/session-timeout-prompt.md) dans Experience Manager Guides.

## Amélioration des options de téléchargement des cartes dans l’éditeur

Experience Manager Guides introduit une nouvelle option **Utiliser les noms de fichiers réels** dans la boîte de dialogue **Télécharger le mappage**. Désormais, lorsque vous téléchargez des fichiers de mappage, vous pouvez choisir de conserver leurs noms de fichier d’origine au lieu des UUID par défaut, ce qui facilite la reconnaissance et la gestion de vos fichiers. Cette option n’est disponible que si vous sélectionnez **Conserver la hiérarchie de fichiers** et est désactivée lorsque vous choisissez **Aplatir la hiérarchie de fichiers**, ce qui vous offre davantage de flexibilité dans l’organisation des cartes téléchargées.

Pour plus d’informations, voir [Télécharger des fichiers](../user-guide/authoring-download-assets.md#download-a-dita-map-file-from-the-editor).

![](assets/download-map-dialog-new.png){width="300" align="left"}


## Amélioration de la gestion des `navref` dans l’éditeur

Les dernières améliorations apportées à l&#39;éditeur améliorent la gestion des éléments `navref` dans un plan DITA. Désormais, lorsque vous ajoutez un élément de `navref` à une carte, la boîte de dialogue **Sélectionner le chemin** s’ouvre, ce qui vous permet de choisir facilement les références de carte à inclure comme liens de navigation dans votre carte. Une fois ajouté, le titre de la carte ajoutée est affiché en mode Auteur et en mode Mise en page, ce qui offre une meilleure visibilité de la navigation incluse lors de la création.  En outre, l’élément `navref` ajouté est résolu automatiquement pour afficher la carte référencée dans l’éditeur.

Pour plus d’informations, voir [Ajouter des références de navigation](../user-guide/map-editor-other-features.md#add-navigation-references).
