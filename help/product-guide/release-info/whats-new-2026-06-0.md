---
title: Notes de mise à jour | Nouveautés de la version Adobe Experience Manager Guides 2026.06.0
description: Découvrez les fonctionnalités nouvelles et améliorées de la version 2026.06.0 d’Adobe Experience Manager Guides
role: Leader
source-git-commit: f3f30400f776f746427e257e2c937ff3413aa9ac
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 0%

---

# Nouveautés de la version 2026.06.0 (juin 2026)

Cet article présente les nouvelles fonctionnalités améliorées introduites dans la version 2026.06.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour obtenir la liste des problèmes résolus dans cette version, voir [Problèmes résolus dans la version 2026.06.0](fixed-issues-2026-06-0.md).

Découvrez les [instructions de mise à niveau pour la version 2026.06.0](../release-info/upgrade-instructions-2026-06-0.md).


## Nouvelle collection de cartes (Beta) pour la gestion des cartes et les sorties de publication

>[!NOTE]
>
> Cette fonctionnalité est actuellement disponible en tant que fonctionnalité Beta et est désactivée par défaut. Pour l’activer dans votre environnement, contactez l’équipe du succès client.

La nouvelle collection de cartes (Beta) rassemble les activités de gestion de la collection de cartes et de génération de sortie dans une seule interface. À partir d’un emplacement, vous pouvez gérer les mappages et les paramètres prédéfinis, générer et publier des sorties, afficher l’historique de génération et de publication, etc. En rassemblant les tâches de publication associées, il est plus facile d&#39;utiliser des collections de cartes et de suivre l&#39;activité de sortie sur plusieurs cartes et leurs langues associées.

![](assets/new-maps-collection.png)

Pour plus d’informations, consultez [Utilisation d’une nouvelle collection de cartes pour la génération de sortie (Beta)](../user-guide/generate-output-use-new-map-collection-output-generation.md).

## Présentation d’un nouveau moteur de publication pour le PDF natif

Un nouveau moteur de publication, *moteur PDF natif v2*, est désormais disponible pour le PDF natif dans Experience Manager Guides. Elle comprend des améliorations et des correctifs de rendu pour les problèmes du moteur PDF natif v1. Comme le comportement de rendu a été mis à jour, la sortie PDF générée avec le *moteur PDF natif v2* peut différer de la sortie générée avec le moteur de publication PDF natif existant, *moteur PDF natif v1*.

Par exemple, le texte des PDF générés peut apparaître légèrement différent en raison des mises à jour des polices principales utilisées par le *moteur PDF natif v2*. De même, les images peuvent sembler plus nettes en raison des améliorations de l’interpolation des images et du comportement de rendu.

Découvrez comment [activer le moteur PDF natif v2](../native-pdf/conf-new-pdf-engine.md) dans votre environnement.

Pour plus d’informations sur **le moteur PDF natif v2**, consultez la page [Utilisation du moteur PDF natif v2](../native-pdf/new-pdf-engine.md).


## Améliorations de l’éditeur

### Prise en charge du style de citation AMA

Experience Manager Guides prend désormais en charge le style de citation de l’American Medical Association (AMA), en étendant le cadre de citation existant pour répondre aux normes de documentation requises par les clients des secteurs de la santé, de la réglementation et des sciences de la vie.

Lorsque AMA est sélectionné comme style de citation dans les paramètres ****, les citations sont automatiquement formatées conformément aux directives AMA, y compris le rendu numérique d&#39;exposant, la numérotation séquentielle et l&#39;ordre précis de la liste de référence. L’option **Analyser les citations** dans l’éditeur de texte enrichi est disponible exclusivement lorsque l’option AMA est sélectionnée, ce qui permet aux auteurs d’ajouter et d’analyser les citations sans changer de contexte.

Le style de citation AMA est pris en charge dans les formats de sortie Native PDF et AEM Sites. Pour configurer le style de citation, accédez aux paramètres de **** puis sélectionnez AMA dans les options de style de citation. Pour plus d’informations, consultez la section [Utilisation de citations](../user-guide/web-editor-apply-citations.md).


