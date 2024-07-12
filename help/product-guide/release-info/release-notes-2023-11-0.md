---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans Adobe Experience Manager Guides, version de novembre 2023
description: Découvrez les correctifs et comment effectuer la mise à niveau vers la version de novembre 2023 d’Adobe Experience Manager Guides as a Cloud Service
exl-id: 80839890-075f-4187-a167-444c73215496
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1673'
ht-degree: 0%

---

# Version de novembre 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cette note de mise à jour traite des instructions de mise à niveau, de la matrice de compatibilité et des problèmes résolus dans la version de novembre 2023 d’Adobe Experience Manager Guides as a Cloud Service (appelée ultérieurement *Experience Manager Guides as a Cloud Service*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, consultez la section [Nouveautés de la version de novembre 2023 d’Experience Manager Guides as a Cloud Service](whats-new-2023-11-0.md).

## Mise à niveau vers la version de novembre 2023

Mettez à niveau votre configuration Experience Manager Guides as a Cloud Service actuelle en procédant comme suit :

1. Extrayez le code Git des Cloud Service et passez à la branche configurée dans le pipeline Cloud Service correspondant à l’environnement que vous souhaitez mettre à niveau.
2. Mettez à jour la propriété `<dox.version>` dans le fichier `/dox/dox.installer/pom.xml` de votre code Git Cloud Service vers 2023.11.0.406.
3. Validez les modifications et exécutez le pipeline Cloud Service pour effectuer la mise à niveau vers la version de novembre 2023 de Experience Manager Guides as a Cloud Service.

## Procédure d’activation du déclencheur d’un script via un servlet

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 de Experience Manager Guides as a Cloud Service)

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

Dans la réponse précédente JSON, la clé `lockNodePath` contient le chemin d’accès au noeud créé dans le référentiel pointant vers la tâche envoyée. Il sera automatiquement supprimé une fois la tâche terminée. Vous pouvez alors vous référer à ce noeud pour connaître le statut de la tâche.

Patientez jusqu’à ce que cette tâche soit terminée avant de passer aux étapes suivantes.

>[!NOTE]
>
> Vérifiez si le noeud est toujours présent et l’état de la tâche.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Étapes de post-traitement du contenu existant pour utiliser le rapport de lien rompu

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 de Experience Manager Guides as a Cloud Service)

Effectuez les étapes suivantes pour post-traiter le contenu existant et utiliser le nouveau rapport de lien rompu :

1. (Facultatif) S’il existe plus de 100 000 fichiers DITA dans le système, mettez à jour les `queryLimitReads` et `queryLimitInMemory` sous `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` vers une valeur plus grande (toute valeur supérieure au nombre de ressources présentes, par exemple 200 000), puis redéployez.

   - Suivez les instructions de la section *Remplacements de configuration* dans Installation et configuration de l’as a Cloud Service Adobe Experience Manager Guides pour créer le fichier de configuration.
   - Dans le fichier de configuration, fournissez les détails (propriété) suivants pour configurer l’option `queryLimitReads` et `queryLimitInMemory` :

     | PID | Clé de propriété | Valeur de la propriété |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valeur : 200000 Valeur par défaut : 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Valeur : 200000 Valeur par défaut : 100000 |

1. Exécutez une requête de POST sur le serveur (avec l’authentification correcte) - `http://<server:port>//bin/guides/reports/upgrade`.

1. L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Une fois la tâche terminée, la requête de GET précédente répond avec succès. Si la tâche échoue pour une raison quelconque, l’échec est visible à partir des journaux du serveur.

1. Revenez à la valeur existante par défaut ou précédente de `queryLimitReads` si vous l’avez modifiée à l’étape 1.

## Étapes pour indexer le contenu existant afin d’utiliser la nouvelle liste de rubrique et de recherche sous l’onglet Rapports :

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 de Experience Manager Guides as a Cloud Service)

Effectuez les étapes suivantes pour indexer le contenu existant et utilisez le nouveau texte de recherche et de remplacement au niveau de la carte et de la liste des rubriques sous l’onglet rapports :

