---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans Adobe Experience Manager Guides, version de novembre 2023
description: Découvrez les correctifs et comment effectuer une mise à niveau vers la version de novembre 2023 d’Adobe Experience Manager Guides as a Cloud Service
exl-id: 80839890-075f-4187-a167-444c73215496
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1673'
ht-degree: 1%

---

# Version de novembre 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cette note de mise à jour couvre les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans la version de novembre 2023 d’Adobe Experience Manager Guides as a Cloud Service (plus tard appelée *Experience Manager Guides as a Cloud Service*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, consultez [Nouveautés de la version de novembre 2023 de Experience Manager Guides as a Cloud Service](whats-new-2023-11-0.md).

## Mise à niveau vers la version de novembre 2023

Mettez à niveau votre configuration as a Cloud Service Experience Manager Guides actuelle en procédant comme suit :

1. Consultez le code Git des services cloud et passez à la branche configurée dans le pipeline des services cloud correspondant à l’environnement à mettre à niveau.
2. Mettez à jour `<dox.version>` propriété dans `/dox/dox.installer/pom.xml` fichier de votre code Git Cloud Services sur 2023.11.0.406.
3. Validez les modifications et exécutez le pipeline Cloud Services pour effectuer la mise à niveau vers la version de novembre 2023 de Experience Manager Guides as a Cloud Service.

## Procédure d’activation du déclenchement d’un script via une servlet

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 de Experience Manager Guides as a Cloud Service)

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

Dans la réponse précédente JSON, la clé `lockNodePath` contient le chemin d’accès au nœud créé dans le référentiel pointant vers la tâche envoyée. Elle sera automatiquement supprimée une fois le traitement terminé. Vous pouvez alors vous référer à ce nœud pour connaître le statut du traitement.

Patientez jusqu’à ce que ce traitement soit terminé avant de passer aux étapes suivantes.

>[!NOTE]
>
> Vous devez vérifier si le nœud est toujours présent, ainsi que le statut de la tâche.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Étapes de post-traitement du contenu existant pour utiliser le rapport de lien rompu

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 de Experience Manager Guides as a Cloud Service)

Effectuez les étapes suivantes pour post-traiter le contenu existant et utiliser le nouveau rapport de lien rompu :

1. (Facultatif) Si le système contient plus de 100 000 fichiers DITA, mettez à jour les `queryLimitReads` et `queryLimitInMemory` sous `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` avec une valeur plus élevée (toute valeur supérieure au nombre de ressources présentes, par exemple 200 000), puis redéployez.

   - Suivez les instructions de la section *Remplacements de configuration* dans Installation et configuration d’Adobe Experience Manager Guides as a Cloud Service pour créer le fichier de configuration.
   - Dans le fichier de configuration, fournissez les détails (propriété) suivants pour configurer les options `queryLimitReads` et `queryLimitInMemory` :

     | PID | Clé de la propriété | Valeur de la propriété |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valeur : 200000 Valeur par défaut : 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Valeur : 200000 Valeur par défaut : 100000 |

1. Exécutez une requête POST au serveur (avec l’authentification correcte) - `http://<server:port>//bin/guides/reports/upgrade`.

1. L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée : `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Une fois le traitement terminé, la requête GET précédente répond avec succès. Si la tâche échoue pour une raison quelconque, l’échec est visible dans les journaux du serveur.

1. Revenez à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifiée à l’étape 1.

## Procédure à suivre pour indexer le contenu existant afin d’utiliser la nouvelle liste de recherche et de remplacement et de rubriques sous l’onglet Rapports :

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 de Experience Manager Guides as a Cloud Service)

Effectuez les étapes suivantes pour indexer le contenu existant et utiliser le nouveau texte rechercher et remplacer au niveau du mappage et de la liste de rubriques sous l’onglet rapports :

1. Exécutez une requête POST au serveur (avec l’authentification correcte) - `http://<server:port>/bin/guides/map-find/indexing`. (Facultatif) Vous pouvez transmettre des chemins spécifiques des mappages pour les indexer. Par défaut, tous les mappages sont indexés || Par exemple : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

