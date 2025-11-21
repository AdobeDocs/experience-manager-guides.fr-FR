---
title: Notes de mise à jour | Adobe Experience Manager Guides version 4.1
description: Dernière version d’Adobe Experience Manager Guides
exl-id: c70b3bbc-3332-4626-bc30-641034f8fd06
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '3644'
ht-degree: 1%

---

# Version 4.1.x d’Adobe Experience Manager Guides

Ces notes de mise à jour couvrent les instructions de mise à niveau, les nouvelles fonctionnalités et les améliorations de la version 4.1.x d’Adobe Experience Manager Guides (ultérieurement appelée *AEM Guides*).

## Mettre à niveau vers la dernière version

Vous pouvez facilement mettre à niveau votre version actuelle d’AEM Guides vers la version 4.1.3. Avant de procéder à la mise à niveau vers la version 4.1.3 d’AEM Guides, vous devez tenir compte des points suivants :

* Si vous utilisez la version 4.1 ou 4.1.x, vous pouvez directement effectuer la mise à niveau vers la version 4.1.3.
* Si vous utilisez la version 4.0.x, vous devez effectuer la mise à niveau vers la version 4.1 ou 4.1.x avant la mise à niveau vers la version 4.1.3.
* Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0.x avant la mise à niveau vers la version 4.1.
* Si vous utilisez une version antérieure à la version 3.8.5, reportez-vous à la section mise à niveau du guide d’installation spécifique au produit.

Pour plus d’informations, voir [Instructions de mise à niveau](assets/Adobe-Experience-Manager-Guides-Upgrade-Instructions-EN.pdf).

## 4,1,3 | Notes de mise à jour

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par la version 4.1.3 d’AEM Guides.

### ADOBE EXPERIENCE MANAGER

**Non-UUID**
Version 6.5 Service Pack 13, 12, 11 ou 10

**UUID**
Version 6.5 Service Pack 13, 12, 11 ou 10

Pour plus d’informations, voir la section Exigences techniques dans le guide Installation et configuration d’Adobe Experience Manager Guides .


### FrameMaker et FrameMaker Publishing Server

| Version | FMPS 2020 | FMPS 2019 | Fm 2020 | Fm 2019 |
| --- | --- | --- | --- | --- |
| 4.1.3 (Non-UUID) | 2020.2 ou version ultérieure* | 2019 | 2020.3 ou version ultérieure | 2019.8 (dernière mise à jour) |
| 4.1.3 (UUID) | 2020.2 ou version ultérieure* | Non compatible | 2020.4 ou version ultérieure | Non compatible |
| | | | |  |

*La ligne de base et les conditions créées dans AEM sont prises en charge dans les versions FMPS à compter de 2020.2.

### Connecteur D&#39;Oxygène

| Version | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.1.3 (Non-UUID) | 2.0 | 2.0 | 1,6 | 1,6 |
| 4.1.3 (UUID) | 2,7 | 2,7 | 2,3 | 2,3 |
|  |  |   |  |  |


## Problèmes résolus

Le bogue corrigé est répertorié ci-dessous :

* L’éditeur web charge une page vierge par intermittence. (10678)


## 4.1.2 | Notes de mise à jour

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par la version 4.1.2 d’AEM Guides.

### ADOBE EXPERIENCE MANAGER

**Non-UUID**
Version 6.5 Service Pack 13, 12, 11 ou 10

**UUID**
Version 6.5 Service Pack 13, 12, 11 ou 10

Pour plus d’informations, voir la section Exigences techniques dans le guide Installation et configuration d’Adobe Experience Manager Guides .


### FrameMaker et FrameMaker Publishing Server

| Version | FMPS 2020 | FMPS 2019 | Fm 2020 | Fm 2019 |
| --- | --- | --- | --- | --- |
| 4.1.2 (Non-UUID) | 2020.2 ou version ultérieure* | 2019 | 2020.3 ou version ultérieure | 2019.8 (dernière mise à jour) |
| 4.1.2 (UUID) | 2020.2 ou version ultérieure* | Non compatible | 2020.4 ou version ultérieure | Non compatible |
| | | | |  |

*La ligne de base et les conditions créées dans AEM sont prises en charge dans les versions FMPS à compter de 2020.2.

### Connecteur D&#39;Oxygène

| Version | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.1.2 (Non-UUID) | 2.0 | 2.0 | 1,6 | 1,6 |
| 4.1.2 (UUID) | 2,7 | 2,7 | 2,3 | 2,3 |
|  |  |   |  |  |


