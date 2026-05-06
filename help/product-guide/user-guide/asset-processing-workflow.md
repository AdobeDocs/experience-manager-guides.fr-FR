---
title: FAQ sur les performances et l’évolutivité de la publication dans Adobe Experience Manager Guides
description: Découvrez les questions fréquentes sur les performances et l’évolutivité de la publication dans Adobe Experience Manager Guides.
source-git-commit: f188c2827a9e27249d0162c9f9913e090b29672d
workflow-type: tm+mt
source-wordcount: '1666'
ht-degree: 1%

---


# Traitement des ressources

Le traitement des ressources est un workflow essentiel qui permet de s’assurer que les ressources de contenu sont structurées, validées, indexées et rendues accessibles dans la plateforme. En raison de l’évolution des exigences d’évolutivité et des exigences natives liées au cloud, l’architecture a subi une transformation significative, passant d’un modèle de traitement hiérarchique à thread unique à un système distribué, compatible avec les graphiques et multithread.

## Workflow de traitement des ressources actuelles

### Présentation du traitement

Lorsqu’une ressource est importée dans Experience Manager Guides, les étapes de traitement séquentiel suivantes sont exécutées :

- Attribution d’une clé unique : un identifiant unique est attribué à chaque document pour assurer la traçabilité et l’intégrité des références.
- Analyse : le contenu (par exemple, le fichier XML DITA) est analysé en composants structurés pour une compréhension au niveau du système.
- Validation : la validation de la structure et du schéma garantit la conformité aux normes du document.
- Résolution de référence : les références croisées (liens, images, dépendances) sont résolues sur l’ensemble des ressources.
- Extraction des métadonnées : les métadonnées telles que le titre, l’auteur et les attributs personnalisés sont extraites à des fins d’indexation et de recherche.
- Retraitement en cas de modification : le retraitement incrémentiel garantit la cohérence après les mises à jour du contenu.

### Caractéristiques architecturales

- **Traitement mono-thread** : empêche la corruption des structures JCR (Java Content Repository), qui reposent sur des implémentations B-Tree.Cela garantit l’intégrité des données, mais introduit des goulots d’étranglement lors de l’ingestion en masse.

- **Dépendance de mappage parent** : maintient les relations hiérarchiques entre les ressources à l’aide du parcours transversal des graphiques. Il s’agit d’une opération intensive avec une latence élevée lors d’un traitement à grande échelle, une surcharge de calcul accrue et une contrainte due à des opérations de traversée lourdes.

## Nouveau flux de traitement des ressources

Les principales étapes de traitement restent cohérentes sur le plan fonctionnel, mais sont désormais exécutées dans un framework distribué et parallélisé, ce qui améliore considérablement le débit.

### Améliorations architecturales

- **Intégration de la base de données Graph** :
   - Transition du JCR hiérarchique vers une base de données Graph native
   - Gestion efficace des relations et des dépendances
   - Complexité de la simulation des opérations graphiques sur le stockage hiérarchique
- **Traitement distribué multithread** :
   - Le traitement est exécuté sur plusieurs capsules dans un environnement cloud
   - Supprime la dépendance sur un seul nœud leader
   - Permet une évolutivité horizontale et une exécution parallèle
- **Suppression de la dépendance de mappage parent :**
   - Supprime la nécessité d’une traversée de graphique explicite
   - Réduction des opérations d’E/S et de la latence de traitement
   - Simplifie le pipeline de traitement
- **Attribution d’ID uniques synchronisés**
   - La coordination centralisée assure :
   - Pas de duplication des ID de document
   - Cohérence entre les nœuds distribués
   - Maintient l’intégrité du référentiel dans un environnement simultané
- **Base de données évolutive native dans le cloud (hébergée par AWS)**
   - Couche de base de données hautement disponible et résiliente
   - Prend en charge une mise à l’échelle élastique en fonction de la charge de travail
   - Améliore la fiabilité et les performances globales du système

![](images/workflow.png)

## Avantages de la nouvelle architecture

- Améliorations des performances :
   - L’exécution en parallèle réduit considérablement le temps de traitement
   - L’élimination des opérations transverses lourdes réduit la latence
   - La gestion optimisée des graphiques améliore la vitesse de résolution des dépendances
