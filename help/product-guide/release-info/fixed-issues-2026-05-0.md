---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides, version 2026.05.0
description: Découvrez les correctifs de bugs de la version 2026.05.0 d’Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 4a22e6f8e2505a5e2a990ec38571913c838d0ea1
workflow-type: tm+mt
source-wordcount: '1255'
ht-degree: 0%

---

# Correction de problèmes dans la version 2026.05.0

Cet article couvre les bugs corrigés dans différentes zones de la version 2026.05.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, consultez [Nouveautés de la version 2026.05.0](whats-new-2026-05-0.md).

Découvrez les [instructions de mise à niveau pour la version 2026.05.0](upgrade-instructions-2026-05-0.md).

## Création

- Lors de la sélection d’une image dans l’éditeur à l’aide de la boîte de dialogue **Sélectionner un fichier**, seuls les formats de pixellisation (tels que JPG, PNG et GIF) s’affichent. Les fichiers vectoriels (tels que .ai et .eps) ne sont pas affichés et ne peuvent pas être sélectionnés. (GUIDES-45110)
- Au moment de la mise à niveau, le paramètre `tagsView` est désactivé par défaut, même si sa valeur par défaut dans `ui_config.json` est définie sur `true`. (GUIDES-44651)
- Dans l’éditeur, les références de fichiers s’affichent sous la forme de GUID au lieu de chemins d’accès aux fichiers malgré la configuration `xmleditor.uuid`. (GUIDES-42438)
- Lorsque des schémas Objet avec des valeurs clés similaires sont appliqués dans une rubrique DITA, ils sont mis en surbrillance avec des couleurs presque identiques, ce qui rend difficile de les distinguer et d&#39;identifier le schéma appliqué. (GUIDES-38472)
- Lors de la modification d’une carte de schéma d’objet en mode Création, l’ajout de l’élément `hasInstance` déclenche automatiquement la boîte de dialogue de sélection du fichier, ce qui nécessite que les auteurs insèrent un `href` indésirable pointant vers une ressource AEM. En outre, le chargement du panneau **Propriétés du contenu** échoue pour ces mappages, ce qui empêche les créateurs et créatrices de mettre à jour les attributs d’élément dans la vue de création et les oblige à utiliser la vue Source pour mettre à jour les attributs. (GUIDES-38164)
- Lors de la modification d’un fichier `.ditaval`, tous les commentaires XML ajoutés dans la vue Source sont supprimés lorsque vous passez en vue Création, puis revenez à la vue Source. (GUIDES-33228)


## Gestion des ressources numériques

- La création d’une rubrique dans un dossier dont le nom contient des espaces crée un dossier en double dans lequel les espaces sont remplacés par des tirets et la rubrique y est enregistrée au lieu du dossier d’origine. (GUIDES-41938)
- Lors de la première traduction de mappages volumineux, des fichiers XML vides sont créés pour la langue de destination, ce qui entraîne une charge de serveur accrue et des performances plus lentes. (GUIDES-41613)
- Dans les environnements basés sur une base de données, les liens DITA internes valides apparaissent comme des liens rompus dans **Propriétés de la ressource**, même s&#39;ils fonctionnent correctement dans l&#39;éditeur et dans la sortie publiée. (GUIDES-35048)

## Publication

- Lorsque des modifications apportées à un paramètre prédéfini de sortie dans un profil de dossier sont appliquées à des mappages existants, le **contexte de publication** enregistré pour le paramètre prédéfini d’AEM Sites est réinitialisé. (GUIDES-38377)
- Le symbole de marque (®) n’est pas rendu sur la page de garde de la sortie Native PDF lorsque l’élément `tm` est utilisé dans le titre d’une carte ou d’une carte-livre. (GUIDES-28832)
- Lors de la publication d’un mappage à l’aide d’un modèle de PDF natif, le **Titre du mappage** n’inclut pas le contenu des éléments enfants utilisés dans le `title` de mappage et le filtrage de contenu correspondant n’est pas appliqué au titre.(GUIDES-33730)
- Les liens d’homologue sur plusieurs mappages dans la sortie AEM Sites ne parviennent pas à se résoudre lorsqu’ils pointent vers un `topicref` qui utilise `chunk="to-content"`. (GUIDES-37873)
- Lors de la publication, les fichiers associés aux indicateurs DITAVAL sont déplacés vers un nouveau dossier généré par le système au lieu de rester à leur emplacement relatif attendu dans la sortie. (GUIDES-37564)
- Lorsque plusieurs fichiers DITAVAL avec des conditions en conflit sont utilisés, la sortie Native PDF échoue. (GUIDES-37484)

## Ligne de base

- Les références de rubriques dans un mappage s&#39;affichent incorrectement comme indirectes lors de l&#39;utilisation d&#39;un DITA-OT personnalisé, même si elles sont directement référencées. Ce problème a été résolu avec la nouvelle expérience de base. (GUIDES-19286)
- Les références avec `scope="peer"` sont incorrectement incluses dans le contexte de la ligne de base, ce qui entraîne un temps de publication plus long que prévu. Ce problème a été résolu avec la nouvelle expérience de base. (GUIDES-30048)

## Plateforme

- Lorsque des rubriques ou des mappages volumineux sont ouverts, l’instance de création ne répond plus, ce qui nécessite un redémarrage dans certains cas. (GUIDES-43547)

