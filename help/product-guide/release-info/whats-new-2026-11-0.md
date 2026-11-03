---
title: Notes de mise à jour | Nouveautés de la version Adobe Experience Manager Guides 2026.11.0
description: Découvrez les nouvelles fonctionnalités de la version 2026.11.0 d’Adobe Experience Manager Guides, notamment l’embranchement au niveau de la carte et la création de contenu de l’assistant d’IA.
role: Leader
source-git-commit: ef5e433214f15b12102af7c9e38031536183ca72
workflow-type: tm+mt
source-wordcount: '1512'
ht-degree: 0%
---

# Nouveautés de la version 2026.11.0 (novembre 2026)

Cet article présente les nouvelles fonctionnalités améliorées introduites dans la version 2026.11.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour obtenir la liste des problèmes résolus dans cette version, voir [Problèmes résolus dans la version 2026.11.0](fixed-issues-2026-11-0.md).

Découvrez les [instructions de mise à niveau pour la version 2026.11.0](../release-info/upgrade-instructions-2026-11-0.md).

## Présentation de l’embranchement et de la fusion au niveau de la carte

Adobe Experience Manager Guides introduit une fonctionnalité d’embranchement et de fusion au niveau de la carte, ce qui permet aux auteurs de travailler sur plusieurs versions de documentation, mises à jour de fonctionnalités et correctifs critiques en parallèle sans affecter le contenu principal. Les auteurs peuvent créer des branches isolées d&#39;un plan DITA et de ses dépendances, en s&#39;assurant que les modifications, les verrous et les aperçus restent spécifiques à chaque branche.

Cette fonctionnalité permet aux équipes de documentation de gérer les flux de travail parallèles, de collaborer efficacement et de maintenir la stabilité de la version de documentation principale. Vous pouvez :

- **Créez des branches** à partir de la version principale d&#39;un plan DITA pour travailler indépendamment sur des fonctionnalités, des améliorations ou des correctifs critiques.
- **Basculer entre les branches** dans l’éditeur pour gérer plusieurs versions de documentation.
- **Gérez les versions de contenu** pour organiser les modifications par embranchement et fusion.
- **Résolvez les conflits de fusion** à l’aide d’un workflow de comparaison guidée avec fusion à trois.
- **Fusionner les modifications** dans la version principale.
- **Publication directe à partir d’une branche** à l’aide de la publication standard sans modifier la version principale.

En savoir plus sur [Branchement et fusion](../user-guide/branching-overview.md).

![](./assets/branching.png){width="650"}


## Compétences en création et importation de contenu optimisées par l’IA dans l’assistant AI

>[!NOTE]
>
>Pour utiliser l’assistant AI en mode Agence, votre entreprise doit être intégrée à Adobe CX Enterprise Coworker et disposer des crédits requis.

Vous pouvez désormais utiliser l&#39;**assistant AI** pour créer et importer du contenu DITA à l&#39;aide d&#39;invites en langage naturel. Optimisées par **&#x200B;**, les nouvelles compétences **Créer** et **Importer** simplifient la création de contenu structuré et aident les auteurs à travailler avec du contenu DITA sans avoir besoin d&#39;une expertise approfondie de DITA.

- **Créer :** génère des rubriques et des mappages DITA à partir d&#39;invites en langage naturel, de documents de référence ou de contenu existant à l&#39;aide de modèles de référentiel. Vous pouvez réviser le contenu généré avant de l’enregistrer et affiner de manière itérative le contenu nouveau ou existant pour répondre à vos besoins.
- **Importer :** permet de convertir des fichiers PDF, DOCX ou Markdown existants en rubriques et mappages DITA structurés. Vous pouvez prévisualiser et réviser le contenu converti avant de l’enregistrer dans le référentiel.
- **Balisage intelligent :** obtenez des recommandations de balises pertinentes pour votre contenu en fonction de la taxonomie de votre organisation. L’expérience améliorée permet aux administrateurs de profils de dossiers de configurer des espaces de noms de taxonomie dans les paramètres Workspace, assurant ainsi des recommandations de balises cohérentes et régies.

Le panneau **Assistant IA** introduit également un mode plein écran et une section **Conversations actives** pour une expérience de conversation améliorée.

