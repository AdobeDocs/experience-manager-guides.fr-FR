---
title: Notes de mise à jour | Adobe Experience Manager Guides as a Cloud Service, version de mai 2022
description: Version de mai d’Adobe Experience Manager Guides as a Cloud Service
exl-id: 7928a300-5ec9-492c-b9be-02b6f87638c6
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1887'
ht-degree: 0%

---

# Version de mai d’Adobe Experience Manager Guides as a Cloud Service

## Mise à niveau vers la version de mai

Mettez à niveau votre configuration Adobe Experience Manager Guides as a Cloud Service actuelle (ultérieurement appelée *AEM Guides as a Cloud Service*) en procédant comme suit :
1. Consultez le code Git des services cloud et passez à la branche configurée dans le pipeline des services cloud correspondant à l’environnement à mettre à niveau.
1. Mettez à jour `<dox.version>` propriété dans `/dox/dox.installer/pom.xml` fichier de votre code Git Cloud Services vers la version 2022.5.144.
1. Validez les modifications et exécutez le pipeline Cloud Services pour effectuer la mise à niveau vers la version de mai d’AEM Guides as a Cloud Service.

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par la version de mai 2022 d’AEM Guides as a Cloud Service.

### FrameMaker et FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Non compatible | Mise à jour 2020 4 et versions ultérieures |
| | |

*La ligne de base et les conditions créées dans AEM sont prises en charge dans les versions FMPS à compter de 2020.2.

### Connecteur D&#39;Oxygène

| Version d’AEM Guides as a Cloud | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène |
| --- | --- | --- |
| 2022.5.0 | 2,6,9 | 2,6,9 |
|  |  |  |


## Nouvelles fonctionnalités et améliorations

AEM Guides as a Cloud Service offre de nombreuses améliorations et nouvelles fonctionnalités dans la version de mai :

### Éditeur Web amélioré

* **Création de mappages à partir de modèles personnalisés**

Vous bénéficiez désormais de la puissante fonctionnalité de création de modèles de carte personnalisés. Vous pouvez les utiliser pour créer des plans DITA avec les modèles de rubrique et les modèles de plan référencés dans le modèle de plan.

![modèles dita](assets/dita-templates.png)

Vous pouvez également vous reporter à d’autres modèles de carte et modèles de rubrique à partir du modèle de carte personnalisé. Les modèles de mappage référencés peuvent faire référence à divers modèles de mappage, modèles de rubrique, rubriques, mappages, images, vidéos et autres ressources.

![créer des modèles dita](assets/create-dita-template.png)

Le modèle de mappage personnalisé peut vous aider à répliquer très facilement les modèles de mappage et l’ensemble de la structure de dossiers à laquelle il est fait référence. Ces modèles personnalisés sont particulièrement utiles pour créer et recréer plusieurs mappings dotés de structures et de références récursives.

* La fonctionnalité **Insérer le mot-clé** a été améliorée. Vous pouvez désormais trouver plus facilement un mot-clé à insérer, car les mots-clés sont répertoriés par ordre alphabétique. Vous pouvez également rechercher un ou plusieurs mots-clés en saisissant une chaîne de recherche dans la zone de recherche.

![insérer le mot-clé](assets/insert-keyword.png)

* Désormais, dans le référentiel, les fichiers sont chargés par lots. 75 fichiers sont chargés à la fois. Ce chargement par lots est efficace et vous pouvez accéder aux fichiers plus rapidement qu’avec le chargement de tous les fichiers existants dans un dossier.

![charger d’autres fichiers](assets/load-more-files.png)

* Vous pouvez effectuer le rendu d’images SVG qui incluent des données incorporées ou des liens dans tous les écrans de l’éditeur XML, y compris, mais sans s’y limiter, les vues Prévisualisation et Création.

* Le schéma XSD/DTD par défaut peut être mis à jour vers la dernière version

### Processus de traduction amélioré