## Problèmes résolus disponibles avec l’éditeur 2.0

Les problèmes suivants ont été corrigés et ne se produisent plus lors de l’utilisation de l’éditeur 2.0 (ou nouvel éditeur) :

- Lorsque plusieurs colonnes sont supprimées d’un tableau, la structure du tableau devient incohérente ou endommagée. (GUIDES-35438)
- Lorsqu’une colonne est supprimée d’un tableau contenant des cellules fusionnées, une nouvelle colonne vide est ajoutée. (GUIDES-30147)
- Lorsqu’une nouvelle ligne est insérée dans un tableau existant à partir du menu de chemin de navigation, la structure du tableau change de manière inattendue, ce qui entraîne l’absence de bordures et une colonne supplémentaire. (GUIDES-29194)
- En mode Création, la copie et le collage d’une ligne de tableau placent le contenu en dehors du tableau au lieu de l’insérer en tant que nouvelle ligne dans le tableau. (GUIDES-24372)
- Lorsqu’un élément de section sélectionné à l’aide du déplacement de la souris en mode Création est copié et collé, il est converti en éléments de `(<p>)` de paragraphe au lieu de conserver la structure de section. (GUIDES-30023)
- Lorsque le texte mis en surbrillance dans des éléments tels que step ou uicontrol est modifié, le texte sélectionné n’est pas remplacé correctement et est ajouté ou précédé à la place, ce qui entraîne des erreurs de validation. (GUIDES-24371)
- Lorsque la largeur des colonnes d’un tableau est définie à l’aide de valeurs relatives, les colonnes restantes ne s’ajustent pas proportionnellement, ce qui entraîne un alignement incorrect de la disposition du tableau. (GUIDES-26109)
- Lorsqu’un titre de rubrique copié est collé avec les balises désactivées, le premier collage applique un style incorrect et affecte le type dans les propriétés de contenu en tant que rubrique au lieu du titre. (GUIDES-28838)
- Lorsque de grandes sections de contenu sont modifiées, un mouvement de défilement involontaire éloigne la vue de l’éditeur du contenu actif. (GUIDES-35436)
- Lorsque la touche Retour arrière est utilisée sur des éléments, l’éditeur fait défiler l’écran jusqu’en haut de la rubrique, quelle que soit la position du curseur. (GUIDES-32520)
- Lorsque vous utilisez la touche fléchée à gauche ou à droite pour vous déplacer hors des balises intégrées, le curseur se déplace de manière inattendue lors de la première tentative. (GUIDES-26363)
- La vérification orthographique d’AEM fonctionne uniquement pour la langue par défaut en-US et ne respecte pas les autres paramètres régionaux. (GUIDES-14731)
- Lorsque des rubriques DITA volumineuses sont déverrouillées dans l&#39;éditeur, la même rubrique s&#39;ouvre à nouveau dans un onglet en double. En outre, un avertissement de limite de balises est déclenché où `NaN` s’affiche à la place du nombre réel de balises. (GUIDES-34008)
- Les suggestions Acrolinx ne sont pas correctement mises en surbrillance dans l’éditeur pour les rubriques en lecture seule ou verrouillées. (GUIDES-29614)
- Lors de la création d’une `reltable` sans ligne d’en-tête dans la vue Création, la disposition du tableau change après l’ajout d’un sujet à la première cellule, ce qui réduit la colonne suivante et rend difficile le placement des sujets associés. (GUIDES-19555)
- Lorsqu’un lien `xref` est ajouté à une petite cellule de tableau en mode Création, il ne reste pas contenu dans la cellule et apparaît dans les cellules adjacentes de la même ligne. (GUIDES-5489)
- Lorsque vous passez de la vue Auteur à la vue Source, la position du curseur n’est pas conservée et l’éditeur fait défiler l’écran vers le haut. En outre, dans les sujets longs, la position du curseur est perdue et saute aléatoirement vers le milieu ou le haut lors du basculement entre les vues Auteur et Source. (GUIDES-18114, GUIDES-21164)
- Appuyer sur *Entrée* dans un élément de `<li>` crée une nouvelle `<li>`, mais revenir à une `<li>` précédente et appuyer sur *Entrée* convertit incorrectement le contenu de l’élément actif en un élément de `<p>`, ce qui rompt la structure de la liste. (GUIDES-27505)

## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 2026.05.0 :

- Lorsqu&#39;un mappage contient un `topicref` externe pointant vers une ressource non DITA (telle que `.html` ou `.htm`), son aperçu ne s&#39;affiche pas dans l&#39;interface utilisateur d&#39;Assets. (GUIDES-45409)
- Dans l’interface utilisateur d’Assets, le contenu référencé à l’aide de `conref` ne s’affiche pas pour les rubriques DITA, même s’il est correctement rendu dans l’aperçu de l’éditeur. (GUIDES-45505)<br>**Solution de contournement** : pour ce type de contenu, vous pouvez utiliser l’aperçu de l’éditeur.
- Lorsque `xmleditor.uniquefilenames` propriété est activée, les nouvelles rubriques créées à l’aide d’un modèle n’incluent pas le titre de la rubrique. (GUIDES-44737)
- Les API `getAsset`, `startAssetProcessing` et `getAssetProcessingStatus` ne sont pas disponibles via Java SDK.

