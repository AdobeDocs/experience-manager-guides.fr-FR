---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans Adobe Experience Manager Guides, version de septembre 2023
description: Découvrez les correctifs et comment effectuer la mise à niveau vers la version de septembre 2023 d’Adobe Experience Manager Guides as a Cloud Service
exl-id: 795b86a0-e763-404a-a4bb-35d3d2a42672
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1485'
ht-degree: 0%

---

# Version de septembre 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cette note de mise à jour couvre les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans la version de septembre 2023 d’Adobe Experience Manager Guides (plus tard appelée *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version de septembre 2023 d’AEM Guides as a Cloud Service](whats-new-2023-9-0.md).

## Mise à niveau vers la version de septembre 2023

Mettez à niveau votre configuration AEM Guides as a Cloud Service actuelle en procédant comme suit :

1. Consultez le code Git des services cloud et passez à la branche configurée dans le pipeline des services cloud correspondant à l’environnement à mettre à niveau.
2. Mettez à jour `<dox.version>` propriété dans `/dox/dox.installer/pom.xml` fichier de votre code Git Cloud Services sur 2023.9.0.359.
3. Validez les modifications et exécutez le pipeline Cloud Services pour effectuer la mise à niveau vers la version de septembre 2023 d’AEM Guides as a Cloud Service.

## Procédure d’activation du déclenchement d’un script via une servlet

(Uniquement si vous utilisez une version d’AEM Guides as a Cloud Service antérieure à la version de juin 2023)

Une fois l’installation terminée, vous pouvez choisir d’APPUYER sur le déclencheur pour démarrer la tâche de traduction :

PUBLICATION :

```
http://localhost:4503/bin/guides/script/start?jobType=translation-map-upgrade
```

Réponse :

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/translation-map-upgrade/1683190032886",
"status": "SCHEDULED"
}
```

Dans la réponse précédente JSON, la clé `lockNodePath` contient le chemin d’accès au nœud créé dans le référentiel pointant vers la tâche envoyée. Elle sera automatiquement supprimée une fois le traitement terminé. En attendant, vous pouvez vous référer à ce nœud pour connaître le statut actuel du traitement.

Patientez jusqu’à ce que ce traitement soit terminé avant de passer aux étapes suivantes.

>[!NOTE]
>
> Vous devez vérifier si le nœud est toujours présent, ainsi que le statut de la tâche.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Étapes de post-traitement du contenu existant pour utiliser le rapport de lien rompu

(Uniquement si vous utilisez une version d’AEM Guides as a Cloud Service antérieure à la version de juin 2023)

Effectuez les étapes suivantes pour post-traiter le contenu existant et utiliser le nouveau rapport de lien rompu :

1. (Facultatif) S’il existe plus de 100 000 fichiers dita dans le système, mettez à jour le `queryLimitReads` sous `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` avec une valeur plus élevée (toute valeur supérieure au nombre de ressources présentes, par exemple 200 000), puis redéployez.

   - Suivez les instructions de la section *Remplacements de configuration* dans Installation et configuration d’Adobe Experience Manager Guides.
as a Cloud Service, pour créer le fichier de configuration.
   - Dans le fichier de configuration, fournissez les détails (propriété) suivants pour configurer l’option queryLimitReads :

     | PID | Clé de la propriété | Valeur de la propriété |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valeur : 200000 Valeur par défaut : 100000 |

1. Exécutez une requête POST au serveur (avec l’authentification correcte) - `http://<server:port>//bin/guides/reports/upgrade`.

1. L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée : `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Une fois le traitement terminé, la requête GET précédente répond avec succès. Si le traitement échoue pour une raison quelconque, l’échec est visible dans les journaux du serveur.

1. Revenez à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifiée à l’étape 1.

## Procédure à suivre pour indexer le contenu existant afin d’utiliser la nouvelle liste de recherche et de remplacement et de rubriques sous l’onglet Rapports :

(Uniquement si vous utilisez une version d’AEM Guides as a Cloud Service antérieure à la version de juin 2023)

Effectuez les étapes suivantes pour indexer le contenu existant et utiliser le nouveau texte rechercher et remplacer au niveau du mappage et de la liste de rubriques sous l’onglet rapports :

1. Exécutez une requête POST au serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des mappages pour les indexer. Par défaut, tous les mappages sont indexés \|\| Par exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. Vous pouvez également transmettre un dossier racine pour indexer les plans DITA d&#39;un dossier spécifique (et de ses sous-dossiers). Par exemple, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Notez que si le paramètre de chemins d’accès et le paramètre racine sont transmis, seul le paramètre de chemins d’accès est pris en compte.

1. L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée : `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\).


1. Une fois la tâche terminée, la requête GET précédente répond avec succès et mentionne si des mappages ont échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par la version de septembre 2023 d’AEM Guides as a Cloud Service.

### FrameMaker et FrameMaker Publishing Server

| Version d’AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.09.0 | Non compatible | 2022 ou version ultérieure |
| | | |


### Connecteur D&#39;Oxygène

| Version d’AEM Guides as a Cloud | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.09.0 | 3.1-uuid 17 | 3.1-uuid 17 | 2,3 | 2,3 |
|  |  |  |  |  |


### Version du modèle de la base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu de composants AEM Guides pour Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problèmes résolus

Les bogues corrigés dans différentes zones sont répertoriés ci-dessous :