## Problèmes résolus

Les bogues corrigés dans différentes zones sont répertoriés ci-dessous :

* Lors de la sélection de tous les profils de dossier, un profil de dossier invisible (incorrect) s’affiche. (10393)
* La création de la ligne de base ne sélectionne pas la dernière version lorsque le fuseau horaire de l’utilisateur ou de l’utilisatrice est différent de celui du serveur. (10336)
* Le raccourci Contrôle+F n’ouvre pas la boîte de dialogue modale de recherche du navigateur sur la console Assets après l’installation d’AEM Guides 4.1. (10339)
* Une erreur de création de ligne de base se produit pour le topic qui contient la référence à un dossier. (10383)
* L’onglet Paramètres prédéfinis de sortie affiche par intermittence un écran vide et, dans certains cas, des paramètres prédéfinis non modifiables s’affichent. (10390)
* La gestion de l’espace clé entraîne des exceptions et des erreurs. (10449)

### Problèmes connus liés à la solution de contournement

* La ligne de base exportée pendant la traduction ne se charge pas dans l’onglet ligne de base de l’éditeur.

  **Solution** : utilisez l&#39;onglet de base du tableau de bord DITA Map.

## 4,1 | Notes de mise à jour

Ces notes de mise à jour couvrent les instructions de mise à niveau, les nouvelles fonctionnalités et les améliorations de la version 4.1.x d’Adobe Experience Manager Guides (ultérieurement appelée *AEM Guides*).

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par la version 4.1 d’AEM Guides.

### ADOBE EXPERIENCE MANAGER

**Non-UUID**
Version 6.5 Service Pack 13, 12, 10 ou 11

**UUID**
Version 6.5 Service Pack 13, 12, 10 ou 11

Pour plus d’informations, voir la section Exigences techniques dans le guide Installation et configuration d’Adobe Experience Manager Guides .




### FrameMaker et FrameMaker Publishing Server

| Version | FMPS 2020 | FMPS 2019 | Fm 2020 | Fm 2019 |
| --- | --- | --- | --- | --- |
| 4.1 (non-UUID) | 2020.2 ou version ultérieure* | 2019 | 2020.3 ou version ultérieure | 2019.8 (dernière mise à jour) |
| 4.1 (UUID) | 2020.2 ou version ultérieure* | Non compatible | 2020.4 ou version ultérieure | Non compatible |
| | | | | |

*La ligne de base et les conditions créées dans AEM sont prises en charge dans les versions FMPS à compter de 2020.2.

### Connecteur D&#39;Oxygène

| Version | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.1 (non-UUID) | 2.0 | 2.0 | 1,6 | 1,6 |
| 4.1 (UUID) | 2,7 | 2,7 | 2,3 | 2,3 |
|  |  |  | | |


## Nouvelles fonctionnalités et améliorations

AEM Guides offre de nombreuses améliorations et nouvelles fonctionnalités dans la version 4.1 :

### Publication native de PDF

La prise en charge de la création d’un PDF natif a également été ajoutée dans la version 4.1 d’AEM Guides. Un nouveau moteur de publication a été introduit avec les fonctionnalités suivantes :

* Création d’un modèle CSS
* Créer différents modèles de page
* Conception de modèles PDF comprenant des modèles CSS et de page
* Publier le contenu de carte et de rubrique au format PDF

### Prise en charge du chemin d’accès au site de la base de connaissances dans la publication basée sur des articles

AEM Guides fournit la fonctionnalité de publication d’article pour générer de manière incrémentielle une sortie d’une ou de plusieurs rubriques ou publier votre contenu sur une plateforme de base de connaissances. Avec la version 4.1, vous disposez d’une option supplémentaire pour choisir le chemin d’accès au site de la base de connaissances vers lequel la rubrique/carte doit être publiée. Une fois le chemin sélectionné, la sortie est générée à l’emplacement spécifié.

### Éditeur Web amélioré

* **Résolution de clé améliorée**

Une référence de clé de contenu DITA insère une partie du contenu d&#39;une rubrique dans une autre. Il utilise une clé pour localiser le contenu. Les références clés associées à une rubrique DITA doivent être résolues. La carte racine sélectionnée a la priorité la plus élevée pour résoudre les références clés.

![boîte de dialogue préférences utilisateur](assets/user-preferences.png)

