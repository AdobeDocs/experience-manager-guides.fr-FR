---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides, version 2026.11.0
description: Découvrez les correctifs de bugs de la version 2026.11.0 d’Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: f33da832def2bf2cc8caf46f3b6f8102bcfafb19
workflow-type: tm+mt
source-wordcount: '1448'
ht-degree: 0%

---

# Correction de problèmes dans la version 2026.11.0

Cet article couvre les bugs corrigés dans différentes zones de la version 2026.11.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, consultez [Nouveautés de la version 2026.11.0](./whats-new-2026-11-0.md).

Découvrez les [instructions de mise à niveau pour la version 2026.11.0](./upgrade-instructions-2026-11-0.md).

## Éditeur 2.0

- Lorsqu’une ligne de tableau est sélectionnée à l’aide des chemins de navigation de l’éditeur et que l’option **Supprimer** est sélectionnée dans le menu contextuel, seul le contenu de la cellule est supprimé au lieu de supprimer la ligne entière. (GUIDES-56759)
- Lorsqu’un tableau est collé à partir de Microsoft Word, les cellules des lignes d’en-tête sont créées, mais leur contenu est perdu. (GUIDES-49847)
- Les modifications suivies dans les fichiers créés avant de passer à l’éditeur 2.0 n’apparaissent pas dans le panneau **Suivi des modifications**. (GUIDES-44777)
- Lorsque du code est collé dans un élément de `codeblock`, à partir de Microsoft Word ou d’éditeurs de texte similaires, à l’aide de Ctrl+V, les sauts de ligne et les espaces de début sont perdus et le code est aplati en une seule ligne. (GUIDES-33247)

## Création

- Lorsque Unified Shell est activé, l’en-tête Adobe Experience Manager Guides apparaît également dans l’éditeur et la console Carte. (GUIDES-56812)
- Dans l&#39;interface utilisateur d&#39;Assets, les actions spécifiques à DITA telles que **Afficher la source**, **Modifier les rubriques** et **Partager le lien UUID** s&#39;affichent pour les ressources non-DITA. En outre, la mention **Partager le lien UUID** génère un lien non valide pour les ressources qui n’ont pas d’UUID. (GUIDES-47043)
- Dans le panneau Schéma d’objet , le titre affiché est sélectionné uniquement dans l’attribut `navtitle` . L’élément `navtitle` est ignoré même lorsque les deux sont présents. (GUIDES-37722)
- Dans la **vue Titre** du panneau Référentiel, les points de suspension ne sont pas visibles initialement pour les fichiers dont le nom est long. Lorsque vous cliquez avec le bouton droit sur un fichier, les points de suspension et le menu contextuel s’affichent à droite du fichier, parfois en partie hors de l’écran. (GUIDES-37118)
- Dans le panneau Conditions, les conditions sont triées par ordre alphabétique en fonction de leurs valeurs plutôt que de leurs libellés. (GUIDES-14593)
- Dans les modèles de sortie, le bouton **Nouveau style** (+) ne s’affiche pas dans le panneau Styles lorsqu’une feuille de style, telle que layout.css, est ouverte. (GUIDES-49448)

## Gestion des ressources numériques

- Lorsque vous téléchargez un fichier modifié à l’aide de l’option **Remplacer le fichier existant**, le téléchargement semble terminé si le fichier existant ne comporte aucun UUID Guides et est stocké dans un dossier répertorié sous **Chemins ignorés pour le post-traitement**. Toutefois, le fichier existant n’est pas remplacé et aucune nouvelle version n’est créée. (GUIDES-55866)
- Dans un bookmap, lorsqu’un élément de `booktitle` contient plusieurs sous-éléments, tels que `booklibrary` et `mainbooktitle`, des espaces supplémentaires sont ajoutés entre leurs valeurs dans les métadonnées de `dc:title`. (GUIDES-28877)

## Publication

