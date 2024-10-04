---
title: Notes de mise à jour | Correction de problèmes dans la version Adobe Experience Manager Guides 4.6.0
description: Découvrez les correctifs de la version 4.6.0 d’Adobe Experience Manager Guides
role: Leader
source-git-commit: 6bff0a9c8770418c4486b65feb1c11792b893ca8
workflow-type: tm+mt
source-wordcount: '1985'
ht-degree: 0%

---


# Correction de problèmes dans la version 4.6.0 (septembre 2024)


Cet article couvre les bogues corrigés dans différentes zones de la version 4.6.0 d’Adobe Experience Manager Guides.


Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, consultez la section [Nouveautés de la version 4.6.0](whats-new-4-6.md).

Découvrez les [instructions de mise à niveau pour la version 4.6.0](../release-info/upgrade-instructions-4-6-0.md).

## Création

- L&#39;option **Rechercher** ne fonctionne pas dans la vue **Source**. (18610)
- Les icônes **Extraire** et **Archiver** s’affichent lorsque `autocheckout` est configuré dans l’éditeur. (18088)
- Les cartes DITA volumineuses se chargent lentement et prennent du temps pour passer à la vue **Disposition**.  (17590)
- Les erreurs d’ID d’image en double dans les rubriques empêchent l’utilisateur d’enregistrer ou de créer une rubrique. (17528)
- L’opération de copier-coller de rubriques supérieures à 15 Ko échoue avec une erreur inattendue. 17171
- La fonctionnalité permettant de modifier l’état du document à partir du panneau **Propriétés du fichier** ne fonctionne pas correctement et passe à l’état *Brouillon*. 17088
- Lors de la modification des paramètres de l’éditeur XML à l’aide d’un profil de dossier personnalisé, `ui_config.json` est mis à jour avec un fichier incorrect. (17011)
- Les panneaux de contenu réutilisables ne répertorient pas les éléments lorsque les **préférences utilisateur** sont définies pour afficher les fichiers par **nom de fichier**. (16896)
- Le rendu des sous-éléments dans l’élément de titre de la table échoue dans le mode **Aperçu** de Experience Manager Guides. (16691)
- **Les caractères spéciaux** écrits avec des caractères d’échappement sont supprimés de la rubrique après avoir été téléchargés vers Experience Manager Guides. (16495)
- Les vidéos Vimeo ne prennent pas en charge la fonctionnalité plein écran dans Experience Manager Guides. (15996)
- Le collage de longues séquences de texte préformatées dans des éléments `<pre>` ou `<codeblock>` entraîne la troncation de texte. 15859)
- La suppression de contenu est due à des GUID en double lorsque les modèles sont installés par le biais du code, mais restent non traités. (15858)
- Experience Manager Guides ne parvient pas à se conformer à l’attribut **Rôle de traitement** en mode **Aperçu**. (15787)
- L’éditeur supprime par intermittence le texte supplémentaire au-delà de la zone sélectionnée. (15708)
- Impossible de copier et coller des tableaux volumineux à partir de documents Word ou d’un HTML dans l’éditeur Web. (15369)
- Absence d’API ou d’événements pour capturer l’ajout d’attributs à un élément ou l’insertion d’un nouvel élément. 15351
- Impossible d’ajouter la balise `<data>` dans la balise `<ol>` de l’éditeur web. 15161)
- Le composant d’espace réservé **Element** provoque le gel de l’interface utilisateur. (14957)
- L’éditeur web ne peut pas télécharger de fichiers .pptx. (14837)
- Lors de la recherche d’un texte dans l’éditeur web, le curseur revient à la première occurrence du texte recherché, en appuyant sur la touche Entrée. (14820)
- L’enregistrement automatique entraîne plusieurs problèmes, repositionne le curseur et nécessite des clics manuels dans le document. (14253)
- Appuyez sur la touche **Entrée** d’une cellule de tableau dans le texte pour ne pas fractionner le paragraphe comme prévu. 14251)
- Les fichiers volumineux ne se chargent pas dans l’éditeur web et provoquent le gel du navigateur. (13227)
- Les résultats de la recherche sont désactivés après l’ouverture d’un fichier trouvé par l’intermédiaire de la méthode globale **Chercher et Remplacer**. (12142)
- Dans la vue source, `</conbody>` est parfois inséré à des emplacements incorrects. (11305)
- Le chemin d’accès au composant `/libs/fmdita/components/versions` est codé en dur et les utilisateurs ne peuvent pas le superposer. (8779)
- `<conref>` pour une rubrique référencée dans un mappage DITA n’est pas reflété dans l’aperçu dans l’éditeur. 17794
- Le guide DITA Experience Manager ne parvient pas à déclencher la fonction Enregistrer après l’utilisation de la fonction de retrait automatique. 16482
- La fonction d’info-bulle ne parvient pas à mettre à jour le champ Source dans l’éditeur XML. (15847)
- La fonction **Partager le lien UUID** ne fonctionne pas pour les images dans Adobe Experience Manager. (15598)
- Dans la vue **Auteur**, un problème de copier-coller se produit lors de l’utilisation d’espaces insécables et entraîne un débordement de texte. (15541)
- Des problèmes de chevauchement de texte se produisent dans les balises `<reltable>` et `<fig>`. 15238
- Des problèmes de scintillement se produisent dans le panneau **Attributs**. (15237)
- Dans l’élément `<othermeta>` dans `<topicmeta>`, lors de l’ajout d’un `<conref>` à un autre mappage DITA, l’ID de mappage est également ajouté avec l’ID de l’élément. (15226)
- Le curseur se déplace entre les éléments de bloc lors de la suppression d’un caractère ou d’un mot dans le contenu. 15224
- Le message d’erreur Fichier extrait par &quot;&quot; s’affiche incorrectement lors de la modification des fichiers qui sont déplacés d’un autre onglet, lorsque des jetons ont expiré ou lorsque l’utilisateur est déconnecté. (15223)
- `<conref>` ne peut pas être mis à jour à partir du panneau **Attributs** lors de l’apport de modifications. 15209
- La cellule entière est sélectionnée lors de la sélection d’une image dans une cellule d’un tableau. (15188)
- Le panneau **Attributs** ne s’affiche pas dans la vue Source de l’éditeur web. (14387)
- `<Topicref>` ajouté à l’aide de `<keyref>` ne s’affiche pas dans le PDF natif. (1974)
- Des espaces indésirables insécables sont ajoutés lors de la modification à la fin d’une balise dans l’éditeur web. (11786)
- Le contenu est supprimé lors de la correction des erreurs d’orthographe dans les fichiers DITA. (11610)
- L’ouverture d’une rubrique ou d’un mappage DITA dans un nouvel onglet pour la modification gèle la navigation de la sélection dans l’interface utilisateur d’Assets. (4992)
- La suppression de noeuds de révision perturbe la possibilité d’ouvrir et d’afficher des commentaires dans Adobe Experience Manager Guides. 15366
- La version DITA affiche incorrectement le nom d’utilisateur dans l’interface utilisateur d’Assets. (17580)
- L’élément `<title>` est automatiquement ajouté lorsque l’élément `<fig>` est inséré en tant que fragment de code. 18562
- Des problèmes se produisent lors du chargement d’un grand nombre de fichiers avec des jeux de données denses vers Experience Manager Guides.(17008)
- L’éditeur web n’affiche pas le mot-clé correct par défaut, en particulier si le mot-clé est défini différemment dans les mappages enfants. (14748)
- L’ **état du document** n’est pas affiché lors de la modification des propriétés de plus de 50 fichiers en bloc à partir de la vue Carte de l’éditeur web. 14574
- Le comportement du bouton Fermer est incohérent lors de l’utilisation de la fonctionnalité d’enregistrement automatique. (10996)
- Des problèmes de validation se produisent dans les éléments MathML lors de l’insertion d’un nouvel élément ou de la modification d’équations. 10624
- La fonctionnalité de suivi des modifications ne fonctionne pas avec le texte qui commence par des caractères coréens. 14538
- Les images liées des rubriques ne s’affichent pas dans la ligne de base après la création de la version. 16931