1. Exécutez une requête de POST sur le serveur (avec l’authentification correcte) - `http://<server:port>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des cartes pour les indexer ; par défaut, toutes les cartes seront indexées. || Par exemple : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

1. Vous pouvez également transmettre un dossier racine pour indexer les mappages DITA d’un dossier spécifique (et de ses sous-dossiers). Par exemple, `http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test`. Notez que si les paramètres paths et root sont transmis, seul le paramètre paths est pris en compte.

1. L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`)


1. Une fois la tâche terminée, la requête de GET précédente répond avec succès et indique si une correspondance a échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Procédure de gestion du conflit `'fmdita rewriter'`

Experience Manager Guides dispose d’un module [**de réécriture sling personnalisée**](../cs-install-guide/conf-output-generation.md#custom-rewriter) pour gérer les liens générés en cas de mappage croisé (liens entre les rubriques de deux cartes différentes).

Si votre code base comporte un autre module de réécriture sling personnalisé, utilisez une valeur `'order'` supérieure à 50, car Experience Manager Guides sling rewriter utilise `'order'` 50.  Pour le remplacer, vous devez disposer d’une valeur supérieure à 50. Pour plus d’informations, voir [ Pipelines de réécriture de sortie](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Pendant cette mise à niveau, puisque la valeur `'order'` est passée de 1000 à 50, vous devez fusionner le module de réécriture personnalisé existant, le cas échéant, avec `'fmdita-rewriter'`.


## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par Experience Manager Guides as a Cloud Service en novembre 2023.

### FrameMaker et FrameMaker Publishing Server

| Guides Experience Manager Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.11.0 | Non compatible | 2022 ou version ultérieure |
| | | |


### Connecteur Oxygen

| Version de Experience Manager Guides as a Cloud | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.11.0 | 3.2-uuid 5 | 3.2-uuid 5 | 2,3 | 2,3 |
|  |  |  |  |


### Version du modèle de base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu des composants Experience Manager Guides pour Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :



### Création

- L’espace après l’élément `<ph>` de référence disparaît lors de l’enregistrement de la rubrique. 13642
- Une erreur d’application se produit lors de la tentative d’enregistrement des fichiers DITA avant la fin du post-traitement. 13571
- Si le titre d’une rubrique contient une barre oblique `/`, l’onglet de l’éditeur n’affiche que les lettres qui lui succèdent. (13455)
- L’aperçu de l’image ne disparaît pas après l’affichage de l’aperçu dans l’éditeur. (13454)
- La fenêtre contextuelle Insérer un mot-clé n’apparaît pas lors de l’utilisation de clés définies par la carte racine dans d’autres rubriques. (12950)
- Les icônes de fermeture ne sont pas visibles lorsque de très grands graphiques sont prévisualisés dans le panneau Historique de version . (12867)
- Impossible de modifier le fuseau horaire de la colonne **Version créée le** pour les lignes de base. (12711)
- Le panneau **Historique de version** de l’interface utilisateur d’Assets affiche un horodatage incorrect pour le champ **Actuel**. 12624
- La création d’un fichier DITA à partir d’un modèle dont le nom commence par des caractères numériques entraîne une erreur d’espace de noms. (12188)
- Dans l’éditeur Web, la fenêtre **Références clés** s’ouvre lors de l’insertion de la balise `varname`. (10940)
- Les fichiers ZIP ne sont pas reconnus dans l’éditeur web et vous ne pouvez pas les faire glisser et les déposer. 12709
- Le contenu auquel certains attributs sont appliqués n’est pas mis en surbrillance en mode création ou aperçu. (11063)
- Lorsque vous fermez une rubrique après l’avoir modifiée, vous êtes redirigé vers la page d’accueil AEM au lieu de revenir à la vue du dossier. (13306)
- Le délai survient lors du post-traitement des fichiers qui ont été copiés et collés dans les services cloud. (12457)
- Le paramètre rootmap persiste dans l’éditeur web même si l’utilisateur ne l’a pas défini explicitement à partir des préférences utilisateur. (11551)


### Publication

- La fonctionnalité Publish en tant que fragment de contenu ne fonctionne pas pour les fichiers répertoriés dans les résultats de recherche. (14090)
- Dans la publication avec un PDF natif, la sélection de couleur d’arrière-plan sur la mise en page du modèle nécessite un rechargement de page lors du rétablissement vers `None`. 13621
- Problème lors de la validation de la banque de données pour un mappage DITA volumineux avec des liens de portée par rapport à la publication d’AEM site. (13530)
- Dans la publication avec un PDF natif, l’accessibilité est compromise, car les images dans l’en-tête et le pied de page n’affichent pas de texte secondaire. (12829)
- La duplication de la mise en page dans le PDF natif ne fonctionne pas si aucune extension n’est ajoutée automatiquement. 12534
- Lors de la génération de la sortie du PDF avec la publication d’un PDF natif, le nom de fichier est tronqué après un point. (13620)
- Une icône et une info-bulle incorrectes s’affichent pour l’option **Modifier le contenu** dans la barre d’outils des mises en page des modèles utilisés dans la publication avec les PDF natifs. 13492
- Les métadonnées personnalisées ne sont pas disponibles dans la sortie finale. (12116)
- fmdita rewriter entre en conflit avec la configuration de réécriture de l’utilisateur et entraîne l’affichage de longues URL au lieu des liens. (12076)
- Dans le paramètre prédéfini AEM site, l’option **Générer un PDF distinct pour chaque rubrique** n’est pas fonctionnelle. (11555)
- La publication de PDF natif ne prend pas en charge la conversion de l’espace colorimétrique CMJN. 10754)
- Les appels de ligne de base dynamiques utilisent le nom plutôt que le titre, ce qui entraîne l’échec de l’API de mappage d’exportation DITA. (14268)

### Gestion

- La référence au contenu est rompue lors du copier-coller des fichiers DITA comportant des liens d’auto-référence sans GUID. (13540)
- Dans l’éditeur Web, la ligne de base affiche le titre de la version précédente au lieu de la version sélectionnée du fichier DITA. (13444)
- L’onglet **Rapports** de l’interface utilisateur de l’éditeur web n’affiche pas la liste des rubriques pour les anciens mappages DITA créés avant la mise à niveau de Experience Manager Guides as a Cloud Service en juillet 2023. (11852)
- Les paramètres prédéfinis de condition pour une carte DITA volumineuse ne sont pas créés. 10936
- Un lien d’auto-référence s’affiche sous la liste des liens rompus dans les rapports. 13539)

