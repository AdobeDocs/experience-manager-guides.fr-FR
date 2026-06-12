---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides, version 2024.10.0
description: Découvrez les correctifs de bugs de la version 2024.10.0 d’Adobe Experience Manager Guides as a Cloud Service.
exl-id: d23552a1-8f15-4a05-9317-f383dea3253d
source-git-commit: 682eaf6f4a3a158f49a8f2ea91ce9cd2de3ff772
workflow-type: tm+mt
source-wordcount: '1169'
ht-degree: 6%

---

# Correction de problèmes dans la version 2024.10.0

Cet article couvre les bugs corrigés dans différentes zones de la version 2024.10.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2024.10.0](whats-new-2024-10-0.md).

Découvrez les [instructions de mise à niveau pour la version 2024.10.0](upgrade-instructions-2024-10-0.md).


## Création

- L&#39;option **Rechercher** ne fonctionne pas dans la vue **Source**. (18610)
- L’élément `<title>` est automatiquement ajouté lorsque l’élément `<fig>` est inséré sous la forme d’un fragment de code. (18562)
- La régénération de la rubrique échoue en raison de l’échec de Régénération de la rubrique ou de l’API de publication incrémentielle prête à l’emploi. (18452)
- L’instance de Experience Manager Guides devient instable et la taille des journaux d’erreurs augmente jusqu’à 30 à 40 Go après l’accès à l’interface utilisateur d’Assets. (18414)
- Les icônes **Extraire** et **Archiver** s’affichent ensemble lorsque `autocheckout` est configuré dans xmleditor. (18088)
- Le copier-coller des images à partir de la vue Auteur ne fonctionne pas dans la version 2024.06.0 d’Adobe Experience Manager Guides as a Cloud Service.(18062)
- La `<conref>` d&#39;une rubrique référencée dans un plan DITA n&#39;est pas reflétée dans l&#39;aperçu dans l&#39;éditeur. (17794)
- Les plans DITA volumineux se chargent lentement et prennent du temps à passer à la vue **Disposition**. (17590)
- La version de DITA affiche incorrectement le nom d&#39;utilisateur dans l&#39;interface utilisateur d&#39;Assets. (17580)
- Les erreurs relatives aux identifiants d’image en double dans les rubriques empêchent l’utilisateur d’enregistrer ou de créer une rubrique. (17528)
- Des problèmes se produisent lors du chargement d’un grand nombre de fichiers avec des jeux de données denses vers Experience Manager Guides.(17008)
- Des échecs intermittents se produisent avec la fonctionnalité de rendu PDF dans Experience Manager Guides as a Cloud Service. (16966)
- Lors de la création d&#39;un plan DITA basé sur un modèle, le workflow DXML prêt à l&#39;emploi provoque des interruptions de processus et entraîne 503 erreurs inutilisables. (16529)
- Les **caractères spéciaux** écrits avec des caractères d’échappement sont supprimés du sujet après avoir été chargés sur Experience Manager Guides. (16495)
- Le message d’erreur Fichier extrait par «  » ne s’affiche pas correctement lorsque les fichiers de modification sont déplacés à partir d’un autre onglet, lorsque les jetons expirent ou lorsque l’utilisateur est déconnecté. (15223)
- Les fichiers volumineux ne se chargent pas dans l’éditeur web et entraînent le blocage du navigateur. (13227)
- Les `<Topicref>` ajoutés à l’aide de `<keyref>` ne s’affichent pas dans le PDF natif. (11974)
- Le chemin d’accès au composant `/libs/fmdita/components/versions` est codé en dur et les utilisateurs ne peuvent pas le superposer. (8779)
- L&#39;ouverture d&#39;une rubrique ou d&#39;un plan DITA pour modification dans un nouvel onglet gèle la navigation de sélection dans l&#39;interface utilisateur d&#39;Assets. (4992)
- Le téléchargement d&#39;un plan DITA avec des fichiers vidéo volumineux déclenche une erreur de mémoire insuffisante dans les journaux et échoue dans l&#39;interface utilisateur. (18884)
- Lors de l’insertion d’une équation MathML contenant le symbole « &lt; », un **caractère non valide** est généré. (18742)
- Une génération incorrecte d’UUID pendant le processus d’ingestion de contenu entraîne des ruptures des références de sous-mappages dans le mappage ingéré. (18308)
- Dans certains cas, des retards dans le traitement d&#39;une nouvelle rubrique DITA sont observés lors de sa création à partir de l&#39;éditeur web. (16836)
- La recherche de fichiers dans le **référentiel** à l’intérieur de l’éditeur web prend trop de temps et ne parvient parfois pas à charger les résultats. (16837)

## Publication