Désormais, les références clés sont résolues sur la base du mappage racine défini dans l’ordre de priorité suivant :

1. Préférences utilisateur
1. Panneau Vue Carte
1. Profil de dossier

Pour plus d’informations, voir la section *Résoudre les références clés* dans le guide Utilisation d’Adobe Experience Manager Guides .

* **Ajouter un panneau personnalisé dans le panneau de gauche**

Vous pouvez maintenant ajouter un panneau personnalisé dans le panneau de gauche de l’éditeur web. Vous pouvez utiliser un panneau personnalisé à diverses fins, par exemple pour fournir de l’aide ou effectuer les tests d’un projet. Si un panneau personnalisé a été configuré, il apparaît également dans la liste des panneaux dans l’**Paramètres de l’éditeur**. Vous pouvez activer/désactiver le basculement pour afficher ou masquer le panneau personnalisé.

* **Possibilité de modifier l&#39;état du document des rubriques dans un plan DITA**

Vous pouvez désormais facilement modifier l&#39;état du document des rubriques sélectionnées dans un plan DITA. Vous pouvez également ouvrir et modifier les propriétés des rubriques sélectionnées dans un plan DITA à partir du menu **Plus d&#39;options** au bas du panneau Vue Carte.

![propriétés de rubrique sélectionnées](assets/map-view-properties.png)

* **Informations de version affichées en mode Aperçu**

L’éditeur web vous aide à gérer vos versions. Vous pouvez également voir la version de la rubrique active ou du plan DITA dans le coin supérieur droit de l&#39;onglet Fichier de la rubrique dans le mode Aperçu d&#39;une rubrique.

![version d’aperçu](assets/preview-version.png)


* **Amélioration du comportement d’actualisation de l’éditeur web**

Les améliorations suivantes sont désormais disponibles avec l’opération d’actualisation du navigateur dans l’éditeur web :

* Vous obtenez maintenant la prise en charge pour actualiser le navigateur pendant que vous modifiez votre
contenu dans l’éditeur web. Si vous appuyez sur l’icône d’actualisation du navigateur pendant qu’un ou plusieurs fichiers avec
si des modifications non enregistrées sont ouvertes pour modification, vous êtes invité à enregistrer vos fichiers ou à annuler l’action d’actualisation.

* Même lors de l’actualisation du navigateur, les vues du panneau de gauche et du panneau de droite sont conservées.

* La rubrique active ou le plan DITA est rouverte dans la zone d&#39;édition du contenu.

* **Création de mappages à partir de modèles personnalisés**

Vous bénéficiez désormais de la puissante fonctionnalité de création de modèles de carte personnalisés. Vous pouvez les utiliser pour créer des plans DITA avec les modèles de rubrique et les modèles de plan référencés dans le modèle de plan.

![modèles dita](assets/dita-templates.png)

Vous pouvez également vous reporter à d’autres modèles de carte et modèles de rubrique à partir du modèle de carte personnalisé. Les modèles de mappage référencés peuvent faire référence à divers modèles de mappage, modèles de rubrique, rubriques, mappages, images, vidéos et autres ressources.

![créer des modèles dita](assets/create-dita-template.png)

Le modèle de mappage personnalisé peut vous aider à répliquer très facilement les modèles de mappage et l’ensemble de la structure de dossiers à laquelle il est fait référence. Ces modèles personnalisés sont particulièrement utiles pour créer et recréer plusieurs mappings dotés de structures et de références récursives.

* **Prise en charge de Schematron**
« Schéma » fait référence à un langage de validation basé sur des règles utilisé pour définir des tests pour un fichier XML. À l&#39;aide d&#39;un fichier Schematron, vous pouvez définir certaines règles, puis les valider pour une rubrique DITA ou une carte. L’éditeur web prend en charge les fichiers Schematron. Vous pouvez importer les fichiers Schematron et les modifier également dans l&#39;éditeur Web. La prise en charge de Schematron dans l’éditeur web vous permet de valider les fichiers par rapport à un ensemble de règles, tout en préservant la cohérence et l’exactitude des rubriques.

![valider le schéma](assets/schematron-validate.png)

* **Boîte de dialogue améliorée lors de la fermeture du fichier**

AEM Guides vous invite à enregistrer vos modifications et à déverrouiller vos fichiers verrouillés lorsque vous tentez de fermer un fichier ouvert dans l’éditeur web. Les invites s&#39;affichent en fonction des paramètres **Demander l&#39;archivage à la fermeture** et **Demander la nouvelle version à la fermeture** configurés par votre administrateur.

