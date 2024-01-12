---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans les guides Adobe Experience Manager, version de septembre 2023
description: Découvrez les correctifs et comment mettre à niveau vers la version de septembre 2023 de Adobe Experience Manager Guides as a Cloud Service
exl-id: 795b86a0-e763-404a-a4bb-35d3d2a42672
feature: Release Notes
role: Leader
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 0%

---

# Version de septembre 2023 des Guides Adobe Experience Manager as a Cloud Service

Cette note de mise à jour traite des instructions de mise à niveau, de la matrice de compatibilité et des problèmes résolus dans la version de septembre 2023 des Guides Adobe Experience Manager (ultérieurement appelée *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version de septembre 2023 d’AEM Guides as a Cloud Service](whats-new-2023.9.0.md).

## Mise à niveau vers la version de septembre 2023

Mettez à niveau votre configuration as a Cloud Service actuelle AEM Guides en procédant comme suit :

1. Extrayez le code Git des Cloud Service et passez à la branche configurée dans le pipeline Cloud Service correspondant à l’environnement que vous souhaitez mettre à niveau.
2. Mettre à jour `<dox.version>` dans `/dox/dox.installer/pom.xml` du code Git Cloud Service vers la version 2023.9.0.359.
3. Validez les modifications et exécutez le pipeline Cloud Service pour effectuer la mise à niveau vers la version de septembre 2023 d’AEM Guides as a Cloud Service.

## Procédure d’activation du déclencheur d’un script via un servlet

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 d’AEM Guides as a Cloud Service)

Une fois l’installation terminée, vous pouvez choisir d’ACCÉDER au déclencheur pour lancer la tâche de traduction :

POST :

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

Dans la réponse précédente JSON, la clé `lockNodePath` contient le chemin d’accès au noeud créé dans le référentiel pointant vers la tâche envoyée. Il sera automatiquement supprimé une fois la tâche terminée. Vous pourrez alors vous référer à ce noeud pour connaître l’état actuel de la tâche.

Patientez jusqu’à ce que cette tâche soit terminée avant de passer aux étapes suivantes.

>[!NOTE]
>
> Vérifiez si le noeud est toujours présent et l’état de la tâche.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Étapes de post-traitement du contenu existant pour utiliser le rapport de lien rompu

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 d’AEM Guides as a Cloud Service)

Effectuez les étapes suivantes pour le post-traitement du contenu existant et l’utilisation du nouveau rapport de lien rompu :

1. (Facultatif) Si le système contient plus de 100 000 fichiers dita, mettez à jour la variable `queryLimitReads` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` à une valeur plus élevée (toute valeur supérieure au nombre de ressources présentes, par exemple 200 000), puis redéployez.

   - Suivez les instructions de la section *Remplacements de configuration* dans la section Installation et configuration de Adobe Experience Manager Guides as a Cloud Service pour créer le fichier de configuration.
   - Dans le fichier de configuration, fournissez les détails (propriété) suivants pour configurer l’option queryLimitReads :

     | PID | Clé de propriété | Valeur de la propriété |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valeur : 200000 Valeur par défaut : 100000 |

1. Exécutez une requête de POST sur le serveur (avec l’authentification correcte) - `http://<server:port>//bin/guides/reports/upgrade`.

1. L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison : `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Une fois la tâche terminée, la requête de GET précédente répond avec succès. Si la tâche échoue pour une raison quelconque, l’échec peut être visible à partir des journaux du serveur.

1. Revenir à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifié à l’étape 1.

## Étapes pour indexer le contenu existant afin d’utiliser la nouvelle liste de rubrique et de recherche sous l’onglet Rapports :

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 d’AEM Guides as a Cloud Service)

Effectuez les étapes suivantes pour indexer le contenu existant et utilisez le nouveau texte de recherche et de remplacement au niveau de la carte et de la liste des rubriques sous l’onglet rapports :

1. Exécutez une requête de POST sur le serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des cartes pour les indexer ; par défaut, toutes les cartes seront indexées \|\| Par exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. Vous pouvez également transmettre un dossier racine pour indexer les mappages DITA d’un dossier spécifique (et de ses sous-dossiers). Par exemple, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Notez que si les paramètres paths et root sont transmis, seul le paramètre paths est pris en compte.

1. L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison : `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Une fois la tâche terminée, la requête de GET précédente répond avec succès et indique si une correspondance a échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par AEM Guides as a Cloud Service de septembre 2023.

### FrameMaker et FrameMaker Publishing Server

| AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.09.0 | Non compatible | 2022 ou version ultérieure |
| | | |


### Connecteur Oxygen

| AEM Guides as a Cloud | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.09.0 | 3.1-uuid 17 | 3.1-uuid 17 | 2,3 | 2,3 |
|  |  |  |  |


### Version du modèle de base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| AEM Guides Components Content Package pour Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :

### Création

