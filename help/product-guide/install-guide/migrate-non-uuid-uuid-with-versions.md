---
title: Conversion de contenu non UID avec des versions en contenu UID
description: Découvrez comment migrer du contenu non UUID avec des versions vers du contenu UID.
feature: Migration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 1%

---

# Migration de contenu versionné

Effectuez les étapes suivantes pour migrer votre contenu versionné non UUID vers le contenu UID.

>[!NOTE]
>
>Suivez la [instructions de mise à niveau](./upgrade-xml-documentation.md) spécifique à la version sous licence de votre produit.

## Matrice de compatibilité

| Version actuelle des guides du Experience Manager (non UUID) | Version requise pour la migration vers UUID | Chemin de mise à niveau pris en charge |
|---|---|---|
| 3.8.5, 4.0.x ou 4.1.x | 4.1 non UUID | Installez la version 4.1 (UUID) et exécutez la migration |
| 4.2, 4.2.x ou 4.3 | 4.3.0 non UUID | Installez la version 4.3.1 (UUID) et exécutez la migration |
| 4.3.1 | N/A | N/A |

## Installation du package

Téléchargez les packages requis à partir du portail de distribution de logiciels Adobe, en fonction de votre version :
<details>
<summary>  Packages pour le chemin de mise à niveau version 4.1</summary>

1. **Avant migration**: [com.adobe.guides.pre-uuid-migration-1.0.9.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F1-0%2Fcom.adobe.guides.pre-uuid-migration-1.0.9.zip)
1. **Migration**: [com.adobe.guides.uuid-upgrade-1.0.19.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F1-0%2Fcom.adobe.guides.uuid-upgrade-1.0.19.zip)
</details>


<details>
<summary> Packages pour le chemin de mise à niveau version 4.3.1</summary>

1. **Avant migration**: [com.adobe.guides.pre-uuid-migration-1.1.3.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2Fcom.adobe.guides.pre-uuid-migration-1.1.3.zip)
1. **Migration**: [com.adobe.guides.uuid-upgrade-1.1.15.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2Fcom.adobe.guides.uuid-upgrade-1.1.15.zip)

</details>

## Avant migration

Effectuez les vérifications suivantes sur la version non UUID (4.1 non UUID ou 4.3.0 non UUID) :

1. Installez le package de pré-migration en fonction de votre version.

   >[!NOTE]
   >
   >* Vous avez besoin de l’autorisation d’administrateur pour exécuter la migration.
   >* Il est recommandé de corriger les fichiers en erreur avant de poursuivre la migration.

1. (Facultatif) Effectuez la purge des versions sur le contenu pour supprimer les versions inutiles et accélérer le processus de migration. Pour effectuer la purge de version, sélectionnez l’option . **Purge de version** à partir de l’écran de migration et accédez à l’interface utilisateur à l’aide de l’URL . `http://<server- name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.
   >[!NOTE]
   >
   >Cet utilitaire ne supprime aucune version utilisée dans les lignes de base ou les révisions, ni ne comporte d’étiquettes.

1. Launch `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.
1. Sélectionner **Évaluation de la compatibilité**  dans le panneau de gauche, puis parcourez un chemin d’accès au dossier.
1. Vérifiez la compatibilité pour lister les informations suivantes :
   * Fichiers totaux
   * Versions totales
   * Durée estimée de la migration
   * Nombre de fichiers en erreur

   ![onglet évaluation de la compatibilité dans la migration](assets/migration-compatibility-assessment.png){width="800" align="left"}


1. Sélectionner **Configuration des validations** dans le panneau de gauche. Alors, **Sélectionner une carte** et **Sélectionner un paramètre prédéfini** de la carte pour les configurer. La liste de validation de sortie actuelle affiche les fichiers de sortie présents avant la migration et peut être validée par rapport aux fichiers de sortie générés après la migration.

   ![Configuration de l’onglet Validations dans la migration](assets/migration-configure-validation.png){width="800" align="left"}




## Migration

### Etape 1 : mise à jour de la configuration

