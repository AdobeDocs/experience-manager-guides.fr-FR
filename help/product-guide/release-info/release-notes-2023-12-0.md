---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans Adobe Experience Manager Guides, version de décembre 2023
description: Découvrez les correctifs de bogues et comment effectuer la mise à niveau vers la version de décembre 2023 d’Adobe Experience Manager Guides as a Cloud Service.
feature: Release Notes
role: Leader
exl-id: 63efe42a-b817-49df-8f76-df8d7acf9194
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 1%

---

# Version de décembre 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cette note de mise à jour traite des instructions de mise à niveau, de la matrice de compatibilité et des problèmes résolus dans la version de décembre 2023 d’Adobe Experience Manager Guides as a Cloud Service (plus tard appelée *Experience Manager Guides as a Cloud Service*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version de décembre 2023 d’Experience Manager Guides as a Cloud Service](whats-new-2023-12-0.md).

## Mise à niveau vers la version de décembre 2023

Mettez à niveau votre configuration Experience Manager Guides as a Cloud Service actuelle en procédant comme suit :

1. Extrayez le code Git des Cloud Service et passez à la branche configurée dans le pipeline Cloud Service correspondant à l’environnement que vous souhaitez mettre à niveau.
2. Mettez à jour la propriété `<dox.version>` dans le fichier `/dox/dox.installer/pom.xml` de votre code Git Cloud Service vers 2023.12.0.16.
3. Validez les modifications et exécutez le pipeline Cloud Service pour effectuer la mise à niveau vers la version de décembre 2023 de Experience Manager Guides as a Cloud Service.

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

1. Exécutez une requête de POST sur le serveur (avec l’authentification correcte) - `http://<server>//bin/guides/reports/upgrade`.

1. L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison - `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(Par exemple : `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Une fois la tâche terminée, la requête de GET précédente répond avec succès. Si la tâche échoue pour une raison quelconque, l’échec est visible à partir des journaux du serveur.

1. Revenez à la valeur existante par défaut ou précédente de `queryLimitReads` si vous l’avez modifiée à l’étape 1.

## Étapes pour indexer le contenu existant afin d’utiliser la nouvelle liste de rubrique et de recherche sous l’onglet Rapports :

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 de Experience Manager Guides as a Cloud Service)

Effectuez les étapes suivantes pour indexer le contenu existant et utilisez le nouveau texte de recherche et de remplacement au niveau de la carte et de la liste des rubriques sous l’onglet rapports :

