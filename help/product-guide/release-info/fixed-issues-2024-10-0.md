---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides, version 2024.10.0
description: Découvrez les correctifs de bogues de la version 2024.10.0 d’Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 64c5318a064d28a42f3f11d2fe5b7d8548e341d8
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 2%

---

# Correction de problèmes dans la version 2024.10.0

Cet article couvre les bogues corrigés dans différentes zones de la version 2024.10.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2024.10.0](whats-new-2024-10-0.md).

Découvrez les [instructions de mise à niveau pour la version 2024.10.0](upgrade-instructions-2024-10-0.md).


## Création

- L&#39;option **Rechercher** ne fonctionne pas dans la vue **Source**. (18610)
- L’élément `<title>` est automatiquement ajouté lorsque l’élément `<fig>` est inséré en tant que fragment de code. 18562
- La régénération de la rubrique échoue en raison de l’échec de l’API de publication incrémentielle ou de la rubrique de regénération prête à l’emploi. 18452
- L’instance Experience Manager Guides devient instable et la taille des journaux d’erreurs passe de 30 à 40 Go après l’accès à l’interface utilisateur d’Assets. 18414
- Les icônes **Extraire** et **Archiver** s’affichent lorsque `autocheckout` est configuré dans l’éditeur. (18088)
- Le copier-coller des images depuis la vue Auteur ne fonctionne pas dans 2024.06.0 version d’Adobe Experience Manager Guides as a Cloud Service.18062
- `<conref>` pour une rubrique référencée dans un mappage DITA n’est pas reflété dans l’aperçu dans l’éditeur. 17794
- Les cartes DITA volumineuses se chargent lentement et prennent du temps pour passer à la vue **Disposition**. (17590)
- La version DITA affiche incorrectement le nom d’utilisateur dans l’interface utilisateur d’Assets. (17580)
- Les erreurs d’ID d’image en double dans les rubriques empêchent l’utilisateur d’enregistrer ou de créer une rubrique. (17528)
- Des problèmes se produisent lors du chargement d’un grand nombre de fichiers avec des jeux de données denses vers Experience Manager Guides.(17008)
- Des échecs intermittents se produisent avec la fonctionnalité de rendu du PDF as a Cloud Service Experience Manager Guides. (16966)
- Lors de la création d’une carte DITA basée sur un modèle, le workflow DXML prêt à l’emploi provoque des interruptions de processus et génère des erreurs 503 non utilisables. 16529
- **Les caractères spéciaux** écrits avec des caractères d’échappement sont supprimés de la rubrique après avoir été téléchargés vers Experience Manager Guides. (16495)
- Le message d’erreur Fichier extrait par &quot;&quot; s’affiche incorrectement lors de la modification des fichiers qui sont déplacés d’un autre onglet, lorsque des jetons ont expiré ou lorsque l’utilisateur est déconnecté. (15223)
- Les fichiers volumineux ne se chargent pas dans l’éditeur web et provoquent le gel du navigateur. (13227)
- `<Topicref>` ajouté à l’aide de `<keyref>` ne s’affiche pas dans le PDF natif. (1974)
- Le chemin d’accès au composant `/libs/fmdita/components/versions` est codé en dur et les utilisateurs ne peuvent pas le superposer. (8779)
- L’ouverture d’une rubrique ou d’un mappage DITA dans un nouvel onglet pour la modification gèle la navigation de la sélection dans l’interface utilisateur d’Assets. (4992)
- Le téléchargement d’un mappage DITA avec des fichiers vidéo volumineux déclenche une erreur de mémoire insuffisante dans les journaux et échoue sur l’interface utilisateur. (18884)
- Lors de l’insertion d’une équation MathML contenant le symbole &quot;&lt;&quot;, une erreur **Caractère non valide** est générée. (18742)
- Une génération incorrecte de l’UUID pendant le processus d’ingestion du contenu entraîne des références d’envoi rompues dans la carte ingérée. (18308)
- Dans certains cas, des retards de traitement d’une nouvelle rubrique DITA sont observés lors de sa création à partir de l’éditeur web. (16836)
- La recherche de fichiers dans le **référentiel** à l’intérieur de l’éditeur web prend trop de temps et parfois ne parvient pas à charger les résultats. (16837)

## Publication

