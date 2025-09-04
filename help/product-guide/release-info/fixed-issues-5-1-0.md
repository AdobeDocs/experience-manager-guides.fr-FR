---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides version 5.1.0
description: Découvrez les correctifs de la version 5.1.0 d’Adobe Experience Manager Guides.
source-git-commit: 6c29d5540f48c850416db279b4392b6042c8ca2c
workflow-type: tm+mt
source-wordcount: '1789'
ht-degree: 1%

---

# Correction de problèmes dans la version 5.1.0 (septembre 2025)

Cet article couvre les bugs corrigés dans différentes zones de la version 5.1.0 d’Adobe Experience Manager Guides.


Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 5.1.0](whats-new-5-1-0.md).

Découvrez les [instructions de mise à niveau pour la version 5.1.0](upgrade-instructions-5-1-0.md).


## Création

- Les fichiers **CSS** et **Mise en page** dans les modèles PDF natifs présentent un comportement de verrouillage de fichier incohérent, ce qui permet d’apporter des modifications même lorsque les fichiers sont verrouillés. (GUIDES-26688)
- L’actualisation de la page après l’ajout de boutons personnalisés au panneau de gauche crée des onglets en double. (GUIDES-30899)
- Lorsque du contenu XML contenant des crochets angulaires (tel que &lt;/ ou />) est ajouté dans un élément `code block` dans une rubrique, l’élément de bloc de code apparaît vide dans la sortie finale. (GUIDES-31007)
- Les valeurs des variables globales `canCheckIn` et `canCheckOut` ne sont pas correctement définies lorsqu’un fichier est extrait et archivé à partir de la barre d’outils de l’éditeur.(GUIDES-29890)
- Lorsqu&#39;un plan DITA est sélectionné dans la vue Carte, le nombre de sélections est d&#39;abord affiché de manière incorrecte car les nœuds enfants du plan ne sont pas sélectionnés. Le nombre correct de sélections et l’inclusion de tous les nœuds enfants ne sont reflétés que lors de la sélection suivante. (GUIDES-25663)
- Les fichiers Markdown ne sont pas récupérés lors d’une recherche dans le panneau Référentiel à l’aide du filtre **Rubrique DITA**. En outre, les fonctions **Rechercher et remplacer** ne fonctionnent pas pour les fichiers Markdown et le contenu associé. (GUIDES-27133)
- Impossible de personnaliser la **liste déroulante du menu** de la barre d’outils de l’éditeur à l’aide du framework d’extension. Par conséquent, vous ne pouvez pas masquer ni afficher les boutons existants ni en ajouter de nouveaux dans la liste déroulante Menu . (GUIDES-28748)
- Lorsqu’un commentaire XML est ajouté à l’intérieur d’un élément dans la vue Source, les espaces de début et de fin autour du commentaire sont perdus lors du changement de vue. (GUIDES-29781)
- Les options multimédias ne fonctionnent pas lorsqu’elles sont présentes dans l’icône représentant des points de suspension (menu **Plus**) de la barre d’outils. (GUIDES-29583)
- Lors de la création d’une rubrique dans l’interface utilisateur ou l’éditeur d’Assets, la rubrique ne s’ouvre pas automatiquement dans l’éditeur si le paramètre `xmleditor.uniquefilenames` est défini sur true dans `XMLEditorConfig`. (GUIDES-28171)
- Les espaces ajoutés dans une équation MathML dans la vue Source ne sont pas conservés lors du changement de vue de l’éditeur. (GUIDES-26111)
- Si vous ne fermez pas les connexions de session JCR lors de la mise à jour ou de la création de rubriques, des fuites de mémoire et des temps d’arrêt du service surviennent. (GUIDES-26282)
- Faire glisser les colonnes modifie leur largeur de pourcentage en valeurs en pixels, ce qui entraîne des distorsions ou des incohérences dans les tableaux.(GUIDES-23128)
- Lorsque du contenu est collé dans une `code block` ou lorsque des espaces sont ajoutés dans la `code block` et que la vue est changée, l’espacement est perdu. (GUIDES-27478)
- Lors de l’ajout d’un mappage au `bookmap`, il est stocké dans `fmditatopicrefs` au lieu de `fmditamaprefs`. (GUIDES-25480)
- La boîte de dialogue **Insérer une image** ne s’affiche pas correctement sur un écran haute résolution ou sur un écran agrandi, ce qui entraîne la disparition du titre de la figure et des champs de texte secondaire. (GUIDES-26459)
- Le chargement de la zone d’insertion de caractères spéciaux dans l’éditeur échoue pour les paramètres régionaux allemands. (GUIDES-24537)
- Les commentaires et les étiquettes ajoutés lors de l&#39;enregistrement d&#39;une nouvelle version d&#39;un fichier DITAVAL ne sont pas enregistrés dans l&#39;historique des versions avec la nouvelle version. (GUIDES-24076)
- Les références entrantes et sortantes sous **Propriétés du fichier** dans le panneau de droite ne s’actualisent pas correctement lors du changement entre les fichiers de mappage. Ce problème se produit spécifiquement lorsque les fichiers de mappage contiennent un grand nombre de références. (GUIDES-23344)
- Le filtre Référentiel ne conserve pas l’ordre des filtres personnalisés définis dans le `ui_config.json`. (GUIDES-21193)
- La suppression de plusieurs lignes de texte dans un élément de `codeblock` crée un espace vide qui ne peut pas être supprimé de la vue de création. (GUIDES-20672)
- La génération de nouveaux identifiants pour les éléments échoue lorsque ces éléments sont ajoutés via des fragments de code ou créés via des modèles, même si l’option **générer automatiquement l’identifiant** est activée dans `XMLEditorConfig`. (GUIDES-21734)
- La création d&#39;une ressource DITA à partir de modèles DITA copie les propriétés de réplication des modèles DITA correspondants. (GUIDES-25145)
- Impossible d’accéder aux propriétés du fichier à partir du panneau du référentiel si le nom du dossier parent inclut le caractère «&amp; ». (GUIDES-25762)
- La fermeture d&#39;un fichier de rubrique permet de l&#39;enregistrer en tant que nouvelle version, même lorsque la rubrique est verrouillée. Ce problème se produit spécifiquement lorsque l’option **Demander une nouvelle version à la fermeture** est activée dans `XMLEditorConfig`. (GUIDES-23875)
- La largeur maximale actuelle du panneau du référentiel masque les titres de rubrique et de mappage lorsque la hiérarchie de contenu est profondément imbriquée. (GUIDES-27751)

