---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides version 5.2.0
description: Découvrez les correctifs de la version 5.2.0 d’Adobe Experience Manager Guides.
source-git-commit: 5eee826022f798b4eb0014ea4b97d2916eb92f33
workflow-type: tm+mt
source-wordcount: '3559'
ht-degree: 0%

---

# Correction de problèmes dans la version 5.2.0 (mai 2026)

Cet article couvre les bugs corrigés dans différentes zones de la version 5.2.0 d’Adobe Experience Manager Guides.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, consultez [Nouveautés de la version 5.2.0](whats-new-5-2-0.md).

Découvrez les [instructions de mise à niveau pour la version 5.2.0](upgrade-instructions-5-2-0.md).


## Création

- Si un élément de `prop` vide sans attribut ni valeur est ajouté à un fichier DITAVAL, les éléments de `prop` supplémentaires ne peuvent pas être ajoutés. (GUIDES-33597)
- Après la mise à niveau de Experience Manager Guides vers la version 2025.08.0, l’option permettant d’activer ou de désactiver l’onglet personnalisé **Acrolinx** ne s’affiche plus dans les paramètres de **Workspace**. (GUIDES-35261)
- Le CSS personnalisé appliqué à un profil au niveau du dossier pour les rubriques ou les mappages est rétabli au style par défaut dans le mode Aperçu lors de l’actualisation du navigateur. (GUIDES-31098)
- Les opérations **Annuler** et **Rétablir** ne fonctionnent pas comme prévu dans la vue Source de l&#39;éditeur pour les fichiers DITA. (GUIDES-24914, GUIDES-25034)
- Lors du référencement d&#39;un plan DITA dans une rubrique à l&#39;aide de l&#39;élément `Xref`, le nom de fichier du plan référencé est affiché à la place du titre du plan. (GUIDES-21759)
- Lors de l’ajout de plusieurs fichiers Schematron à des fins de validation via le panneau de droite de l’interface de l’éditeur, une erreur **les fichiers Schematron n’existent pas ou contiennent des erreurs** s’affiche même si les fichiers ajoutés sont valides et ne comportent aucune erreur. (GUIDES-33731)
- Les équations MathML volumineuses ou complexes ne s’affichent pas dans l’éditeur. (GUIDES-29095)
- Lorsque plusieurs plans ou rubriques DITA sont ouverts et que l&#39;une des rubriques est fermée, le bouton **>>** qui affiche tous les onglets ouverts est chevauché par les onglets ouverts restants dans la barre d&#39;onglets. (GUIDES-31421)
- Lorsque le **workflow d’approbation** est activé, le bouton **Démarrer une nouvelle version** n’est pas visible sur la barre d’outils de l’éditeur si le panneau de gauche et le panneau des propriétés de contenu sont ouverts. (GUIDES-29093)
- Lorsque les noms des fragments de code dépassent la largeur du panneau, ils sont renvoyés à la ligne suivante de manière incorrecte, ce qui entraîne un chevauchement avec les fragments de code adjacents et un impact sur la lisibilité. (GUIDES-22685)
- Lorsque vous ajoutez la même référence plusieurs fois à un plan DITA, la vue **Map** affiche le titre uniquement pour la dernière occurrence, tandis que les précédentes affichent l&#39;UUID de la référence. (GUIDES-9699)
- Les fichiers DITAVAL restent modifiables, même lorsqu’ils sont verrouillés par un autre utilisateur ou lorsque le serveur a activé **Désactiver l’édition sans verrouiller le fichier** et que le fichier est ouvert en mode lecture seule. (GUIDES-27754)
- Les journaux des nœuds manquants sont générés à partir de tâches de nettoyage interne qui ne sont pas requises et qui sont incorrectement marquées comme des erreurs, ce qui encombre les fichiers journaux. (GUIDES-31765)
- Lors de la modification d’un fichier Schematron (`*.sch`) et de l’utilisation de la fonction Rechercher et remplacer , le panneau Rechercher et remplacer s’affiche partiellement hors écran en bas, empêchant l’accès à ses champs et contrôles de saisie. (GUIDES-38412)
- Impossible d’ajouter plusieurs **libellés de version** à une rubrique dans la boîte de dialogue **Enregistrer en tant que nouvelle version**. (GUIDES-32716)
- Lors de la sélection d’une image dans l’éditeur à l’aide de la boîte de dialogue **Sélectionner un fichier**, seuls les formats de pixellisation (tels que JPG, PNG et GIF) s’affichent. Les fichiers vectoriels (tels que .ai et .eps) ne sont pas affichés et ne peuvent pas être sélectionnés. (GUIDES-45110)
- Au moment de la mise à niveau, le paramètre `tagsView` est désactivé par défaut, même si sa valeur par défaut dans `ui_config.json` est définie sur `true`. (GUIDES-44651)
- Dans l’éditeur, les références de fichiers s’affichent sous la forme de GUID au lieu de chemins d’accès aux fichiers malgré la configuration `xmleditor.uuid`. (GUIDES-42438)
- Lorsque des schémas Objet avec des valeurs clés similaires sont appliqués dans une rubrique DITA, ils sont mis en surbrillance avec des couleurs presque identiques, ce qui rend difficile de les distinguer et d&#39;identifier le schéma appliqué. (GUIDES-38472)
- Lors de la modification d’une carte de schéma d’objet en mode Création, l’ajout de l’élément `hasInstance` déclenche automatiquement la boîte de dialogue de sélection du fichier, ce qui nécessite que les auteurs insèrent un `href` indésirable pointant vers une ressource AEM. En outre, le chargement du panneau **Propriétés du contenu** échoue pour ces mappages, ce qui empêche les créateurs et créatrices de mettre à jour les attributs d’élément dans la vue de création et les oblige à utiliser la vue Source pour mettre à jour les attributs. (GUIDES-38164)
- Lors de la modification d’un fichier `.ditaval`, tous les commentaires XML ajoutés dans la vue Source sont supprimés lorsque vous passez en vue Création, puis revenez à la vue Source. (GUIDES-33228)
- Lors de la mise à jour d’une équation de MathML intégrée à l’aide de l’option Modifier le MathML du menu contextuel, la valeur mise à jour n’est pas reflétée tant que la page n’est pas actualisée. (GUIDES-38198)
- Lorsqu’une rubrique contient de nombreux éléments réutilisables (ceux avec des ID) ajoutés dans le panneau Réutilisable , certains éléments peuvent ne pas être accessibles en raison de la hauteur fixe du conteneur. (GUIDES-37220)
- Lors de l&#39;insertion d&#39;une référence croisée à un fichier, les icônes des cartes et des rubriques sont identiques. (GUIDES-36662)
- Lors de la modification d’une carte, les symboles spéciaux de la `navtitle` ne s’affichent pas pour `topichead` dans la vue de création. (GUIDES-35435)

