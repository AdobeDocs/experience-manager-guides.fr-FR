---
title: Convertir du contenu non UID avec des versions en contenu UID à partir de l’interface utilisateur
description: Découvrez comment migrer le contenu non UUID avec les versions 4.3.x.
source-git-commit: f18c19eb493cd4d2003f68b082e71ebe7b3e6b7a
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 1%

---

# Migration de contenu non UUID avec des versions depuis l’interface utilisateur

Si vous utilisez la version 4.3.x ou ultérieure, procédez comme suit pour migrer votre contenu non UUID avec des versions vers le contenu UUID.

## Matrice de compatibilité

| Version actuelle d’AEM Guides (non UUID) | Version requise pour la migration vers UUID | Chemin de mise à niveau pris en charge |
|---|---|---|
| 4.3.x ou version ultérieure | 4.3.0 non UUID | Installation de 4.3.1 (UUID) |

## Packages requis

1. **Purge de version** : `com.adobe.guides.version-purge-1.0.11.zip` (facultatif)
1. **Avant-migration** : `com.adobe.guides.pre-uuid-migration-1.1.2 .zip`
1. **Migration** : `com.adobe.guides.uuid-upgrade-1.1.13.zip`



## Avant migration

1. (Facultatif) Effectuez la purge des versions sur le contenu pour supprimer les versions inutiles et accélérer le processus de migration. Pour effectuer la purge de version sur la version 4.1 (NON prise en charge sur la version 4.0), installez le package `com.adobe.guides.version-purge-1.0.11.zip`, puis accédez à l’interface utilisateur à l’aide de cette URL `http://<server-name> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`.

   >[!NOTE]
   >
   >Cet utilitaire ne supprime aucune version utilisée dans les lignes de base ou les révisions, ni ne comporte d’étiquettes.
1. Installez le package de pré-migration (`ccom.adobe.guides.pre-uuid-migration-1.1.2 .zip`).

   >[!NOTE]
   >
   >* Vous avez besoin de l’autorisation d’administrateur pour exécuter la migration.
   >* Il est recommandé de corriger les fichiers en erreur avant de poursuivre la migration.

1. Sélectionnez **Évaluation de la compatibilité** dans le panneau de gauche et recherchez un chemin d’accès au dossier.
1. Vérifiez la compatibilité pour lister les informations suivantes :
   * Total des fichiers
   * Versions totales
   * Durée estimée de la migration
   * Nombre de fichiers en erreur



![ Onglet d&#39;évaluation de la compatibilité dans la migration](assets/migration-compatibility-assessment.png){width="800" align="left"}


1. Sélectionnez **Configurer les validations** dans le panneau de gauche. Ensuite, **Sélectionnez map** et **sélectionnez preset** de la carte pour les configurer. La liste de validation de sortie actuelle affiche les fichiers de sortie présents avant la migration et peut être validée par rapport aux fichiers de sortie générés après la migration.

![ Onglet Configurer les validations dans la migration](assets/migration-configure-validation.png){width="800" align="left"}




## Migration

### Etape 1 : mise à jour de la configuration

1. Assurez-vous que l’espace disponible est au moins 10 fois supérieur à l’espace utilisé par AEM (répertoire crx-quickstart) pendant la migration. Une fois la migration terminée, vous pouvez récupérer la plus grande partie de l’espace disque en exécutant la compression (voir [Nettoyage des révisions](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=fr)).

1. Activez *Activer les lanceurs de processus de traitement Post* dans `com.adobe.fmdita.config.ConfigManager` et *Activer le posttraitement de version* dans `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Installez la version UID de la version prise en charge sur la version non UUID. Par exemple, si vous utilisez une version 4.0 non UUID ou une version 4.1 non UUID, vous devez installer UID version 4.1.

1. Installez le nouveau package pour la migration uuid (`com.adobe.guides.uuid-upgrade-1.1.13`).

1. Désactivez les workflows suivants et tout autre workflow s&#39;exécutant sur `/content/dam` à l&#39;aide de lanceurs dans `http://localhost:4502/libs/cq/workflow/content/console.html`.

   * Workflow Ressource de mise à jour de la gestion des DAM
   * Workflow d’écriture différée des métadonnées de gestion des actifs numériques

1. Désactivez *Activer les lanceurs de processus de traitement Post* dans `com.adobe.fmdita.config.ConfigManager` et désactivez *Activer le posttraitement de version* dans `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`.

1. Désactivez la propriété Activer la validation (`validation.enabled`) dans le service de balisage Day CQ.

1. Assurez-vous que le dossier de propriétés `uuid.regex` est correctement défini dans `com.adobe.fmdita.config.ConfigManager`. S’il est vide, définissez-le sur la valeur par défaut : `^GUID-(?<id>.*)`.
1. Ajoutez un journal distinct pour `com.adobe.fmdita.uuid.upgrade.UuidUpgrade`. La réponse du navigateur est également disponible à l’adresse `/content/uuid-upgrade/logs`.

### Etape 2 : lancer la migration et valider

#### Installation du package de migration

![Onglet Mise à niveau du système dans la migration](assets/migration-system-upgrade.png){width="800" align="left"}

* Sélectionnez **Mise à niveau du système** dans le panneau de gauche pour exécuter la migration. Démarrez sur un dossier contenant des données plus petites avant de l’exécuter sur `/content/dam`.

* Sélectionnez **Télécharger le rapport** pendant la migration pour vérifier si tous les fichiers du dossier sont correctement mis à niveau et si toutes les fonctionnalités ne fonctionnent que pour ce dossier.


>[!NOTE]
>
> La migration du contenu peut être exécutée au niveau du dossier ou sur l’ensemble `/content/dam` ou sur le même dossier (réexécuter la migration).

En outre, il est important de s’assurer que la migration du contenu est également effectuée pour toutes les ressources multimédias, telles que les images et les graphiques que vous avez utilisés dans le contenu DITA.

#### Migration de référence et de révision

Sélectionnez **Mise à niveau de référence/révision** dans le panneau de gauche pour migrer les lignes de base et la révision au niveau du dossier.

![Onglet Ligne de base et révision dans la migration](assets/migration-baseline-review-upgrade.png){width="800" align="left"}


### Etape 3 : restauration de la configuration

Une fois la migration du serveur terminée, activez les workflows de post-traitement, de balisage et suivants (y compris tous les autres workflows initialement désactivés lors de la migration) pour continuer à fonctionner sur le serveur.

* Workflow Ressource de mise à jour de la gestion des DAM
* Workflow de métadonnées de gestion des actifs numériques

>[!NOTE]
>
>Si certains fichiers ne sont pas traités ou sont corrompus avant la migration, ils seront corrompus avant la migration et resteront corrompus même après la migration.

## Validation de la migration

Une fois la migration terminée, sélectionnez **Valider la mise à niveau du système** dans le panneau de gauche et validez les fichiers de sortie avant et après la migration pour vous assurer que la migration est réussie.

![Valider l’onglet de mise à niveau du système dans la migration](assets/migration-validate-system-upgrade.png){width="800" align="left"}


1. Une fois la migration terminée, la plus grande partie de l&#39;espace disque peut être récupérée en exécutant la compression (voir `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).

