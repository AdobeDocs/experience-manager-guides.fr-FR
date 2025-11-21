---
title: Notes de mise à jour | Adobe Experience Manager Guides as a Cloud Service, version de novembre 2022
description: Version de novembre d’Adobe Experience Manager Guides as a Cloud Service
exl-id: 9f329ec1-dd74-47cc-8567-3fadd962584a
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1383'
ht-degree: 0%

---

# Version de novembre d’Adobe Experience Manager Guides as a Cloud Service

## Mise à niveau vers la version de novembre

Mettez à niveau votre configuration Adobe Experience Manager Guides as a Cloud Service actuelle (ultérieurement appelée *AEM Guides as a Cloud Service*) en procédant comme suit :
1. Consultez le code Git des services cloud et passez à la branche configurée dans le pipeline des services cloud correspondant à l’environnement à mettre à niveau.
1. Mettez à jour `<dox.version>` propriété dans `/dox/dox.installer/pom.xml` fichier de votre code Git Cloud Services vers la version 2022.11.198.
1. Validez les modifications et exécutez le pipeline Cloud Services pour effectuer la mise à niveau vers la version de novembre d’AEM Guides as a Cloud Service.

## Procédure à suivre pour indexer le contenu existant (uniquement si vous utilisez une version antérieure à la version de septembre d’AEM Guides as a Cloud Service)

Effectuez les étapes suivantes pour indexer le contenu existant et utiliser le nouveau texte de recherche et de remplacement au niveau du mappage :

