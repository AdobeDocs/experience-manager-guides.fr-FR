---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides 5.2.0 Service Pack 1
description: Découvrez les correctifs de bugs dans la version 5.2.0 Service Pack 1 d’Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: 429d2abf0aad8722ac30c08c9c9d134be0759ff4
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 0%
---
# Correction de problèmes dans la version 5.2.0 Service Pack 1 (septembre 2026)

Cet article couvre les bugs corrigés dans différentes zones de la version 5.2.0 Service Pack 1 d’Adobe Experience Manager Guides.

Découvrez les [instructions de mise à niveau pour la version 5.2.0 du Service Pack 1](upgrade-instructions-5-2-0-sp1.md).

## Création

- Sur les écrans basse résolution, la boîte de dialogue Insérer un mot-clé ne s’affiche pas lors de l’insertion d’un mot-clé à partir de la barre d’outils, tandis qu’elle s’ouvre comme prévu lors de l’utilisation de l’option **Plus**. (GUIDES-48304)
- L&#39;insertion d&#39;une référence croisée à l&#39;aide de l&#39;option **Lien web** permet d&#39;ajouter un lien `scope=local` et de modifier la valeur `href`, au lieu d&#39;insérer un lien `scope=external` comme prévu. (GUIDES-48457)
- L’enregistrement d’un mappage de référence rompt la référence au lieu de la résoudre sur le mappage correct lorsqu’un auteur déplace le mappage référencé tandis qu’un autre auteur y ajoute simultanément une référence dans un mappage non enregistré. (GUIDES-47467)
- Les termes alphanumériques ajoutés au dictionnaire sont toujours marqués par le vérificateur orthographique d’AEM au lieu d’être ignorés. (GUIDES-48587)
- Lors du basculement de la sélection entre les champs **Largeur** et **Hauteur** dans la boîte de dialogue des propriétés de l’image à l’aide de tailles d’unité telles que `in`, `mm` ou `px`, les valeurs continuent d’augmenter progressivement au lieu de rester stables. (GUIDES-45929)

## Éditeur 2.0

- Espace saisi juste avant la suppression d’une balise intégrée dans une cellule de tableau `<entry>`. (GUIDES-49144)
- L&#39;insertion d&#39;un élément à la position `tgroup` affiche un avertissement **#text n&#39;est pas autorisé ici** ce qui empêche l&#39;insertion d&#39;un tableau normal à cette position. (GUIDES-47446)
- Copier un tableau à partir d’une feuille de calcul Excel et le coller dans le nouvel éditeur place tout le contenu de cellule copié dans une seule cellule de tableau au lieu de le distribuer dans les cellules correspondantes. (GUIDES-47435)
- Un bouton personnalisé **Exporter en tant que PDF** configuré via `editor_toolbar.json` est rendu et reste cliquable en mode Aperçu, mais n’effectue aucune action lorsque l’utilisateur ou l’utilisatrice clique dessus. (GUIDES-47402)
- L’ouverture de certaines rubriques contenant des tableaux ajoute une balise `<foreign>` inattendue avec deux nouvelles colonnes, même si aucune modification n’a été apportée à la rubrique. (GUIDES-46748)
- Lorsqu’une équation MathML est insérée en tant que `conref`, elle ne s’affiche pas correctement. (GUIDES-46601)
- Les éléments MathML et SVG n’effectuent pas le rendu de leur ensemble complet d’attributs, ce qui entraîne la rupture des classes CSS personnalisées et des attributs conditionnels appliqués à ces éléments. (GUIDES-46371)
- L’attribut **Scale** ne s’applique pas aux images en mode Création. (GUIDES-45996)
- L’application d’un attribut `scale` à un tableau ne rend pas le tableau à la taille configurée en modes Création et Aperçu. (GUIDES-45984)
- Le collage d’images copiées à partir de sources externes telles que Paint ou l’outil Capture n’insère pas l’image dans la rubrique. (GUIDES-45983)
- Si vous copiez et collez des `<keywords>` à l’intérieur de `<topicmeta>` dans une `<keydef>` ou une `<topicref>`, les mots-clés sont insérés dans des balises étrangères indésirables. (GUIDES-45800)
- Dans la vue Balise d’un tableau, appuyer sur la touche fléchée vers le haut lorsque le curseur est positionné dans la cellule située directement en dessous d’une balise d’entrée réduite ignore la balise réduite et déplace le curseur au début du document. (GUIDES-45408)
- Toute opération effectuée à partir de la barre d&#39;outils contextuelle du tableau ferme la barre d&#39;outils de manière inattendue, interrompant les opérations suivantes du tableau. (GUIDES-45405)
- L’option **Modifier MathML** s’affiche incorrectement en mode lecture seule ou lorsqu’un fichier est extrait par un autre utilisateur, ce qui permet aux utilisateurs de mettre à jour le contenu de MathML même si le fichier ne doit pas être modifiable. (GUIDES-45172)
- Après avoir utilisé **Insérer après** ou **Insérer avant** à partir du chemin de navigation ou de la vue Plan, le curseur se déplace vers une position arbitraire au lieu de se trouver à l’intérieur de la balise nouvellement ajoutée. (GUIDES-45147)
- Lors d’un glisser-déposer avec la vue Balise activée, la sélection de contenu avec des balises XML ou DITA partielles laisse des balises orphelines indésirables, ce qui entraîne un contenu ou une vue incorrect. (GUIDES-28191)