## Gestion des ressources numériques

- Lorsque vous chargez à nouveau une image modifiée via l’interface utilisateur de Experience Manager Guides, le rendu d’origine de l’image est mis à jour, mais le contenu DITA associé continue d’afficher la version précédente de l’image. (GUIDES-33693)
- Lorsque vous tentez de déplacer plusieurs dossiers de leur emplacement source vers un autre emplacement (à l’aide de l’outil de déplacement en bloc), l’opération échoue si les noms de dossier commencent par la même chaîne (par exemple, Product et ProductImages). (GUIDES-29096)
- La suppression d’une ressource recherchée dans l’interface utilisateur d’Omnisearch Assets contourne la boîte de dialogue d’avertissement **Forcer la suppression** et supprime directement la ressource, même si elle est référencée dans du contenu DITA existant. (GUIDES-17232)
- Impossible de supprimer les libellés de version du panneau **Historique des versions** dans l’interface utilisateur Assets. (GUIDES-38276)
- La création d’une rubrique dans un dossier dont le nom contient des espaces crée un dossier en double dans lequel les espaces sont remplacés par des tirets et la rubrique y est enregistrée au lieu du dossier d’origine. (GUIDES-41938)
- Lors de la première traduction de mappages volumineux, des fichiers XML vides sont créés pour la langue de destination, ce qui entraîne une charge de serveur accrue et des performances plus lentes. (GUIDES-41613)
- Dans la recherche Assets, les sous-ressources et les nœuds de métadonnées (tels que les images et les fichiers PDF) sont incorrectement inclus dans les résultats. En outre, pour un paramètre prédéfini de sortie lorsque des filtres DITAVAL sont appliqués, la recherche renvoie des fichiers DITAVAL générés en interne et créés à partir de paramètres prédéfinis de condition. (GUIDES-35418)
- Lors du chargement de ressources dont le nom de fichier contient des caractères non valides, la ressource ne charge pas et affiche un message incorrect **Le fichier est verrouillé par un autre utilisateur** même si la ressource est déverrouillée. (GUIDES-32680)

