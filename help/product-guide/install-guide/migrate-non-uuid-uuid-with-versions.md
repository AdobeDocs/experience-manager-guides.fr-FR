---
title: Conversion de contenu non UID avec des versions en contenu UID
description: Découvrez comment migrer du contenu non UUID avec des versions.
exl-id: 9387e0d1-906c-4e5c-a7a0-0ed1600f5eb6
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1287'
ht-degree: 2%

---

# Migration de contenu non UUID avec des versions

Effectuez les étapes suivantes pour migrer votre contenu non UUID avec des versions vers le contenu UID.

## Matrice de compatibilité

| Version actuelle des guides AEM (non UUID) | Version requise pour la migration vers UUID | Chemin de mise à niveau pris en charge |
|---|---|---|
| 3.8.5 | 4.0 non UUID | Installez la version 4.1 (UUID) et exécutez la migration |
| 4.0, 4.0.x, 4.1 ou 4.1.x | Identique au non-UUID actuel | Installez la version 4.1 (UUID) et exécutez la migration |
| 4.2 ou version ultérieure | S/O | Pas encore pris en charge |

## Packages requis

1. **Purge de version**: `com.adobe.guides.version-purge-1.0.11.zip` (facultatif)
1. **Avant migration**: `com.adobe.guides.pre-uuid-migration-1.0.7.zip`
1. **Migration**: `com.adobe.guides.uuid-upgrade-1.0.17`
1. **Post-migration**: `com.adobe.guides.post-uuid-migration-1.0.2.zip`


## Avant migration

1. (Facultatif) Effectuez la purge des versions sur le contenu pour supprimer les versions inutiles et accélérer le processus de migration. Pour effectuer la purge de version sur la version 4.1 (NON pris en charge sur la version 4.0), installez le module . `com.adobe.guides.version-purge-1.0.11.zip`et accédez à l’interface utilisateur à l’aide de cette URL. `http://<server-name> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`.

   >[!NOTE]
   >
   >Cet utilitaire ne supprime aucune version utilisée dans les lignes de base ou les révisions, ni ne comporte d’étiquettes.
1. Installez le package de pré-migration (`com.adobe.guides.pre-uuid-migration-1.0.7.zip`).

1. Exécutez la requête suivante ci-dessous pour obtenir un rapport avec une durée estimée (ETA) de la durée de la migration. Il indique s’il existe des fichiers avec des problèmes de contenu qui ne migreront pas.

>[!NOTE]
>
>Vous avez besoin de l’autorisation d’administrateur pour exécuter la migration.


| URL du point d’entrée | Type de requête | Paramètre de requête | Résultats attendus |
|---|---|---|---|
| `/bin/guides/pre_uuid_upgrade` <br> <br>**Par exemple**: http://localhost:4502/bin/guides/pre_uuid_upgrade?root=/content/dam | GET | **root**: dossier racine<br> **Valeur**: `/content/dam` pour l’ensemble du référentiel. | Un rapport de pré-migration (.csv) sera créé, répertoriant le nombre de fichiers, le nombre total de versions et les erreurs. <br><br> **Exemple de résultat**:<br>RootFolder: /content/dam <br>Total des fichiers : 2697 <br>Total des versions : 10380 <br>Nombre de fichiers en erreur : 28 <br>Un rapport détaillé sera disponible via AEM CRX à l’adresse `/content/uuid-pgrade/UuidMigrationReport_1688400131039.csv` |

Cette étape peut échouer si le système contient de nombreux fichiers DITA. Pour résoudre ce problème, augmentez la limite du nombre de fichiers parcourus dans la requête en augmentant la valeur de *Limite de lecture en mémoire (queryLimitReads)* dans le service de paramètres du moteur de requête Apache Jackrabbit à partir du 100000 un nombre supérieur au nombre total de ressources DITA présentes dans le système.

## Migration

### Etape 1 : mise à jour de la configuration

1. Assurez-vous que l’espace disponible est au moins 10 fois supérieur à l’espace utilisé par AEM (répertoire crx-quickstart) pendant la migration. Une fois la migration terminée, vous pouvez récupérer la plus grande partie de l’espace disque en exécutant la compression (voir [Nettoyage des révisions](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=fr)).

1. Activer *Activation des lanceurs de workflow de post-traitement* in `com.adobe.fmdita.config.ConfigManager` et *Activation du post-traitement des versions* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Installez la version UID de la version prise en charge sur la version non UUID. Par exemple, si vous utilisez une version 4.0 non UUID ou une version 4.1 non UUID, vous devez installer UID version 4.1.