## Publication

- La référence croisée à la clé n’est pas résolue dans la sortie du PDF natif. (18087)
- L’erreur **duplicate_value** se produit par intermittence lors de la republication d’un article existant dans Salesforce. (17932)
- La validation de la connexion Salesforce échoue avec l’URL d’éclair. 17797
- Lors de la sélection de l’option **Utiliser les métadonnées ajoutées dans la topicmeta** , les propriétés de métadonnées ne sont pas propagées dans les propriétés de document de la sortie de l’PDF natif.(17283)
- Le filtrage des conditions dans la sortie du PDF natif ne fonctionne pas comme prévu par rapport à DITA-OT. (17095)
- La table des matières n’honore pas les balises `<sub>` ou `<sup>` dans la sortie du PDF natif. 17028
- La liaison croisée n’affiche pas toutes les cartes parentes dans les paramètres de contexte de publication pour un lien qui contient le `scope="peer"` . (16700)
- La génération AEM site et l’API de publication incrémentielle ne fonctionnent pas comme prévu. (16666)
- La génération AEM sortie du site échoue lorsque l’option **Supprimer le site orpheline** est activée. (15896)
- Les anciens attributs sont conservés dans les **paramètres de condition prédéfinis** lors de l’ajout ou de la suppression d’attributs nouveaux ou existants. (15890)
- Dans la sortie JSON, les métadonnées du mappage DITA ou des rubriques ne se propagent pas aux fichiers de sortie JSON. (15713)
- Le contenu de la langue RTL n’est pas géré correctement dans la sortie de publication du PDF natif. 15709
- La publication du PDF natif échoue lorsque le paramètre prédéfini est renommé. (15662)
- La propriété **sourcePath** est incorrecte sur la sortie publiée AEM site. (15502)
- La sélection et la personnalisation des variables de langue ne fonctionnent pas correctement dans le paramètre prédéfini de sortie du PDF natif. (15399)
- La génération d’un PDF natif échoue lors de l’utilisation d’une feuille de style ou d’un modèle de mise en page volumineux. 15344
- Le contenu n’est pas rendu correctement dans la sortie publiée si `<conref>` est utilisé avec un chemin d’accès absolu. (15222)
- Le raccourcissement des URL AEM Sites ne fonctionne pas en raison de conflits entre `fmdita rewriter` et `ResourceResolver`. (14793)
- La génération du PDF natif échoue avec une erreur liée à l’obtention des dépendances pour Node.js. (14445)
- Les attributs **processing-role=&quot;resource-only&quot;**, **search=&quot;no&quot;** et **chunk=&quot;to-content&quot;** apparaissent respectivement dans la sortie AEM Sites. (14442)
- `<Conref>` n’est pas résolu dans le mode `Preview` de l’éditeur web et de la sortie du PDF natif. (17827)
- Dans le PDF natif, les rubriques DITA imbriquées s’affichent incorrectement dans la table des matières. 16742
- Les miniatures générées à partir de **Dynamic Media** pour les fichiers vidéo ne sont pas conservées dans la sortie publiée. 15656)
- Le PDF référencé n’est pas activé à partir du **tableau de bord du Publish en bloc** lors de l’activation en bloc du contenu publié. (17793)
- Si un dossier contenant des mappages 2k est défini dans le chemin du dossier dans un profil de dossier, les modifications appliquées au paramètre prédéfini de sortie échouent. 14852
- La régénération de la rubrique échoue en raison de l’échec de l’API de publication incrémentielle ou de la rubrique de regénération prête à l’emploi. 18452
- Le paramètre prédéfini de condition ne récupère pas les attributs mis à jour après la mise à niveau de Experience Manager Guides. (18174)
- Les références de contenu ne sont pas correctement résolues pour la sortie du PDF natif si le fichier contenant des définitions de clé ne se trouve pas dans le même dossier que le mappage DITA. 15062)


