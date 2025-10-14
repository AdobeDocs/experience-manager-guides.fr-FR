---
title: Notes de mise à jour | Nouveautés de la version Adobe Experience Manager Guides 2025.08.0
description: Découvrez les fonctionnalités nouvelles et améliorées de la version 2025.08.0 d’Adobe Experience Manager Guides
role: Leader
exl-id: c3461d0a-6394-4275-9d54-b2b1545d7c18
source-git-commit: 1a44af3522060ebc531393d4d01b1cd00eb02c10
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 2%

---

# Nouveautés de la version 2025.08.0 (août 2025)

Cet article présente les nouvelles fonctionnalités améliorées introduites dans la version 2025.08.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour connaître la liste des problèmes résolus dans cette version, voir la section [Problèmes résolus dans la version 2025.08.0](fixed-issues-2025-08-0.md).

Découvrez les [instructions de mise à niveau pour la version 2025.08.0](../release-info/upgrade-instructions-2025-08-0.md).


## Workflow de révision amélioré

Avec cette version, le workflow de révision a été considérablement amélioré afin de mieux prendre en charge la communication transparente entre les auteurs et les réviseurs. Les principales mises à jour sont les suivantes :

- Workflows de gestion des tâches avec notifications exploitables
- Possibilité de baliser les utilisateurs pour demander une attention immédiate
- Accès aux détails des projets et des tâches depuis le panneau de révision pour plus de facilité d’utilisation

Grâce à ces améliorations, les utilisateurs peuvent maintenant s’attendre à :

- Cycles d’examen efficaces et opportuns
- Réduction de l’effort manuel lors des échanges de commentaires

Pour plus d’informations, voir [Présentation de la révision](../user-guide/review.md)

## Actions configurables de l’assistant d’IA dans les paramètres de l’éditeur

La dernière mise à jour introduit une configuration améliorée pour les **actions rapides de création** dans l’assistant AI, ce qui permet aux administrateurs de personnaliser l’environnement de création en fonction de workflows et de préférences spécifiques.

Une fois que le bouton (bascule) **Assistant IA** est activé, les administrateurs peuvent sélectionner de manière sélective les actions rapides visibles sous l’onglet **Création**, ce qui permet de rationaliser les interactions de création. Ces paramètres de visibilité sont spécifiques à chaque profil de dossier.