1. Exécutez une requête de POST sur le serveur (avec l’authentification correcte) - `http://<server:port>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des cartes pour les indexer ; par défaut, toutes les cartes seront indexées|| Par exemple : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

1. Vous pouvez également transmettre un dossier racine pour indexer les mappages DITA d’un dossier spécifique (et de ses sous-dossiers). Par exemple, `http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test`. Notez que si les paramètres paths et root sont transmis, seul le paramètre paths est pris en compte.

1. L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)


1. Une fois la tâche terminée, la requête de GET précédente répond avec succès et indique si une correspondance a échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Procédure de gestion du conflit `'fmdita rewriter'`

Experience Manager Guides dispose d’un module [**de réécriture sling personnalisée**](../cs-install-guide/conf-output-generation.md#custom-rewriter) pour gérer les liens générés en cas de mappage croisé (liens entre les rubriques de deux cartes différentes).

Si votre code base comporte un autre module de réécriture sling personnalisé, utilisez une valeur `'order'` supérieure à 50, car Experience Manager Guides sling rewriter utilise `'order'` 50.  Pour le remplacer, vous devez disposer d’une valeur supérieure à 50. Pour plus d’informations, voir [ Pipelines de réécriture de sortie](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Pendant cette mise à niveau, puisque la valeur `'order'` est passée de 1000 à 50, vous devez fusionner le module de réécriture personnalisé existant, le cas échéant, avec `'fmdita-rewriter'`.


## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par la version as a Cloud Service Experience Manager Guides de décembre 2023.

### FrameMaker et FrameMaker Publishing Server

| Version de Experience Manager Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.12.0 | Non compatible | 2022 ou version ultérieure |
| | | |


### Connecteur Oxygen

| Version de Experience Manager Guides as a Cloud | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.12.0 | 3.3-uuid.5 | 3.3-uuid.5 | 2,3 | 2,3 |
|  |  |  |  |


### Version du modèle de base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu des composants Experience Manager Guides pour Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :



### Création

- Le **titre** de l’onglet Éditeur web est tronqué après un point(.) caractère « ? » supplémentaire. 14372
- Les messages d’erreur relatifs aux noms de mappage en double dans l’interface utilisateur d’Assets ne sont pas mis à jour. (14320)
- Une erreur se produit dans la logique de création de version lors du glisser-déposer des ressources. (14291)
- Le contenu réutilisable ignore les identifiants d’élément. (14213)
- Le contrôle de paramètre pour masquer le panneau **Variables de langue** sous l’onglet **Output** est manquant. (14194)
- L’éditeur web renvoie des erreurs d’application lors de l’ajout d’une nouvelle référence ou d’une nouvelle rubrique à l’aide d’un schéma spécialisé dans la vue Disposition. 14094
- Un lien d’ancrage vers l’élément `<dlentry>` ou `<dt>` n’affiche pas le texte du lien. (13543)
- Échec du chargement de la collection **Favoris** dans l’éditeur web. (13495)
- Les citations affichent des liens non cliquables lorsqu’elles sont créées avec un identifiant unique avec des espaces. (13447)
- Dans la vue **Disposition** d’une carte de contenu, l’utilisation de **Déplacer à droite** pour faire d’un chapitre sélectionné un sous-élément ne fonctionne pas. (12567)
- La fenêtre Aperçu de l’éditeur XML est tronquée dans les navigateurs Google Chrome et Microsoft Edge. 10755)
- L’éditeur web n’a pas la possibilité de placer un élément à l’intérieur des éléments parents possibles. (8791)

### Publication

- Les composants de formulaire ont un chemin d’accès codé en dur `delegator.jsp`, ce qui empêche la superposition des composants AEM Sites. (13993)
- La vue balisée du réacteur PDF dans la sortie de publication du PDF natif ne fonctionne pas comme prévu. 13622
- AEM La publication sur site rencontre un problème lors de la validation de la banque de données pour les cartes volumineuses avec des liens de portée partagée. 13531
- Impossible d’activer un site à l’aide du tableau de bord Publication en bloc de Experience Manager Guides . 13439
- La localisation des libellés d’élément ne fonctionne pas correctement dans la sortie AEM Sites. (12144)
- Option **ditaval** manquante dans les paramètres prédéfinis de sortie au niveau du profil de dossier créés via l’interface utilisateur de l’éditeur web. (11903)

### Gestion

- AEM environnements cloud rencontrent l’exception MongoWrite en raison de noeuds de grande taille. 13509

### Traduction

- Les boutons **Accepter/Rejeter** s’affichent par erreur pour la traduction humaine approuvée automatiquement. (14318)
- Des problèmes d’internationalisation (i18n) se produisent lors de la transformation de fichiers DITA non anglais en pages AEM. (14286)
- La synchronisation du contenu traduit échoue à partir des projets de traduction temporaires, et l’assistant de traduction de l’éditeur XML DITA affiche incorrectement l’état **En cours** pour les tâches approuvées. (9938)

### Accessibilité

- Impossible de naviguer dans l’interface utilisateur du canevas de création, car la cible d’action devient bloquée dans l’éditeur de rubrique. (13517)

## Problème connu

Adobe a identifié le problème connu suivant pour la version de décembre 2023 :
- &quot;Obtention d’une erreur DTD non valide&quot; se produit par intermittence lors de la mise à niveau vers la version de décembre 2023.
