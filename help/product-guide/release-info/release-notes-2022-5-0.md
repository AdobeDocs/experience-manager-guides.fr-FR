---
title: Notes de mise à jour | Guides Adobe Experience Manager as a Cloud Service, version de mai 2022
description: Version de mai des guides Adobe Experience Manager as a Cloud Service
exl-id: 7928a300-5ec9-492c-b9be-02b6f87638c6
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1887'
ht-degree: 0%

---

# Version de mai des guides Adobe Experience Manager as a Cloud Service

## Mise à niveau vers la version de mai

Mettez à niveau vos guides Adobe Experience Manager actuels as a Cloud Service (plus tard appelés *AEM Guides as a Cloud Service*) en procédant comme suit :
1. Extrayez le code Git des Cloud Service et passez à la branche configurée dans le pipeline Cloud Service correspondant à l’environnement que vous souhaitez mettre à niveau.
1. Mettre à jour `<dox.version>` dans `/dox/dox.installer/pom.xml` du code Git Cloud Service vers la version 2022.5.144.
1. Validez les modifications et exécutez le pipeline Cloud Service pour effectuer la mise à niveau vers la version de mai d’AEM Guides as a Cloud Service.

## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par AEM Guides as a Cloud Service de mai 2022.

### FrameMaker et FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Non compatible | Mise à jour 4 et ultérieure 2020 |
| | |

*Les conditions de base et créées dans AEM sont prises en charge dans les versions FMPS à partir de 2020.2.

### Connecteur Oxygen

| AEM Guides as a Cloud | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen |
| --- | --- | --- |
| 2022.5.0 | 2.6.9 | 2.6.9 |
|  |  |  |


## Nouvelles fonctionnalités et améliorations

AEM Guides as a Cloud Service comporte de nombreuses améliorations et nouvelles fonctionnalités dans la version de mai :

### Éditeur web amélioré

* **Création de cartes à partir de modèles personnalisés**

Vous disposez désormais de la puissante fonctionnalité permettant de créer des modèles de carte personnalisés. Vous pouvez les utiliser pour créer des mappages DITA avec les modèles de rubrique et de mappage référencés dans le modèle de mappage.

![modèles dita](assets/dita-templates.png)

Vous pouvez également vous référer à d’autres modèles de mappage et de rubriques à partir du modèle de mappage personnalisé. Les modèles de mappage référencés peuvent faire référence à divers modèles de mappage, modèles de rubrique, rubriques, cartes, images, vidéos et autres ressources.

![créer des modèles dita](assets/create-dita-template.png)

Le modèle de carte personnalisé peut vous aider à répliquer très facilement les modèles de carte et la structure de dossiers référencée entière. Ces modèles personnalisés sont particulièrement utiles pour créer et recréer plusieurs cartes qui comportent des structures et des références récursives.

* La variable **Insérer un mot-clé** fonctionnalité a été améliorée. Vous pouvez désormais trouver plus facilement un Mot-clé à insérer lorsque les mots-clés sont répertoriés par ordre alphabétique. Vous pouvez également rechercher des mots-clés en saisissant une chaîne de recherche dans la zone Rechercher.

