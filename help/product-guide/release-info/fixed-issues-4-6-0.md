---
title: Notes de mise à jour | Correction de problèmes dans la version 4.6.0 d’Adobe Experience Manager Guides
description: Découvrez les correctifs de bugs dans la version 4.6.0 d’Adobe Experience Manager Guides
role: Leader
exl-id: fd12d627-5163-4edd-b28e-bef13267fcc9
TQID: https://experienceleague.adobe.com/zaQd6UfebgClEP7JxSWRwsGqIziDkIN3QLLP-iGufhM
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552eid: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: c6d09140-3c91-45d3-b7ed-b681af752f43id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0eid: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: c38bc65b-dea9-4a6e-9de3-3daf1d2b388bid: d4f22c6d-7923-41e5-9da3-527ff8df4bc8id: d6596f3f-92a7-43ec-b444-237db6adad05id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0efid: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 2019
ht-degree: 5%

---

# Correction de problèmes dans la version 4.6.0 (septembre 2024)


Cet article couvre les bugs corrigés dans différentes zones de la version 4.6.0 d’Adobe Experience Manager Guides.


Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, consultez [Nouveautés de la version 4.6.0](whats-new-4-6.md).

Découvrez les [instructions de mise à niveau pour la version 4.6.0](../release-info/upgrade-instructions-4-6-0.md).

## Création

