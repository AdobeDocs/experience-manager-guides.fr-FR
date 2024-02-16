---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans les guides Adobe Experience Manager, version de février 2024
description: Découvrez les correctifs de bogues et comment mettre à niveau vers la version de février 2024 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1311'
ht-degree: 1%

---

# Version de février 2024 des Guides Adobe Experience Manager as a Cloud Service

Cette note de mise à jour traite des instructions de mise à niveau, de la matrice de compatibilité et des problèmes résolus dans la version de février 2024 des Guides Adobe Experience Manager as a Cloud Service (appelée ultérieurement *Guides du Experience Manager as a Cloud Service*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version de février 2024 des Guides Experience Manager as a Cloud Service](whats-new-2024-02-0.md).

## Mise à niveau vers la version de février 2024

Mettez à niveau votre configuration as a Cloud Service actuelle des guides de Experience Manager en procédant comme suit :

1. Extrayez le code Git des Cloud Service et passez à la branche configurée dans le pipeline Cloud Service correspondant à l’environnement que vous souhaitez mettre à niveau.
2. Mettre à jour `<dox.version>` dans `/dox/dox.installer/pom.xml` du code Git Cloud Service vers la version 2024.02.0.15.
3. Validez les modifications et exécutez le pipeline Cloud Service pour effectuer la mise à niveau vers la version de février 2024 des Guides Experience Manager as a Cloud Service.

## Procédure d’activation du déclencheur d’un script via un servlet

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 de Guides de Experience Manager as a Cloud Service)

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

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 de Guides de Experience Manager as a Cloud Service)

Effectuez les étapes suivantes pour post-traiter le contenu existant et utiliser le nouveau rapport de lien rompu :

1. (Facultatif) Si le système contient plus de 100 000 fichiers DITA, mettez à jour la variable `queryLimitReads` et `queryLimitInMemory` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` à une valeur plus élevée (toute valeur supérieure au nombre de ressources présentes, par exemple 200 000), puis redéployez.

   - Suivez les instructions de la section *Remplacements de configuration* dans la section Installation et configuration de Adobe Experience Manager Guides as a Cloud Service pour créer le fichier de configuration.
   - Dans le fichier de configuration, fournissez les détails (propriété) suivants pour configurer la variable `queryLimitReads` et `queryLimitInMemory` option :

     | PID | Clé de propriété | Valeur de la propriété |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valeur : 200000 Valeur par défaut : 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Valeur : 200000 Valeur par défaut : 100000 |

1. Exécutez une requête de POST sur le serveur (avec l’authentification correcte) - `http://<server>//bin/guides/reports/upgrade`.

1. L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison : `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(Par exemple : `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Une fois la tâche terminée, la requête de GET précédente répond avec succès. Si la tâche échoue pour une raison quelconque, l’échec est visible à partir des journaux du serveur.

1. Revenir à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifié à l’étape 1.

## Étapes pour indexer le contenu existant afin d’utiliser la nouvelle liste de rubrique et de recherche sous l’onglet Rapports :

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 de Guides de Experience Manager as a Cloud Service)

Effectuez les étapes suivantes pour indexer le contenu existant et utilisez le nouveau texte de recherche et de remplacement au niveau de la carte et de la liste des rubriques sous l’onglet rapports :

1. Exécutez une requête de POST sur le serveur (avec l’authentification correcte) - `http://<server:port>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des cartes pour les indexer ; par défaut, toutes les cartes seront indexées|| Par exemple : `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison : `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(Par exemple : `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Une fois la tâche terminée, la requête de GET précédente répond avec succès. Si la tâche échoue pour une raison quelconque, l’échec peut être visible à partir des journaux du serveur.

1. Revenez à la valeur par défaut ou à la valeur existante précédente de queryLimitReads si vous l’avez modifiée à l’étape 1.

## Procédure de gestion de la variable `'fmdita rewriter'` conflit

