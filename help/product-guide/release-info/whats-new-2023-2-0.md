---
title: Notes de mise à jour | Adobe Experience Manager Guides as a Cloud Service, version de février 2023
description: Version de février d’Adobe Experience Manager Guides as a Cloud Service
exl-id: 090eaf94-fe3a-47e9-9937-f84f8434550d
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/8alpUFz4njJtpUZrGcZ5wdrbmqSGOjSVqaHX1T4YeJ4
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 1382
ht-degree: 0%

---

# Nouveautés de la version de février 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cet article couvre les nouvelles fonctionnalités et les fonctionnalités améliorées de la version de février 2023 d’Adobe Experience Manager Guides (plus tard appelée *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans cette version, consultez l’article [Notes de mise à jour](release-notes-2023-2-0.md).


## Générer des rapports à partir de l’éditeur web

AEM Guides s’accompagne d’une fonctionnalité dans l’éditeur web qui vous permet de vérifier l’exhaustivité globale de vos documents techniques et de générer des rapports pour ceux-ci.
Vous pouvez afficher la liste des rubriques, gérer les métadonnées et voir le contenu multimédia utilisé dans toutes les références pour la carte actuelle à partir du
Onglet **Rapports** dans l’éditeur web.

**Générer la vue Liste de rubriques**

Vous pouvez générer la liste des rubriques qui fournit des informations détaillées sur vos rubriques, telles que le type de référence, le statut du document et l’auteur. Vous pouvez également générer le fichier CSV pour télécharger l&#39;instantané actuel des rubriques dans le plan DITA.

**Gestion des métadonnées et modification de l’état du document**

Vous pouvez appliquer des balises sur une rubrique individuelle ou utiliser la fonction de balisage en bloc pour appliquer plusieurs balises sur plusieurs rubriques, un plan DITA ou un sous-plan. Vous pouvez également modifier l&#39;état du document de toutes les rubriques sélectionnées pour passer à l&#39;état suivant du document commun.

<img src="assets/web-editor-metadata-panel.png" alt="gestion des métadonnées" width="600">

**Générer le rapport multimédia**

Vous pouvez générer le rapport multimédia qui contient des informations détaillées sur le multimédia utilisé dans vos références dans la carte actuelle. Vous avez la possibilité de filtrer et de trier les fichiers multimédias répertoriés dans le rapport.
Vous pouvez également générer le fichier CSV pour télécharger l&#39;instantané actuel du fichier multimédia utilisé dans le plan DITA.

<img src="assets/web-editor-reports-multimedia.png" alt="rapport multimédia" width="600">

## Nouvelle expérience utilisateur pour la fonctionnalité de révision

Désormais, les guides d’AEM fournissent une expérience utilisateur améliorée qui vous aide à examiner les rubriques partagées pour révision. Dans la dernière expérience, la fonctionnalité de révision bénéficie des améliorations suivantes :

* Actualisation de l’interface utilisateur
* Panneau Conditions qui permet de mettre en surbrillance le contenu en fonction des conditions disponibles dans la rubrique
* Chaque commentaire du panneau de commentaires est lié au texte correspondant dans la rubrique active. Cela vous permet d’identifier le texte commenté.
* Les commentaires s’affichent dans l’ordre du texte commenté dans le document.
* Le nom de la tâche de révision s’affiche dans le workflow de révision.
* Sélectionnez la feuille de route de la tâche de révision, qui est utilisée pour résoudre toutes les références clés et tous les termes du glossaire utilisés dans le contenu de révision.
* Barre d’outils contextuelle qui permet de mettre rapidement en surbrillance ou de barrer le texte
* Menu Options permettant de modifier ou de supprimer vos propres commentaires
* Pour les commentaires obsolètes, vous avez accès à la vue côte à côte qui vous aide à comparer la version précédente de la rubrique à la version de révision actuelle.
* Lors de l’utilisation des filtres, les commentaires du panneau de droite sont filtrés en fonction de la sélection, puis le
le nombre de commentaires dans le panneau de gauche est mis à jour en conséquence.


  <img alt="tâche de révision" src="assets/comment-pop-up-panel.png" width="600">



## Améliorations apportées à la traduction

Vous disposez désormais d’améliorations plus conviviales dans le tableau de bord de traduction qui vous permettent de traduire facilement vos documents à partir de l’éditeur web.

**Transmettez le libellé de version à la version cible**

AEM Guides permet de transmettre le libellé du fichier source au fichier cible. Cela vous permet d’identifier facilement la version source du fichier traduit.

<img alt="libellés de traduction" src="assets/translation-pass-source-label.png" width="600">

Par exemple, si vous disposez de fichiers source auxquels est appliqué le libellé de version 1.0, vous pouvez également transmettre le libellé source (version 1.0) au fichier traduit.

**Forcer la synchronisation pour les ressources non synchronisées**

Si vous apportez des modifications à certaines des ressources, AEM Guides les marque comme étant désynchronisées. Vous pouvez soit retraduire les ressources modifiées, soit ignorer le statut Désynchronisé . Par exemple, si vous avez apporté des modifications mineures qui n’ont pas vraiment besoin d’être traduites, vous pouvez marquer leur statut comme étant Synchronisé.

<img src="assets/translation-version-diff.png" alt="tableau de traduction" width="600">

**Afficher les projets de traduction en cours pour une rubrique ou un plan**

Certaines références de votre tableau de bord de traduction peuvent être en cours. AEM Guides propose désormais une fonctionnalité pour vous aider à afficher la liste de tous les projets de traduction en cours (ainsi que la langue cible) qui contiennent la référence sélectionnée.