## Publication

- Lors de la publication d&#39;un plan DITA à l&#39;aide de la ligne de base sur AEM Sites (avec le mappage de composant hérité), les éléments de plan avec l&#39;attribut `processing-role = resource-only` sont également publiés. (GUIDES-37649)
- Dans certains cas, la propriété `jcr:content/fmUuidOfSource` est absente des pages de sortie AEM Sites (avec le mappage des composants hérités), ce qui entraîne la création de pages de contenu indétectables. (GUIDES-34242)
- Le filtrage de contenu à l’aide de filtres DITAVal et de paramètres prédéfinis conditionnels ne fonctionne pas pour la publication Salesforce. (GUIDES-33515)
- Impossible de créer un paramètre prédéfini PDF natif pour un mappage si un dossier portant le même nom existe dans sa hiérarchie de contenu. (GUIDES-33012)
- Lorsque la sortie native de PDF est générée à l’aide d’une ligne de base dynamique, le terme **PDFProject** s’affiche en tant que titre de PDF au lieu du titre de mappage réel. (GUIDES-31102)
- La génération d’une sortie PDF native avec certaines valeurs d’attribut `print` dans les références de rubrique ne fonctionne pas comme prévu. (GUIDES-31101)
- Lorsqu&#39;un dossier contenant des mappages DITA est déplacé à l&#39;aide de l&#39;interface utilisateur d&#39;Assets ou de l&#39;option **Déplacement en bloc**, les collections de mappages existantes et les collections d&#39;activation en bloc qui font référence à ces mappages ne se chargent pas. (GUIDES-28355)
- Lorsque vous déplacez un dossier contenant une carte avec des paramètres prédéfinis de condition, les conditions ne sont pas appliquées à la sortie générée après le déplacement. (GUIDES-28352)
- Lorsque vous générez une sortie AEM Sites à l’aide du mappage des composants hérités, les rubriques qui utilisent l’attribut `copy-to` sont publiées avec le nom de la rubrique `copy-from` au lieu du nom défini dans l’attribut `copy-to`. (GUIDES-22155)
- L&#39;activation d&#39;un ou plusieurs plans DITA à partir du **tableau de bord de publication en masse** génère des journaux trop volumineux. (GUIDES-20746)
- Lors de la génération de PDF, les règles de filtrage d’un fichier DITAVAL sont ignorées si un nom de propriété contient un point. (GUIDES-33229)
- La publication Salesforce affiche un statut réussi dans l&#39;interface utilisateur même lorsqu&#39;un plan DITA contenant un élément `topichead` ne parvient pas à publier les rubriques qu&#39;il contient. (GUIDES-32143)
- Pour le paramètre prédéfini de sortie HTML5, la fonctionnalité de filtrage de recherche ne fonctionne pas dans AEM Assets pour le filtrage DITAVAL, car les fichiers correspondants ne s’affichent pas lorsque le filtre DITAVAL est sélectionné. (GUIDES-28231)
- Lors de la génération d&#39;un PDF natif pour un plan DITA avec plusieurs rubriques, si une rubrique contient un élément `fig` dans une `figgroup` avec un `title`, le titre du `figgroup` est incorrectement rendu en tant que titre de chapitre dans la table des matières. (GUIDES-23223)
- Lors de la duplication de modèles PDF à partir de l’interface utilisateur, l’UUID est également dupliqué, ce qui entraîne la suppression de fichiers de modèle et génère des sorties PDF incorrectes. (GUIDES-30456)
- Lors de la génération d&#39;un PDF natif pour un plan DITA, le titre de `example` élément est rendu `h1` niveau titre, ce qui entraîne une incohérence visuelle et une structure de table des matières incorrecte. (GUIDES-19958)
- Lorsque la même rubrique est réutilisée sur plusieurs mappages avec différents paramètres prédéfinis conditionnels, la publication du dernier mappage sur Salesforce remplace le contenu de la rubrique, ce qui entraîne l’affichage de données incorrectes aux utilisateurs de mappages précédemment publiés. (GUIDES-37806)
- Lors de la publication d’un PDF natif pour un mappage qui inclut un traitement conditionnel ou certains mappages imbriqués, le `dc:title` défini dans le mappage ne s’affiche pas sur la couverture du PDF, ce qui entraîne l’absence du titre de la couverture. (GUIDES-37733)
- La génération de la sortie du site AEM (à l’aide du mappage des composants composites) pour un mappage échoue et entraîne une erreur lorsque la variable `map_title` est présente dans le chemin de sortie. (GUIDES-36968)
- Lorsqu’un chemin de sortie avec une barre oblique est spécifié dans le paramètre prédéfini de sortie Native PDF, l’interface utilisateur ajoute automatiquement une barre oblique supplémentaire, ce qui entraîne un double chemin d’accès qui entraîne l’échec du chargement PDF dans certains scénarios. (GUIDES-34932)
- La publication de pages AEM Sites générées à partir de contenu DITA par le biais de Publication rapide ou de Gérer la publication publie involontairement les ressources DITA associées. (GUIDES-27967)
- Lors de la publication d’un mappage dans AEM Sites (à l’aide du mappage des composants hérités), les références croisées (`xrefs`) avec les `scope = peer` qui ciblent des sous-éléments d’une rubrique (comme des paragraphes) dans un autre mappage ne se résolvent pas sur l’ID d’élément spécifique et se résolvent uniquement sur la rubrique parente, ce qui entraîne le chargement de la page au début de la rubrique plutôt que le défilement vers la section prévue. (GUIDES-21802)
- Lors de la publication d&#39;un plan DITA à l&#39;aide de la ligne de base sur AEM Sites (avec le mappage de composant hérité), les éléments de plan avec l&#39;attribut `processing-role = resource-only` sont également publiés. (GUIDES-34298)
- Lorsque des modifications apportées à un paramètre prédéfini de sortie dans un profil de dossier sont appliquées à des mappages existants, le **contexte de publication** enregistré pour le paramètre prédéfini d’AEM Sites est réinitialisé. (GUIDES-38377)
- Le symbole de marque (®) n’est pas rendu sur la page de garde de la sortie Native PDF lorsque l’élément `tm` est utilisé dans le titre d’une carte ou d’une carte-livre. (GUIDES-28832)
- Lors de la publication d’un mappage à l’aide d’un modèle de PDF natif, le **Titre du mappage** n’inclut pas le contenu des éléments enfants utilisés dans le `title` de mappage et le filtrage de contenu correspondant n’est pas appliqué au titre.(GUIDES-33730)
- Les liens d’homologue sur plusieurs mappages dans la sortie AEM Sites ne parviennent pas à se résoudre lorsqu’ils pointent vers un `topicref` qui utilise `chunk="to-content"`. (GUIDES-37873)
- Lors de la publication, les fichiers associés aux indicateurs DITAVAL sont déplacés vers un nouveau dossier généré par le système au lieu de rester à leur emplacement relatif attendu dans la sortie. (GUIDES-37564)
- Lorsque plusieurs fichiers DITAVAL avec des conditions en conflit sont utilisés, la sortie Native PDF échoue. (GUIDES-37484)
- Lors de la création ou de la modification d’une rubrique qui inclut une citation, si le champ Auteur n’est pas ajouté à la boîte de dialogue de citation, le PDF n’est pas généré. (GUIDES-37934)
- Lors de la génération de la sortie AEM Sites, les titres de carte contenant des mots-clés et des titres de rubrique avec `<ph>` élément ne sont pas inclus dans la sortie publiée. (GUIDES-36641)
- Le fichier CSS (`rhdefault.css`) est incorrectement appliqué au modèle PDF bien qu’aucune feuille CSS ne soit référencée, ce qui entraîne l’absence de journaux d’erreurs de fichier CSS.(GUIDES-31752)
- Lors du téléchargement de fichiers temporaires pour une carte avec une ligne de base lors de la publication d’un paramètre prédéfini, le fichier `metadata.xml` référence incorrectement le `versionPath` au lieu du `dampath`.(GUIDES-29815)
- Pour la sortie Native PDF, l’élément `<alt>` pour les images est ignoré, ce qui empêche l’application de texte secondaire pour des raisons d’accessibilité. (GUIDES-29087)
- Dans la sortie PDF native, l’élément `abbreviated-form` affiche le `glossterm` au lieu du `glossSurfaceForm` ou du `glossAcronym` désigné. (GUIDES-26393)
- Lors de l’activation en bloc, la création de package ajoute des filtres pour tous les chemins répertoriés sous la propriété `fileReference` d’une page, y compris les chemins externes et d’homologue. (GUIDES-24887)
- Lors de la publication à l’aide d’un paramètre prédéfini personnalisé avec du contenu contenant des liens vers des fichiers PDF sans portée définie comme externe, le processus ne se termine pas. (GUIDES-21708)
- La publication Salesforce échoue avec une erreur d’application, lorsqu’une rubrique portant le même nom et la même URL existe déjà. (GUIDES-32390)
- La césure automatique n’est pas appliquée dans la sortie PDF native, même si le paramètre **Utiliser la césure automatique** est activé pour le paramètre prédéfini de sortie. (GUIDES-19703)