- Évolutivité :
   - La mise à l’échelle horizontale sur les capsules permet de gérer d’importants volumes d’ingestion
   - L’infrastructure native au cloud s’adapte dynamiquement aux demandes de charge de travail.
- Fiabilité et disponibilité :
   - Le traitement distribué supprime le point unique de défaillance
   - La base de données hébergée par AWS garantit une haute disponibilité et une tolérance aux pannes
- Gains d’efficacité :
   - Réduction de la surcharge d’E/S due à la suppression du parcours transversal de la carte parent
   - Meilleure utilisation des ressources entre les nœuds de calcul
- Intégrité des données :
   - L’attribution d’identifiants synchronisée maintient la cohérence entre les systèmes distribués
   - Conserve la robustesse tout en activant la simultanéité

## Configuration de la base de données

Experience Manager Guides permet une configuration de base de données rationalisée pour les environnements AEM Cloud. Pour configurer la base de données de votre instance AEM Cloud, procédez comme suit :

1. Accédez à AEM Cloud Manager : accédez à Adobe Experience Cloud Manager à l’aide de l’URL ci-dessous, en remplaçant les espaces réservés par les détails de votre organisation, de votre programme et de votre environnement : `https://experience.adobe.com/#/${orgName}/cloud-manager/environments.html/program/${programId}/environment/${envId}`

1. Configuration de l’environnement : après l’ouverture de la page de configuration de l’environnement via Cloud Manager, vous pourrez ajuster les paramètres spécifiques à votre instance, y compris configurer les configurations de base de données requises.

Cette approche rationalisée garantit un accès et une configuration faciles des environnements AEM dans l’infrastructure cloud d’Adobe.

1. Configurez les propriétés suivantes :


| Nom de la propriété | Valeur | Service appliqué | Type |
|----------------------------------|--------------------------------|-----------------|----------|
| DATABASE_URL | `<host>:<port>/<db_name>` | Création | Variable |
| GUIDES_ENABLE_DATABASE | `true` | Création | Variable |
| DATABASE_PASSWORD | `password` | Création | Secret |
| DATABASE_USERNAME | `username` | Création | Variable |
| RUN_POSTPROCESS_IN_PHASES | `true` | Création | Variable |
| DATABASE_CONNECTION_POOL_SIZE | `10` | Création | Variable |


![](images/environment-config.png){width="350"}

1. Enregistrer les modifications : une fois les modifications de configuration effectuées, veillez à les **enregistrer** dans l’interface de Cloud Manager.

1. Disponibilité du système : une fois les configurations entièrement appliquées, ouvrez GET `http://host/bin/guides/v1/system/status` et vérifiez les propriétés ci-dessous :
   - `<isDatabase>` : doit être vrai
   - `<databaseConnectionCheck>` : doit être transmis

   Si les valeurs ci-dessus sont correctes dans la réponse, le système peut être utilisé avec la base de données nouvellement configurée.

En suivant ce processus, vous disposerez d’un environnement cloud AEM correctement configuré et prêt à l’emploi.

>[!NOTE]
>
> Si vous migrez vers un environnement existant avec du contenu préexistant, vous devez d’abord exécuter la Phase 2 (Migration du contenu existant) avant d’ingérer du nouveau contenu. Cela permet de s’assurer que les GUID temporaires sont correctement attribués au nouveau contenu.

## Ingestion de données dans AEM DAM (environnement cloud) (phase 1)

Pour configurer un nouveau dossier dans la gestion des ressources numériques (DAM) d’AEM, ingérer des données et les comparer à un environnement basé sur JCR, procédez comme suit.

1. Créez un dossier dans la gestion des ressources numériques (DAM).

2. Ingérer des données à l’aide de l’outil de chargement de données : pour plus d’informations, consultez le **Chargement d’Assets vers AEM Cloud**.

3. Vérification du système
   - Une fois le chargement terminé, vérifiez que les ressources sont présentes dans la gestion des ressources numériques (DAM).
   - Assurez-vous que les métadonnées (telles que les types de fichiers, les descriptions et les balises) ont été extraites et associées aux ressources.
   - Vérifiez le traitement Experience Manager Guides (multithread) pour confirmer que toutes les références, l’extraction des métadonnées et les validations ont réussi.
   - Testez l’accès et la modification d’un document pour confirmer l’intégrité du système.