- Le fichier de rubrique n’est pas déverrouillé dans l’éditeur web, bien que les options Déverrouiller le fichier et Ne pas enregistrer soient sélectionnées. 12558
- Impossible d’extraire un fichier dans l’éditeur web, bien que vous ayez choisi l’option NON pour ignorer les modifications avant l’archivage. (12557)
- Les info-bulles des icônes Verrouiller et déverrouiller le fichier dans la barre d’outils principale de l’éditeur web ne sont pas cohérentes avec les icônes affichées dans la vue Repository.12555
- L’option Annuler l’extraction et Déverrouiller s’affiche pour un fichier dans l’éditeur web qui n’est pas encore extrait en mode Carte. 12556
- Impossible de sélectionner les ressources du PDF dans les liens &quot;topicref&quot; existants. (12477)
- Dans la vue Repository, les rubriques ou les images ne peuvent pas être glissées après l’utilisation de la fonctionnalité Search/Filter . (12396)
- Les résultats de recherche sont désactivés dans le panneau Rechercher et remplacer après l’ouverture d’un fichier de recherche. (12142)
- La touche numérique &quot;8&quot; du clavier latéral ne fonctionne pas dans l’éditeur AEM Guides. (12106)

- Le préfixe est dupliqué en mode d’aperçu de l’éditeur web. (13133)
- `Choicetable` les lignes ne s’affichent pas ou ne peuvent pas être sélectionnées. (12616)
- L’éditeur web renvoie des erreurs de validation dans des scénarios spécifiques lors de la création d’une rubrique à l’aide d’un schéma personnalisé. (12576)
- Les références de modèle de rubrique différentielle ne créent pas de copie dans le dossier de contenu lors de la création d’un mappage à partir du modèle de mappage. (12150)
- La zone de recherche dans les mappages DITA ne comporte pas de bouton de fermeture. (11867)
- Lors de l’enregistrement de fichiers longs dans l’éditeur Web, `DirtyChecker` renvoie une exception avec une longue trace de pile et remplit les fichiers journaux. (11860)
- La création de rubriques DITA nécessite l’autorisation Supprimer sur le noeud de dossier correspondant, bien que le mappage puisse être créé avec l’autorisation En écriture. (11706)
- L’éditeur web affiche un titre incorrect lorsqu’une barre oblique est présente. (10949)


### Gestion

- Le champ &quot;titre&quot; des propriétés de métadonnées de mappage DITA est remplacé par `<title>` pour la carte. 10702
- La référence au contenu est un fichier DITA copié-collé rompu lorsque l’ID de rubrique n’est pas identique au GUID. (12614)
- Dans les lignes de base dynamiques, la liste des libellés n’est pas extraite des références directes de la copie de travail d’un mappage DITA. (1917)

### Publication

- La publication échoue lors du changement du nom d’un paramètre prédéfini de PDF natif. 12564
- La duplication d’un modèle de PDF natif duplique l’emplacement du modèle par défaut au lieu de l’emplacement du modèle personnalisé fourni. 12563

- PDF natif | L’inclusion de plusieurs expressions étend le texte au-delà de la largeur de colonne. 13004
- PDF natif | Lorsque la rubrique et le titre ont le même ID, cela entraîne une génération incorrecte de la sortie du PDF. 12644
- PDF natif | Lors de l’ajout d’une classe sortante à un parent `<topicref>` dans un mappage DITA et en appliquant un style personnalisé à la classe outputclass, le style est appliqué aux éléments du corps de la rubrique, y compris les titres des sections.(12166)
- La publication incrémentielle ne fonctionne pas si un mappage DITA comporte plusieurs attributs ditavalrefs. (12117)
- AEM site | Lors de la création d’un mappage avec keydef pointant vers une rubrique en tant que variable, l’ajout de processing-role=resource-only crée des pages inattendues. (12099)
- Si des ressources de la gestion des ressources numériques d’AEM sont utilisées dans une sortie autre que le site AEM, les métadonnées &quot;jcr:createdBy&quot; ne reflètent pas le nom de l’éditeur ou le nom de l’utilisateur qui a modifié la dernière fois le mappage ou la rubrique DITA. (12090)
- AEM Sites | Le mappage DITA avec le titre de la topique dans le titre de navigation (avec des caractères non pris en charge) entraîne des URL de page incorrectes. (1978)
- PDF natif | Des problèmes se produisent pour la prise en charge de topichead/topicmeta/navtitle dans les sections Frontmatter et Backmatter. (1969)
- PDF natif | La génération de PDF pour les documents volumineux prend du temps. (11955)
- PDF natif | Le changement de nom d’un paramètre prédéfini renvoie une exception NullPointerException lors de la génération d’une sortie de PDF. (11889)
- La variable `<conref>` le contenu n’est pas affiché dans la sortie du PDF. (11131)
- Un espace supplémentaire est ajouté dans la variable `<div>` éléments sur le basculement entre les vues Auteur et Source dans l’éditeur de mise en page. 10750
- Le contenu répliqué sur AEM Cloud Manager n’est pas visible sur l’instance de publication. (9564)

### Traduction

- Le processus d’exportation d’une ligne de base renommée pour une traduction échoue. (12993)
- Le titre du fichier traduit est affiché à la place du titre du fichier source. (11630)