- L&#39;option **Rechercher** ne fonctionne pas dans la vue **Source**. (18610)
- Les icônes **Extraire** et **Archiver** s’affichent ensemble lorsque `autocheckout` est configuré dans xmleditor. (18088)
- Les plans DITA volumineux se chargent lentement et prennent du temps à passer à la vue **Disposition**.  (17590)
- Les erreurs relatives aux identifiants d’image en double dans les rubriques empêchent l’utilisateur d’enregistrer ou de créer une rubrique. (17528)
- L’opération de copier-coller de rubriques dépassant 15 Ko échoue avec une erreur inattendue. (17171)
- La fonctionnalité permettant de modifier l’état du document à partir du panneau **Propriétés du fichier** ne fonctionne pas correctement et passe à l’état *Brouillon*. (17088)
- Lors de la modification des paramètres de l’éditeur XML à l’aide d’un profil de dossier personnalisé, le `ui_config.json` est mis à jour avec un fichier incorrect. (17011)
- Les panneaux de contenu réutilisables ne répertorient pas les éléments lorsque les **Préférences utilisateur** sont définies pour afficher les fichiers par **Nom de fichier**. (16896)
- Le rendu des sous-éléments dans l’élément de titre du tableau échoue dans le mode **Aperçu** de Experience Manager Guides. (16691)
- Les **caractères spéciaux** écrits avec des caractères d’échappement sont supprimés du sujet après avoir été chargés sur Experience Manager Guides. (16495)
- Les vidéos Vimeo ne prennent pas en charge les fonctionnalités plein écran dans Experience Manager Guides. (15996)
- Le collage de longues séquences de texte préformaté dans des éléments `<pre>` ou `<codeblock>` entraîne la troncature du texte. (15859)
- La suppression de contenu se produit en raison de GUID en double lorsque des modèles sont installés via le code, mais restent non traités. (15858)
- Experience Manager Guides ne parvient pas à se conformer à l’attribut **Rôle de traitement** en mode **Aperçu**. (15787)
- L’éditeur supprime par intermittence le texte supplémentaire au-delà de la zone sélectionnée. (15708)
- Impossible de copier et coller des tableaux volumineux à partir de documents Word ou HTML dans l’éditeur web. (15369)
- Manque d’API ou d’événements pour capturer l’ajout d’attribut à un élément ou l’insertion d’un nouvel élément. (15351)
- Impossible d’ajouter `<data>` balise dans `<ol>` balise dans l’éditeur web. (15161)
- Le composant d’espace réservé **Element** bloque l’interface utilisateur. (14957)
- L’éditeur Web ne peut pas charger les fichiers .pptx. (14837)
- Lors de la recherche d’un texte dans l’éditeur web, le curseur revient à la première occurrence du texte recherché, lorsque vous appuyez sur la touche Entrée. (14820)
- L’enregistrement automatique entraîne plusieurs problèmes, repositionne le curseur et nécessite des clics manuels dans le document. (14253)
- Appuyez sur la touche **Entrée** dans une cellule de tableau pour fractionner le paragraphe de la manière prévue. (14251)
- Les fichiers volumineux ne se chargent pas dans l’éditeur web et entraînent le blocage du navigateur. (13227)
- Les résultats de la recherche sont désactivés après l’ouverture d’un fichier trouvé par le biais du **Rechercher et remplacer** global. (12142)
- Dans la vue source, `</conbody>` est parfois inséré à des emplacements incorrects. (11305)
- Le chemin d’accès au composant `/libs/fmdita/components/versions` est codé en dur et les utilisateurs ne peuvent pas le superposer. (8779)
- La `<conref>` d&#39;une rubrique référencée dans un plan DITA n&#39;est pas reflétée dans l&#39;aperçu dans l&#39;éditeur. (17794)
- Le guide Experience Manager DITA ne parvient pas à déclencher la fonction Enregistrer après avoir utilisé la fonction de retrait automatique. (16482)
- La fonction d’info-bulle ne parvient pas à mettre à jour le champ Source dans l’éditeur XML. (15847)
- La fonction **Partager le lien UUID** ne fonctionne pas pour les images dans Adobe Experience Manager. (15598)
- Dans la vue **Auteur**, un problème de copier-coller se produit lors de l’utilisation d’espaces insécables et entraîne un débordement du texte. (15541)
- Des problèmes de chevauchement de texte se produisent dans les balises `<reltable>` et `<fig>`. (15238)
- Le panneau **Attributs** génère des problèmes de scintillement. (15237)
- Dans `<othermeta>` élément de `<topicmeta>`, lors de l&#39;ajout d&#39;un `<conref>` à un autre plan DITA, l&#39;ID de plan est également ajouté avec l&#39;ID de l&#39;élément. (15226)
- Le curseur se déplace entre les éléments de bloc lors de la suppression d’un caractère ou d’un mot dans le contenu. (15224)
- Le message d’erreur Fichier extrait par «  » ne s’affiche pas correctement lorsque les fichiers de modification sont déplacés à partir d’un autre onglet, lorsque les jetons expirent ou lorsque l’utilisateur est déconnecté. (15223)
- Le `<conref>` ne peut pas être mis à jour à partir du panneau **Attributs** lors de l’application de modifications. (15209)
- La cellule entière est sélectionnée lors de la sélection d’une image dans une cellule de tableau. (15188)
- Le panneau **Attributs** ne s’affiche pas dans la vue Source de l’éditeur web. (14387)
- Les `<Topicref>` ajoutés à l’aide de `<keyref>` ne s’affichent pas dans le PDF natif. (11974)
- Des espaces superflus sont ajoutés lors de la modification à la fin d’une balise dans l’éditeur web. (11786)
- Le contenu est supprimé lors de la correction des fautes d&#39;orthographe dans les fichiers DITA. (11610)
- L&#39;ouverture d&#39;une rubrique ou d&#39;un plan DITA pour modification dans un nouvel onglet gèle la navigation de sélection dans l&#39;interface utilisateur d&#39;Assets. (4992)
- La suppression des nœuds de révision interrompt la possibilité d’ouvrir et d’afficher des commentaires dans Adobe Experience Manager Guides. (15366)
- La version de DITA affiche incorrectement le nom d&#39;utilisateur dans l&#39;interface utilisateur d&#39;Assets. (17580)
- L’élément `<title>` est automatiquement ajouté lorsque l’élément `<fig>` est inséré sous la forme d’un fragment de code. (18562)
- Des problèmes se produisent lors du chargement d’un grand nombre de fichiers avec des jeux de données denses vers Experience Manager Guides.(17008)
- L’éditeur Web ne parvient pas à afficher le mot-clé correct par défaut, en particulier si le mot-clé est défini différemment dans les mappages enfants. (14748)
- Le **état du document** ne s’affiche pas lors de la modification des propriétés de plus de 50 fichiers en bloc à partir de la vue Carte de l’éditeur web. (14574)
- Le comportement du bouton Fermer est incohérent lors de l’utilisation de la fonctionnalité d’enregistrement automatique. (10996)
- Des problèmes de validation se produisent dans les éléments MathML lors de l’insertion d’un nouvel élément ou de la modification d’équations. (10624)
- La fonctionnalité de suivi des modifications ne fonctionne pas avec le texte qui commence par des caractères coréens. (14538)
- Les images liées des rubriques ne s’affichent pas dans la ligne de base après la création de la version. (16931)

## Publication