1. Installez le nouveau package pour la migration uuid (`com.adobe.guides.uuid-upgrade-1.0.17`).

1. Désactivez les workflows suivants et tout autre workflow qui s’exécute sur `/content/dam` utilisation des lanceurs dans `http://localhost:4502/libs/cq/workflow/content/console.html`.

   * Workflow Ressource de mise à jour de la gestion des DAM
   * Workflow d’écriture différée des métadonnées de gestion des actifs numériques

1. Désactiver *Activation des lanceurs de workflow de post-traitement* in `com.adobe.fmdita.config.ConfigManager` et désactiver *Activation du post-traitement des versions* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`.

1. Désactivez la propriété Activer la validation (`validation.enabled`) dans le service de balisage Day CQ.

1. Assurez-vous que `uuid.regex` Le dossier de propriétés est correctement défini dans `com.adobe.fmdita.config.ConfigManager`. S’il est vide, définissez-le sur la valeur par défaut - `^GUID-(?<id>.*)`.
1. Ajouter un journal distinct pour `com.adobe.fmdita.uuid.upgrade.UuidUpgrade` La réponse du navigateur est également disponible sur la page `/content/uuid-upgrade/logs`.

### Etape 2 : Exécuter le script et valider

Exécutez la requête donnée sur un dossier contenant des données plus petites avant de l’exécuter sur `/content/dam`.

>[!TIP]
>
>Vous pouvez vérifier si tous les fichiers du dossier sont correctement mis à niveau et si toutes les fonctionnalités ne fonctionnent que pour ce dossier.

| URL du point d’entrée | Type de requête | Paramètre de requête | Résultats attendus |
|---|---|---|---|
| `/bin/guides/uuid_upgrade`<br><br> **Par exemple**: `http://localhost:4502/bin/guides/uuid_upgrade?root=/content/dam/test` | GET | **root**: dossier racine <br>**Valeur**: /content/dam pour le référentiel entier.<br><br>**ignoreImageVersions**<br> **Valeur**: vrai/faux (ignore le traitement des versions d’image). La valeur par défaut est false) | Rapport de migration avec la liste des fichiers migrés avec succès, échec de la mise à niveau, mise à niveau avec des erreurs et temps total. <br><br> **Exemple de résultat**: <br> [INFO] Liste des fichiers en échec : 0 <br>[INFO] Non. de fichiers mis à niveau : 2241 <br>[INFO] Non. de fichiers mis à niveau avec des erreurs : 28 <br>[INFO] Non. de fichiers n’ayant pas pu être mis à niveau : 0 <br> [INFO] Durée totale prise : 0:37:03.131 |

>[!NOTE]
>
> La migration du contenu peut être exécutée au niveau du dossier ou l’intégralité de la `/content/dam` ou sur le même dossier (réexécuter la migration).

En outre, il est important de s’assurer que la migration du contenu est également effectuée pour toutes les ressources multimédias, telles que les images et les graphiques que vous avez utilisés dans le contenu DITA.

#### Migration de base

Exécutez la requête sur le dossier que vous avez déjà migré pour migrer les lignes de base dessus.

| URL du point d’entrée | Type de requête | Paramètre de requête | Résultats attendus |
|---|---|---|---|
| `/bin/guides/baseline_uuid_upgrade`<br><br> **Par exemple**: ` http://localhost:4502/bin/guides/baseline_uuid_upgrade?root=/content/dam/test` | GET | **root**: dossier racine <br> **Valeur**: /content/dam pour le référentiel entier. <br><br> **ignoreImageVersions**<br> **Valeur**: true/false <br>(Ignore le traitement des versions d’image. La valeur par défaut est false) <br><br> **doReviews** <br> **Valeur**: true/false <br> (Si les révisions doivent être mises à niveau ou non. La valeur par défaut est false.) Rapport de migration avec la liste des fichiers migrés avec succès, échec de la mise à niveau, mise à niveau avec des erreurs et temps total. <br> <br> **Exemple de résultat**:<br>[INFO] Échec de la liste des fichiers <br> [INFO] Non. de fichiers mis à niveau avec succès 241<br> [INFO] Non. de fichiers mis à niveau avec des erreurs 28<br>[INFO] Non. de fichiers n’ayant pas pu mettre à niveau 0<br>[INFO] Durée totale prise : 0:37:03.131 |


### Etape 3 : restauration de la configuration

Une fois la migration du serveur terminée, activez les workflows de post-traitement, de balisage et suivants (y compris tous les autres workflows initialement désactivés lors de la migration) pour continuer à fonctionner sur le serveur.