### Création

- Le fichier rubrique n&#39;est pas déverrouillé dans l&#39;éditeur Web, bien que les options Déverrouiller le fichier et Ne pas enregistrer soient sélectionnées. (12558)
- Impossible d&#39;extraire un fichier dans l&#39;éditeur Web, bien que vous ayez choisi l&#39;option NON pour ignorer les modifications avant l&#39;archivage. (12557)
- Les info-bulles des icônes Verrouiller et Déverrouiller le fichier dans la barre d’outils principale de l’éditeur web ne sont pas cohérentes avec les icônes affichées dans la vue Référentiel.(12555)
- L&#39;option Annuler l&#39;extraction et Déverrouiller s&#39;affiche pour un fichier dans l&#39;éditeur Web qui n&#39;est pas encore extrait en mode Carte. (12556)
- Impossible de sélectionner les ressources PDF dans les liens « topicref » existants. (12477).
- Dans la vue Référentiel, les rubriques ou images ne peuvent pas être déplacées après avoir utilisé la fonctionnalité Rechercher/Filtrer. (12396)
- Les résultats de la recherche sont désactivés dans le panneau Rechercher et remplacer après l’ouverture d’un fichier recherché. (12142)
- La touche numérique « 8 » du clavier latéral ne fonctionne pas dans l’éditeur d’AEM Guides. (12106)

- Le préfixe est dupliqué dans le mode d’aperçu de l’éditeur web. (13133)
- `Choicetable` lignes ne sont pas affichées ou ne peuvent pas être sélectionnées. (12616)
- L’éditeur web renvoie des erreurs de validation dans des scénarios spécifiques lors de la création d’une rubrique à l’aide d’un schéma personnalisé. (12576)
- Les références au modèle de rubrique de dictionnaire ne créent pas de copie dans le dossier de contenu lors de la création d’un mappage à partir du modèle de mappage. (12150)
- La zone de recherche dans les plans DITA ne comporte pas de bouton Fermer. (11867)
- Lors de l’enregistrement de fichiers longs dans l’éditeur web, `DirtyChecker` renvoie une exception avec une longue trace de pile et remplit les fichiers journaux. (11860)
- La création de rubriques DITA requiert l&#39;autorisation Supprimer sur le nœud de dossier correspondant, bien que le mappage puisse être créé avec l&#39;autorisation Écriture. (11706)
- Web Editor affiche un titre incorrect en présence d’une barre oblique. (10949)


### Gestion

- Le champ « title » des propriétés de métadonnées de plan DITA est remplacé par `<title>` élément pour le plan. (10702)
- La référence au contenu consiste à copier-coller des fichiers DITA rompus lorsque l&#39;ID de rubrique est différent du GUID. (12614)
- Dans les références dynamiques, la liste des libellés n&#39;est pas extraite des références directes de la copie de travail d&#39;un plan DITA. (11917)

### Publication

- La publication échoue lors du changement du nom d’un paramètre prédéfini de PDF natif. (12564)
- La duplication d’un modèle PDF natif duplique l’emplacement du modèle par défaut au lieu de l’emplacement du modèle personnalisé fourni. (12563)

- PDF natif | L’inclusion de plusieurs xréfs étend le texte au-delà de la largeur de colonne. (13004)
- PDF natif | Lorsque la rubrique et le titre ont le même ID, cela entraîne une génération incorrecte de la sortie PDF. (12644)
- PDF natif | Lors de l&#39;ajout d&#39;une classe outputclass à un élément `<topicref>` parent dans un plan DITA et de l&#39;application d&#39;un style personnalisé à la classe outputclass, le style est appliqué aux éléments du corps de la rubrique, y compris les titres de section.(12166)
- La publication incrémentielle ne fonctionne pas si un plan DITA comporte plusieurs variables DITA. (12117)
- Site AEM | Lors de la création d’une carte avec keydef pointant vers un topic en tant que variable et en ajoutant processing-role=resource-only, certaines pages sont inattendues. (12099)
- Si des ressources de la gestion des ressources numériques d’AEM sont utilisées dans une sortie autre que le site AEM, alors le « jcr :createdBy » des métadonnées ne reflète pas le nom de l’éditeur ou de l’utilisateur qui a effectué la dernière modification du plan ou de la rubrique DITA. (12090)
- AEM Sites | Un plan DITA avec topichead dans le titre de la navigation (avec des caractères non pris en charge) génère des URL de page incorrectes. (11978)
- PDF natif | Des problèmes se produisent à l’appui de topichead / topicmeta / navtitle dans FrontMATTER et BackMATTER. (11969)
- PDF natif | La génération de PDF pour les documents volumineux prend du temps. (11955)
- PDF natif | Le changement de nom d’un préréglage renvoie une exception NullPointerException lors de la génération d’une sortie PDF. (11889)
- Le contenu `<conref>` ne s’affiche pas dans la sortie PDF. (11131)
- Un espace supplémentaire est ajouté dans les éléments `<div>` lors du basculement entre la vue Auteur et Source dans l’éditeur de mise en page. (10750)
- Le contenu répliqué sur AEM Cloud Manager n’est pas visible sur l’instance de publication. (9564)

### Traduction

- Le processus d’exportation d’une ligne de base renommée pour une traduction échoue. (12993)
- Le titre du fichier traduit s’affiche à la place du titre du fichier source. (11630)