- La référence croisée à la clé n’est pas résolue dans la sortie native de PDF. (18087)
- L’erreur **duplicate_value** se produit par intermittence lors de la republication d’un article existant dans Salesforce. (17932)
- La validation de la connexion Salesforce échoue avec l’URL d’éclair. (17797)
- Lors de la sélection de l’option **Utiliser des métadonnées ajoutées dans topicmeta**, les propriétés de métadonnées ne sont pas propagées dans les propriétés du document de la sortie Native PDF (17283).
- Le filtrage des conditions dans la sortie PDF native ne fonctionne pas comme prévu par rapport à DITA-OT. (17095)
- La table des matières n’honore pas les balises `<sub>` ou `<sup>` dans la sortie native de PDF. (17028)
- La liaison de cartes croisées ne parvient pas à afficher toutes les cartes parentes dans les paramètres de contexte de publication pour un lien qui possède le `scope="peer"` . (16700)
- La génération du site AEM et l’API de publication incrémentielle ne fonctionnent pas comme prévu. (16666)
- La génération de la sortie du site AEM échoue lorsque l’option **Supprimer le site orphelin** est activée. (15896)
- Les anciens attributs sont conservés dans les **paramètres prédéfinis de condition** lors de l’ajout ou de la suppression d’attributs nouveaux ou existants. (15890)
- Dans la sortie JSON, les métadonnées du plan ou des rubriques DITA ne se propagent pas aux fichiers de sortie JSON. (15713)
- Le contenu en langue RTL n’est pas correctement géré dans la sortie de publication Native PDF. (15709)
- La publication native de PDF échoue lorsque le préréglage est renommé. (15662)
- La propriété **sourcePath** est incorrecte sur la sortie de site AEM publiée. (15502)
- La sélection et la personnalisation des variables de langue ne fonctionnent pas correctement dans le paramètre prédéfini de sortie PDF natif. (15399)
- La génération native de PDF échoue lors de l’utilisation d’une feuille de style ou d’un modèle de mise en page volumineux. (15344)
- Le contenu n’est pas rendu correctement dans la sortie publiée si `<conref>` est utilisé avec un chemin d’accès absolu. (15222)
- Le raccourcissement des URL d’AEM Sites ne fonctionne pas en raison de conflits entre le `fmdita rewriter` et le `ResourceResolver`. (14793)
- La génération native de PDF échoue avec une erreur liée à l’obtention des dépendances pour Node.js. (14445)
- Les attributs **processing-role=« resource-only »**, **search=« no »** et **chunk=« to-content »** s’affichent indépendamment dans la sortie AEM Sites. (14442)
- `<Conref>` n’est pas résolu dans le mode `Preview` de l’éditeur web et de la sortie Native PDF. (17827)
- Dans Native PDF, les rubriques DITA imbriquées ne s&#39;affichent pas correctement dans la table des matières. (16742)
- Les miniatures générées à partir de **Dynamic Media** pour les fichiers vidéo ne sont pas conservées dans la sortie publiée. (15656)
- Le PDF référencé n’est pas activé à partir du **tableau de bord de publication en bloc** lors de l’activation en bloc du contenu publié. (17793)
- Si un dossier contenant 2 000 mappages est défini dans le chemin du dossier à l’intérieur d’un profil de dossier, les modifications appliquées au paramètre prédéfini de sortie échouent. (14852)
- La régénération de la rubrique échoue en raison de l’échec de Régénération de la rubrique ou de l’API de publication incrémentielle prête à l’emploi. (18452)
- Le préréglage de condition ne récupère pas les attributs mis à jour après la mise à niveau de Experience Manager Guides. (18174)
- Les références de contenu ne sont pas correctement résolues pour la sortie Native PDF si le fichier contenant les définitions de clé ne se trouve pas dans le même dossier que le plan DITA. (15062)
- Le tableau de bord de publication en bloc s’affiche vide pour les mappages qui sont toujours en cours de traduction. (19352)
- L’activation en bloc du contenu publié ne fonctionne pas pour les mappages localisés. (17638)



## Gestion