## Générer une sortie dans divers formats à partir de l’éditeur web

Vous pouvez désormais facilement générer la sortie de vos rubriques ou de votre plan DITA à partir de l&#39;éditeur web. Vous pouvez configurer différents paramètres prédéfinis de sortie tels qu’AEM Site, PDF, HTML5,
JSON (format de sortie découplé) et sortie personnalisée. Vous pouvez ensuite les utiliser pour générer les sorties respectives.

Vous pouvez définir des attributs dans vos rubriques DITA, puis utiliser le paramètre prédéfini de condition pour appliquer une condition lors de la publication de la sortie. Vous pouvez également utiliser la fonction Publication de ligne de base pour publier de manière sélective une version spécifique de votre plan ou rubrique DITA.


## Rechercher et remplacer le texte au niveau de la carte

AEM Guides vous permet de rechercher des fichiers dans une carte qui contiennent du texte spécifique. Le texte recherché est mis en surbrillance dans les fichiers. Vous pouvez désormais remplacer le mot ou l’expression recherché par un autre mot ou une autre expression dans tous les fichiers. Vous pouvez sélectionner l’icône **Tout remplacer** en haut à droite de la liste pour remplacer toutes les occurrences du terme recherché dans tous les fichiers.

<img src="assets/map-find-replace.png" alt="remplacer la recherche de carte" width="600">

## Supprimer et dupliquer des fichiers du panneau Référentiel

Vous pouvez désormais facilement créer un doublon ou une copie d’un fichier à partir du menu **Options** du fichier sélectionné dans le panneau Référentiel. Par défaut, le fichier est créé avec
un suffixe (comme `filename_1.extension`).

<img src="assets/options-menu-repo-view-file-level.png" alt="menu options du fichier " width="500">


## Autres améliorations de l’éditeur web

* Dans AEM Guides, vous pouvez effectuer certaines opérations courantes pour les images et les fichiers multimédias à l’aide du menu contextuel. Vous pouvez désormais également localiser l’image ou le média sélectionné dans le référentiel ou afficher l’aperçu du fichier dans l’interface utilisateur d’Assets.

* Le nom du profil de dossier actuel est affiché comme libellé pour l’icône Préférences utilisateur dans la barre d’outils principale. Cela vous permet d’identifier le profil de dossier sur lequel vous travaillez.

* Lorsque vous ouvrez une carte dans la vue Carte, le titre de la carte actuelle s’affiche au centre de la barre d’outils principale. Cela s’avère utile pour indiquer à l’utilisateur ou à l’utilisatrice quel mappage est actuellement ouvert.


## Afficher le titre à la place de l’UUID dans l’éditeur d’oxygène

AEM Guides vous permet désormais de choisir l’option **Utiliser le titre dans l’éditeur et le gestionnaire de cartes** dans les paramètres. Si vous sélectionnez cette option, le titre du fichier s&#39;affiche dans l&#39;onglet du fichier lorsqu&#39;il est ouvert dans l&#39;éditeur ou dans le gestionnaire de cartes DITA. Si vous ne sélectionnez pas cette option, l’UUID du fichier est affiché dans l’onglet du fichier.

## Publication basée sur les microservices pour AEM Guides as a Cloud Service

Le nouveau microservice de publication vous permet d’exécuter simultanément d’importantes charges de travail de publication sur AEM Guides as a Cloud Service et d’exploiter la plateforme sans serveur Adobe I/O Runtime de pointe.

Pour chaque demande de publication, AEM Guides as a Cloud Service exécute un conteneur distinct qui se met à l’échelle horizontale en fonction des demandes des utilisateurs. Vous pouvez ainsi exécuter plusieurs requêtes de publication et obtenir de meilleures performances.

Pour plus d’informations, consultez [Configuration d’une nouvelle publication basée sur un microservice pour AEM Guides as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/publishing/configure-microservices.md).

## PDF natif | Ajout d’un signet personnalisé dans la sortie PDF

Vous pouvez désormais ajouter un signet personnalisé sur un contenu particulier dans votre sortie PDF finale pour une navigation plus facile. Elle est ajoutée à la table des matières créée à partir des titres de rubrique ou de section dans votre plan DITA.

## PDF natif | Application d’un style personnalisé aux entrées de la table des matières et au contenu de la rubrique

AEM Guides permet d’appliquer un style personnalisé aux entrées de la table des matières ou à une rubrique spécifique dans la sortie PDF. Par exemple, vous pouvez modifier la couleur du texte dans la table des matières et le titre de la rubrique. Vous pouvez également appliquer des styles à l’ensemble du contenu dans la rubrique.


## PDF natif | Appliquer un style au marqueur de page dans le composant de note de bas de page

Vous pouvez maintenant mettre en forme le marqueur de page dans les notes de pied de page. Par exemple, vous pouvez ajouter des crochets ou modifier leur couleur. Ces styles permettent aux utilisateurs d’identifier facilement les marqueurs de page dans le document.

## Native PDF | Barre de modification pour indiquer les rubriques modifiées dans la table des matières

AEM Guides vous permet désormais d’identifier rapidement les rubriques modifiées dans la table des matières de la sortie PDF.  Une barre de modification s’affiche à gauche des rubriques modifiées dans la table des matières. Vous pouvez cliquer sur la rubrique dans la table des matières et afficher les modifications détaillées.

<img src="assets/change-marker-toc.png" alt="Modifier le marqueur dans la table des matières " width="500">