* Workflow Ressource de mise à jour de la gestion des DAM
* Workflow de métadonnées de gestion des actifs numériques

>[!NOTE]
>
>Si certains fichiers ne sont pas traités ou sont corrompus avant la migration, ils seront corrompus avant la migration et resteront corrompus même après la migration.

## Validation de la migration

1. Installez le package de migration post uuid (`com.adobe.guides.post-uuid-migration-1.0.2.zip`).

1. Exécutez la requête suivante pour vérifier qu’aucune erreur ne s’est produite lors de la migration, ce qui a entraîné la rupture de tous les liens. Ce script identifie les liens qui n’ont pas été rompus auparavant, mais qui ont été rompus maintenant pour une raison quelconque.

   | URL du point d’entrée | Type de requête | Paramètre de requête | Résultats attendus |
   |---|---|---|---|
   | `/bin/guides/get_broken_links` <br> <br> **Par exemple**:<br>`http://localhost:4502/bin/guides/get_broken_links` | GET | S/O | Rapport de migration avec le nombre total de fichiers ayant des UUID rompus et leurs chemins d’accès aux fichiers respectifs. <br> <br> **Exemple de résultat**:<br>[DEBUG] Vérifiez si tous ces GUID sont utilisés dans le contenu.<br>[DEBUG] Nombre total de fichiers ayant potentiellement des UUID rompus : 0 <br>[DEBUG] Chemins ayant potentiellement un UUID rompu:0 |

1. Une fois la migration terminée, la plus grande partie de l’espace disque peut être récupérée en exécutant la compression (voir `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).

## Migration du contenu delta

1. Pour migrer le contenu delta du serveur actif (non UUID) vers le serveur uuid actuel, installez le script de pré-migration sur le serveur non UUID.

1. Exécutez la requête suivante sur l’ensemble du jeu de données (ou sous-dossier) afin d’identifier et d’exporter tous les fichiers modifiés après l’horodatage donné : l’horodatage utilise le format ISO8601 pour les dates et heures ( AAAA-MM-JJTHH:mm:s.SSSZ) et permet également des représentations partielles, comme AAAA-MM-JJ.

   | URL du point d’entrée | Type de requête | Paramètre de requête | Résultats attendus |
   |---|---|---|---|
   | `/bin/guides/data_export`<br><br>**Par exemple**: <br> `http://localhost:4502/bin/guides/data_export?timestamp=2023-07-11&root=/content/dam` | GET | **timestamp** <br> **Valeur**: AAAA-MM-JJ<br><br> **root**: dossier racine <br> **Valeur**: `/content/dam` pour l’ensemble du référentiel. | Un fichier zip avec du contenu delta est créé dans /var/dxml/exports. <br> <br>**Exemple**: dataexport_1689761491218.zip (le fichier est créé) |

1. Téléchargez le fichier zip exporté par le script. La dernière ligne de la réponse doit indiquer le chemin d’accès au fichier zip généré (stocké dans /var/dxml/exports dans le système).

1. Téléchargez le fichier zip sur le serveur uuid à l’emplacement souhaité dans l’interface utilisateur d’Assets.

1. Vérifiez que le package post-migration est installé sur le serveur uuid.

1. Exécutez la requête donnée suivante pour importer le contenu delta du fichier zip téléchargé dans le système. La requête doit inclure le chemin d’accès au fichier zip chargé afin d’identifier et de traiter correctement les données.

   | URL du point d’entrée | Type de requête | Paramètre de requête | Résultats attendus |
   |---|---|---|---|
   | `/bin/guides/data_import`<br> **Par exemple**:`http://localhost:4502/bin/guides/data_import?path=/content/dam/dataexport_1689344927551.zip&createVersion=true` | POST | **Chemin.**<br> **Valeur**: `/content/dam/filename.zip`(Emplacement du fichier téléchargé) **createVersion** <br> **Valeur**: true/false<br>(La valeur par défaut de createVersion est false). | Le fichier est téléchargé vers le chemin d’accès au contenu souhaité.<br><br>**Exemple**: `dataexport_1689761491218.zip`<br><br> (Le même fichier qui a été exporté à l’étape précédente est téléchargé vers le chemin d’accès souhaité dans `/content/dam`). |

1. Le script crée un nouveau fichier s’il n’existe pas ou remplace le fichier existant s’il a été modifié.

>[!NOTE]
>
> L’historique des versions et toute autre modification apportée sur le serveur (comme les workflows et les révisions ) doivent être mis à jour manuellement.