En savoir plus sur l’assistant [AI dans les paramètres de l’éditeur](../cs-install-guide/workspace-settings.md#general) dans Experience Manager Guides.

![](assets/authoring-quick-actions.png){width="350" align="left"}


## Amélioration de l’expérience de création et d’utilisation des fichiers DITAVAL

Cette mise à jour introduit plusieurs améliorations qui simplifient la création, la gestion et l’application des fichiers DITAVAL, permettant un meilleur contrôle du contenu conditionnel et du style sur les sorties.

Les principaux points forts sont les suivants :

- **Prise en charge améliorée des indicateurs dans la création de fichiers DITAVAL :** Experience Manager Guides offre de nouvelles fonctionnalités de personnalisation de la publication de contenu grâce à la prise en charge améliorée des indicateurs dans les fichiers DITAVAL. Vous pouvez désormais appliquer des indicateurs de début et de fin à un contenu spécifique, y compris des images, et enrichir les sections marquées avec des options de mise en forme telles que le gras, l’italique, etc. Pour gérer les chevauchements de conditions, le **conflit de style** peut être configuré, ce qui inclut la définition d’une couleur d’arrière-plan et de texte par défaut, afin de garantir la clarté et la cohérence de la sortie. Ces indicateurs sont entièrement pris en charge dans la génération du PDF natif et la sortie qui en résulte reflète précisément et entièrement tous les éléments de style appliqués.
Pour plus de détails, voir [Utiliser l&#39;éditeur DITAVAL](../user-guide/ditaval-editor.md).

  ![](assets/ditaval-flag-style-new.png){width="350" align="left"}

- **Prise en charge de plusieurs fichiers DITAVAL pour Native PDF :** pour Native PDF, il est désormais possible d’ajouter plusieurs fichiers DITAVAL, chacun affiché en tant qu’entrée balisée pour une identification et une suppression faciles, offrant ainsi une plus grande flexibilité et un meilleur contrôle du contenu conditionnel dans les sorties PDF

  En outre, cette mise à jour améliore la création de paramètres prédéfinis de sortie en activant les champs DITAVAL modifiables dans tous les formats, ce qui permet aux utilisateurs de spécifier manuellement des chemins DITAVAL.

  Pour plus d’informations, consultez la section [Présentation des paramètres prédéfinis de sortie](../user-guide/generate-output-understand-presets.md) dans Experience Manager Guides.

## Amélioration du filtrage du journal de génération de sortie

Cette version apporte des améliorations à l’interface utilisateur de la fonctionnalité de filtrage des journaux de génération de sortie. Vous pouvez désormais mieux filtrer les journaux de génération de sortie pour les quatre niveaux distincts : **Info**, **Avertissement**, **Erreur** (y compris les erreurs et les exceptions) et **Fatal** ; avec des indicateurs améliorés et intuitifs avec code de couleur qui simplifient l’analyse et améliorent la visibilité sur le flux de journaux. Cette amélioration vous permet de parcourir les journaux plus efficacement et de localiser les problèmes critiques avec précision.

Pour plus d’informations, consultez la section [Dépannage de base](../user-guide/generate-output-basic-troubleshooting.md).

![](./assets/log-file-new.png){align="left"}


## Les fichiers temporaires pour la sortie publiée incluent désormais les URL de création et de publication dans un nouveau fichier de configuration

Les dernières améliorations de publication apportées à Experience Manager Guides ajoutent désormais un nouveau fichier `system_config.xml` aux fichiers temporaires générés lors de la publication des sorties HTML, PDF et JSON à l’aide de DITA-OT, ainsi que la sortie Native PDF. Ce fichier est automatiquement inclus dans la tâche de publication et également accessible par le biais de fichiers temporaires lorsque vous activez l’option **Conserver les fichiers temporaires** pour les paramètres prédéfinis et que vous générez la sortie.

Le fichier `system_config.xml` contient les détails de l’instance AEM, y compris l’URL de création, l’URL locale et l’URL de publication, ce qui permet de clarifier le contexte et d’améliorer la traçabilité des URL téléchargées.

Pour plus d’informations, consultez la section [Présentation des paramètres prédéfinis de sortie](../user-guide/generate-output-understand-presets.md).

## Nouvelle prise en charge des variables de chemin de sortie pour la génération de sortie

Cette mise à jour introduit une configuration `output path` dynamique pour les paramètres prédéfinis de sortie tels que Native PDF, DITA-OT PDF, JSON, HTML5 et Custom. Au lieu d’utiliser un chemin fixe, les utilisateurs et utilisatrices peuvent désormais définir l’emplacement de sortie à l’aide de la variable `${base_output_path}` lors de l’installation, offrant ainsi une plus grande flexibilité. Le chemin d’accès par défaut précédent `/content/dam/fmdita-outputs` n’est plus obligatoire.

Tous les chemins de sortie associés aux paramètres prédéfinis de profil de dossier global seront automatiquement migrés pour utiliser la nouvelle variable de chemin de sortie de base. Toutefois, pour les profils de dossiers personnalisés, la migration n’est pas automatique. Nous vous conseillons de contacter l’équipe du succès client pour obtenir de l’aide.

Pour plus d’informations, consultez la section [Présentation des paramètres prédéfinis de sortie](../user-guide/generate-output-understand-presets.md).

## Améliorations de l’interface utilisateur dans la barre d’outils de l’éditeur et les préférences utilisateur

Avec cette version, les paramètres des onglets **Préférences utilisateur** Page d’accueil pour Général et Apparence ont été restructurés. Vous pouvez notamment renommer le libellé **Ouverture des préférences pour les cartes** et déplacer le bouton (bascule) Espaces insécables vers la barre d’outils de l’éditeur.

En outre, dans la barre d’outils de l’éditeur, certains boutons d’accès rapide permettant d’activer ou de désactiver le suivi des modifications, des balises et des espaces insécables sont désormais regroupés sous l’option **Afficher** dans la liste déroulante Menu pour une meilleure utilisation.

Pour plus d’informations, voir [Barre d’outils dans l’éditeur](../user-guide/web-editor-toolbar.md#menu-dropdown).
