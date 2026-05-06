---
title: Notes de mise à jour | Nouveautés de la version Adobe Experience Manager Guides 2026.05.0
description: Découvrez les fonctionnalités nouvelles et améliorées de la version 2026.05.0 d’Adobe Experience Manager Guides
role: Leader
source-git-commit: 3f38264b6ce09366d07cdd302c9c53e8abcf4b7c
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 0%

---

# Nouveautés de la version 2026.05.0 (mai 2026)

Cet article présente les nouvelles fonctionnalités améliorées introduites dans la version 2026.05.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour obtenir la liste des problèmes résolus dans cette version, voir [Problèmes résolus dans la version 2026.05.0](fixed-issues-2026-05-0.md).

Découvrez les [instructions de mise à niveau pour la version 2026.05.0](../release-info/upgrade-instructions-2026-05-0.md).

## Présentation de l’éditeur 2.0

Editor 2.0 (ou nouvel éditeur) simplifie la création, ce qui vous permet de créer du contenu plus efficacement dans les modes de balise et non de balise, grâce à une expérience plus intuitive. Cette version offre des performances améliorées, avec des chargements de page plus rapides et une modification plus fluide, même pour les sujets volumineux et complexes. Il offre également une stabilité améliorée en comblant les principales lacunes de création, en particulier en ce qui concerne la navigation et le comportement du curseur. En outre, une interface moderne offre une interface utilisateur actualisée et conviviale qui équilibre fonctionnalité et facilité d’utilisation. Pour plus d’informations, consultez [Présentation de l’éditeur](../user-guide/web-editor.md).

Regardez cet aperçu vidéo mettant en évidence les fonctionnalités de l’éditeur 2.0.