## Traduction

- Lors du zoom sur l’écran de l’interface utilisateur de traduction, le bouton **Envoyer pour traduction** se déplace sous les points de suspension et devient activé même si aucune ressource n’est sélectionnée. (GUIDES-33720)
- Lors de la sélection de fichiers avec le statut **Désynchronisé** dans l’interface utilisateur de traduction et lorsque la largeur d’écran est limitée en raison de l’ouverture des panneaux Gauche et Droite, le libellé **Envoyer pour traduction** est tronqué. (GUIDES-33692)
- Lorsqu’une image initialement gérée en tant que ressource spécifique à la langue avec une version spécifique (par exemple, sous `/en/`) est déplacée vers un dossier global avec une version mise à jour et que l’exportation de la ligne de base est effectuée, la nouvelle ligne de base continue à référencer des versions obsolètes spécifiques à la langue de cette image, ce qui entraîne l’échec de l’exportation de la ligne de base. (GUIDES-39394)
- Lors du traitement de projets de traduction créés en dehors de Experience Manager Guides, plusieurs messages de journal d’erreurs sont générés indiquant que *`fmTarget`propriété est introuvable*. (GUIDES-37804)

## Ligne de base

- Lors de la création d’une ligne de base dynamique, l’éditeur ne répond parfois plus en raison de plusieurs requêtes d’API simultanées, ce qui interrompt toutes les autres opérations. (GUIDES-39054)
- Les références de rubriques dans un mappage s&#39;affichent incorrectement comme indirectes lors de l&#39;utilisation d&#39;un DITA-OT personnalisé, même si elles sont directement référencées. Ce problème a été résolu avec la nouvelle expérience de base. (GUIDES-19286)
- Les références avec `scope="peer"` sont incorrectement incluses dans le contexte de la ligne de base, ce qui entraîne un temps de publication plus long que prévu. Ce problème a été résolu avec la nouvelle expérience de base. (GUIDES-41823)