## Gestion


- L’InDesign à la conversion DITA comporte un chemin de configuration codé en dur, de sorte que les fichiers de configuration personnalisés ne sont pas sélectionnés. (16891)
- Les **résolveurs de ressource** non fermés provoquent une augmentation du nombre de sessions et des erreurs `PathNotFoundException` après la version 4.3.1 de Experience Manager Guides. 15604
- Erreur lors de l’installation des packages Guides dans des référentiels volumineux. (15160)
- La création d’une ligne de base à l’aide de l’API Java ne fonctionne pas avec Experience Manager Guides. (14787)
- L’API `/bin/fmdita/import` reste bloquée indéfiniment dans la requête en attente lorsque les ressources de chargement dépassent 500 Mo. (14743)
- La modification d’une ligne de base existante et la sélection d’une version spécifique déclenchent des erreurs d’application. 14451)
- L’exécution du script de posttraitement échoue en raison de l’exception **FileNotFoundException**. (16517)
- Les titres dynamiques avec `<conkeyref>` n’apparaissent pas dans la liste des rubriques du rapport. (16967)
- Le nombre inexact de **Topic List** se produit dans l’interface utilisateur des rapports Experience Manager Guides en raison des propriétés non corrigées lors de la copie de ressources DITA. (15529)
- Les rubriques contenant des références externes avec %20 dans l’URL affichent des références de fichier rompues. (15347)
- Les propriétés fmditaMaprefs et fmditakeydefrefs affichent des chemins d’accès relatifs, même si vous définissez des chemins d’accès absolus pour le mappage DITA et les rubriques. 18353
- Le chemin d’accès de la fonctionnalité de superposition est codé en dur pour le fichier de langue coréenne et n’est pas correctement sélectionné. 17089
- L’heure par défaut dans la section Création de la ligne de base de l’éditeur web s’affiche à 00:00 au lieu de l’heure actuelle. 15215