### Prise en charge des sources de données externes et des citations désormais disponibles dans le nouvel éditeur

Le nouvel éditeur prend désormais en charge deux fonctionnalités Experience Manager Guides existantes : la possibilité de se connecter à des sources de données externes et d’utiliser des citations dans les documents.

Les auteurs peuvent continuer à utiliser les sources de données externes configurées lors de la création ou de la mise à jour de contenu dans le nouvel éditeur. Les citations sont également prises en charge, de sorte que les auteurs peuvent ajouter et gérer des références dans leur contenu sans changer d’éditeur.

## Améliorations de la révision

### Fin de la tâche de révision de synchronisation entre l’interface utilisateur de révision et la boîte de réception AEM (Beta)

>[!NOTE]
>
> Cette fonctionnalité est actuellement disponible en tant que fonctionnalité Beta et est désactivée par défaut. Pour l’activer dans votre environnement, contactez l’équipe du succès client.

Vous pouvez désormais synchroniser l’achèvement de la tâche de révision entre l’interface utilisateur de révision et la boîte de réception AEM. Lorsque cette fonctionnalité est activée, terminer une tâche dans l’interface utilisateur de révision la supprime de la boîte de réception d’AEM et la terminer dans la boîte de réception d’AEM la marque comme terminée dans l’interface utilisateur de révision. Cela permet d’éviter de terminer la même tâche deux fois et rend le processus de révision plus fluide. Les auteurs et les initiateurs de tâche peuvent continuer à consulter les commentaires et à réaffecter des tâches si une révision supplémentaire est nécessaire. Lorsqu’une tâche est réaffectée, une nouvelle notification de boîte de réception AEM est générée pour le réviseur, ce qui permet au cycle de révision de se poursuivre de manière transparente.

Pour plus d’informations, voir [Terminer la tâche de révision en tant que réviseur](../user-guide/review-complete-review-tasks.md).

## Améliorations du contenu d’apprentissage

Les améliorations suivantes sont disponibles pour la fonctionnalité de contenu Formation et Apprentissage du produit dans cette version :

- Les auteurs peuvent désormais rendre une vérification des connaissances obligatoire pour les élèves avant d’avancer dans un cours. Une nouvelle option **Exiger une vérification des connaissances pour continuer** est introduite pour les vérifications des connaissances dans les cours. Lorsque cette option est activée, les élèves doivent effectuer une vérification des connaissances avant de passer au contenu du cours suivant. Cela permet de s’assurer que les vérifications de connaissances requises sont effectuées à des points désignés du cours. Pour plus d&#39;informations, consultez [Autres options du menu Insertion](../learning-content/lc-other-insert-options.md).
- Vous pouvez désormais utiliser des champs de saisie de texte multiligne lors de la création de contenu de formation. Cette amélioration facilite la capture de réponses plus longues des élèves en prenant en charge les sauts de ligne et l’habillage du texte dans un seul champ, sans recourir à un script personnalisé. En savoir plus sur [Autres options du menu Insertion](../learning-content/lc-other-insert-options.md).
- Les modèles de sortie SCORM prennent désormais en charge l’attribution de différentes mises en page à différents types de sujets au sein d’un cours. Vous pouvez ainsi configurer des mises en page dédiées pour les leçons, les quiz, les pages de présentation et d’autres types de rubriques directement à partir des paramètres du modèle de sortie.

  Cela permet à chaque type de rubrique d’utiliser une mise en page appropriée à son contenu et à sa structure, plutôt que d’appliquer la même mise en page sur toutes les pages du cours. Pour plus d&#39;informations sur la configuration des mises en page pour les modèles de sortie SCORM, voir [Configurer des profils de dossier](../lc-config-guide/lc-folder-profile.md).
- Experience Manager Guides prend désormais en charge la publication directe de contenu SCORM dans Adobe Learning Manager (ALM). Après la configuration d’un profil de publication ALM, les auteurs peuvent générer une sortie SCORM et la charger directement dans Adobe Learning Manager sans télécharger et importer manuellement le package.

  Pour plus d’informations, consultez [Configuration du paramètre prédéfini SCORM](../learning-content/config-scorm-preset.md).