Selon la configuration, vous avez la possibilité d’enregistrer les modifications et de créer une nouvelle version de votre document. Vous pouvez également archiver le fichier et enregistrer les modifications apportées à la version actuelle.

![Fermeture du fichier](assets/file-close-save-changes-unlock.png)

Pour plus d’informations, voir la section *Scénarios de fermeture et d’enregistrement de fichier* dans le guide Utilisation d’Adobe Experience Manager Guides .* La fonctionnalité **Insérer le mot-clé** a été améliorée. Vous pouvez désormais trouver plus facilement un mot-clé à insérer, car les mots-clés sont répertoriés par ordre alphabétique. Vous pouvez également rechercher un ou plusieurs mots-clés en saisissant une chaîne de recherche dans la zone de recherche.

![insérer le mot-clé](assets/insert-keyword.png)

* **Prise en charge des documents Markdown**
Markdown est un langage de balisage léger qui peut vous aider à ajouter des éléments de mise en forme aux documents en texte brut. L&#39;éditeur Web vous permet d&#39;utiliser des documents Markdown (.md) avec vos documents DITA. Vous pouvez facilement créer et prévisualiser un document Markdown dans l’éditeur web et l’ajouter dans votre fichier map via l’éditeur de map DITA.  Pour plus d’informations, consultez la section *Créer des documents Markdown à partir de l’éditeur web* dans le guide Utilisation d’Adobe Experience Manager Guides .

![prise en charge de markdown](assets/create-markdown-dita-topic.png)

* **Possibilité de configurer une vue de balises par défaut**
Si un utilisateur ou une utilisatrice active la vue Balises à partir de l’éditeur web, elle reste activée même entre les sessions.  Cela signifie que vous n’avez pas besoin d’activer à nouveau la vue Balises pour y accéder ultérieurement. Votre administrateur peut configurer l’état par défaut de la vue Balises dans l’éditeur web. La valeur par défaut de la vue Balises pour la session d’un nouvel utilisateur est déterminée par la propriété tagsView du fichier ui_config.json.

* Désormais, dans le référentiel, les fichiers sont chargés par lots. Tous les fichiers présents dans le fichier principal ou `/content/dam folder` sont répertoriés. Mais à partir du niveau suivant ou du dossier secondaire, 75 fichiers sont chargés à la fois. Ce chargement par lots est efficace et vous pouvez accéder aux fichiers plus rapidement qu’avec le chargement de tous les fichiers existants dans un dossier.

![charger d’autres fichiers](assets/load-more-files.png)

### Nouveau tableau de bord de référence

La version 4.1 d’AEM Guides offre la fonctionnalité de ligne de base intégrée à l’éditeur web. Vous pouvez désormais créer des lignes de base à partir de l&#39;éditeur Web et les utiliser pour publier ou traduire des rubriques de différentes versions.

**Remarque** : pour le système mis à niveau, veuillez mettre à jour la dernière **ui_config.json** pour le profil de dossier.

Utilisez cette fonctionnalité pour créer une ligne de base avec une version spécifique des rubriques disponibles à une date et une heure spécifiques. En outre, vous obtenez la prise en charge de l’API pour créer ou mettre à jour une ligne de base avec un libellé défini pour une version des rubriques.

![onglet gestion de base](assets/baseline-manage.png)

Vous pouvez rechercher les fichiers en fonction de leurs noms ou de leur emplacement. Vous pouvez également filtrer les rubriques à afficher dans la fenêtre d&#39;édition de la ligne de base et les trier en fonction de colonnes spécifiques.

![onglet gestion de base](assets/baseline-filter.png)

Les performances du processus de création de la ligne de base ont été améliorées. Le processus de création des lignes de base est asynchrone. Vous pouvez donc continuer à modifier d&#39;autres fichiers dans l&#39;éditeur Web pendant la création de la ligne de base. Pour plus d&#39;informations, consultez la section *Créer et gérer des lignes de base à partir de l&#39;éditeur web* dans le guide Utilisation d&#39;Adobe Experience Manager Guides .

Remarque : l&#39;onglet Ligne de base du tableau de bord des cartes est masqué par défaut. Votre administrateur peut activer l’onglet Ligne de base dans le tableau de bord des cartes.

