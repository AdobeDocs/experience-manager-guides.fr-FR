---
title: Notes de mise à jour | Guides Adobe Experience Manager as a Cloud Service, version de septembre 2022
description: Version de septembre des guides Adobe Experience Manager as a Cloud Service
exl-id: f6247f91-43cc-43a4-a6f8-3b1f09d0533f
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1299'
ht-degree: 0%

---

# Version de septembre des guides Adobe Experience Manager as a Cloud Service

## Mise à niveau vers la version de septembre

Mettez à niveau vos guides Adobe Experience Manager actuels as a Cloud Service (plus tard appelés *AEM Guides as a Cloud Service*) en procédant comme suit :
1. Extrayez le code Git des Cloud Service et passez à la branche configurée dans le pipeline Cloud Service correspondant à l’environnement que vous souhaitez mettre à niveau.
1. Mettre à jour `<dox.version>` dans `/dox/dox.installer/pom.xml` du code Git Cloud Service vers la version 2022.9.178.
1. Validez les modifications et exécutez le pipeline Cloud Service pour effectuer la mise à niveau vers la version de septembre d’AEM Guides as a Cloud Service.

## Étapes d’indexation du contenu existant

Effectuez les étapes suivantes pour indexer le contenu existant et utilisez le nouveau texte de recherche et de remplacement au niveau de la carte :
* Exécutez une requête de POST sur le serveur (avec l’authentification correcte) - `http://<server:port>/bin/guides/map-find/indexin`.
(Facultatif : vous pouvez transmettre des chemins spécifiques des cartes pour les indexer ; par défaut, toutes les cartes seront indexées. || Exemple :   `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)
* L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison : `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Par exemple : `http://<_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)`
* Une fois la tâche terminée, la requête de GET ci-dessus répond avec succès et indique si une correspondance a échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.


## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par AEM Guides as a Cloud Service de septembre 2022.

### FrameMaker et FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Non compatible | Mise à jour 4 et ultérieure 2020 |
| | |

*Les conditions de base et créées dans AEM sont prises en charge dans les versions FMPS à partir de 2020.2.

### Connecteur Oxygen

| AEM Guides as a Cloud | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2022.9.0 | 2,7.13 | 2,7.13 | 2,3 | 2,3 |
|  |  |  |  |


## Nouvelles fonctionnalités et améliorations

AEM Guides as a Cloud Service comporte de nombreuses améliorations et nouvelles fonctionnalités dans la version de septembre :


### Création d’une ligne de base dynamique basée sur des libellés

Désormais, AEM Guides vous offre la fonctionnalité de création de lignes de base dynamiques basées sur des libellés. Si vous générez une ligne de base, téléchargez une ligne de base ou créez un projet de traduction à l’aide d’une ligne de base, les fichiers sont sélectionnés dynamiquement en fonction des étiquettes mises à jour. Cette fonctionnalité est pratique, car vous n’avez pas à modifier la ligne de base lors de la mise à jour des libellés.
Vous pouvez également exporter l’instantané de la ligne de base au format CSV.

![Création de lignes de base](assets/dynamic-baseline.png)

### Rechercher et remplacer le texte au niveau de la carte

Vous pouvez désormais rechercher des fichiers dans une carte qui contient du texte spécifique. Le texte recherché est mis en surbrillance dans les fichiers. Vous pouvez également remplacer le mot ou l’expression recherché par un autre mot ou expression dans les fichiers.
Sélectionnez la variable **Remplacer** pour remplacer l’occurrence actuelle et la variable **Remplacer tout dans le fichier** pour remplacer toutes les occurrences dans le fichier sélectionné.

![Rechercher un remplacement dans la carte](assets/map-find-replace.png)

Par défaut, les options **Extraction de fichier avant remplacement** et **Créer une version après remplacement** étant sélectionnés, un fichier est extrait avant de remplacer le texte et une nouvelle version est créée après le remplacement du texte.

### Afficher la différence de version des fichiers désynchronisés depuis le tableau de bord de traduction

Vous pouvez maintenant choisir de traduire le **Désynchronisé** en fonction des modifications apportées entre les deux versions d’une rubrique.\
![Tableau de bord des traductions](assets/translation-version-diff.png)
Dans le tableau de bord de traduction, vous pouvez facilement voir les différences entre la dernière version traduite et la version actuelle du fichier sélectionné.

![boîte de dialogue de différence de version](assets/version-diff.png)

En fonction des différences, vous pouvez décider si vous souhaitez traduire un sujet ou non.

### Interface utilisateur des métadonnées disponible pour les paramètres prédéfinis de PDF

Vous pouvez définir les métadonnées à partir du paramètre prédéfini de sortie d’un mappage DITA. Vous pouvez définir les métadonnées Titre, Auteur, Objet et Mots-clés. Ces métadonnées sont mappées aux métadonnées dans les propriétés de fichier de votre PDF de sortie.
Ces métadonnées remplacent les métadonnées définies au niveau du livre. Vous pouvez définir les métadonnées spécifiquement dans chaque paramètre prédéfini de sortie et les transmettre au PDF de sortie.

![Métadonnées dans les paramètres prédéfinis](assets/preset-metadata.png)


## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :

* Éditeur web | Lors du déplacement d’éléments dans une rubrique, les identifiants attribués pour les éléments sont remplacés par des identifiants attribués automatiquement. (7895)
* Suivi des modifications | Le contenu est perdu lorsqu’un nouvel élément est saisi à l’aide de la touche Entrée. (10246)
* Le sous-mappage référencé à la carte principale dans les modèles dita n’est pas créé. (10231)
* Éditeur XML | Le copier-coller ne fonctionne pas en mode création. 10309
* Une fois sélectionnés, plusieurs libellés de version ne sont pas désélectionnés. (9561)
* La navigation automatique vers le chemin d’accès dans la boîte de dialogue de navigation du site ne fonctionne pas comme la navigation dans les fichiers. (9920)
* Le panneau Plan n’affiche pas de contenu lorsqu’il est sélectionné à partir de **Auteur** to **Source** mode . 10319)
* La référence dans une nouvelle rubrique créée à l’aide d’un contenu dans le modèle de rubrique ne fonctionne pas. L’ID de hachage copié n’est pas mis à jour dans la copie de contenu. (9890)
* Éditeur web | Il n’existe aucun chargeur lors de la création d’une carte à partir du modèle de carte. (9891)
* Nouvel éditeur de cartes | Le texte gras ou italique ajouté dans le titre de la carte n’est pas conservé si nous changeons de **Auteur** à la fonction **Disposition** vue. 10218
* Nouvel éditeur de cartes | Les conditions appliquées à une référence ne peuvent pas être supprimées de la vue Mise en page. (10213)
* Nouvel éditeur de cartes | L’application de références de conditions ne fonctionne pas dans la vue Disposition comme dans la vue Auteur. (10198)
* Nouvel éditeur de cartes | Déplacer à gauche du menu contextuel supprime la référence si elle ne peut pas être déplacée à gauche. (10219)
* Nouvel éditeur de cartes |L’icône s’affiche incorrectement pour les références dans une carte créée à l’aide de la vue Mise en page. (10197)
* Panneau Référentiel | Le clic droit dans le panneau du référentiel renvoie une erreur d’application. (10123)
* Rechercher et remplacer | Le mode sombre n’est pas lisible pour les résultats de recherche dans l’éditeur web. (9978)
* Traduction | Les métadonnées et les balises ne sont pas propagées aux copies traduites. (4696)
* Le fait de copier-coller (ctrl+c/ctrl+v) renvoie une erreur en mode création. 10304
* Modèle de PDF | L’ajout d’images d’arrière-plan à n’importe quelle mise en page affiche le chemin d’accès à l’image absolu, et les images ne sont pas affichées dans le PDF de sortie. (10297)
* PDF natif | Le titre du chapitre et l’en-tête du chapitre ne fonctionnent pas dans la publication en PDF. (9947)
* PDF natif | `xref` pour un concept n’est pas résolu correctement pour une rubrique DITA spécifique. (10229)
* PDF natif | Impossible d’afficher le texte de légende d’un tableau dans la sortie de PDF générée. (9827)
* PDF natif | Les références dans les annexes ne s’affichent pas en tant qu’annexes dans la sortie PDF. 10182
* PDF natif | L’attribut de cadre d’un tableau n’est pas propagé vers le HTML temporaire (en tant que classe). (10353)
* PDF natif | Les fichiers de HTML temporaire ajoutent les classes colsep et rowsep à td et même si leur valeur est 0 dans le DITA source. 10352)
* PDF natif | Les métadonnées des critères ajoutés dans la mise en page ne sont pas honorées. 10377
* PDF natif | La génération du PDF échoue pour un contenu spécifique. (9927)
* PDF natif | Le contenu via conkeyref n’est pas affiché dans la sortie du PDF. (9836)
* PDF natif | Les références clés des Keydefs avec des images ou des liens externes ne sont pas résolues. (10063)
* L’affichage Auteur d’une carte n’affiche pas de texte d’espace réservé pour la liste de tabulations et la liste de figures. (10330)
* Lorsque nous créons une nouvelle ligne de base, le filtre de ligne de base déjà sélectionné n’est pas appliqué. (9954)
* Le fichier vidéo est absent de la ligne de base si le nom du dossier parent comporte un espace. 10031)
* La création de ligne de base ne sélectionne pas la dernière version lorsque le fuseau horaire de l’utilisateur est différent du fuseau horaire du serveur. (10190)
* Le raccourci Ctrl + F n’ouvre pas le modal de recherche du navigateur sur la console Ressources après l’installation d’AEM Guides 4.1 sur AEM 6.5.12. 10189


## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version as a Cloud Service de septembre 2022 de AEM Guides.


* La ligne de base dynamique n&#39;est pas intégrée à la publication de la base de connaissances.

* Traduction | L’icône de différence de version s’affiche pour le contenu source en raison d’une modification du contenu cible.