## Gestion des ressources numériques

- L’utilitaire de purge de version ne se termine pas dans plusieurs scénarios, y compris certains types de fichiers, les ressources avec des métadonnées manquantes et les rapports volumineux, au lieu de terminer la purge et de générer un rapport précis. (GUIDES-43453)

## Publication

- Les noms de fichiers non anglais dans les noms de page générés sont remplacés par des tirets, ce qui rend difficile l’identification de la rubrique ou du fichier associé lors de la publication d’une sortie AEM Sites à l’aide du mappage des composants hérités. (GUIDES-48387)
- Les fichiers JAR `jackson-databind` vulnérables (version 2.9.8) fournis avec AEM Guides dans le package DITA-OT sont identifiés. (GUIDES-43081)

## Révision

- L’ouverture de la vue **côte à côte** dans le panneau Commentaires affiche la copie de travail avec la version commentée, mais les panneaux ne défilent pas de manière synchronisée horizontalement, et le fait de cliquer sur un commentaire ne déplace pas le curseur vers le texte correspondant. (GUIDES-44083)

## Plateforme

- L’utilisation de `scope="external"` pour une référence au contenu de gestion des ressources numériques dans une rubrique ou un mappage entraîne la substitution du chemin relatif de la ressource par un GUID. (GUIDES-35605)
- Pour le contenu créé avant la migration de l’UUID, le téléchargement d’une carte avec les options **Conserver la hiérarchie de fichiers** et **Utiliser le nom de fichier réel** sélectionnées convertit incorrectement les valeurs `href` des éléments `topicref`, `xref` et `conref` avec des `scope="external"` en noms de fichiers basés sur le GUID au lieu de conserver les chemins de fichier relatifs d’origine. Par conséquent, les références externes sont rompues. (GUIDES-46526)
- Lors du chargement de ressources via l’interface utilisateur d’Assets, le statut de chargement n’est pas affiché. (GUIDES-7207)

## Problèmes connus

- Lors de l’exécution d’une opération de révision dans un bloc de code, un avertissement **Opération non autorisée** s’affiche à la première tentative, mais l’opération réussit lorsqu’elle est répétée. (GUIDES-56749)
- Lorsqu’une tâche de révision est créée pour le contenu contenant une `code block`, le formatage barré ne s’applique pas correctement après l’importation et le contenu mis en surbrillance est absent de la vue de comparaison côte à côte. (GUIDES-56811)
- Dans certains cas, l’onglet **Liste des rubriques** du panneau Rapports n’affiche aucun résultat, même si la carte contient plusieurs rubriques. (GUIDES-56893) <br> **Solution :** réindexez le contenu affecté pour recréer les relations parent-mappage. Les rubriques s’affichent alors comme prévu dans l’onglet Liste des rubriques .
- La sélection d’un élément d’instruction de traitement en mode Plan met en surbrillance l’intégralité de la balise parent au lieu de l’élément sélectionné. (GUIDES-48318)
- Lors des opérations de suppression, des incohérences mineures dans le mouvement et la navigation du curseur peuvent se produire sur les zones cliquables, les éléments structurés, les balises de formatage intégrées et les blocs non fusionnables, ce qui peut parfois entraîner un comportement inattendu du curseur ou de la suppression. (GUIDES-46756)
- Une équation MathML encapsulée dans un bloc `foreign` et `equation` entraîne un espacement indésirable. En outre, la saisie dans l’équation entraîne des problèmes même après le réglage de la mise en retrait. (GUIDES-46606)
- Impossible de placer un curseur à l’intérieur d’un `topicref` dans un `reltable` lorsque l’option **Afficher les balises** est activée et que l’option **Afficher les attributs** est désactivée dans les paramètres de l’éditeur. (GUIDES-46565)
- Appuyer sur la touche Retour arrière au début d’un paragraphe juste après un contenu en lecture seule (tel qu’un paragraphe conref) peut supprimer ou fusionner de manière inattendue le paragraphe modifiable, ce qui entraîne la suppression inattendue du paragraphe modifiable. (GUIDES-45049)
- Lorsqu’une balise intégrée est renommée à l’aide de l’option Renommer l’élément , le chemin de navigation ne se met pas immédiatement à jour et ne reflète la modification qu’après le déplacement du curseur dans la balise ou la modification du mode d’affichage. (GUIDES-44993)<br>**Solution :** actualisez le navigateur après avoir renommé la balise intégrée pour mettre à jour le chemin de navigation.
- Lorsque les indicateurs de condition sont appliqués à des éléments tels que bodydiv, les indicateurs débordent sur les balises adjacentes dans la vue Balises complètes, ce qui entraîne un rendu visuel incorrect. (GUIDES-44971)