* Exécutez une requête POST au serveur (avec l’authentification correcte) - `http://<server:port>/bin/guides/map-find/indexing`.
(Facultatif) Vous pouvez transmettre des chemins spécifiques des mappages pour les indexer. Par défaut, tous les mappages sont indexés || Exemple : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée : `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Par exemple : http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Une fois la tâche terminée, la requête GET ci-dessus répond avec succès et mentionne si des mappages ont échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par la version de novembre 2022 d’AEM Guides as a Cloud Service.

### FrameMaker et FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Non compatible | Mise à jour 2020 4 et versions ultérieures |
| | |

*La ligne de base et les conditions créées dans AEM sont prises en charge dans les versions FMPS à compter de 2020.2.

### Connecteur D&#39;Oxygène

| Version d’AEM Guides as a Cloud | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2022.11.0 | 2,7,13 | 2,7,13 | 2,3 | 2,3 |
|  |  |  |  |  |


## Nouvelles fonctionnalités et améliorations

AEM Guides as a Cloud Service offre des améliorations et de nouvelles fonctionnalités dans la version de novembre :


### Supprimer des fichiers du panneau Référentiel

Vous pouvez désormais facilement supprimer des fichiers (un seul fichier à la fois) du menu **Options** du fichier sélectionné dans le panneau du référentiel.
<img src="assets/repository-delete-file.png" alt="Supprimer du référentiel" width="500">

Une invite de confirmation s’affiche avant la suppression du fichier. Si le fichier n’est pas référencé à partir d’un autre fichier, il est supprimé et un message de réussite s’affiche.

Si le fichier sélectionné est extrait, vous ne pouvez pas le supprimer et un message d&#39;erreur s&#39;affiche. Si le fichier sélectionné est ajouté à une collection de favoris ou s’il est référencé à partir d’un autre fichier, AEM guides vérifie votre confirmation et vous donne la possibilité de le supprimer de force. Si vous supprimez une rubrique référencée et que vous avez ouvert le fichier contenant les références pour le modifier, le lien rompu pour le fichier référencé s’affiche.

**Remarque** : vous pouvez également supprimer le fichier sélectionné à l’aide de la touche Supprimer du clavier.


### Purge des versions sélectionnées des fichiers

Au fur et à mesure que vous créez et conservez votre contenu, il se peut que de nombreuses versions soient créées pour vos fichiers DITA dans votre référentiel. AEM Guides vous permet de purger les anciennes versions de vos fichiers DITA du référentiel et de libérer de l’espace disque.

<img src="assets/preview-purge-report.png" alt="Aperçu du rapport de purge" width="500">


AEM Guides ne supprime pas la première version du fichier ou une version incluse dans une ligne de base, ou à laquelle un libellé est appliqué. L’opération de purge ne supprime même pas les fichiers inclus dans un workflow de traduction ou de révision. Vous pouvez choisir le nombre de versions à conserver et également décider de supprimer les fichiers qui sont plus anciens que le nombre de jours défini.

Avant de commencer la purge, vous pouvez prévisualiser le rapport pour afficher les versions qui seront purgées. Vous pouvez ensuite décider de démarrer ou d’annuler l’opération de purge.

<img src="assets/download-purge-report.png" alt="Télécharger le rapport de purge" width="500">

Une fois l’opération de purge terminée, vous pouvez vérifier le rapport de purge pour afficher les fichiers purgés.

### Gestion des paramètres prédéfinis de sortie de profil global et de dossier

AEM Guides permet de créer et de gérer des paramètres prédéfinis de sortie pour les profils globaux et de dossiers. Vous pouvez ensuite facilement utiliser ces paramètres prédéfinis de sortie pour générer une sortie pour tous les mappages liés à ce profil global ou de dossier.

<img src="assets/add-global-output-preset.png" alt="Ajouter un profil global" width="400">

**Remarque** seuls les utilisateurs administratifs au niveau du dossier peuvent créer des paramètres prédéfinis de profil global et de profil de dossier.

Ces paramètres prédéfinis globaux s’affichent sous l’onglet **Sortie** de tous les mappages associés. Vous pouvez les utiliser pour générer la sortie de tous les mappages associés. Vous pouvez sélectionner le paramètre prédéfini comme paramètre prédéfini PDF par défaut pour générer la sortie PDF. Vous pouvez également **Modifier**, **Renommer**, **Dupliquer** ou **Supprimer** un paramètre prédéfini de sortie existant à partir du menu **Options**.

### Colonne Libellé de version ajoutée au tableau de bord de traduction

Dans le tableau de bord de traduction, vous pouvez également voir la colonne Libellé de version . Le libellé de la version sélectionnée du fichier source s’affiche. Cela peut vous aider à sélectionner tous les fichiers avec un libellé spécifique et à les traduire en une seule fois.

<img src="assets/send-translation.png" alt="envoyer pour traduction" width="600">


### PDF natif | PDF avec barre de modification indiquant la différence entre les versions du document

Vous pouvez maintenant créer un PDF qui affiche les différences de contenu entre deux versions à l’aide de la barre de modification. Vous pouvez choisir de comparer la version actuelle à une version de référence de la version précédente ou de comparer les deux versions de référence sélectionnées.

<img src="assets/pdf-change-version.png" alt="spdf-change-version" width="600">

Une barre de modification s’affiche dans le PDF pour indiquer le contenu modifié, inséré ou supprimé. Vous avez également la possibilité d’effectuer les opérations suivantes :
* Afficher le contenu inséré en vert et souligné
* Afficher le contenu supprimé en rouge et barré

### PDF natif | Prise en charge des variables pour le chemin de sortie et le nom de fichier PDF

Vous pouvez désormais également utiliser les variables prêtes à l’emploi suivantes pour définir le chemin de sortie et le fichier PDF. Vous pouvez utiliser une seule variable ou une combinaison de variables pour définir ces options :
* `${map_filename}`
* `${map_title}`
* `${preset_name}`
* `${language_code}`
* `${map_parentpath}` (uniquement pour le chemin de sortie)
* `${path_after_langfolder}` (uniquement pour le chemin de sortie)


### PDF natif | Générer la table des matières pour les plans DITA et réorganiser les mises en page

Vous pouvez désormais générer la table des matières dans les plans DITA à l&#39;aide d&#39;un paramètre PDF avancé du modèle. Vous pouvez choisir d’activer ou de désactiver l’affichage des différentes mises en page et de réorganiser leur position.

## Problèmes résolus

Les bogues corrigés dans différentes zones sont répertoriés ci-dessous :

* PDF natif | `conkeyref` n’est pas résolu dans la sortie PDF générée. (10564)
* PDF natif | Des problèmes se produisent lors de l’accès aux métadonnées d’un mappage dans la sortie PDF. (10556)
* PDF natif | Les styles intégrés sont utilisés pour générer des balises au lieu du nom de classe.  (10498)
* L’éditeur web charge une page vierge par intermittence. (10678)
* La publication PDF échoue si nous créons un paramètre prédéfini en dupliquant un paramètre prédéfini existant. (10584)
* Le bouton **Afficher le journal** ne fonctionne pas lorsque la génération PDF échoue pour un préréglage. (10576)
* Notez qu’une balise para qui est une conref ne s’affiche pas dans l’aperçu. (10559)
* Appuyer sur la touche Retour arrière à la fin d’un élément de liste supprime la liste entière. (10540)
* Lors de l’utilisation d’une exportation PDF native, les `<indexterm>` imbriqués ne sont pas imbriqués dans l’index. (10521)
* Le bouton **Retrait automatique** de la barre d’outils n’apparaît pas dans la vue Source. (10448)
* Le premier caractère d’un élément de liste est perdu pendant la création de la liste dans l’éditeur. (10447)
* Plusieurs fenêtres contextuelles s&#39;affichent si une version de ressource DITA est modifiée et enregistrée dans la fenêtre de modification de ligne de base. (10399)
* Une erreur d’application se produit en cliquant sur le bouton **Modifier** après avoir sélectionné tous les paramètres prédéfinis de sortie dans le panneau Génération rapide. (10388)
* Les métadonnées personnalisées de la rubrique DITA ne sont pas conservées lorsqu&#39;une action de copier-coller est effectuée à partir de l&#39;interface utilisateur d&#39;Assets. (10367)
* Le post-traitement est bloqué pour l’ensemble du dossier de langue dont les ressources sont présentes dans un projet de traduction actif. (10332)
* L’onglet Modèle dans l’éditeur XML n’est pas visible par les administrateurs de profils de dossiers. (10266)
* Des problèmes de navigation se produisent dans l’éditeur web après la mise à niveau vers la version 4.0. (10159)
* Les fichiers SVG ne s’affichent pas en mode Aperçu . (10010)
* Si l’onglet Sortie de l’éditeur contient d’autres paramètres prédéfinis, la section Paramètres prédéfinis ne peut pas faire défiler l’écran et tous les paramètres prédéfinis ne s’affichent pas. (9787)
* Les options **Modifier** et **Annoter** d’une image ne fonctionnent pas correctement en mode Colonnes. (8758)
* Le lien d’homologue n’est pas résolu et apparaît comme un texte normal dans la sortie générée. (7774)