- La conversion d’InDesign en DITA comporte un chemin de configuration codé en dur afin que les fichiers de configuration personnalisés ne soient pas sélectionnés. (16891)
- Les **résolveurs de ressources** non fermés entraînent une augmentation du nombre de sessions et des erreurs de `PathNotFoundException` après la version 4.3.1 de Experience Manager Guides. (15604)
- Erreur lors de l’installation des packages Guides dans des référentiels volumineux. (15160)
- La création d’une ligne de base à l’aide de l’API Java ne fonctionne pas avec Experience Manager Guides. (14787)
- L’API `/bin/fmdita/import` reste bloquée indéfiniment dans la requête en attente lorsque le chargement des ressources dépasse 500 Mo. (14743)
- La modification d&#39;une ligne de base existante et la sélection d&#39;une version spécifique déclenchent des erreurs d&#39;application. (14451)
- L&#39;exécution du script de post-processus échoue en raison de l&#39;exception **FileNotFoundException**. (16517)
- Les titres dynamiques avec `<conkeyref>` n’apparaissent pas dans la liste Rubrique de rapport . (16967)
- Les nombres inexacts **Liste de rubriques** apparaissent dans l’interface utilisateur des rapports Experience Manager Guides en raison des propriétés non corrigées lors de la copie de ressources DITA. (15529)
- Les rubriques contenant des références externes avec %20 dans l&#39;URL affichent des références de fichier endommagées. (15347)
- Les propriétés fmditaMaprefs et fmditakeydefrefs affichent des chemins d&#39;accès relatifs, malgré la définition de chemins d&#39;accès absolus pour le plan et les rubriques DITA. (18353)
- Le chemin d’accès à la fonctionnalité de recouvrement est codé en dur pour le fichier de langue coréenne et n’est pas correctement sélectionné. (17089)
- L’heure par défaut lors de la création de la ligne de base dans l’éditeur web s’affiche sous la forme 00:00 au lieu de l’heure actuelle. (15215)

## Révision

- La récupération de la liste des utilisateurs lors de la création d’une tâche de révision échoue si le nombre d’utilisateurs dépasse 25. (17329)
- Les rubriques de révision n’apparaissent pas dans le bon ordre. (16319)
- Dans l’éditeur web, le panneau Révision se charge lentement. (14680)
- Les réviseurs ne peuvent pas ajouter, mettre en surbrillance ou supprimer des espaces lors de la révision d’un document dans Experience Manager Guides. (14752)
- Lorsque l’utilisateur met à jour une tâche de révision, tous les réviseurs assignés ne reçoivent pas de notification de la mise à jour. (9496)

## Traduction

- Les références des ressources traduites ne sont pas mises à jour. (18086)
- Impossible de créer des projets XLIFF avec traduction humaine. (16964)
- Le titre avec `<conref>` ou `<conkeyref>` n’est pas résolu dans les tableaux de bord Ligne de base et Traduction de l’éditeur web. (16961, 16879)
- Les projets de traduction ne parviennent pas à ajouter de nouvelles tâches linguistiques au pack de services 18 de Adobe Experience Manager 6.5 avec la version 4.3.1 de Experience Manager Guides. (15398)
- **Accepter la traduction** ne parvient pas à terminer la traduction des fichiers temporaires. (14665)
- L’ajout d’une rubrique mise à jour dans un projet de traduction actif génère une rubrique en double et le processus échoue. (7688)
- Les références ne sont pas correctement filtrées comme directes ou indirectes lors de la traduction dans plusieurs langues. (17891)
- La traduction basée sur XLIFF échoue avec une erreur pour les utilisateurs « non-administrateurs ».(17296)
- Le titre des fichiers traduits revient à l’anglais après la deuxième traduction, même si le contenu a été traduit. (15200)
- Lors de la sélection d’un projet de traduction avec le **Statut de traduction** en tant que **En cours**, une page incorrecte s’ouvre. (13248)
- Aucun UUID n’est affecté aux projets de traduction créés en sélectionnant l’option **Créer uniquement la structure**. (18980)


## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 4.6.0 :
- L’ouverture d’un paramètre prédéfini **** (non hérité) marque le sujet comme sale.
- Le panneau sélectionné n’est pas conservé lors de l’actualisation du navigateur à partir de l’onglet **Sortie**.
- Impossible de glisser-déposer des rubriques entre deux `topicrefs` dans la vue **Auteur**.
- Le filtrage de condition appliqué dans le préréglage n’est pas appliqué via **Télécharger en tant que PDF**.
- La génération d’une seule rubrique à partir du panneau de mappage génère toutes les rubriques sélectionnées dans le paramètre prédéfini **** (non hérité).
- La référence de la rubrique apparaît interrompue dans l&#39;interface utilisateur lors de son insertion à partir de la barre d&#39;outils supérieure du plan DITA.
- La génération native de PDF échoue pour un plan DITA s&#39;il manque des références.
- Une fois que l’état du document d’une rubrique est mis à jour à **Terminé**, l’icône **Démarrer une nouvelle version** n’est disponible que dans le mode **Aperçu** de la rubrique.
- Lors de la sélection d&#39;un fichier DITA dans l&#39;interface utilisateur d&#39;Asset, l&#39;option **Ouvrir dans FrameMaker** apparaît, même si elle est désactivée dans les paramètres de configuration.