1. Vous pouvez également transmettre un dossier racine pour indexer les plans DITA d&#39;un dossier spécifique (et de ses sous-dossiers). Par exemple, `http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test`. Notez que si le paramètre de chemins d’accès et le paramètre racine sont transmis, seul le paramètre de chemins d’accès est pris en compte.

1. L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée, `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}` (par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`).


1. Une fois la tâche terminée, la requête GET précédente répond avec succès et mentionne si des mappages ont échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Procédure à suivre pour gérer le conflit de `'fmdita rewriter'`

Experience Manager Guides dispose d’un module [**custom sling rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter) qui gère les liens générés en cas de mappages croisés (liens entre les rubriques de deux mappages différents).

Si votre base de code contient un autre module de réécriture Sling personnalisé, utilisez une valeur de `'order'` supérieure à 50, car le module de réécriture Sling de Experience Manager Guides utilise `'order'` 50.  Pour remplacer cela, vous avez besoin d’une valeur >50. Pour plus d’informations, consultez la section [Pipelines de réécriture de sortie](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Lors de cette mise à niveau, puisque la valeur `'order'` est modifiée de 1 000 à 50, vous devez fusionner le module de réécriture personnalisé existant, le cas échéant, avec `'fmdita-rewriter'`.


## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par la version de novembre 2023 de Experience Manager Guides as a Cloud Service.

### FrameMaker et FrameMaker Publishing Server

| Version de Experience Manager Guides Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.11.0 | Non compatible | 2022 ou version ultérieure |
| | | |


### Connecteur D&#39;Oxygène

| Version de Experience Manager Guides as a Cloud | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.11.0 | 3.2-uuid 5 | 3.2-uuid 5 | 2,3 | 2,3 |
|  |  |  |  |  |


### Version du modèle de la base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu de composants Experience Manager Guides pour Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problèmes résolus

Les bogues corrigés dans différentes zones sont répertoriés ci-dessous :



### Création

- L’espace après l’élément `<ph>` conref disparaît lors de l’enregistrement de la rubrique. (13642)
- Une erreur d&#39;application se produit lors de la tentative d&#39;enregistrement de fichiers DITA avant la fin du post-traitement. (13571)
- Si le titre d’une rubrique contient une barre oblique `/`, l’onglet de l’éditeur affiche uniquement les lettres qui suivent. (13455)
- L’aperçu de l’image ne disparaît pas après l’affichage de l’aperçu dans l’éditeur. (13454)
- La fenêtre contextuelle Insérer un mot-clé n’apparaît pas lors de l’utilisation de clés définies par une carte racine dans d’autres rubriques. (12950)
- Les icônes de fermeture ne sont pas visibles lorsque des graphiques très hauts sont prévisualisés dans le panneau Historique des versions. (12867)
- Impossible de modifier le fuseau horaire de la colonne **Version créée le** pour les lignes de base. (12711)
- Le panneau **Historique des versions** de l’interface utilisateur d’Assets affiche un horodatage incorrect pour le champ **Actuel**. (12624)
- La création d&#39;un fichier DITA à partir d&#39;un modèle dont le nom de fichier commence par des caractères numériques entraîne une erreur d&#39;espace de noms. (12188)
- Dans l’éditeur web, la fenêtre **Références clés** s’ouvre lors de l’insertion de la balise `varname`. (10940)
- Les fichiers Zip ne sont pas reconnus dans l’éditeur web et vous ne pouvez pas les faire glisser et les déposer. (12709)
- Le contenu auquel certains attributs sont appliqués n’est pas mis en surbrillance en mode Création ou Aperçu. (11063)
- Lorsque vous fermez une rubrique après l’avoir modifiée, vous êtes redirigé vers la page d’accueil d’AEM au lieu de revenir à la vue des dossiers. (13306)
- Un retard se produit lors du post-traitement des fichiers qui ont été copiés et collés dans les services cloud. (12457)
- Le paramètre de feuille de route persiste dans l’éditeur web même si l’utilisateur ne l’a pas défini explicitement à partir des préférences utilisateur. (11551)


### Publication

- La fonctionnalité de publication en tant que fragment de contenu ne fonctionne pas pour les fichiers répertoriés dans les résultats de recherche. (14090)
- Dans la publication Native PDF, la sélection de la couleur d’arrière-plan sur la mise en page du modèle nécessite un rechargement de page lors du retour à la `None`. (13621)
- Problème lors de la validation dans le magasin de données d&#39;un plan DITA volumineux avec des liens d&#39;homologue de portée dans la publication sur le site AEM. (13530)
- Dans la publication Native PDF, l’accessibilité est compromise, car les images de l’en-tête et du pied de page n’affichent pas de texte secondaire. (12829)
- La duplication de la mise en page dans le PDF natif ne fonctionne pas si aucune extension n’est ajoutée automatiquement. (12534)
- Lors de la génération de la sortie PDF avec publication Native PDF, le nom du fichier est tronqué après un point. (13620)
- Une icône et une info-bulle incorrectes s’affichent pour l’option **Modifier le contenu** dans la barre d’outils Mises en page des modèles utilisés dans la publication native de PDF. (13492)
- Les métadonnées personnalisées ne sont pas disponibles dans la sortie finale. (12116)
- fmdita rewriter est en conflit avec la configuration de réécriture de l’utilisateur et entraîne l’affichage d’URL longues au lieu des liens. (12076)
- Dans le paramètre prédéfini de site AEM, l’option **Générer un PDF distinct pour chaque rubrique** n’est pas fonctionnelle. (11555)
- La publication native de PDF ne prend pas en charge la conversion de l’espace colorimétrique CMJN. (10754)
- Les appels de base dynamiques utilisent le nom au lieu du titre, ce qui entraîne l’échec de l’exportation de l’API map DITA. (14268)

### Gestion

- La référence au contenu est rompue lors du copier-coller des fichiers DITA ayant des liens d&#39;auto-référence sans GUID. (13540)
- Dans l&#39;éditeur Web, la ligne de base affiche le titre de la version précédente au lieu de la version sélectionnée du fichier DITA. (13444)
- L’onglet **Rapports** de l’interface utilisateur de l’éditeur web n’affiche pas la liste de rubriques pour les anciens plans DITA créés avant la mise à niveau de juillet 2023 de Experience Manager Guides as a Cloud Service. (11852)
- Les paramètres prédéfinis de condition pour les plans DITA volumineux ne sont pas créés. (10936)
- Un lien d’auto-référence s’affiche sous la liste des liens rompus dans les rapports. (13539)

### Révision

- Les panneaux de révision côte à côte des versions précédente et actuelle de l’éditeur web ne sont pas corrects dans la version d’octobre 2023 de Experience Manager Guides as a Cloud Service. (14156)
- La personnalisation du modèle d’e-mail pour le workflow **Révision** ne fonctionne pas avec le recouvrement des nœuds. (13954)
- Le bouton **Fermer** de la page Réviser dans Experience Manager Guides permet d’accéder à la page d’accueil d’AEM. (13535)
- Des caractères rompus apparaissent lors de la création des fragments de code en coréen. (13489)
- Vous ne pouvez pas cliquer sur les pièces jointes coréennes dans l’écran de révision Experience Manager Guides. (13436)
- Le titre de la carte est tronqué dans l’écran de révision et de collaboration, sans possibilité d’afficher le titre complet. (13012)

### Traduction

- L’approbation automatique ne fonctionne pas toujours et des exceptions se produisent si une valeur incorrecte est définie sur **Statut de traduction**. (13607)
- La ligne de base exportée à partir du tableau de bord de traduction échoue et ne s’ouvre pas dans la langue cible. (12993)

## Problème connu

Adobe a identifié le problème connu suivant pour la version de novembre 2023.

- La régénération sélective des rubriques pour la sortie du site AEM échoue.