4. Comparaison avec l’environnement basé sur JCR
   - Comparez les résultats sur différents cas de test.
   - Évaluez la vitesse d’ingestion.


Pour migrer le contenu chargé et traité avant de passer de Experience Manager Guides à une configuration de base de données, vous pouvez utiliser un script de migration. Le script utilise un ensemble d’API pour lancer et surveiller le processus de migration. Les étapes suivantes décrivent l’approche recommandée.

## Migration du contenu de JCR vers la base de données (phase 2)

Pour migrer le contenu chargé et traité avant de passer de Experience Manager Guides à une configuration de base de données, vous devez utiliser un script de migration. Le script utilise un ensemble d’API pour lancer et surveiller le processus de migration. Les étapes suivantes décrivent l’approche recommandée.

1. Déclenchez l’API de migration à l’aide d’un client REST.
2. Vérifiez la progression de la migration.
3. Surveillez la migration jusqu’à la fin : continuez la surveillance jusqu’à ce que l’API de progression signale une fin à 100 %. Une fois l’opération terminée, tout le contenu précédemment chargé et traité à partir du référentiel JCR est migré vers la base de données.

   >[!NOTE]
   >
   > - Assurez-vous que les en-têtes d’autorisation requis (tels que les jetons OAuth, les clés API ou les jetons d’accès à partir de la Developer Console) sont inclus pour authentifier les requêtes avec AEM.
   > - La durée de la migration dépend de la taille du référentiel de contenu. Il est recommandé de vérifier régulièrement l’avancement du projet et de surveiller les erreurs ou les interruptions.
   > - Consultez les journaux de migration, le cas échéant, pour évaluer les performances de la migration et identifier les problèmes éventuels.

4. Pour prendre en charge la migration pour les tailles de référentiel volumineuses, suivez la configuration ci-dessous

   >[!NOTE]
   >
   > Appliquez cette configuration uniquement si des erreurs de traversée du référentiel se produisent lors de la migration.

   `file name: `org.apache.jackrabbit.oak.query.QueryEngineSettingsService.xml«

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0"
         xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
         jcr:primaryType="sling:OsgiConfig"
         queryLimitInMemory="5000000"
         queryLimitReads="1000000"
   />
   ```


## API de migration

### Démarrer la migration

- point d’entrée : `POST /bin/guides/v1/assets/process`
- corps de la requête : (`application/json`) :

```json
  {
    "path": "/content/dam/dita-templates",
    "excludedPaths": [
      "/content/dam/demo",
      "/content/dam/demo1"
    ],
    "type": "ASSET_PROCESSING"
  }