1. Assurez-vous que l’espace disponible est au moins dix fois supérieur à l’espace utilisé par AEM (répertoire crx-quickstart) pendant la migration. Une fois la migration terminée, vous pouvez récupérer la plus grande partie de l’espace disque en exécutant la compression (voir [Nettoyage des révisions](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=fr)).

1. Activer *Activation des lanceurs de workflow de post-traitement* in `com.adobe.fmdita.config.ConfigManager` et *Activation du post-traitement des versions* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Installez la version UID de la version prise en charge sur la version non UUID. Par exemple, si vous utilisez une version 4.1 non UUID, vous devez installer UID version 4.1 et exécuter la migration.

1. Installez le nouveau package pour la migration uuid.

1. Désactivez les workflows suivants et tout autre workflow qui s’exécute sur `/content/dam` utilisation des lanceurs dans `http://<server-name>/libs/cq/workflow/content/console.html`.

   * Workflow Ressource de mise à jour de la gestion des DAM
   * Workflow d’écriture différée des métadonnées de gestion des actifs numériques

1. Désactiver *Activation des lanceurs de workflow de post-traitement* in `com.adobe.fmdita.config.ConfigManager` et désactiver *Activation du post-traitement des versions* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`.

1. Désactivez la propriété Activer la validation (`validation.enabled`) dans le service de balisage Day CQ.

1. Assurez-vous que `uuid.regex` Le dossier de propriétés est correctement défini dans `com.adobe.fmdita.config.ConfigManager`. S’il est vide, définissez-le sur la valeur par défaut - `^GUID-(?<id>.*)`.
1. Ajouter un journal distinct pour `com.adobe.fmdita.uuid` La réponse du navigateur est également disponible sur la page `/content/uuid-upgrade/logs`.

### Etape 2 : lancer la migration et valider

#### Installation du package de migration

1. Launch `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.

   ![Onglet Mise à niveau du système dans la migration](assets/migration-system-upgrade.png){width="800" align="left"}

1. Sélectionner **Mise à niveau du système** dans le panneau de gauche pour exécuter la migration. Commencez sur un dossier contenant des données plus petites avant de l’exécuter sur `/content/dam`.

1. Sélectionner **Télécharger le rapport** pendant la migration pour vérifier si tous les fichiers du dossier sont correctement mis à niveau et si toutes les fonctionnalités ne fonctionnent que pour ce dossier.


>[!NOTE]
>
> La migration du contenu peut être exécutée au niveau du dossier, la `/content/dam`ou le même dossier (réexécuter la migration).

En outre, il est important de s’assurer que la migration du contenu est effectuée pour toutes les ressources multimédias, telles que les images et les graphiques que vous avez utilisés dans le contenu DITA.

#### Migration de référence et de révision

Sélectionner **Mise à niveau de référence/révision** dans le panneau de gauche pour migrer les lignes de base et effectuer une révision au niveau du dossier.

![Onglet Référence et révision de la migration](assets/migration-baseline-review-upgrade.png){width="800" align="left"}


### Etape 3 : restauration de la configuration

Une fois la migration du serveur réussie, activez le post-traitement, le balisage et les workflows suivants (y compris tous les autres workflows désactivés initialement pendant la migration) pour continuer à fonctionner sur le serveur.

* Workflow Ressource de mise à jour de la gestion des DAM
* Workflow de métadonnées de gestion des actifs numériques

>[!NOTE]
>
>Si certains fichiers ne sont pas traités ou corrompus avant la migration, ils seront corrompus avant la migration et resteront corrompus même après la migration.

## Validation de la migration

1. Une fois la migration terminée, sélectionnez **Validation de la mise à niveau du système** dans le panneau de gauche et validez les fichiers de sortie avant et après la migration pour vous assurer que la migration est réussie.

   ![Onglet Validation de la mise à niveau du système dans la migration](assets/migration-validate-system-upgrade.png){width="800" align="left"}


1. Une fois la validation terminée, la plupart de l’espace disque peut être récupéré en exécutant la compression (voir `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).