Pour plus d’informations, consultez [Utilisation de l’assistant AI en mode Agence](../user-guide/ai-assistant.md#agentic-mode).

![](./assets/preview-import.png){width="650"}


## Nouveau panneau d’aide d’Experience Manager Guides

La fonctionnalité d’**aide intelligente** générée par l’IA est disponible via le panneau dédié **assistant d’aide**, accessible à partir des interfaces Page d’accueil, Éditeur et Console de cartes. Le panneau offre une expérience de recherche conversationnelle, ce qui vous permet de poser des questions en langage naturel et de trouver rapidement des informations pertinentes à partir de la documentation de Experience Manager Guides. Vous pouvez ainsi accéder à des conseils contextuels et résoudre des requêtes sans quitter l’éditeur, ce qui vous permet de rationaliser votre workflow de création.

Les administrateurs peuvent gérer la disponibilité du panneau d’aide via les paramètres de Workspace. La section **Assistant d’aide AI** comprend un bouton (bascule) permettant d’activer ou de désactiver le panneau pour les utilisateurs.

Pour plus d’informations, voir [Assistant d’aide](../user-guide/ai-based-smart-help.md).

![](./assets/help-assistant.png){width="650"}

## Améliorations de la création

### Panneau Suivi des modifications dans le nouvel éditeur

Le panneau **Suivi des modifications** est désormais disponible dans le nouvel éditeur, ce qui vous permet d’afficher toutes les insertions et suppressions suivies au sein d’une rubrique. Vous pouvez effectuer le suivi des modifications apportées par plusieurs utilisateurs et utilisatrices et accepter ou refuser les modifications directement à partir du panneau.

Vous pouvez également contrôler l’affichage du contenu supprimé dans l’éditeur à l’aide du paramètre **Afficher les suppressions suivies en ligne** qui vous permet d’afficher le contenu supprimé sous forme de texte barré ou de le remplacer par une icône en forme de crayon liée à la modification correspondante. En savoir plus sur le [suivi des modifications](../user-guide/config-editor-settings.md#track-changes).

![&#x200B; Paramètres de l’éditeur &#x200B;](./assets/track-changes-all.png){width="650"}

### Trier des fichiers et des dossiers dans le panneau de l’explorateur

Le panneau **Explorateur** de l’éditeur vous permet de trier les fichiers et les dossiers par ordre croissant ou décroissant à l’aide du bouton **Trier**. Par défaut, les éléments sont triés dans l’ordre croissant par titre ou nom de fichier, en fonction du paramètre **Affichage des fichiers de l’éditeur** dans **Préférences utilisateur**. Cela facilite la navigation et la localisation du contenu dans l’éditeur.

Pour plus d’informations, consultez la section [Explorateur](../user-guide/paginated-loading-assets.md#explorer) dans Chargement paginé de fichiers et de dossiers.

### Gérer les versions et les libellés des fichiers non DITA à partir de l&#39;éditeur

Experience Manager Guides vous permet d’afficher l’historique des versions et de gérer les libellés de version des fichiers non DITA, tels que les fichiers images, multimédias, ZIP, PDF et DOCX, directement à partir de l’éditeur. Vous pouvez prévisualiser ces fichiers, consulter leur historique de versions, comparer des versions et revenir à une version antérieure sans accéder à l’interface utilisateur d’Assets. Vous pouvez également appliquer ou mettre à jour des libellés de version pour les versions de fichiers existantes afin de simplifier l’identification et la gestion des versions.

Pour plus d&#39;informations, voir [Utiliser des fichiers multimédias et autres fichiers non DITA](../user-guide/authoring-file-management.md#work-with-media-and-other-non-dita-files).


![&#x200B; Paramètres de l’éditeur &#x200B;](./assets/version-management-non-dita-files.png){width="650"}


## Améliorations de la révision

### Collaboration améliorée en matière de révision avec les commentaires de l’initiateur ou de l’initiatrice

Les initiateurs de révision peuvent ajouter des commentaires et des annotations intégrés aux rubriques d’une tâche de révision à l’aide de l’interface utilisateur de révision. Cela leur permet de fournir un contexte supplémentaire, de mettre en évidence un contenu spécifique et d’attirer l’attention des réviseurs et des réviseuses sur les domaines nécessitant des commentaires.

Ces commentaires apparaissent dans le panneau **Commentaires** avec les commentaires des autres réviseurs et réviseuses, offrant ainsi une vue d’ensemble des discussions relatives à la révision. Les réviseurs reçoivent également une notification AEM lorsque l’initiateur ajoute un commentaire, ce qui permet de rationaliser la collaboration et la communication tout au long du processus de révision. Pour plus d’informations, voir [Ajouter des commentaires pour les réviseurs](../user-guide/review-send-topics-for-review.md#add-comments-for-reviewers).

## Améliorations de la publication

### Afficher et gérer l’historique de sortie à partir de la console de mappage

La console Mappage de Experience Manager Guides comprend désormais un onglet **Historique de sortie** qui vous permet d’afficher et de gérer les tâches de génération de sortie directement à partir de l’éditeur sans avoir à accéder au tableau de bord Mappage.

L’onglet fournit une vue consolidée des tâches de génération de sortie, y compris leur statut, les détails du préréglage, la date de génération et la durée. Vous pouvez rechercher et filtrer des tâches, annuler des générations en cours, accéder aux sorties et aux journaux générés et supprimer des entrées terminées de l’historique. Vous pouvez également exporter l’historique de sortie au format CSV pour effectuer une analyse plus approfondie. Les statuts de génération de sortie utilisent des indicateurs de couleur cohérents avec le tableau de bord de la carte.

Pour plus d’informations, consultez [Gérer le processus de génération de sortie](../user-guide/generate-output-manage-process.md#view-and-manage-output-generation-tasks-from-the-editor).

![&#x200B; Paramètres de l’éditeur &#x200B;](./assets/output-history-editor-view.png){width="650"}


### Amélioration des options de purge de l’historique de sortie

Vous pouvez purger l’historique de sortie **Par âge** (en supprimant les entrées datant de plus d’un nombre de jours spécifié) ou **Par nombre** (en conservant uniquement un nombre spécifié d’entrées récentes).

Vous pouvez également choisir de purger uniquement les journaux de sortie tout en conservant les entrées d’historique à des fins d’audit ou de supprimer les journaux et les entrées associées. Ces options permettent d’optimiser le stockage du référentiel tout en offrant un meilleur contrôle sur la purge de l’historique de sortie.

Pour plus d’informations, consultez [Configuration de la période de purge automatique pour l’historique de sortie](../install-conf-guide/conf-output-generation.md#configure-auto-purging-period-for-output-history-id19aai070v8q).

### Prise en charge de GitLab pour les profils de publication Edge Delivery Services

La publication Edge Delivery Services prend en charge les référentiels hébergés par GitLab à côté de GitHub, offrant ainsi une plus grande flexibilité dans la gestion et la publication du contenu DITA. Pour effectuer une publication sur un site hébergé par GitLab, sélectionnez GitLab comme type de serveur lors de la création d’un profil de publication Edge Delivery Services et fournissez le jeton d’accès au projet du référentiel dans le champ Jeton d’accès .

Les paramètres prédéfinis de publication incluent également un champ pour un sous-dossier, afin que vous puissiez publier du contenu dans un sous-dossier au sein du dossier racine spécifié dans le profil.

Pour plus d’informations, consultez [Configuration d’un Edge Delivery Services](../knowledge-base/publishing/configure-eds.md).

### Améliorations apportées à la publication sur Salesforce

Experience Manager Guides améliore la publication Salesforce, ainsi que la sécurité, les performances et l’efficacité de publication. Ces améliorations comprennent la prise en charge de la clé de vérification pour l’échange de code (PKCE), l’authentification par jeton d’actualisation, l’état de publication au niveau de l’article, les journaux de publication détaillés, l’historique de sortie et la publication optimisée des ressources pour réduire les chargements redondants.

Pour plus d’informations, consultez la section [Publication Salesforce améliorée à l’aide du traitement principal](../user-guide/web-editor-article-publishing.md#enhanced-salesforce-publishing-using-backend-processing).


### Prise en charge des images à partir des métadonnées de carte dans Native PDF

La publication native de PDF prend en charge l&#39;affichage dynamique des images définies dans les métadonnées des plans DITA, des bookmaps et des plans personnalisés. Vous pouvez utiliser un modèle PDF unique sur plusieurs mappages tout en affichant des images spécifiques aux mappages, telles que les images de couverture de produit, dans la sortie générée.

En ajoutant un espace réservé pour l’image à la mise en page, vous pouvez le remplir automatiquement avec l’image référencée dans les métadonnées de carte lors de la publication. Cela élimine la nécessité de conserver des modèles distincts pour différentes images et simplifie la gestion des modèles.

Pour plus d’informations, voir [Ajouter une image à partir des métadonnées de carte](../native-pdf/design-page-layout.md#add-an-image-from-map-metadata-add-image-map-metadata).

### Valider la qualité du contenu avec le contrôle de l’intégrité du contenu dans l’ancien éditeur

Le contrôle de l&#39;intégrité du contenu est disponible dans l&#39;ancien éditeur (déjà pris en charge par le nouvel éditeur), ce qui permet de valider la qualité du contenu dans les plans DITA avant la publication. Les administrateurs peuvent créer des paramètres prédéfinis de contrôle de l’intégrité réutilisables en combinant les contrôles pour les liens rompus, les identifiants en double et la validation du schéma.

Les auteurs peuvent exécuter un contrôle d&#39;intégrité sur un plan DITA ou sur une ligne de base sélectionnée dans l&#39;ancien éditeur pour générer un rapport consolidé des problèmes sur les rubriques et plans associés. Pour plus d’informations, consultez [Exécuter le contrôle d’intégrité sur une carte](../user-guide/map-editor-other-features.md#run-health-check-on-a-map).

## API d’upsert pour la migration de contenu héritée

Cette API vous permet de créer ou de mettre à jour du contenu et ses métadonnées via une seule API. Il prend en charge la spécification du contenu de rubrique, des métadonnées et d’un GUID dans la requête. L’API est disponible dans la documentation de l’API Swagger à l’adresse `/bin/guides/v1/asset/upsert/`.