```

- renvoie l’ID de traitement pour la migration.
- déclenche le workflow de traitement des ressources intégré au produit.

### Vérification du statut de migration

point d’entrée : `GET /bin/guides/v1/assets/process/status?processingId=<processingId>`

### Annuler une migration en cours

- point d’entrée : `POST /bin/guides/v1/assets/process/cancel`
- corps de la requête (application/json) :

  ```
  {
   "processingId": "processingId"
  }
  ```

### Reprise d’une migration ayant échoué ou annulée

- point d’entrée : `POST /bin/guides/v1/assets/process/resume`
- corps de la requête (application/json) :

  ```
  {
   "processingId": "processingId"
  }
  ```

## Chargement de ressources dans le cloud AEM

Adobe Experience Manager (AEM) as a Cloud Service propose plusieurs approches pour l’ingestion de contenu en masse. Pour garantir des performances optimales, en particulier pour le post-traitement Experience Manager Guides, il est essentiel d’adopter une stratégie d’ingestion prise en charge et évolutive.

### Ingestion en bloc à l’aide des intégrations de stockage dans le cloud

AEM prend en charge l’ingestion de contenu en masse par le biais de fournisseurs de stockage dans le cloud pris en charge, ce qui permet aux entreprises de connecter leur solution de stockage préférée et d’importer du contenu directement dans AEM. Cette approche est recommandée pour une ingestion à grande échelle et sensible aux performances en raison des avantages suivants :

- Infrastructure évolutive : le processus d’ingestion s’exécute sur l’infrastructure cloud gérée par Adobe, permettant la mise à l’échelle automatique en fonction de la charge et du volume de contenu. Cela garantit des performances d’ingestion cohérentes même pour les jeux de données volumineux.

- Planification prévisible de l’ingestion : les utilisateurs et les utilisatrices peuvent estimer la durée de l’ingestion à l’avance, ce qui permet de planifier les versions, de les planifier et de les coordonner avec les équipes dépendantes.

  ![](images/ingestion-time.png){width="350"}

- Journalisation et suivi complets : le workflow d’ingestion comprend des fonctionnalités de journalisation et de suivi détaillées, offrant une visibilité sur la progression, les états de succès et les problèmes potentiels tout au long du processus d’importation.

  ![](images/bulk-import-job.png){width="350"}

- Ingestion planifiée : l’ingestion de contenu peut être planifiée pendant des périodes prédéfinies, afin d’assurer un impact minimal ou nul sur les utilisateurs finaux et les opérations en cours.

Pour plus d’informations, voir [Utilisation de l’importation en bloc](https://experienceleague.adobe.com/fr/docs/experience-manager-learn/cloud-service/migration/bulk-import).

## Ingestion en bloc à l’aide du chargement AEM

AEM fournit également [AEM upload](https://github.com/adobe/aem-uploa), une bibliothèque et une interface de ligne de commande (CLI) qui permet aux utilisateurs d’ingérer du contenu directement à partir d’un système de fichiers local. Cette option peut être intégrée dans des solutions personnalisées ou utilisée en tant qu’outil d’interface de ligne de commande autonome pour charger du contenu.

Cette approche s’exécutant sur l’ordinateur local des utilisateurs et utilisatrices, elle nécessite une connexion réseau stable et ininterrompue pour garantir une expérience d’ingestion fiable et transparente.


## Vérification de l’intégrité de la connectivité de la base de données Experience Manager Guides

Les déploiements de Experience Manager Guides configurés pour utiliser une base de données nécessitent une connectivité de base de données stable et cohérente pour fonctionner de manière fiable. La vérification de l’état de connexion à la base de données est une étape essentielle de vérification de l’intégrité pour exclure les problèmes de connectivité susceptibles d’avoir une incidence sur les fonctionnalités du système.

Ce contrôle de l’intégrité permet aux utilisateurs de confirmer si la base de données est configurée, accessible et fonctionne comme prévu. Pour vérifier le statut de la connexion à la base de données, procédez comme suit.

1. Ouvrez un navigateur ou un client REST.
2. Déclenchez un appel GET à l’aide de cette [URL](https://host:port/bin/guides/v1/system/status)
3. Les champs ci-dessous peuvent être utilisés pour déterminer la configuration du système et son état de santé
   1. isDatabase :
      - true : l’environnement est configuré avec la base de données .
      - false : l’environnement n’utilise pas la base de données

   2. databaseConnectionCheck :
      - réussi : Experience Manager Guides vérifie l’état de connexion et si Guides peut se connecter à la base de données, il renvoie l’état passé.
      - échec : l’environnement ne peut pas communiquer avec la base de données. Les clients doivent immédiatement cesser d’utiliser le système et contacter l’assistance Adobe.

## Surveillance du journal

Experience Manager Guides avec base de données consigne efficacement les détails pour donner à une insight l’état du système.
Utilisez les requêtes ci-dessous dans Splunk pour obtenir des journaux pour différents scénarios.

1. Journaux de migration :
   - `index IN ("dx_aem_engineering") aem_service=cm-${programid}-${environmentId} sourcetype=aemerror "AssetProcessingJob" OR "AssetJobProducerDb" NOT "ServiceEvent"`
2. Logs de post-traitement :
   - `index IN ("dx_aem_engineering") aem_service= cm-${programid}-${environmentId} sourcetype=aemerror com.adobe.fmdita.uuid.concrete.Cor*`


>[!NOTE]
>
> En savoir plus sur les [fonctionnalités de requête Splunk](https://www.splunk.com/en_us/blog/learn/splunk-cheat-sheet-query-spl-regex-commands.html) pour filtrer ces journaux en fonction de la durée, du niveau de journal ou de la recherche de modèles spécifiques.