## Révision

- La récupération de la liste des utilisateurs lors de la création d’une tâche de révision échoue si le nombre d’utilisateurs dépasse 25. 17329
- Les rubriques de révision n’apparaissent pas dans l’ordre correct. (16319)
- Dans l’éditeur web, le panneau Révision se charge lentement. (14680)
- Les réviseurs ne peuvent pas ajouter, mettre en surbrillance ou supprimer des espaces lors de la révision d’un document dans Experience Manager Guides. 14752
- Lorsqu’un utilisateur met à jour une tâche de révision, tous les réviseurs affectés ne reçoivent pas de notification à propos de la mise à jour. (9496)

## Traduction

- Les références des ressources traduites ne sont pas mises à jour. (18086)
- Impossible de créer des projets XLIFF avec traduction humaine. (16964)
- Le titre avec `<conref>` ou `<conkeyref>` ne se résout pas dans les tableaux de bord de ligne de base et de traduction de l’éditeur web. (16961, 16879)
- Les projets de traduction ne parviennent pas à ajouter de nouvelles tâches linguistiques à Adobe Experience Manager 6.5 SP18 avec la version 4.3.1 de Experience Manager Guides. (15398)
- **Accepter la traduction** ne parvient pas à terminer la traduction des fichiers temporaires. (14665)
- L’ajout d’une rubrique mise à jour dans un projet de traduction actif entraîne la duplication d’une rubrique et l’échec du processus. (7688)
- Les références ne sont pas correctement filtrées en tant que Direct ou Indirect lors de la traduction dans plusieurs langues. (17891)
- La traduction basée sur XLIFF échoue avec une erreur pour les utilisateurs &quot;non-administrateurs&quot;.(17296)
- Le titre des fichiers traduits revient à l’anglais après la seconde traduction, même si le contenu a été traduit. (15200)
- Lors de la sélection d’un projet de traduction dont le **statut de traduction** est **En cours**, une page incorrecte s’ouvre. (13248)
- Les projets de traduction créés en sélectionnant l’option **Créer une structure uniquement** n’ont pas d’UUID attribués. (18980)


## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 4.6.0 :
- L’ouverture d’un paramètre prédéfini **AEM Sites** (non hérité) marque le sujet comme &quot;sale&quot;.
- Le panneau sélectionné n’est pas conservé lors de l’actualisation du navigateur à partir de l’onglet **Output**.
- Impossible de faire glisser et de déposer des rubriques entre deux `topicrefs` dans la vue **Auteur**.
- Le filtrage de condition appliqué dans le paramètre prédéfini n’est pas appliqué via **Télécharger en tant que PDF**.
- La génération de rubrique unique à partir du panneau de mappage génère toutes les rubriques sélectionnées dans le paramètre prédéfini **AEM Sites** (non hérité).
- La référence de la rubrique apparaît rompue dans l’interface utilisateur lorsqu’elle est insérée à partir de la barre d’outils supérieure du mappage DITA.
- La génération d’un PDF natif échoue pour un mappage DITA s’il manque des références.
- Une fois que l’état du document d’une rubrique est mis à jour sur **Terminé**, l’icône **Démarrer une nouvelle version** n’est disponible que dans le mode **Aperçu** de la rubrique.
- Lors de la sélection d’un fichier DITA dans l’interface utilisateur d’Assets, l’option **Ouvrir dans le FrameMaker** s’affiche, même si elle est désactivée dans les paramètres de configuration.




