---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans les guides Adobe Experience Manager, version d’octobre 2023
description: Découvrez les correctifs et comment mettre à niveau vers la version d’octobre 2023 des Guides Adobe Experience Manager as a Cloud Service
exl-id: 536d2ec2-31a0-4533-9c29-16a27525acca
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 1%

---

# Version d’octobre 2023 des Guides Adobe Experience Manager as a Cloud Service

Cette note de mise à jour décrit les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans la version d’octobre 2023 des Guides Adobe Experience Manager (appelée ultérieurement *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version d’octobre 2023 d’AEM Guides as a Cloud Service](whats-new-2023-10-0.md).

## Mise à niveau vers la version d’octobre 2023

Mettez à niveau votre configuration as a Cloud Service actuelle AEM Guides en procédant comme suit :

1. Extrayez le code Git des Cloud Service et passez à la branche configurée dans le pipeline Cloud Service correspondant à l’environnement que vous souhaitez mettre à niveau.
2. Mettre à jour `<dox.version>` dans `/dox/dox.installer/pom.xml` du code Git Cloud Service vers la version 2023.10.0.373.
3. Validez les modifications et exécutez le pipeline Cloud Service pour effectuer la mise à niveau vers la version d’octobre 2023 d’AEM Guides as a Cloud Service.

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

Effectuez les étapes suivantes pour post-traiter le contenu existant et utiliser le nouveau rapport de lien rompu :

1. (Facultatif) Si le système contient plus de 100 000 fichiers DITA, mettez à jour la variable `queryLimitReads` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` à une valeur plus élevée (toute valeur supérieure au nombre de ressources présentes, par exemple 200 000), puis redéployez.

   - Suivez les instructions de la section *Remplacements de configuration* dans la section Installation et configuration de Adobe Experience Manager Guides as a Cloud Service pour créer le fichier de configuration.
   - Dans le fichier de configuration, fournissez les détails (propriété) suivants pour configurer l’option queryLimitReads :

     | PID | Clé de propriété | Valeur de la propriété |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valeur : 200000 Valeur par défaut : 100000 |

1. Exécutez une requête de POST sur le serveur (avec l’authentification correcte) - `http://<server:port>//bin/guides/reports/upgrade`.

1. L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison : `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Une fois la tâche terminée, la requête de GET précédente répond avec succès. Si la tâche échoue pour une raison quelconque, l’échec est visible à partir des journaux du serveur.

1. Revenir à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifié à l’étape 1.

## Étapes pour indexer le contenu existant afin d’utiliser la nouvelle liste de rubrique et de recherche sous l’onglet Rapports :

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 d’AEM Guides as a Cloud Service)

Effectuez les étapes suivantes pour indexer le contenu existant et utilisez le nouveau texte de recherche et de remplacement au niveau de la carte et de la liste des rubriques sous l’onglet rapports :

1. Exécutez une requête de POST sur le serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des cartes pour les indexer ; par défaut, toutes les cartes seront indexées \|\| Par exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. Vous pouvez également transmettre un dossier racine pour indexer les mappages DITA d’un dossier spécifique (et de ses sous-dossiers). Par exemple, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Notez que si les paramètres paths et root sont transmis, seul le paramètre paths est pris en compte.

1. L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison : `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Une fois la tâche terminée, la requête de GET précédente répond avec succès et indique si une correspondance a échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par AEM Guides as a Cloud Service d’octobre 2023.

### FrameMaker et FrameMaker Publishing Server

| AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.10.0 | Non compatible | 2022 ou version ultérieure |
| | | |


### Connecteur Oxygen

| AEM Guides as a Cloud | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.10.0 | 3.2-uuid 5 | 3.2-uuid 5 | 2,3 | 2,3 |
|  |  |  |  |


### Version du modèle de base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| AEM Guides Components Content Package pour Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :

### Création

- Les heures de l’après-midi ne sont pas définies dans la variable **Date** pour la création de lignes de base. (12712)
- Impossible de coller le code JSON dans la variable `<codeblock>` de l’éditeur Web. (12326)
- Les modifications de version non enregistrées et les indicateurs associés ne sont pas affichés pour les fichiers volumineux. (11784)
- Lors de l’édition en coréen, le premier caractère est remplacé par défaut. (10049)


### Publication

- PDF natif | L’ordre des rubriques n’est pas fixe lors de la génération de la sortie du PDF. (13157)
- PDF natif| Aucune balise de style par défaut n’est disponible pour `<p>`élément . (12559)
- PDF natif | Les styles intégrés appliqués à la région de contenu ne sont pas appliqués aux rubriques en premier et en arrière. (13510)
- La variable `DeliveryTarget` n’est pas propagé lors de la génération de la sortie AEM Site.  (13132)
- La variable **Publier** Le workflow se bloque lors de la génération AEM sortie du site pour le contenu contenant certaines erreurs. (12000)

### Gestion

- L’historique de version ne s’affiche pas même si la variable `dc:format` n’est pas présente pour une ressource. 10463


### Révision

- La révision d’une rubrique affiche des commentaires incorrects. (13453)



### Traduction

- La ligne de base exportée à partir du **Traduction** le tableau de bord échoue et ne s’ouvre pas dans la langue cible. (13466)

- De nouveaux projets de traduction sont créés au lieu d’ajouter de nouvelles tâches aux projets de traduction existants sélectionnés.  (10214)

## Problème connu

Adobe a identifié le problème connu suivant pour la version d’octobre 2023.

- La republication du fragment de contenu échoue.