>[!VIDEO](https://video.tv.adobe.com/v/3484007)


>[!NOTE]
>
> Contactez l’équipe du succès client AEM Guides pour que l’éditeur 2.0 soit activé dans votre environnement.

Voici les améliorations qui rendent la création plus facile et plus efficace.

### Interface utilisateur et expérience repensées

Une interface actualisée améliore la convivialité globale, ce qui rend la navigation et la création de contenu plus intuitives et plus cohérentes.

- **CSS plus riche pour les éléments en mode création et aperçu** : le CSS par défaut amélioré pour les éléments offre un style amélioré et une meilleure cohérence visuelle dans les modes création et aperçu.

  ![](assets/rich-css.png){width="650"}

- **Prise en charge des thèmes sombres** : la prise en charge d’un thème sombre dans la zone d’édition du contenu améliore l’expérience de création pour les utilisateurs et utilisatrices qui préfèrent travailler avec une interface sombre.

  ![](assets/dark-theme.png){width="650"}

- **Paramètres consolidés de l’éditeur au niveau de l’utilisateur** : nouveau panneau de paramètres centralisé qui offre aux créateurs et aux créatrices un meilleur contrôle sur le comportement de l’éditeur, ce qui permet aux utilisateurs et aux utilisatrices de gérer plus facilement les préférences à partir d’un seul emplacement. Les options de configuration incluent la possibilité d’activer/désactiver :

   - Espaces insécables en mode Création
   - Paramètres de visibilité des balises avec ou sans attributs
   - Commentaires XML en mode Création
   - Menu d’insertion rapide pour l’insertion d’éléments dans l’éditeur

  ![](assets/editor-settings-dialog.png){width="350"}


  Pour plus d’informations sur la configuration des paramètres de l’éditeur, voir [Paramètres de l’éditeur](../user-guide/config-editor-settings.md).

- **Meilleure représentation du contenu conditionnel en mode Création** : le contenu conditionnel s’affiche plus clairement en mode Création, ce qui permet aux créateurs et aux créatrices d’identifier et de gérer plus efficacement les variations. Pour plus d’informations, consultez [Conditions](../user-guide/web-editor-left-panel.md#conditions) dans le panneau de gauche de l’éditeur.

  ![](assets/multiple-conditions-applied_cs-editor-2-0.png){width="650"}

### Amélioration des fonctionnalités de création

Offre des outils améliorés et une flexibilité pour rationaliser les workflows de création et de modification de contenu.

- **Affichage des attributs avec les éléments en mode balise** : les auteurs peuvent désormais afficher les attributs d’élément en mode balise, ce qui offre une meilleure visibilité et un meilleur contrôle sur le contenu structuré. Pour configurer cette fonctionnalité, consultez les [paramètres de l’éditeur](../user-guide/config-editor-settings.md).

  ![](assets/config-tags-attributes.png){width="650"}

- **Menu d’insertion rapide** : permet d’ajouter des éléments directement lors de la modification en mode Création à l’emplacement du curseur sans accéder à la barre d’outils. Les éléments fréquemment utilisés peuvent également être configurés dans la section Favoris à l’aide des paramètres de l’éditeur pour un accès plus rapide. Pour plus d’informations, consultez [Modifier les rubriques](../user-guide/web-editor-edit-topics.md).

  ![](assets/quick-insert-menu.png){width="650"}

- **Possibilité d’afficher, de modifier et d’insérer des commentaires XML en mode création** : permet aux auteurs d’afficher, de modifier et d’insérer des commentaires XML directement en mode création, pour une meilleure visibilité dans le contenu. Pour configurer cette fonctionnalité, consultez les [paramètres de l’éditeur](../user-guide/config-editor-settings.md).

  ![](assets/config-xml-comments.png){width="650"}

- **Mode côte à côte** : permet d’afficher simultanément les modes Auteur et Source, les deux vues restant parfaitement synchronisées pour faciliter la comparaison, la modification et la validation des modifications de contenu. Pour plus d’informations, consultez [Vues de l’éditeur](../user-guide/web-editor-views.md).

  ![](assets/side-by-side-editor-2-0.png){width="650"}

- **Amélioration de la création de tableaux** : améliore l’expérience globale de création de tableaux avec des interactions plus intuitives et efficaces pour la création et la gestion des tableaux.

   - Interactions fluides et intuitives : insérez facilement des lignes et des colonnes, ainsi que la prise en charge du glisser-déposer pour réorganiser les lignes et les colonnes.
   - Barre d’outils contextuelle : accédez directement à des actions spécifiques au tableau, telles que la mise en forme, l’alignement, la fusion et d’autres actions supplémentaires dans le tableau.
   - Configuration des tableaux : ajoutez plusieurs lignes ou colonnes en une seule action, ce qui réduit les étapes répétitives et améliore l’efficacité.

  ![](assets/config-table.png){width="650"}

  Pour plus d’informations, consultez la section [Utiliser des tableaux](../user-guide/web-editor-other-features.md#work-with-tables-in-the-new-editor).

### Amélioration des performances pour les sujets volumineux

Le nouvel éditeur améliore l’expérience de travail sur des sujets volumineux et complexes en offrant un rendu du contenu plus rapide, des fonctionnalités d’annulation et de restauration plus fiables, ainsi qu’un marqueur d’intégrité pour indiquer clairement les modifications non enregistrées.

## Accédez au Chemin d’accès et à l’UUID des références dans les fichiers à partir du panneau Propriétés du contenu

Vous pouvez désormais utiliser **Chemin du lien** pour afficher le chemin d’accès relatif de la référence sélectionnée et **UUID du lien** pour afficher son identifiant unique à partir du panneau Propriétés du contenu. Vous pouvez également copier le chemin absolu complet et l’UUID associé directement à partir de l’interface à l’aide des icônes en regard de Chemin du lien et UUID du lien, ce qui facilite le suivi et la réutilisation des ressources liées.

Pour plus d’informations, consultez [Propriétés du contenu](../user-guide/web-editor-right-panel.md#content-properties).

## Améliorations de la révision

Les améliorations de révision suivantes ont été apportées dans le cadre de cette version :

- Vous pouvez désormais activer **Rappels automatisés** pour planifier des notifications AEM et des rappels par e-mail à l’intention des réviseurs et réviseuses, avant ou après l’échéance d’une tâche de révision. Vous pouvez configurer plusieurs rappels dans chaque cas, avec des rappels d’échéance envoyés dans une séquence définie et des rappels d’échéance déclenchés après que la tâche a été marquée comme En retard, en fonction du planning de rappel configuré. Pour plus d’informations sur la configuration des rappels pour les tâches de révision, voir [Envoyer une ou plusieurs rubriques pour révision](../user-guide/review-send-topics-for-review.md#send-one-or-more-topics-for-review).

- Les réviseurs et réviseuses peuvent désormais accéder à l’historique des versions des rubriques en cours de révision, ce qui leur permet d’afficher et de comparer les versions précédemment révisées et mises à jour d’une même rubrique dans les tâches de révision précédentes. Cela permet aux réviseurs et aux réviseuses de valider les modifications apportées depuis les cycles de révision précédents et de maintenir la continuité en examinant les commentaires, les libellés et d’autres détails connexes dans le contexte de révision actuel. Pour plus d’informations, consultez [Historique des versions du réviseur](../user-guide/review-topics.md#version-history-for-the-reviewer).

## Nouvelle expérience de base introduite dans Experience Manager Guides

>[!NOTE]
>
> Contactez l’équipe du succès client AEM Guides pour que la nouvelle ligne de base soit activée dans votre environnement.

La gestion de lignes de base complexes et volumineuses est désormais plus rapide, plus stable et plus facile à mettre à l’échelle grâce à la **nouvelle expérience de ligne de base**, reposant sur une architecture de ligne de base repensée. Cette mise à jour résout des problèmes de performances et de fiabilité de longue date tout en préservant les workflows existants.

Disponible en version bêta, cette mise à jour apporte une solution aux problèmes courants tels que le chargement lent, les incohérences des états de référence et une gérabilité limitée, en offrant une expérience de référence plus rapide, plus stable et plus prévisible, avec une prise en charge supplémentaire de l’automatisation et des opérations de référence à grande échelle. Les principales améliorations sont les suivantes :

- Amélioration des performances et de l’évolutivité
- Cohérence renforcée de l’interface utilisateur et du serveur principal
- Filtrage, navigation et visibilité des dépendances étendus

Pour plus d’informations, consultez [Nouvelle expérience de base (Beta) dans Experience Manager Guides](../user-guide/web-editor-baseline-v2.md).