## Gestion des ressources numériques

- La copie d’un dossier contenant un grand nombre de ressources à partir de l’interface utilisateur d’Assets entraîne un délai d’expiration de l’API. L’opération continue de s’exécuter sur le serveur principal et se termine au bout d’un certain temps, mais aucun message de réussite ou d’échec, ou de notification n’est affiché dans l’interface utilisateur. (GUIDES-30900)
- L’opération de copier-coller effectuée sur un dossier dans l’interface utilisateur d’Assets échoue en raison d’erreurs de post-traitement. (GUIDES-30840)
- L’opération de copier-coller échoue pour les dossiers contenant des ressources composites (ressources avec sous-ressources) dans l’interface utilisateur d’Assets. (GUIDES-28107)
- Les dossiers contenant un grand nombre de ressources ne se chargent pas correctement dans le référentiel. (GUIDES-32500)
- Les noms de nœud de dossier ne s’affichent pas correctement à la place des titres de dossier dans l’éditeur. (GUIDES-32402)
- Une erreur se produit lors du chargement de ressources dont les noms de fichier contiennent des caractères non pris en charge ou interdits . (GUIDES-28845)
- Lors de l’ouverture d’une rubrique dans la vue Auteur après l’actualisation du navigateur, les balises précédemment appliquées dans le panneau Propriétés du fichier ne sont pas conservées et l’ajout de nouvelles balises remplace les balises existantes, en particulier lorsqu’un grand nombre de balises sont disponibles pour la sélection. (GUIDES-29078)
- Lors de la génération d&#39;un rapport de métadonnées pour un plan DITA contenant un grand nombre de ressources, le bouton **Gérer** ne répond plus ou affiche une réponse retardée. (GUIDES-28443)
- L’état du document de la copie de travail d’une rubrique est affiché en regard de toutes les versions de cette rubrique dans l’interface utilisateur de traduction et de ligne de base. (GUIDES-20674)

## Révision

- Les tentatives de création de tâches de révision par le biais du workflow AEM échouent systématiquement, car le nœud de révision n’est pas créé. (GUIDES-28214)
- La vue Document de l’interface utilisateur de révision n’inclut pas le contenu pour certaines tailles d’écran, ce qui oblige les utilisateurs à faire défiler l’écran vers la droite ou la gauche pour afficher l’intégralité du contenu. (GUIDES-25292)
- La mise à jour des détails d’une tâche de révision dans le tableau de bord de révision ne confirme pas si la mise à jour a réussi ou non. (GUIDES-8051)

## Traduction

- Les traductions envoyées via Experience Manager Guides n’incluent pas les ressources jointes, ce qui rend le bouton **Démarrer** de la tâche de traduction indisponible pour les utilisateurs. (GUIDES-28237)

## Publication