- La référence croisée à la clé n’est pas résolue dans la sortie du PDF natif. (18087)
- L’erreur **duplicate_value** se produit par intermittence lors de la republication d’un article existant dans Salesforce. (17932)
- Le style et la mise en forme du contenu dans les modèles client changent automatiquement lorsque la mise en page inclut des champs de métadonnées, ce qui entraîne une mise en forme incorrecte dans les PDF publiés. (17900)
- La validation de la connexion Salesforce échoue avec l’URL d’éclair. 17797
- Le PDF référencé n’est pas activé à partir du **tableau de bord du Publish en bloc** lors de l’activation en bloc du contenu publié. (17793)
- L’activation en bloc du contenu publié ne fonctionne pas pour les cartes localisées. (17638)
- Lors de la sélection de l’option **Utiliser les métadonnées ajoutées dans la topicmeta** , les propriétés de métadonnées ne sont pas propagées dans les propriétés de document de la sortie de l’PDF natif. (17283)
- Le filtrage des conditions dans la sortie du PDF natif ne fonctionne pas comme prévu par rapport à DITA-OT. (17095)
- La table des matières n’honore pas les balises `<sub>` ou `<sup>` dans la sortie du PDF natif. 17028
- La génération AEM site et l’API de publication incrémentielle ne fonctionnent pas comme prévu. (16666)
- La génération du PDF natif échoue avec une erreur liée à l’obtention des dépendances pour Node.js. (14445)
- `<Conref>` n’est pas résolu dans le mode `Preview` de l’éditeur web et de la sortie du PDF natif. (17827)
- Les références de contenu ne sont pas correctement résolues pour la sortie du PDF natif si le fichier contenant des définitions de clé ne se trouve pas dans le même dossier que le mappage DITA. 15062)
- Lorsqu’un mappage DITA contient des niveaux d’en-tête supérieurs ou supérieurs à 7, l’en-tête de niveau 7 est incorrectement traité comme en-tête de niveau 1 dans la sortie du PDF natif. (19698)
- Lorsqu’un élément de contenu (texte) est enveloppé dans un élément, les espaces avant et après le texte ne s’affichent pas dans les formats Aperçu ou Sortie. (19308)
- Les workflows de post-génération déclenchés manuellement échouent en raison d’une EXCEPTION NULL POINTER dans le workflow, ce qui entraîne 11 chargements du contenu. (18880)
- **Le tableau de bord Publish en bloc** affiche un vierge pour les cartes qui sont toujours en cours de traduction. (19352)


## Gestion

- Le chemin d’accès de la fonctionnalité de superposition est codé en dur pour le fichier de langue coréenne et n’est pas correctement sélectionné. 17089
- Les modifications/personnalisations apportées à la boîte de dialogue **Enregistrer la version** ne sont pas répercutées lors de l’utilisation de Guides Extension Framework. 17828
- L’InDesign à la conversion DITA comporte un chemin de configuration codé en dur, de sorte que les fichiers de configuration personnalisés ne sont pas sélectionnés. (16891)
- Les références/ressources complètes ne sont pas téléchargées lorsqu’un mappage DITA contenant de grandes dépendances/références est téléchargé à l’aide de la ligne de base. (19099)


### Révision

- La récupération de la liste des utilisateurs lors de la création d’une tâche de révision échoue si le nombre d’utilisateurs dépasse 25. 17329
- Si une rubrique de tâche contient une balise `<cmd>` dans une ou plusieurs étapes, le panneau de révision affiche l’attribut `importance` comme préfixe dans toutes les étapes contenant la balise. (19699)

## Traduction

- Les références des ressources traduites ne sont pas mises à jour. (18086)
- Les références ne sont pas correctement filtrées en tant que Direct ou Indirect lors de la traduction dans plusieurs langues. (17891)
- Impossible de créer des projets XLIFF avec traduction humaine. (16964)
- L’ajout d’une rubrique mise à jour dans un projet de traduction actif entraîne la duplication d’une rubrique et l’échec du processus. (7688)
- Les projets de traduction créés en sélectionnant l’option **Créer une structure uniquement** n’ont pas d’UUID attribués. (18980)
- Lors de la sélection d’un projet de traduction dont le **statut de traduction** est **En cours**, une page incorrecte s’ouvre. (13248)
- Le titre avec `<conref>` ne se résout pas dans les tableaux de bord Ligne de base et Traduction de l’éditeur web. (16961)

## Problèmes connus

- L’ouverture d’un paramètre prédéfini AEM Sites (non hérité) marque le sujet comme sale.
- Le panneau sélectionné n’est pas conservé lors de l’actualisation du navigateur depuis l’onglet Sortie .
- Impossible de faire glisser et de déposer une rubrique entre deux rubriques dans la vue **Auteur**.
- Le filtrage de condition appliqué dans le paramètre prédéfini n’est pas appliqué via **Télécharger en tant que PDF**.
- La génération de rubrique unique à partir du panneau de mappage génère toutes les rubriques sélectionnées dans le paramètre prédéfini AEM Sites (non hérité).
- La référence de la rubrique apparaît rompue dans l’interface utilisateur lorsqu’elle est insérée à partir de la barre d’outils supérieure du mappage DITA.
- La génération d’un PDF natif échoue pour un mappage DITA s’il manque des références.
- La publication d’une seule rubrique du site AEM avec des conditions échoue dans l’environnement de microservices activé.
- Une fois que l’état du document d’une rubrique est mis à jour sur **Terminé**, l’icône **Démarrer une nouvelle version** n’est disponible que dans le mode **Aperçu** de la rubrique.