- Dans la console Mappage, une fois la sortie générée pour un mappage, le bouton **Générer** est désactivé lorsqu’un autre mappage est ouvert. Actualiser le navigateur active à nouveau le bouton. (GUIDES-54591)
- La publication de certains mappages sur un site AEM avec mappage de composant échoue avec une erreur lors de la création de la table des matières. (GUIDES-53807)
- La publication d’un mappage sur un site AEM avec mappage de composant échoue lorsque le mappage contient un élément `topicref` avec un attribut `navtitle` et aucun attribut `href`. Les tentatives suivantes échouent également, même après la suppression de l’élément , jusqu’à ce que les nœuds de site générés soient supprimés. (GUIDES-53707)
- Dans la sortie de site AEM avec mappage de composant, les en-têtes Markdown des niveaux 2 à 6 sont rendus en tant qu’en-têtes de niveau 1. (GUIDES-51134)
- Pour une sortie de site AEM avec mappage de composant, les métadonnées de prologue, telles que l’auteur, les mots-clés et l’ID de ressource, apparaissent dans le corps de page de la sortie publiée. (GUIDES-44087)
- Lorsqu’une rubrique est publiée sur ServiceNow, le corps de l’article comprend la brève description et le prologue de la rubrique. (GUIDES-47868)
- Lorsqu’une rubrique déjà publiée dans ServiceNow est publiée à nouveau, un nouvel article est créé à l’état de brouillon au lieu d’être remplacé par l’article existant. (GUIDES-37872)
- Lorsque les paramètres prédéfinis de condition excluent les références de rubrique lors de la publication sur Salesforce, la génération de sortie est signalée comme ayant échoué, même si les rubriques restantes sont publiées avec succès. (GUIDES-37807)
- La publication d’une carte volumineuse sur Salesforce échoue avec une erreur de délai d’expiration de passerelle. (GUIDES-33722)
- La publication d’un mappage vers Salesforce échoue avec une erreur de limite dépassée lorsqu’une requête contient plus de 25 opérations. (GUIDES-33721)
- Dans l’ancien tableau de bord des cartes, la **Ajouter tout** d’un paramètre prédéfini de condition existant ne récupère pas les valeurs de condition qui ont été ajoutées ou modifiées après la création du paramètre prédéfini. (GUIDES-45940)
- Les journaux de la page **Historique de sortie** contenant des avertissements s’affichent avec une icône verte, ce qui n’indique pas la présence d’avertissements. (GUIDES-27000)
- Le glossaire n’est pas inclus dans la sortie lorsqu’aucun terme dans le contenu de la carte ne fait référence à une entrée du glossaire. (GUIDES-52964)
- Les rubriques d’une sous-carte référencée dans une annexe sont rendues sous la forme de chapitres au lieu du contenu de l’annexe. (GUIDES-52775)
- Certains caractères chinois simplifiés sont rendus avec une police japonaise lorsque la langue de sortie est définie sur le chinois (simplifié). (GUIDES-48094)
- Les entrées d’index perdent le texte des éléments enfants, tels que `keyword`, `ph` et `sup`. Par conséquent, certains libellés d’index sont incomplets ou vides. (GUIDES-40902)
- Les espaces autour des éléments de `option` intégrés ne sont pas conservés, ce qui fait que le texte adjacent apparaît assemblé. (GUIDES-40900)

## Traduction

- Sur la page Traduction, lors d’une recherche et d’un tri par **Titre** utilisez la valeur de métadonnées localisée au lieu du titre affiché dans la colonne . (GUIDES-45396)

## Révision

- Sur la page **Réviseurs**, lors de la création ou de la modification d’une tâche de révision, les boutons **Effacer la sélection**, **Ajouter des réviseurs**, **Supprimer des réviseurs** et **Réaffecter des réviseurs** sont activés par défaut, même si aucune ligne n’est sélectionnée. (GUIDES-35125)
- Dans la boîte de réception d’AEM, les notifications liées aux tâches de révision, telles que l’affectation de tâche, les commentaires reçus, les mentions et les rappels d’échéance ou de retard, s’affichent sans nom de projet. (GUIDES-10912)
- Dans la vue côte à côte d’une rubrique dans une tâche de révision, le contenu barré s’affiche avec une mise en forme différente dans les deux vues. (GUIDES-56079)