* **Possibilité de créer un projet de traduction de portée**
Si vous devez créer uniquement la portée d’un projet à traduire, vous pouvez sélectionner **Créer un nouveau projet de traduction de la portée**. Les copies ne seront pas envoyées pour traduction et l’état de traduction original des fichiers sera conservé.

![ définition de la portée du projet de traduction ](assets/scoping-translation-project.png)

* Si vous rejetez la traduction d’une ou plusieurs rubriques dans une tâche de traduction, le statut Traduction en cours de toutes les rubriques rejetées revient à son statut d’origine.

* La liste **Langues** affiche les dossiers de langue ainsi que leurs codes de langue. Par exemple, le français (fr) et l’allemand (de).

* La fonction de traduction prend désormais en charge le code de langue qui inclut le pays et la langue. Par exemple, `fr-fr`, `en-us`.

![langue de traduction](assets/translation-languages.png)

* Lors du chargement d&#39;un plan DITA situé en dehors du dossier de langue, aucune exception n&#39;est consignée sur le serveur principal.

Pour plus d’informations sur la traduction, consultez la section *Traduire des documents à partir de l’éditeur web* dans Utilisation d’Adobe Experience Manager Guides as a Cloud Service.


### Publication améliorée

* Vous pouvez également accéder au tableau de bord de publication **Publish Dashboard** à partir de l’onglet Output , tandis que vous générez une sortie à partir du tableau de bord de mappage. Une liste de toutes les tâches de publication actives est disponible dans le tableau de bord de publication.

![sorties mises en file d’attente](assets/queued-output.png)

* Dans le tableau de bord des cartes, vous pouvez sélectionner plusieurs fichiers DITAVAL pour générer du contenu conditionné. Vous pouvez conserver l’ordre des fichiers en ajoutant ou en supprimant des fichiers. Vous pouvez également pointer sur le nom du fichier pour afficher le chemin d’accès dans le référentiel AEM où le fichier est stocké.

* **Fonctionnalité obsolète**
AEM as a Cloud Service ne prend plus en charge la génération de formats de sortie DITA pour les documents FrameMaker. Cette option DITA a également été supprimée des paramètres prédéfinis de sortie du tableau de bord Map.

### Amélioration de la publication basée sur des articles

XML Editor permet de mapper plusieurs catégories de produits à un article lors de la publication sur un profil Salesforce.

### Autres améliorations apportées aux fonctionnalités

* Le mode Aperçu prend également en charge `deliveryTarget` attribut de traitement conditionnel dans DITA. Elle est disponible sous forme d’option dans le filtre déroulant avec **audience**, **plateforme**, **produit**, props **autres props**.
* L’option a été fournie pour forcer la synchronisation entre le serveur AEM dans Oxygen et le système local.

## Problèmes résolus

Les bogues corrigés dans différentes zones sont répertoriés ci-dessous :