## Révision

- Lors de l’affectation d’un utilisateur à une tâche de révision, la liste déroulante répertorie tous les utilisateurs au lieu de seulement ceux associés aux projets sélectionnés, ce qui entraîne des options utilisateur non valides. (GUIDES-37781)
- Lorsque le réviseur termine une tâche de révision ou que l&#39;initiateur met à jour la tâche de révision sans saisir de commentaires, l&#39;e-mail de notification envoyé affiche le commentaire précédent le plus récent. (GUIDES-33590)

## Rapports

- L’ouverture d’un rapport pour une carte entraîne un retard dans le chargement du panneau Filtres (GUIDES-39385)
- Le rapport Liste interrompue inclut incorrectement des liens externes, des `keyrefs` valides et des mots-clés qui sont correctement résolus dans la portée du mappage actuel. (GUIDES-27774)

## Plateforme

- Les journaux d’erreurs générés lors du chargement d’une ressource via l’interface utilisateur d’Assets ou de la création d’un nouveau fichier à partir de l’interface utilisateur de l’éditeur utilisent incorrectement le terme `predecessor` au lieu de `successor` dans le message du journal. (GUIDES-35607)
- L’utilisation de `scope="external"` pour une référence au contenu de gestion des ressources numériques dans une rubrique ou un mappage entraîne la substitution du chemin relatif de la ressource par un GUID. (GUIDES-38783)
- Lorsqu’une rubrique contient un grand nombre de références liées à des dossiers contenant de nombreux fichiers, l’instance de création peut devenir lente ou ne plus répondre, ce qui nécessite dans certains cas un redémarrage de l’instance. (GUIDES-43547)
- Lors de la tentative d’enregistrement d’une rubrique ou d’un mappage, l’opération peut échouer par intermittence avec une erreur **Échec de l’enregistrement du fichier**, en particulier lors de tâches de traitement intensif des ressources ou de workflows de traduction exécutés en arrière-plan. (GUIDES-37837)


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