## Contenu d’apprentissage

- La génération d’une sortie SCORM pour un cours volumineux, généralement entre 300 et 600 Mo, prend plus de 30 minutes et échoue sans détails d’erreur dans les journaux. (GUIDES-56101)
- Les critères d’achèvement d’une sortie SCORM ne peuvent pas être définis dans Experience Manager Guides. (GUIDES-55520)
- Les images au format AVIF sont affichées dans l’éditeur, mais elles sont absentes de la sortie publiée. (GUIDES-55515)
- L’attribut `href` est supprimé des balises d’ancrage dans la sortie publiée, de sorte qu’il n’est pas possible de cliquer sur les liens. (GUIDES-55514)

## Plateforme

- Lorsque l’utilisateur est affecté en tant qu’utilisateur administrateur dans un profil de dossier mais qu’il n’est pas membre du groupe administrateurs , il ne peut pas ajouter d’autres utilisateurs administrateurs. Bien qu’un message de réussite s’affiche, les utilisateurs nouvellement ajoutés disparaissent après l’actualisation de la page. (GUIDES-50144)

## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 2026.11.0 :

## Création

- Lorsque vous créez un mappage à partir d’un modèle contenant des rubriques ou des sous-mappages dépendants, la création d’un mappage peut échouer par intermittence avec une erreur, en particulier lorsque le serveur est soumis à une charge importante. (GUIDES-58715)

### Éditeur 2.0

- L&#39;option **Actualiser l&#39;attribut de titre de navigation** n&#39;ajoute pas l&#39;attribut `@navtitle` aux éléments `topicref` existants dans un plan DITA. (GUIDES-54348)

**Suivi des modifications**

Lorsque le **suivi des modifications** est activé :

- Les suppressions imbriquées effectuées par le même utilisateur ne sont pas toujours fusionnées en une seule entrée lorsque l’élément contenant le contenu supprimé est renommé ou formaté. (GUIDES-58429)
- Le panneau **Suivi des modifications** affiche parfois un contenu incomplet pour l’élément parent lorsqu’une suppression imbriquée est effectuée par un autre utilisateur. (GUIDES-58428)
- Le marqueur de gouttière rouge n’apparaît pas à gauche lorsque vous supprimez du contenu lors d’une insertion effectuée par un autre utilisateur. (GUIDES-58418)

### Publication

- Dans la sortie Native PDF, la mise en exposant et en indice n’est pas conservée dans les entrées d’index. (GUIDES-58349)
- Lorsque vous utilisez le même paramètre prédéfini global pour générer une sortie pour différents mappages, la sélection de rubrique de la carte précédente peut affecter la sortie de la nouvelle carte. (GUIDES-58346)
- Lorsqu’un mappage de livres contient un chapitre avec un `href` valide et une référence de rubrique imbriquée, la publication du mappage dans AEM Sites donne lieu à une page vierge. (GUIDES-58266)
- Lorsque vous accédez à l’onglet **Historique de sortie** à partir d’un paramètre prédéfini avec des modifications non enregistrées, les boutons **Enregistrer** et **Générer la sortie** restent visibles. (GUIDES-57989)
- Lorsqu’un workflow de post-publication est configuré pour un préréglage, la durée de publication indiquée dans **Historique de sortie** n’inclut pas le temps pris par le workflow. (GUIDES-57856)
- Vous ne pouvez pas annuler la génération de sortie Native PDF à partir de la page **Historique de sortie**. (GUIDES-57821)

### Révision

- L’ouverture d’une tâche de révision créée dans la version 2026.08.0 ou 2026.09.0 peut entraîner des erreurs d’application. (GUIDES-56583) <br>**Solution :** terminez ou fermez toutes les tâches de révision créées dans ces versions avant la mise à niveau vers la version 2026.11.0.