* Le paramètre de ligne de base dans les API pour télécharger la carte utilise désormais le titre de la ligne de base pour récupérer le contenu avec version.

### Processus de traduction amélioré

* **Possibilité de créer un projet de traduction de portée**
Si vous devez créer uniquement la portée d’un projet à traduire, vous pouvez sélectionner **Créer un nouveau projet de traduction de la portée**. Les copies ne seront pas envoyées pour traduction et l’état de traduction original des fichiers sera conservé.

![ définition de la portée du projet de traduction ](assets/scoping-translation-project.png)

* La liste **Langues** affiche les dossiers de langue ainsi que leurs codes de langue. Par exemple, le français (fr) et l’allemand (de).

![langue de traduction](assets/translation-languages.png)

Pour plus d’informations sur la traduction, voir la section *Traduire des documents à partir de l’éditeur web* dans le guide Utilisation d’Adobe Experience Manager Guides .


### Publication améliorée

* Vous pouvez également accéder au tableau de bord de publication **Publish Dashboard** à partir de l’onglet Output , tandis que vous générez une sortie à partir du tableau de bord de mappage. Une liste de toutes les tâches de publication actives est disponible dans le tableau de bord de publication.

![sorties mises en file d’attente](assets/queued-output.png)

* Dans le tableau de bord des cartes, vous pouvez sélectionner plusieurs fichiers DITAVAL pour générer du contenu conditionné. Vous pouvez conserver l’ordre des fichiers en ajoutant ou en supprimant des fichiers. Vous pouvez également pointer sur le nom du fichier pour afficher le chemin d’accès dans le référentiel AEM où le fichier est stocké.

* Les références ont été respectées pour les métadonnées de sortie du site AEM. Vous pouvez également traiter les propriétés d’une version de base en tant que métadonnées. Si aucune ligne de base n’est définie, les propriétés de la dernière version sont traitées en tant que métadonnées.

* Les options **Nom de fichier** et **Arguments de ligne de commande DITA-OT** ont été ajoutées pour les paramètres prédéfinis de sortie HTML5, EPUB et Personnalisé. Vous pouvez maintenant spécifier le nom du fichier avec lequel vous souhaitez enregistrer la sortie. Vous pouvez également spécifier les arguments supplémentaires que DITA-OT doit traiter lors de la génération de la sortie.

### Mapper le tableau de bord

Lorsque vous choisissez de télécharger le plan DITA, la requête est mise en file d&#39;attente et vous recevez une notification une fois que le plan est prêt à être téléchargé. Vous pouvez choisir de télécharger immédiatement le fichier de mappage ou de le télécharger ultérieurement à partir du lien fourni dans la boîte de réception de notifications d’AEM.

![Téléchargement des cartes](assets/download-map-prompt.png)

### Autres améliorations apportées aux fonctionnalités

* AEM Guides prend désormais en charge Oxygen XML Author version 24.1.
* Le paramètre de ligne de base dans les API pour télécharger la carte utilise désormais le titre de la ligne de base pour récupérer le contenu avec version.

### Fonctionnalité obsolète

AEM Guides ne prend plus en charge la génération de formats de sortie DITA pour les documents FrameMaker. Cette option DITA a également été supprimée des paramètres prédéfinis de sortie du tableau de bord Map.

## Problèmes résolus

Les bogues corrigés dans différentes zones sont répertoriés ci-dessous :

