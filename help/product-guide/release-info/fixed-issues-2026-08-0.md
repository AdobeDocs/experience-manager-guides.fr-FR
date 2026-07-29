---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides, version 2026.08.0
description: Découvrez les correctifs de la version 2026.08.0 d’Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 11d5db19cc352a3750754099a11290e4c0da0846
workflow-type: tm+mt
source-wordcount: '1203'
ht-degree: 1%

---

# Correction de problèmes dans la version 2026.08.0

Cet article couvre les bugs corrigés dans les différentes zones de la version 2026.08.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, consultez [Nouveautés de la version 2026.08.0](whats-new-2026-08-0.md).

Découvrez les [instructions de mise à niveau pour la version 2026.08.0](upgrade-instructions-2026-08-0.md).

## Création

- Les rubriques ne s’ouvrent pas dans l’éditeur lorsqu’elles sont accessibles à partir des rapports de rubrique dans le tableau de bord Carte. (GUIDES-45277)


## Éditeur 2.0

- Lorsqu’une équation MathML est insérée en tant que `conref`, elle ne s’affiche pas correctement. (GUIDES-46601)
- Si vous copiez et collez des `<keywords>` à l’intérieur de `<topicmeta>` dans une `<keydef>` ou une `<topicref>`, les mots-clés sont insérés dans des balises étrangères indésirables. (GUIDES-45800)
- L’utilisation de `Ctrl+click` sur un lien rompu dans un éditeur de cartes déclenche une erreur d’application. (GUIDES-45544)
- Copier un tableau à partir d’une feuille de calcul Excel et le coller dans le nouvel éditeur place tout le contenu de cellule copié dans une seule cellule de tableau au lieu de le distribuer dans les cellules correspondantes. (GUIDES-47435)
- Un bouton personnalisé **Exporter en tant que PDF** configuré via `editor_toolbar.json` est rendu et reste cliquable en mode Aperçu, mais n’effectue aucune action lorsque l’utilisateur ou l’utilisatrice clique dessus. (GUIDES-47402)
- Les éléments MathML et SVG n’effectuent pas le rendu de leur ensemble complet d’attributs, ce qui entraîne la rupture des classes CSS personnalisées et des attributs conditionnels appliqués à ces éléments. (GUIDES-46371)
- L’ouverture de certaines rubriques contenant des tableaux ajoute une balise `<foreign>` inattendue avec deux nouvelles colonnes, même si aucune modification n’a été apportée à la rubrique. (GUIDES-46748)
- L’attribut **Scale** ne s’applique pas aux images en mode Création. (GUIDES-45996)
- Faire glisser et déposer un élément contenant un `keyref` convertit la valeur `keyref` en chemin absolu. (GUIDES-45701)
- L&#39;insertion d&#39;un élément à la position `tgroup` affiche un avertissement **#text n&#39;est pas autorisé ici** ce qui empêche l&#39;insertion d&#39;un tableau normal à cette position. (GUIDES-47446)
- Les termes alphanumériques ajoutés au dictionnaire sont toujours marqués par le vérificateur orthographique d’AEM au lieu d’être ignorés. (GUIDES-48587)

## Gestion des ressources numériques

- Le traitement des ressources en bloc inclut incorrectement les ressources de fragments de contenu, ce qui entraîne des erreurs dans les journaux et des échecs dans les rapports de traitement. (GUIDES-47085)
- Dans le panneau Mappage, le chargement des rubriques enfants échoue et l’icône de développement disparaît lorsque la case à cocher de mappage est sélectionnée et désélectionnée à plusieurs reprises. (GUIDES-43546)

## Publication

**AEM Sites**

Lors de la publication d’une sortie AEM Sites à l’aide du mappage des composants composites :

- Une **liste de rubriques** vierge s’affiche lorsqu’une nouvelle ligne de base est utilisée dans le paramètre prédéfini AEM Sites avec mappage des composants composites. (GUIDES-46480)
- Les liens de référence croisée (`xref`) vers des ressources non DITA telles que PDF, ZIP, DOCX et les fichiers image ne sont pas résolus correctement, ce qui entraîne la rupture des liens sur la page générée. (GUIDES-44108)

Lors de la publication d’une sortie AEM Sites à l’aide du mappage des composants hérités :

- Les noms de fichier non anglais dans les noms de page générés sont remplacés par des tirets, ce qui rend difficile l’identification du sujet ou du fichier auquel il est associé. (GUIDES-48387)

PDF natif **&#x200B;**

- Dans la sortie PDF native, les références de rubrique marquées avec `toc="no"` attribut sont toujours incluses dans la table des matières, ce qui entraîne une table des matières longue et encombrée. (GUIDES-37940, GUIDES-20156)

**Mappage des collections et activation en bloc**