### Révision

- Les panneaux de révision côte à côte des versions précédentes et actuelles de l’éditeur web ne sont pas corrects dans la version d’octobre 2023 d’Experience Manager Guides as a Cloud Service. (14156)
- La personnalisation du modèle de courrier électronique pour le workflow **Révision** ne fonctionne pas avec le recouvrement des noeuds. (13954)
- Le bouton **Fermer** de la page Révision de Experience Manager Guides permet d’accéder à la page d’accueil d’AEM. 13535)
- Des caractères rompus apparaissent lors de la création des fragments de code en coréen. 13489
- Il n’est pas possible de cliquer sur les pièces jointes coréennes dans l’écran de révision de Experience Manager Guides. (13436)
- Le titre de la carte est coupé dans l’écran de révision et de collaboration, sans possibilité d’afficher le titre complet. (13012)

### Traduction

- L’approbation automatique ne fonctionne pas parfois et des exceptions se produisent si une valeur incorrecte est définie sur **État de traduction**. (13607)
- La ligne de base exportée à partir du tableau de bord Traduction échoue et ne s’ouvre pas dans la langue cible. (12993)

## Problème connu

Adobe a identifié le problème connu suivant pour la version de novembre 2023.

- La régénération sélective de rubrique pour AEM sortie de site échoue.