* La prise en charge de la création n’est pas disponible en tant qu’alternative pour le référencement basé sur les chemins de fichier pour la publication. (8076)
* Le package complémentaire DITA empêche la détection de ressources en double dans la gestion des ressources numériques. (8417)
* Après l’enregistrement d’un document d’Oxygen dans AEM, le contenu japonais du document est remplacé par des points d’interrogation (???). (9124)
* L&#39;actualisation des fichiers extraits ne fonctionne pas lors de la connexion avec l&#39;authentification Web dans Oxygen. (9179)
* Le fichier n&#39;est pas extrait lorsqu&#39;il est ouvert dans Oxygen. (9192)
* Après l’enregistrement d’un document d’Oxygen dans AEM, le contenu japonais du document est remplacé par des points d’interrogation (???). (9276)
* L’authentification web ne fonctionne pas dans Oxygen. (9296)
* Le rechargement échoue dans Oxygen lorsque le ou les fichiers existent déjà dans AEM au même emplacement. (9328)
* Option non disponible pour synchroniser de manière forcée le contenu entre AEM et le système local. (9439)
* L’identifiant n’est pas généré automatiquement pour l’élément ajouté à l’aide de la boîte de dialogue **Insérer du contenu réutilisable** de la barre d’outils secondaire. (5826)
* Aucune boîte de dialogue de confirmation ne s’affiche lors du téléchargement d’une image portant le même nom qu’un fichier existant, via l’éditeur. (6011)
* Espace insécable non disponible dans la palette de caractères. (7523)
* La liste d’éléments (Alt + Entrée) apparaît grisée dans le thème Sombre/Plus sombre. (7913)
* La version n’est pas mise à jour lors de l’enregistrement de la révision d’une rubrique dans la barre d’outils du panneau Carte. (8228)
* la xréf ne peut pas être insérée même à des emplacements valides. (8354)
* L’opération « getversionlabels » est limitée et n’offre pas les performances attendues. (8513)
* Des problèmes se produisent avec la boîte de dialogue de confirmation lors de la fermeture d’un fichier verrouillé ou modifié qui n’est pas actuellement ouvert dans l’éditeur. (8692)
* Une erreur se produit lors de l’ajout d’un utilisateur en tant qu’administrateur dans le profil de dossier lorsque l’ID utilisateur est numérique. (8908)
* Le panneau Traduction est visible même à l&#39;ouverture du plan DITA dans l&#39;éditeur de plans. (9053)
* Le code de langue ne s’affiche pas avec la langue dans le panneau Traduction . (9108)
* Les onglets Traduction et Ligne de base sont visibles pendant un certain temps sur le tableau de bord Carte. (9146)
* Une fois la traduction terminée, une version supplémentaire est créée pour la ressource traduite. (9310)
* La traduction approuvée ne s’intègre pas à la langue cible lorsque le code de langue cible contient cinq caractères tels que `fr_ca`. (9357)
* Le contenu traduit est rompu lorsque le code de langue cible créé est mentionné comme `fr-fr, `, `en-us`. (9527)
* Lors du chargement d&#39;un plan DITA situé en dehors du dossier de langue, une exception est consignée sur le serveur principal.(9543)
* Impossible de créer un fichier DITA à l&#39;aide du modèle DITA personnalisé à partir de l&#39;éditeur. (7262)
* Le plan DITA est perdu lors de la publication d&#39;un plan DITA UUID via FMPS. (7278)
* AEM Guides ne copie pas les propriétés non uniques d’une ressource lorsqu’une ressource est copiée et collée. (8241)
* Le nom de fichier du plan DITA n&#39;est pas converti en minuscules lors de la création. (8383)
* La description de la tâche de révision n’apparaît pas dans l’e-mail de notification envoyé lorsqu’une nouvelle tâche de révision est affectée. (8507)
* Télécharger l’API map | Les dossiers temporaires ne sont pas nettoyés en cas d’erreurs de processus de téléchargement. (8523)
* `columnpreview.jsp` dépend du fournisseur de services.  (8543)
* Les traitements de sortie avec un statut tel que « En attente » ou « En cours d’exécution » ne sont pas nettoyés dans le tableau de bord de publication.  (8569)
* Icône par défaut sélectionnée lors de la génération d’un rapport à l’aide du bouton Générer, même si la propriété de l’icône est définie. (8573)
* Des problèmes se produisent dans le processus de révision lors de la mise à niveau de 3.8.X vers 4.0. (8788)
* Dans le panneau Révision de l’éditeur web, si un nom d’utilisateur est long, les icônes d’acceptation/de rejet ne s’affichent pas clairement. (8793)
* L’arborescence de référence se rompt après la suppression d’une rubrique et l’exécution d’une opération de déplacement. (8804)
* La DTD personnalisée définie par l&#39;utilisateur n&#39;est pas prioritaire par rapport à la DTD DITA standard incorporée dans DITA-OT. (9104)
* La position de la mise en surbrillance est incorrecte dans la vue côte à côte. (9305)
* La note de bas de page Utilisation par référence ne fait pas défiler l’écran jusqu’à la section note de bas de page dans la sortie du site AEM. (9061)
* L’ordre des notes de bas de page est incorrect dans la sortie du site AEM. (9327)
* Les ressources DITA nouvellement créées sont toujours extraites par un autre utilisateur. (9387)
* Une erreur est toujours consignée lors de la création d’un nouveau contenu. (9388)
* Le troisième écran du processus de création de la tâche de révision n’affiche pas la liste des glossaires. (4558)
* Références UUID incorrectes attribuées lors du chargement de plusieurs fichiers à partir de FrameMaker/Oxygen Connector. (8269)
* La notification par e-mail n’est pas envoyée lorsqu’une tâche de révision est réaffectée dans la boîte de réception. (8376)
* Le deuxième utilisateur administrateur ne peut pas être ajouté en tant que premier utilisateur administrateur à un dossier. (8430)
* La boîte de dialogue **Appliquer les libellés** de l’onglet Ligne de base n’affiche pas les libellés dans la liste déroulante. (8455)
* Lors de l’utilisation de la publication de ligne de base avec une image comme conref dans la rubrique, l’image n’est pas publiée dans la sortie. (8564)
* La fonction de purge de sortie échoue si un grand nombre de nœuds d’historique de sortie restants est présent. (8568)
* Dans le panneau Historique des versions, la section Version actuelle affiche un horodatage incorrect et est modifiée par les informations . (8765)
* Référence non mise à jour en fonction du libellé défini. (8799)
* Une erreur se produit lorsque les fichiers dont le dossier parent contient des caractères spéciaux dans le nom de fichier sont ouverts dans Oxygen (à l’aide du bouton **Modifier dans Oxygen**). (8918)
* Le chargement des fichiers d’Oxygen vers AEM échoue. (9157)
* Le mappage de téléchargement avec la ligne de base ne fonctionne pas si le contenu est déplacé vers un autre dossier. (9331)
* Oxygen extrait une version incorrecte d’une rubrique après un retour de version dans AEM. (9411)
* La recherche dans le panneau Référentiel et la boîte de dialogue de navigation de la rubrique figent l’écran lorsque le contenu est volumineux. (9432)
* Si le paramètre **Créer une version pour le fichier téléchargé** est activé, une nouvelle version est créée lors de la restauration et de l’enregistrement sur tout nœud figé. (9473)
* Des différences d’horodatage incorrectes s’affichent dans l’interface utilisateur d’Assets lors du rétablissement d’une version de fichier. (9480)
* Les fichiers sont extraits automatiquement lors du retour à n’importe quelle version. (9482)
* L’icône de cadenas s’affiche dans la vue du référentiel même lorsque le fichier est archivé à partir de l’éditeur.  (5756)
* Impossible d’ajouter des éléments frontend, backMATTER dans un bookmap à l’aide de la vue Auteur de l’éditeur web. (7652)
* Le mode Aperçu ne prend pas en charge `deliveryTarget` attribut de traitement conditionnel dans DITA. (7685)
* Lors de l&#39;ouverture d&#39;une rubrique de glossaire dans l&#39;éditeur XML, AEM force son enregistrement même si elle n&#39;a pas été modifiée. (8105)
* La boîte de dialogue Insérer des références s’ouvre lors de l’ajout d’objets à une carte via l’interface utilisateur. (8212)
* Le panneau Réutiliser le contenu se bloque lors de la recherche de caractères spéciaux `[` ou `*` .(8279)
* Lors de la création d’une entrée Glossentry, l’éditeur web affiche le contenu sous forme de note. (8384)
* L’éditeur XML supprime la nouvelle ligne dans le bloc de code. (8522)
* Le passage entre les modes source et auteur marque la rubrique comme sale et nécessite que le contenu soit à nouveau enregistré.(8524)
* Impossible de fermer une rubrique déverrouillée. (8545)
* Il n’existe aucune option permettant de choisir le chemin d’accès de la base de connaissances dans les paramètres prédéfinis de publication basés sur des articles. (8636)
* Les attributs sont manquants lors de l’ajout d’un chapitre dans la libellule à l’aide du glisser-déposer à partir de la vue Favoris. (8746)
* La boîte de dialogue Insérer un mot-clé ne permet pas de rechercher et les mots-clés ne sont pas répertoriés dans l’ordre de tri. (9094)
* L’exécution d’une recherche dans l’éditeur XML entraîne le blocage de la page. (9452)
* Les sites sont absents des paramètres prédéfinis d’AEM dans l’onglet Sortie . (9567)
* Les images SVG dont le rendu n’est pas correct dans les modes de création de l’éditeur XML. (9426)
* La ligne de base n’est pas respectée lors de la publication via Salesforce. (8953)
* La possibilité d&#39;effacer la feuille de route des paramètres des préférences utilisateur n&#39;est pas présente. (8534)