### Création

- Lors du chargement d’images marquées dans des fichiers DITAVAL, les images sont interrompues après l’actualisation du navigateur lorsque le paramètre `Enable UUIDs` est désactivé. (GUIDES-45853)
- Dans l’éditeur, les fichiers `.ditval` et `.md` ne sont plus modifiables lorsque le *workflow d’approbation* est activé. (GUIDES-42037)
- La sélection d’un sujet en mode Aperçu ne le met pas en surbrillance dans la vue Carte si le sujet se trouve dans des balises de bookmap (frontend, chapter, part ou batter) ou s’il fait partie d’un contenu cyclique. (GUIDES-42416)
- Lorsqu’un fichier est ouvert à la fois dans l’éditeur et dans le panneau de recherche, sa suppression dans le panneau de l’explorateur supprime le fichier et actualise la liste de l’explorateur, mais l’actualisation de la page continue d’afficher le fichier dans le panneau de recherche. (GUIDES-41935)

### Gestion des ressources numériques

- Dans l’interface utilisateur d’Assets, le bouton **Déplacer** n’est pas activé à la première tentative lorsque plus de 2 fichiers ou dossiers sont sélectionnés. (GUIDES-42721) <br> **Solution** : après avoir sélectionné plus de deux fichiers ou dossiers, patientez quelques secondes avant de sélectionner le dossier de destination.

### Révision

- Lors de la mise à jour d’une tâche de révision active, si une rubrique qui fait déjà partie de la révision est supprimée puis ajoutée à nouveau sans cliquer sur Mettre à jour, les informations du ou des réviseurs dans l’onglet Réviseurs sont perdues. (GUIDES-38774)
- Lorsqu’une rubrique de révision en cours est supprimée d’une tâche de révision en cours, son état de document reste **En révision**, même si la rubrique ne fait plus partie d’une tâche de révision. (GUIDES-38709)<br>**Solution de contournement** : remplacez le statut du document de la rubrique **En cours de révision** par le statut approprié à partir de la page Propriétés ou du panneau Propriétés du fichier.

### Éditeur 2.0

- Copier-coller du contenu dans la même rubrique vers un emplacement non valide dans l’éditeur insère une balise étrangère involontaire. (GUIDES-45378)
- La copie et le collage de `<keywords>` dans `<topicmeta>` dans `<keydef>` ou `<topicref>` insère des balises étrangères inattendues. (GUIDES-45800)
- Lorsque le contenu est copié à partir d’un mappage ou d’une rubrique à l’aide de l’option Copier du menu contextuel, puis collé, des balises `<data>` supplémentaires inattendues sont insérées dans le contenu collé. (GUIDES-45703)
- Sous Windows, la copie et le collage d’une ligne de tableau ajoutent des attributs indésirables au tableau, ce qui entraîne des erreurs de balisage et empêche l’enregistrement du document. (GUIDES-45784)
- Faites glisser la sélection autour d’un tableau ou le tableau simple ne fonctionne pas comme prévu. (GUIDES-45406)
- Le collage d’images à partir de sources externes ne les insère pas dans la rubrique. (GUIDES-45983)
- Le contenu MathML référencé via `conref` ne s’affiche pas correctement. (GUIDES-46601)
- Le rendu incomplet des attributs pour les éléments MathML et SVG rompt les classes CSS personnalisées et la gestion des attributs de condition. (GUIDES-46371)
- les équations de MathML encapsulées dans des balises `foreign` et `equation-block` introduisent des espaces indésirables et perturbent le comportement de modification. (GUIDES-46606)
- Effectuer un glisser-déposer d’un élément contenant une référence de clé convertit le `keyref` en chemin absolu. (GUIDES-45701)
- Dans l’éditeur de cartes, la `Ctrl+click` sur un lien rompu déclenche une erreur d’application. (GUIDES-45544)