- La référence croisée à la clé n’est pas résolue dans la sortie native de PDF. (18087)
- L’erreur **duplicate_value** se produit par intermittence lors de la republication d’un article existant dans Salesforce. (17932)
- Le style et la mise en forme du contenu dans les modèles client changent automatiquement lorsque la mise en page inclut des champs de métadonnées, ce qui entraîne une mise en forme incorrecte dans les PDF publiés. (17900)
- La validation de la connexion Salesforce échoue avec l’URL d’éclair. (17797)
- Le PDF référencé n’est pas activé à partir du **tableau de bord de publication en bloc** lors de l’activation en bloc du contenu publié. (17793)
- L’activation en bloc du contenu publié ne fonctionne pas pour les mappages localisés. (17638)
- Lors de la sélection de l’option **Utiliser des métadonnées ajoutées dans topicmeta**, les propriétés de métadonnées ne sont pas propagées dans les propriétés du document de la sortie Native PDF. (17283)
- Le filtrage des conditions dans la sortie PDF native ne fonctionne pas comme prévu par rapport à DITA-OT. (17095)
- La table des matières n’honore pas les balises `<sub>` ou `<sup>` dans la sortie native de PDF. (17028)
- La génération du site AEM et l’API de publication incrémentielle ne fonctionnent pas comme prévu. (16666)
- La génération native de PDF échoue avec une erreur liée à l’obtention des dépendances pour Node.js. (14445)
- `<Conref>` n’est pas résolu dans le mode `Preview` de l’éditeur web et de la sortie Native PDF. (17827)
- Les références de contenu ne sont pas correctement résolues pour la sortie Native PDF si le fichier contenant les définitions de clé ne se trouve pas dans le même dossier que le plan DITA. (15062)
- Lorsqu&#39;un plan DITA contient des niveaux de titre supérieurs ou égaux à 7, le titre de niveau 7 est incorrectement traité comme un titre de niveau 1 dans la sortie Native PDF. (19698)
- Lorsqu’un élément de contenu (texte) est encapsulé dans un élément, les espaces avant et après le texte ne s’affichent pas dans les formats Aperçu ou Sortie . (19308)
- Les workflows de post-génération déclenchés manuellement échouent en raison d’une EXCEPTION DE POINTEUR NUL dans le workflow, ce qui entraîne le chargement du contenu 11 fois. (18880)
- Le tableau de bord de publication en bloc **Bulk Publish Dashboard** s’affiche vide pour les mappages qui sont toujours en cours de traduction. (19352)


## Gestion

- Le chemin d’accès à la fonctionnalité de recouvrement est codé en dur pour le fichier de langue coréenne et n’est pas correctement sélectionné. (17089)
- Les modifications/personnalisations apportées à la boîte de dialogue **Enregistrer la version** ne sont pas répercutées lors de l’utilisation de la structure d’extension Guides. (17828)
- La conversion d’InDesign en DITA comporte un chemin de configuration codé en dur afin que les fichiers de configuration personnalisés ne soient pas sélectionnés. (16891)
- Les références/ressources complètes ne sont pas téléchargées lorsqu&#39;un plan DITA contenant des dépendances/références volumineuses est téléchargé à l&#39;aide de la ligne de base. (19099)


### Révision

- La récupération de la liste des utilisateurs lors de la création d’une tâche de révision échoue si le nombre d’utilisateurs dépasse 25. (17329)
- Si une rubrique de tâche contient `<cmd>` balise en une ou plusieurs étapes, le panneau de révision affiche l’attribut `importance` sous forme de préfixe dans toutes les étapes contenant la balise. (19699)

## Traduction

- Les références des ressources traduites ne sont pas mises à jour. (18086)
- Les références ne sont pas correctement filtrées comme directes ou indirectes lors de la traduction dans plusieurs langues. (17891)
- Impossible de créer des projets XLIFF avec traduction humaine. (16964)
- L’ajout d’une rubrique mise à jour dans un projet de traduction actif génère une rubrique en double et le processus échoue. (7688)
- Aucun UUID n’est affecté aux projets de traduction créés en sélectionnant l’option **Créer uniquement la structure**. (18980)
- Lors de la sélection d’un projet de traduction avec le **Statut de traduction** en tant que **En cours**, une page incorrecte s’ouvre. (13248)
- Le titre avec `<conref>` n’est pas résolu dans les tableaux de bord Ligne de base et Traduction de l’éditeur web. (16961)

## Problèmes connus

- L’ouverture d’un paramètre prédéfini AEM Sites (non hérité) marque le sujet comme sale.
- Le panneau sélectionné n’est pas conservé lors de l’actualisation du navigateur à partir de l’onglet Sortie .
- Impossible de glisser-déposer une rubrique entre deux topicrefs dans la vue **Auteur**.
- Le filtrage de condition appliqué dans le préréglage n’est pas appliqué via **Télécharger en tant que PDF**.
- La génération d’une seule rubrique à partir du panneau de mappage génère toutes les rubriques sélectionnées dans le paramètre prédéfini AEM Sites (non hérité).
- La référence de la rubrique apparaît interrompue dans l&#39;interface utilisateur lors de son insertion à partir de la barre d&#39;outils supérieure du plan DITA.
- La génération native de PDF échoue pour un plan DITA s&#39;il manque des références.
- La publication sur une seule rubrique d’AEM Site avec des conditions échoue dans l’environnement activé pour les microservices.
- Une fois que l’état du document d’une rubrique est mis à jour à **Terminé**, l’icône **Démarrer une nouvelle version** n’est disponible que dans le mode **Aperçu** de la rubrique.