- Dans la sortie Native PDF, la liste des index (LOI) s’affiche dans un ordre non alphabétique et les termes d’index imbriqués ne sont pas correctement regroupés, ce qui rend l’index difficile à parcourir. (GUIDES-29090)
- La liste déroulante **Modèle de page de mappage** et **Modèle de page de rubrique** de la page du paramètre prédéfini de sortie de mappage des composants AEM Sites apparaît vide lorsque le chemin de destination contient une variable avec deux points. (GUIDES-28119)
- Lorsqu&#39;un plan DITA contient différents types de références de rubrique telles que Concept, Référence ou Tâche, et qu&#39;il est fusionné à l&#39;aide de l&#39;attribut `chunk=to-content` pour générer une sortie sur une seule page dans AEM Sites avec le mappage de composant, le contenu n&#39;est pas publié correctement en raison d&#39;erreurs de publication. (GUIDES-28118)
- La publication d&#39;un plan DITA avec `chunk=to-content` attribut crée des nœuds JCR en double dans la nouvelle sortie AEM Sites, ce qui entraîne une structure de contenu redondante dans AEM Sites. (GUIDES-28104)
- Lors de la publication d&#39;un plan DITA à l&#39;aide de la nouvelle sortie AEM Sites, si une rubrique possède l&#39;attribut `chunk =to-content` et que la sortie est définie pour utiliser les titres de rubrique comme noms de page, le nom de page généré affiche incorrectement le mot **chunk** au lieu de conserver le nom de rubrique d&#39;origine. (GUIDES-28102)
- La propriété `cq:template` définie dans le modèle de rubrique AEM Guides pour la nouvelle publication AEM Sites affiche une valeur incorrecte, ce qui affecte la structure du modèle et le rendu du contenu. (GUIDES-27789)
- La publication native de PDF se poursuit indéfiniment si le contenu DITA comporte un lien web sans que la portée soit définie comme `external`. (GUIDES-26434)
- La publication des PDF natifs et des sites AEM est bloquée et mise en file d’attente en cas d’erreur dans le contenu. (GUIDES-26516)
- Lors de la génération de pages du site AEM avec des titres qui incluent plusieurs mots séparés par des espaces, le titre de la carte affiche des tirets au lieu des espaces. (GUIDES-27903)
- Pour le PDF natif, un nom de propriété de métadonnées non valide n’est pas résolu et s’affiche comme `unresolved property name` dans **propriétés du document**. (GUIDES-25680)
- Le texte multiligne dans `codeblock` entraîne des problèmes de débordement de texte lors de la génération de PDF. (GUIDES-15541)
- Lors de l’ajout de mappages à la collection de mappages, les ressources autres que les mappages (telles que les rubriques, etc.) s’affichent et les langues de mappage traduites ne sont pas correctement triées non plus.(GUIDES-25085)
- Dans la sortie AEM Sites héritée, les liens de section dans les rubriques imbriquées d’une carte ne sont pas résolus correctement lorsqu’ils sont définis manuellement en mode Source ou que le contenu est importé à partir d’une source externe. Au lieu d’accéder à la section prévue, il redirige vers la rubrique principale qui contient la rubrique imbriquée. (GUIDES-26103)
- Si l&#39;attribut `scope=external` est absent des liens externes dans une rubrique DITA, la publication HTML5 échoue sans indiquer les fichiers dans lesquels cet attribut est absent des journaux d&#39;erreurs. (GUIDES-25969)
- Impossible d’incorporer des liens vidéo dans le PDF natif, même si l’option **Incorporer des fichiers multimédias** est activée dans le paramètre prédéfini de PDF. (GUIDES-9989)
- Impossible de transmettre les propriétés de métadonnées pour mapper les pages de destination générées à l’aide d’une nouvelle publication AEM Sites. (GUIDES-27288)

## Ligne de base

- La copie d&#39;un plan DITA à partir de l&#39;interface utilisateur d&#39;Assets copie également sa ligne de base associée dans le nouveau plan. (GUIDES-11227)
- Lors de la création d&#39;une nouvelle ligne de base avec un grand nombre de libellés, cela empêche la récupération de tous les libellés. (GUIDES-16232)

## Page d’accueil

- La page d’accueil devient vide lorsque l’un des fichiers répertoriés dans le widget **Fichiers récents** est basé sur un modèle dont le modèle source n’inclut pas de miniature. (GUIDES-31506)

## Plateforme

- Des problèmes de performances tels que des temps de chargement plus longs et des délais d’expiration intermittents sont observés lors de l’utilisation de collections volumineuses. (GUIDES-29065, GUIDES-28793)
- Vulnérabilités liées à l’utilisation de la bibliothèque Guava obsolète dans les composants AEM Guides chargés sur Experience Manager Guides.(GUIDES-27402)

## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 5.1.0 :


- Le commentaire au niveau de la tâche le plus récent s’affiche dans l’e-mail de notification envoyé à l’initiateur de la tâche si le réviseur ou la réviseuse termine la tâche sans ajouter de commentaire. (GUIDES-33590)
- Dans la boîte de dialogue Fusionner , la liste déroulante affiche incorrectement le Contenu principal au lieu d’afficher les versions disponibles de la rubrique sélectionnée. (GUIDES-30820)
- Le fait de basculer entre des paramètres prédéfinis qui utilisent la même ligne de base désactive le bouton Enregistrer du paramètre prédéfini actuel. (GUIDES-28025)
- Une ligne vide est automatiquement insérée lors du collage d’un nouveau contenu dans une nouvelle ligne au sein d’un élément de bloc de code.(GUIDES-27842)
- Une rubrique dans un plan DITA ne parvient pas à publier dans la sortie AEM Sites lorsqu&#39;elle est utilisée à la fois en tant que keydef et topicref dans ses sous-plans. (GUIDES-22269)
- Dans le panneau Propriétés du contenu , le champ Attributs se ferme automatiquement lorsque vous essayez de mettre à jour une référence à partir de la boîte de dialogue Mettre à jour le lien , empêchant la mise à jour du lien. (GUIDES-17767)