![mot-clé d&#39;insertion](assets/insert-keyword.png)

* Désormais, les fichiers en mode Référentiel sont chargés par lots. 75 fichiers sont chargés à la fois. Ce chargement par lots est efficace et vous pouvez accéder aux fichiers plus rapidement par rapport au chargement de tous les fichiers existants dans un dossier.

![charger plus de fichiers](assets/load-more-files.png)

* Vous pouvez effectuer le rendu d’images SVG qui incluent des données ou des liens incorporés dans tous les écrans de l’éditeur XML, y compris, mais sans s’y limiter, la vue Aperçu et création.

* Le fichier XSD/DTD par défaut peut être mis à jour vers la dernière version.

### Processus de traduction amélioré

* **Possibilité de créer un projet de traduction de portée**
Si vous devez créer uniquement la portée d’un projet à traduire, vous pouvez sélectionner **Création d’un projet de traduction d’étendue**. Cela n’enverra pas les copies à traduire et l’état de traduction d’origine des fichiers est conservé.

![projet de traduction de portée](assets/scoping-translation-project.png)

* Si vous refusez la traduction d’une ou de plusieurs rubriques d’une tâche de traduction, l’état de traduction En cours de toutes les rubriques rejetées revient à leur état d’origine.

* La variable **Langues** La liste affiche les dossiers de langue ainsi que leurs codes de langue. Par exemple, Français (fr) et Allemand (de).

* La fonctionnalité de traduction prend désormais en charge le code de langue qui inclut le pays et la langue. Par exemple, `fr-fr`, `en-us`.

![langue de traduction](assets/translation-languages.png)

* Lors du chargement d’un mappage DITA en dehors du dossier de langue, aucune exception n’est consignée au serveur principal.

Pour plus d’informations sur la traduction, voir *Traduire des documents à partir de l’éditeur Web* dans Utilisation des guides Adobe Experience Manager as a Cloud Service.


### Publication améliorée

* Vous pouvez également accéder au **Publier le tableau de bord** dans l’onglet Sorties lorsque vous générez une sortie à partir du tableau de bord de mappage. Une liste de toutes les tâches de publication actives est disponible dans le tableau de bord de publication.

![sorties en file d’attente](assets/queued-output.png)

* Dans le tableau de bord de mappage, vous pouvez sélectionner plusieurs fichiers DITAVAL pour générer du contenu conditionnel. Vous pouvez conserver l’ordre des fichiers en ajoutant ou en supprimant des fichiers. Vous pouvez également survoler le nom du fichier avec la souris pour voir le chemin d’accès dans le référentiel AEM où le fichier est stocké.

* **Fonctionnalité obsolète**
AEM as a Cloud Service ne prend plus en charge la génération du format de sortie DITA pour les documents de FrameMaker. Cette option DITA a également été supprimée des paramètres prédéfinis de sortie du tableau de bord des cartes.

### Amélioration de la publication basée sur des articles

XML Editor permet de mapper plusieurs catégories de produits à un article lors de la publication sur un profil Salesforce.

### Autres améliorations de fonctionnalités

* Le mode Aperçu prend également en charge `deliveryTarget` attribut de traitement conditionnel dans DITA. Elle est disponible sous la forme d’une option dans le filtre déroulant, ainsi que **audience**, **platform**, **product**, props, **Autres props**.
* Une option a été fournie pour une synchronisation forcée entre le serveur AEM dans Oxygen et le système local.

## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :

* Dans le panneau de révision de l’éditeur Web, l’utilisateur ne peut pas répondre aux commentaires de révision. (9667)
* L’application est vide lorsque vous cliquez sur un dossier vide après l’avoir actualisée via le menu Options. (9639)
* Une nouvelle version est créée lorsque nous **Enregistrer et fermer** le fichier archivé. (9638)
* Le bouton Fermer n’est pas affiché lorsque **Enregistrer comme nouvelle version** est activée. (9637)
* Le bon PDF n’est pas publié s’il est d’abord publié via un PDF distinct pour chaque chapitre, puis un seul fichier de PDF (la case Créer des fichiers de PDF distincts n’est pas cochée). (9632)
* Le tableau de bord des cartes génère un problème de métadonnées pour les utilisateurs non-administrateurs. (9620)
* Une fois une ligne de base créée, l’état est défini sur échec sur l’interface utilisateur (l’appel de l’état échoue) si le serveur contient plus de 10 000 fichiers. (9608)
* Le stockage de données volumineuses dans les propriétés entraîne une erreur de publication, car le processus de publication partagé échoue. (9586)
* L’état des filtres d’attributs conditionnels n’est pas conservé lors du passage de l’aperçu à la source, puis au mode Aperçu. (9553)
* Le nom du signet est vide dans la vue Repository au cas où aucun nom n’est donné via la variable `mainbooktitle` balise . (9538)
* Une erreur HTTP 400 se produit lors de l’ouverture d’un fichier téléchargé à l’aide d’Oxygen. (9535)
* Les paramètres prédéfinis d’une carte précédemment ouverte restent visibles dans l’onglet Sortie lors de l’ouverture d’une carte sans paramètre prédéfini. (9523)
* La fonctionnalité de recherche des balises et des attributs ne fonctionne pas dans le panneau Contour . (9506)
* La collection nouvellement créée n’est pas visible tant que le navigateur n’a pas été actualisé. (9505)
* Les libellés Attributs conditionnels (et non les valeurs) apparaissent en mode source lors de l’ajout de toutes les conditions via l’option &quot;Ajouter toutes les props&quot;. (9501)
* Les fichiers sont extraits automatiquement lors du rétablissement d’une version. (9482)
* Des différences d’horodatage incorrectes s’affichent dans l’interface utilisateur d’Assets lors de la restauration d’une version de fichier. (9480)
* Plusieurs éléments des résultats de recherche sont ajoutés lors de l’insertion d’éléments dans l’élément topicref du mappage DITA. (9474)
* Si le paramètre **Créer une version pour le fichier téléchargé** est activé, une nouvelle version est créée lors de la restauration et de l’enregistrement sur n’importe quel noeud figé. (9473)
* Le texte d’affichage de la référence de clé et de la référence de clé de contenu n’est pas conservé lors de la modification de l’URL du lien, si le texte d’affichage n’est pas ajouté lors de la définition de la référence de clé. (9458)
* Dans l’historique de version, le numéro de version et le libellé ne s’affichent pas pour la version actuelle. (9446)
* L’éditeur se bloque lorsque certains fichiers de contenu sont ouverts dans l’éditeur. (9443)
* La recherche dans le panneau Référentiel et la boîte de dialogue de navigation topicref gèle l’écran lorsque le contenu est volumineux. (9432)
* Les métadonnées transmises à AEM sortie du site ne tiennent pas compte de la ligne de base du contenu. (9416)
* Oxygen extrait une version incorrecte d’une rubrique après le rétablissement d’une version dans AEM. (9411)
* La ligne de base ayant échoué désactive la modification dans l’onglet Paramètre prédéfini du tableau de bord de mappage. (9403)
* L’erreur est toujours consignée lors de la création d’un nouveau contenu. (9388)
* Les ressources DITA nouvellement créées sont toujours extraites par un autre utilisateur. (9387)
* L’élément Renommer ne fonctionne pas correctement lors de la conversion de topicref en glossref. (9380)
* Le libellé de version ne figure pas dans la liste déroulante **Enregistrer comme nouvelle version** boîte de dialogue. (9379)
* Les conditions ne sont pas appliquées lors du changement entre différentes versions de **Afficher l’écart** menu déroulant. (9366)
* Plusieurs problèmes se produisent lors de l’utilisation des filtres d’aperçu. (9365)
* Impossible d’insérer des ressources non DITA et DITAVAL dans topicref. (9363)
* La traduction approuvée ne s’intègre pas à la langue cible lorsque le code de langue cible contient cinq caractères tels que `fr_ca`. (9357)
* Impossible de rechercher des fichiers à l’aide de **Recherche de fichiers dans le dossier** de la **Plus d’options** et l’application ne répond plus. (9337)
* La boîte de dialogue de navigation se bloque si un grand nombre de clés sont présentes. (9332)
* Les fichiers DITAVAL ne fonctionnent pas lors de la publication basée sur un article. (9330)
* L’ordre des notes de bas de page est incorrect dans la sortie AEM Site. (9327)
* La recherche n’est pas automatiquement effectuée lorsque le chemin de sélection est modifié. (9323)
* Une fois la traduction terminée, une version supplémentaire est créée pour la ressource traduite. (9310)
* Impossible de supprimer les utilisateurs administrateurs dans le profil de dossier. (9306)
* La carte racine mise à jour à partir de la référence de clé de contenu n’est pas définie tant que la page n’a pas été actualisée. (9302)
* L&#39;authentification web ne fonctionne pas dans Oxygen. (9296)
* Les liens web avec des caractères codés ne fonctionnent pas correctement. (9227)
* Le fichier n’est pas extrait lorsqu’il est ouvert dans Oxygen. (9217)
* L’actualisation des fichiers extraits ne fonctionne pas lors de la journalisation avec l’authentification Web dans Oxygen. (9179)
* Les onglets Traduction et Ligne de base sont visibles pendant un certain temps dans le tableau de bord Carte . (9146)
* Des problèmes d’expérience ou de fonctionnalité se produisent lors du rechargement du profil du dossier. (9103)
* La suppression de l’éditeur de mise en page ne le ferme pas dans le panneau central de la vue Auteur. (9087)
* Une erreur de validation se produit dans l’éditeur Web lors de la suppression d’une image, puis lors de l’enregistrement de la nouvelle version du document. (8985)
* Impossible d’afficher toutes les `glossrefs` dans le panneau Glossaire (spécifique au contenu). (8886)
* `xref` sans texte n’est pas affiché dans la sortie de publication basée sur un article. (8764)
* Les références s’interrompent lors du déplacement d’images ou de fichiers multimédia dont le nom de fichier contient un espace. (8624)
* Saut des références lors du choix `Select All` et déplacer les fichiers multimédias ou le contenu DITA vers un autre dossier. (8622)
* Les tâches de sortie avec le statut &quot;En attente&quot; ou &quot;En cours&quot; ne sont pas nettoyées dans le tableau de bord de publication.  (8569)
* La fonction de purge de sortie échoue si un grand nombre de noeuds d’historique de sortie restants sont présents. (8568)
* Le module complémentaire DITA empêche la détection des ressources en double de la gestion des actifs numériques. (8417)
* Bouton Créer une tâche de révision activé pour les fichiers non DITA. (8401)
* La boîte de dialogue Insérer des références s’ouvre lors de l’ajout d’un objet à un mappage à l’aide de l’interface utilisateur. (8212)
* Espace inattendu trouvé dans chaque espace vide `entry` élément lorsque l’attribut outputclass est ajouté à `tgroup` élément . (7532)
* Le panneau Référentiel n’affiche pas les icônes de verrouillage de fichier archivées ou extraites dès que l’action est terminée. (5817)
* L’icône représentant un cadenas s’affiche dans la vue du référentiel même lorsque le fichier est archivé à partir de l’éditeur.  (5756)
* Sites manquants dans AEM paramètres prédéfinis sous l’onglet Sortie. (9567)
* L’éditeur XML s’accroche à la tentative de modification de certains fichiers DITA. (9537)
* L’exécution d’une recherche dans XML Editor entraîne le blocage de la page. (9452)
* Le mappage de téléchargement avec la ligne de base ne fonctionne pas si le contenu est déplacé vers un autre dossier. (9331)
* La rechargement échoue dans Oxygen lorsque le ou les fichiers existent déjà dans AEM au même emplacement. (9328)
* La position de mise en surbrillance est incorrecte dans la vue côte à côte. (9305)
* Après l’archivage d’un document d’Oxygen vers AEM, le contenu japonais du document est remplacé par des points d’interrogation (???). (9276)
* Le téléchargement des fichiers d’Oxygen vers AEM échoue. (9157)
* La notification électronique n’est pas envoyée lorsqu’une tâche de révision est réaffectée dans la boîte de réception. (8376)

## Problèmes connus

La page vierge s’affiche par intermittence à l’ouverture de l’éditeur.