* Dans le panneau de révision de l’éditeur web, l’utilisateur ne peut pas répondre aux commentaires de révision. (9667)
* L’application devient vide lorsque vous cliquez sur un dossier vide après l’avoir actualisé via le menu Options. (9639)
* Une nouvelle version est créée lorsque nous **Enregistrer et fermer** le fichier archivé. (9638)
* Le bouton Fermer ne s’affiche pas lorsque la case **Enregistrer en tant que nouvelle version** est activée. (9637)
* Le PDF correct n’est pas publié s’il est d’abord publié via un PDF distinct pour chaque chapitre, puis un seul fichier PDF (l’option Créer des fichiers PDF distincts est décochée). (9632)
* Le tableau de bord des cartes génère un problème de métadonnées pour les utilisateurs non-administrateurs. (9620)
* Une fois qu’une ligne de base est créée, le statut est défini sur Échec dans l’interface utilisateur (l’appel get status échoue) si le serveur comporte plus de 10000 fichiers. (9608)
* Le stockage de données volumineuses dans les propriétés entraîne une erreur de publication, car le workflow de publication partagé échoue. (9586)
* L’état des filtres d’attributs conditionnels n’est pas conservé lors du passage entre le mode Aperçu vers Source et le mode Aperçu à nouveau. (9553)
* Le nom de la liasse est vide dans la vue Référentiel au cas où aucun nom n’est donné via la balise `mainbooktitle`. (9538)
* Une erreur HTTP 400 se produit lors de l’ouverture d’un fichier chargé avec Oxygen. (9535)
* Les paramètres prédéfinis d’un mappage précédemment ouvert restent visibles dans l’onglet Sortie lors de l’ouverture d’un mappage sans paramètre prédéfini. (9523)
* La fonctionnalité de recherche de balises et d’attributs ne fonctionne pas dans le panneau Plan. (9506)
* La collection nouvellement créée n’est pas visible tant que le navigateur n’est pas actualisé. (9505)
* Les libellés Attributs conditionnels (et non les valeurs) apparaissent en mode source lors de l’ajout de toutes les conditions via l’option « Ajouter toutes les props ». (9501)
* Les fichiers sont extraits automatiquement lors du retour à n’importe quelle version. (9482)
* Des différences d’horodatage incorrectes s’affichent dans l’interface utilisateur d’Assets lors du rétablissement d’une version de fichier. (9480)
* Plusieurs éléments issus des résultats de la recherche sont ajoutés lors de l&#39;insertion d&#39;éléments dans l&#39;élément topicref du plan DITA. (9474)
* Si le paramètre **Créer une version pour le fichier téléchargé** est activé, une nouvelle version est créée lors de la restauration et de l’enregistrement sur tout nœud figé. (9473)
* Le texte d’affichage de la Référence de clé et de la Référence de clé de contenu n’est pas conservé lors de la modification de l’URL du lien si le texte d’affichage n’est pas ajouté lors de la définition de la référence de clé. (9458)
* Dans l’historique des versions, le numéro de version et le libellé ne s’affichent pas pour la version actuelle. (9446)
* L’éditeur se fige lorsque certains fichiers de contenu sont ouverts dans l’éditeur. (9443)
* La recherche dans le panneau Référentiel et la boîte de dialogue de navigation de la rubrique figent l’écran lorsque le contenu est volumineux. (9432)
* Les métadonnées transmises à la sortie du site AEM ne respectent pas la ligne de base du contenu. (9416)
* Oxygen extrait une version incorrecte d’une rubrique après un retour de version dans AEM. (9411)
* La ligne de base en échec désactive la modification dans l’onglet Paramètre prédéfini du tableau de bord de mappage. (9403)
* Une erreur est toujours consignée lors de la création d’un nouveau contenu. (9388)
* Les ressources DITA nouvellement créées sont toujours extraites par un autre utilisateur. (9387)
* L’élément Renommer ne fonctionne pas correctement lors de la conversion de topicref en glossref. (9380)
* Le libellé de version n’apparaît pas comme liste déroulante dans la boîte de dialogue **Enregistrer en tant que nouvelle version**. (9379)
* Les conditions ne sont pas appliquées lors du changement entre différentes versions à partir du menu déroulant **Afficher la différence**. (9366)
* L’utilisation des filtres de prévisualisation entraîne plusieurs problèmes. (9365)
* Impossible d&#39;insérer des ressources non DITA et DITAVAL dans la rubrique. (9363)
* La traduction approuvée ne s’intègre pas à la langue cible lorsque le code de langue cible contient cinq caractères tels que `fr_ca`. (9357)
* Impossible de rechercher des fichiers à l’aide de l’option **Rechercher des fichiers dans le dossier** du menu **Plus d’options** et l’application ne répond plus. (9337)
* La boîte de dialogue de navigation se bloque en présence d’un grand nombre de clés. (9332)
* Les fichiers DITAVAL ne fonctionnent pas lors de la publication d’articles. (9330)
* L’ordre des notes de bas de page est incorrect dans la sortie du site AEM. (9327)
* La recherche n’est pas automatiquement effectuée lorsque le chemin sélectionné est modifié. (9323)
* Une fois la traduction terminée, une version supplémentaire est créée pour la ressource traduite. (9310)
* Impossible de supprimer les utilisateurs administrateurs dans le profil de dossier. (9306)
* La carte racine mise à jour à partir de la référence de clé de contenu n’est pas définie tant que la page n’est pas actualisée. (9302)
* L’authentification web ne fonctionne pas dans Oxygen. (9296)
* Les liens web avec des caractères codés ne fonctionnent pas correctement. (9227)
* Le fichier n&#39;est pas extrait lorsqu&#39;il est ouvert dans Oxygen. (9217)
* L&#39;actualisation des fichiers extraits ne fonctionne pas lors de la connexion avec l&#39;authentification Web dans Oxygen. (9179)
* Les onglets Traduction et Ligne de base sont visibles pendant un certain temps sur le tableau de bord Carte. (9146)
* Des problèmes d’expérience ou de fonctionnalité se produisent lors du rechargement du profil de dossier. (9103)
* La suppression de l’éditeur de mise en page ne le ferme pas du panneau central en mode Création. (9087)
* Une erreur de validation se produit dans l’éditeur web lors de la suppression d’une image, puis de l’enregistrement de la nouvelle version du document. (8985)
* Impossible d’afficher toutes les `glossrefs` dans le panneau Glossaire (spécifique au contenu). (8886)
* `xref` sans texte n’est pas affiché dans la sortie de publication basée sur des articles. (8764)
* Les références s’interrompent lors du déplacement d’images ou de fichiers multimédias dont les noms de fichier contiennent un espace. (8624)
* Les références s&#39;interrompent lors du choix de `Select All` et du déplacement des fichiers multimédias ou du contenu DITA vers un autre dossier. (8622)
* Les tâches de sortie avec un statut tel que « En attente » ou « En cours d’exécution » ne sont pas nettoyées dans le tableau de bord de publication.  (8569)
* La fonction de purge de sortie échoue si un grand nombre de nœuds d’historique de sortie restants est présent. (8568)
* Le package complémentaire DITA empêche la détection de ressources en double dans la gestion des ressources numériques. (8417)
* Bouton Créer une tâche de révision activé pour les fichiers non DITA. (8401)
* La boîte de dialogue Insérer des références s’ouvre lors de l’ajout d’objets à une carte via l’interface utilisateur. (8212)
* Espace inattendu dans chaque élément de `entry` vide lorsque l’attribut outputclass est ajouté à `tgroup` élément. (7532)
* Le panneau Référentiel n’affiche pas les icônes de verrouillage des fichiers archivés ou extraits une fois l’action terminée. (5817)
* L’icône de cadenas s’affiche dans la vue du référentiel même lorsque le fichier est archivé à partir de l’éditeur.  (5756)
* Les sites sont absents des paramètres prédéfinis d’AEM dans l’onglet Sortie . (9567)
* L&#39;éditeur XML se bloque en essayant de modifier certains fichiers DITA. (9537)
* L’exécution d’une recherche dans l’éditeur XML entraîne le blocage de la page. (9452)
* Le mappage de téléchargement avec la ligne de base ne fonctionne pas si le contenu est déplacé vers un autre dossier. (9331)
* Le rechargement échoue dans Oxygen lorsque le ou les fichiers existent déjà dans AEM au même emplacement. (9328)
* La position de la mise en surbrillance est incorrecte dans la vue côte à côte. (9305)
* Après l’enregistrement d’un document d’Oxygen dans AEM, le contenu japonais du document est remplacé par des points d’interrogation (???). (9276)
* Le chargement des fichiers d’Oxygen vers AEM échoue. (9157)
* La notification par e-mail n’est pas envoyée lorsqu’une tâche de révision est réaffectée dans la boîte de réception. (8376)

## Problèmes connus

Une page vierge s’affiche par intermittence à l’ouverture de l’éditeur.