Les guides du Experience Manager comportent une [**réécriture sling personnalisée**](../cs-install-guide/conf-output-generation.md#custom-rewriter) module de gestion des liens générés en cas de croix (liens entre les rubriques de deux cartes différentes).

Si votre code base comporte un autre module de réécriture sling personnalisé, utilisez une `'order'` valeur supérieure à 50, comme l’utilise le module de réécriture sling de Guides de Experience Manager `'order'` 50.  Pour le remplacer, vous devez disposer d’une valeur supérieure à 50. Pour plus d’informations, voir [Pipelines de réécriture de sortie](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Au cours de cette mise à niveau, depuis la variable `'order'` est modifiée de 1000 à 50, vous devez fusionner le module de réécriture personnalisé existant, le cas échéant, avec `'fmdita-rewriter'`.


## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par les Guides Experience Manager as a Cloud Service de février 2024.

### FrameMaker et FrameMaker Publishing Server

| Version de Experience Manager Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2024.02.0 | Non compatible | 2022 ou version ultérieure |
| | | |


### Connecteur Oxygen

| Version de Experience Manager Guides as a Cloud | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2024.02.0 | 3.1-uuid.17 | 3.1-uuid.17 | 2,3 | 2,3 |
|  |  |  |  |


### Version du modèle de base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Module de contenu des composants des guides du Experience Manager pour Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :

### Création

- La vérification orthographique dans l’éditeur n’autorise pas la sélection de suggestions. 15045
- Le bouton de navigation globale ne fonctionne pas et le tableau de bord ne se charge pas. (14968)
- Dans l’éditeur web, la fonction de mappage de téléchargement ne parvient pas à déclencher une notification contextuelle lorsqu’elle est prête à être téléchargée. 14626
- Dans l’éditeur web, la fonction de mappage de téléchargement ne parvient pas à télécharger un mappage avec la ligne de base. 14622
- Erreur DTD non valide dans la version as a Cloud Service 2310 des Guides du Experience Manager. (14482)
- Le fait de faire glisser une rubrique de glossaire du référentiel vers un mappage de glossaire crée `topicref`. 10767
- L’éditeur web est désinstallé après la réinstallation de Adobe Experience Manager Guides version 4.3.1. 14519)
- Le programme d’installation de la version 4.3.1 rencontre un conflit de filtre, ce qui entraîne le remplacement de `apps/cq/core/content/projects/properties`. (14517)
- L’écran d’aperçu des fragments de code est figé. (14840)

### Publication

- Dans la publication avec des PDF natifs, les attributs personnalisés dans les paramètres prédéfinis de condition ne fonctionnent pas pour la publication avec des PDF natifs. (14943)
- Impossible d’ajouter un modèle personnalisé à partir du **Sorties** dans l’éditeur. (14846)
- **AEM site** ne fonctionne pas en raison d’un chemin de modèle vide. (14804)
- La régénération AEM site échoue pour les mappages DITA avec des rubriques contenant des équations MathML. (14790)
- Dans la publication de PDF natifs, la génération de PDF génère des erreurs lors de l’obtention des dépendances pour `Node.js` publication. (14445)
- AEM paramètre prédéfini n’autorise pas la sélection d’un modèle en dehors de la fonction `/content` hiérarchie dans l’éditeur web. (14260)
- Dans la sortie AEM Sites, le style ou les sauts de ligne ont été perdus pour le `<lines>` élément comportant des sous-éléments .12542
- Les métadonnées personnalisées ne sont pas disponibles dans la sortie finale. (12116)
- Lors de la mise à niveau vers la version 4.3.1, certaines exceptions se produisent dans le noeud de PDF natif. (14492)


### Gestion

- **Filtre de ligne de base** Les fichiers ne fonctionnent pas avec le nom de fichier dans l’éditeur web. (13486)
- La désactivation de l’indexation du mappage DITA parent pour obtenir de meilleures performances peut avoir un impact sur les fonctionnalités de certaines fonctionnalités.(12213)
- Étiquettes des `labels.json` s’affichent dans un ordre aléatoire dans l’éditeur Web. 10508

### Révision

- Le menu contextuel du clic droit ne fonctionne pas pour **Accepter** ou **Rejeter** effectuer le suivi des modifications. (14607)
- Basculer pour fermer les rubriques DITA dans l’écran de révision ne fonctionne pas dans la version 4.3.1 des guides Adobe Experience Manager. (14537)
- La personnalisation des modèles de courrier électronique pour le processus de révision ne fonctionne pas avec la superposition. (13954)

## Problème connu

Adobe a identifié le problème connu suivant pour la version de février 2024 :

- La version 1.0 ne s’affiche pas dans l’interface utilisateur pour le fichier DITA dupliqué.