Les problèmes suivants ont été corrigés avec la fonctionnalité [Nouvelle collection de cartes](../user-guide/generate-output-use-new-map-collection-output-generation.md#use-new-map-collection-for-output-generation-beta) disponible dans la version 2020.08.0 de Experience Manager Guides :

- Impossible de charger une collection de mappages avec plus de 100 entrées de mappage en raison d&#39;une erreur réseau. (GUIDES-34007)
- Impossible de sélectionner plusieurs mappages à la fois à partir d’un dossier dans l’interface utilisateur de collecte de mappages. (GUIDES-29581)
- Impossible de rechercher ou de filtrer les collections de mappages dans l’interface utilisateur Mappage des collections. (GUIDES-27723)
- Impossible de fermer le tableau de bord Publication/activation en bloc ou de revenir à **Outils** ou à la page d’accueil sans utiliser le bouton Précédent du navigateur. (GUIDES-26797)
- Incapacité à gérer facilement des collections de cartes avec un grand nombre de cartes ou de langues. (GUIDES-21735)
- Impossible d’afficher ou de publier la sortie générée directement à partir des interfaces de collecte de cartes ou de tableau de bord d’activation en bloc. (GUIDES-18712)
- Impossible d’utiliser une seule collection pour générer et activer des mappages, car les collections de mappages et le tableau de bord d’activation en bloc gèrent des ensembles distincts de collections. (GUIDES-12730)

## Révision

- Dans l’interface utilisateur de révision, la liste de balisage affiche tous les utilisateurs de la tâche de révision, ce qui rend difficile la sélection de l’utilisateur approprié dans un commentaire ou une réponse. (GUIDES-33420)
- L’ouverture de la vue **côte à côte** dans le panneau Commentaires affiche la copie de travail avec la version commentée, mais les panneaux ne défilent pas de manière synchronisée horizontalement, et le fait de cliquer sur un commentaire ne déplace pas le curseur vers le texte correspondant. (GUIDES-44083)

## Base de données

- `DatabaseConfiguratorService` renvoie une erreur dans les journaux même s’il n’est pas configuré ou activé. (GUIDES-43481)

## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 2026.08.0 :

## Création

- La fermeture d&#39;un fichier DITAVAL déplacé vers un autre emplacement génère un message d&#39;erreur `ERROR IN FETCHING VERSION DETAILS`. (GUIDES-51420)

## Éditeur 2.0


- L’API de conflit échoue et entraîne une erreur d’application lorsque le chemin du dossier du référentiel se termine par une barre oblique. (GUIDES-51006)
- La sélection d’un élément d’instruction de traitement en mode Plan met en surbrillance l’intégralité de la balise parent au lieu de l’élément sélectionné. (GUIDES-48318)
- La modification d’un mot-clé dans un `keyref` dans la vue source interrompt le mot-clé lorsque l’affichage est basculé vers une autre vue. (GUIDES-49998)
- Une équation MathML encapsulée dans un bloc `foreign` et `equation` entraîne un espacement indésirable. En outre, la saisie dans l’équation entraîne des problèmes même après le réglage de la mise en retrait. (GUIDES-46606)
- Impossible de placer un curseur à l’intérieur d’un `topicref` dans un `reltable` lorsque l’option **Afficher les balises** est activée et que l’option **Afficher les attributs** est désactivée dans les paramètres de l’éditeur. (GUIDES-46565)
- Faire glisser et déposer une référence dans un `keydef` vide ajoute un élément `topicref` au lieu de mettre à jour la référence. (GUIDES-45068)

## Publication

- Si vous sélectionnez **Afficher la sortie** après avoir généré la sortie Edge Delivery Services, une URL `hlx.live` s’ouvre, qui renvoie une erreur 403 Interdit au lieu de l’URL `aem.live`. (GUIDES-51572)
- Les composants non valides s’affichent sur la page `common.plt` lors de l’ajout d’une image, d’un lien hypertexte ou d’un iframe à partir de la barre d’outils d’un modèle. (GUIDES-51165)
- La publication d’un mappage qui fait référence à une rubrique à l’aide de l’attribut `copy-to` supprime le lien de portée d’homologue de la rubrique correspondante dans le mappage source. (GUIDES-50701)
- Lorsqu’un PDF est référencé en tant que `xref` dont l’étendue est définie sur `Peer`, il est publié sur le site AEM (à l’aide du mappage des composants hérités) au lieu d’être sourcé à partir du mappage croisé. (GUIDES-50213)

**Mapper des collections**

- La suppression d’une collection de mappages échoue parfois si vous basculez sur des onglets (tels que Référentiel ou Présentation), puis revenez à la page Collection de mappages avant de la supprimer. (GUIDES-50997)
- La génération du même préréglage lorsqu’une génération précédente est en cours n’affiche plus de message indiquant que la génération précédente est en cours. (GUIDES-50523)
- L’horodatage de dernière génération n’est pas affiché ou mis à jour dans l’interface utilisateur de collecte de cartes une fois qu’une carte est générée. Si vous ajoutez à nouveau un préréglage qui a été supprimé, son historique de génération sera à nouveau perdu. (GUIDES-50511)
- La publication à partir de l’**historique de génération** publie toujours la dernière sortie d’un paramètre prédéfini au lieu de la génération sélectionnée. (GUIDES-50508)
- Le statut de publication ne s’actualise pas automatiquement pour les nouvelles collections de mappages. (GUIDES-50367)

## Traduction

- Le démarrage d’une traduction avec l’option **Créer uniquement la structure** renvoie une erreur. (GUIDES-51261)

## Révision

- L’exécution d’une barrure à l’aide d’un raccourci clavier au-dessus du texte qui inclut du contenu conditionnel masqué barrera également le contenu masqué. (GUIDES-49837)


