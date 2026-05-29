---
title: Notes de mise à jour | Instructions de mise à niveau pour la version 5.2.0 d’Adobe Experience Manager Guides
description: Découvrez la matrice de compatibilité et comment effectuer une mise à niveau vers la version 5.2.0 d’Adobe Experience Manager Guides.
source-git-commit: 1dc529ba8913c30fba876f101c3b52474e8a71dd
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 4%

---

# Instructions de mise à niveau pour la version 5.2.0 (mai 2026)

Cet article couvre les instructions de mise à niveau et la matrice de compatibilité pour la version 5.2.0 d’Adobe Experience Manager Guides.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, consultez [Nouveautés de la version 5.2.0](../release-info/whats-new-5-2-0.md).

Pour obtenir la liste des problèmes qui ont été résolus dans cette version, voir [Problèmes résolus dans la version 5.2.0](../release-info/fixed-issues-5-2-0.md).

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par la version 5.2.0 de Experience Manager Guides.

| AEM Guides | Version d’AEM | Pack de services |
| --- | --- | --- |
| 5.2.0 (UUID) | 6.5 LTS | 2 |
| 5.2.0 (UUID) | 6.5 | 24, 23, 22 |

Pour plus d&#39;informations, consultez la section [Exigences techniques](../install-guide/download-install-technical-requirements.md) dans le Guide d&#39;installation et de configuration On-Premise.

### FrameMaker et FrameMaker Publishing Server

| Version | FMPS | FM |
| --- | --- | --- |
| 5.2.0 (UUID) | Pris en charge | 2026 ou version ultérieure |

### Connecteur D&#39;Oxygène

| Version | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 5.2.0 (UUID) | 3.8-uuid.1 | 3.8-uuid.1 | 2,3 | 2,3 |

### Version du modèle de la base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Package de contenu de composants Experience Manager Guides pour Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |

### Nouvelle version du modèle de site AEM


| AEM Guides | Version d’AEM | Version des composants | Version du site |
|---|---|---| ---|
| 5.2.0 UUID | 6.5 LTS | guides-components.all-1.4.1 | S/O |
| 5.2.0 UUID | 6.5 | guides-components.all-1.4.0 | aemg-sites-template-1.3.0 |

## Prérequis

Avant de lancer le processus de mise à niveau vers Experience Manager Guides 5.2.0, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 5.0.0, 5.0.3, 5.1.0, 5.1.3 ou 5.1.4.
1. (Facultatif) A fermé toutes les tâches de traduction.
1. Modification du niveau de journal en **INFO** pour `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` classe et ajout de ces journaux dans un nouveau fichier journal, par exemple, `logs/translation_upgrade.log`.

## Chemin de mise à niveau vers Experience Manager Guides 5.2.0

Vous pouvez facilement mettre à niveau votre version actuelle de Experience Manager Guides vers la version 5.2.0 sur **AEM 6.5** ou **AEM 6.5 LTS**.

>[!IMPORTANT]
>
> - **Pour AEM 6.5 LTS** : Experience Manager Guides 5.2.0 est pris en charge uniquement avec AEM 6.5 LTS Service Pack 2.
> - **Pour AEM 6.5** : Experience Manager Guides 5.2.0 est pris en charge uniquement avec AEM 6.5 Service Pack 24, 23 et 22.
> - Si vous utilisez actuellement AEM 6.5 et envisagez de passer à AEM 6.5 LTS, veillez à effectuer d’abord la mise à niveau d’AEM avant de poursuivre la mise à niveau vers Experience Manager Guides 5.2.0. Pour plus d’informations, consultez la section [Mise à niveau vers Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/fr/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

Avant de procéder à la mise à niveau vers la version 5.2.0 de Experience Manager Guides, vous devez tenir compte des points suivants :

- Si vous utilisez la version 5.0.0, 5.0.3, 5.1.0, 5.1.3 ou 5.1.4, vous pouvez directement effectuer la mise à niveau vers la version 5.2.0.
- Si vous utilisez les versions 4.6.3, 4.6.4 et 5.0.x, vous pouvez directement effectuer la mise à niveau vers la version 5.1.0.
- Si vous utilisez la version 4.6.0 ou 4.6.1, vous devez effectuer la mise à niveau vers la version 4.6.3, 4.6.4 ou 5.0.0 avant d’effectuer la mise à niveau vers la version 5.1.0.
- Si vous utilisez la version 4.3.x, 4.2, 4.2.1 (correctif 4.2.1.3), 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers la version 4.4 avant d’effectuer la mise à niveau vers la version 5.1.0.
- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant d’effectuer la mise à niveau vers la version 4.3.x.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à la version 3.8.5, reportez-vous à la section Mise à niveau de Experience Manager Guides dans le guide d’installation spécifique au produit disponible sur [l’archive PDF d’aide d’Adobe Experience Manager Guides](https://helpx.adobe.com/fr/xml-documentation-for-experience-manager/archive.html).

## Processus de mise à niveau vers Experience Manager Guides 5.2.0

>[!IMPORTANT]
>
> Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de démarrer le processus de mise à niveau pendant les heures creuses.

1. Téléchargez le package de la version 5.2.0 à partir du Portail de distribution logicielle [&#128279;](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package de version sur lequel vous souhaitez effectuer la mise à niveau et attendez que le bundle soit installé.
1. *(Facultatif)* Mettre à niveau le plug-in Oxygen Connector fourni avec la version vers laquelle vous effectuez la mise à niveau.
1. Effacez la mémoire cache du navigateur après l’installation du package.
1. Si vous avez activé le paramètre `Enable markup find and replace` pour accéder à la fonction Rechercher et remplacer dans la vue source du contenu précédemment capturé, vous devez réindexer l’index `guidesAssetLucene`. Pour plus d’informations, consultez [Réindexation pour la recherche et le remplacement](../install-conf-guide/custom-indexing-on-prem.md).
1. Mettez à jour la configuration du système pour incorporer les nouveaux paramètres introduits dans la version 5.2.0, en veillant à ce que les améliorations suivantes soient prises en charge :


| Configurations ajoutées | Fichier de configuration | Afficher le libellé du paramètre | Nom du paramètre |
|-----|-----|------|-----|
| Activation ou désactivation du nouvel éditeur | `com.adobe.fmdita.config.ConfigManager` | Activer l’éditeur 2.0 | `enable.markup.editor` |
| Activer ou désactiver la nouvelle ligne de base | `com.adobe.fmdita.config.ConfigManager` | Activer une ligne de base plus rapide (v2) | `enable.baseline.v2` |
| Ignorer les propriétés de métadonnées pour marquer une version comme sale | `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | Ignorer la propriété de métadonnées pour la version incorrecte | `xmleditor.dirtychecker.ignoremetadata` |
| Fonction de recherche et de remplacement dans la vue Source | `com.adobe.fmdita.config.ConfigManager` | Activer la recherche et le remplacement des balises | `enable.markup.findreplace` |
| Activer ou désactiver l&#39;omission des liens d&#39;homologue pour l&#39;ancienne ligne de base | `com.adobe.fmdita.config.ConfigManager` | Ignorer les liens d’homologue pour la ligne de base V1 | `guides.baseline.v1.skip.peer.links` |
| Activez ou désactivez l’initialisation des copies de destination avec le contenu source dans le workflow de traduction. Cela s’applique uniquement lorsque le workflow de traduction hérité est désactivé.  | `com.adobe.fmdita.config.ConfigManager` | Initialiser la copie de langue de destination avec le contenu source | `translation.workflow.propagate.source.content` |
| Nettoyage du magasin de référence | `com.adobe.fmdita.config.ConfigManager` | Guides avec suppression d’arborescence activée | `btree.deletion.enabled` |
| Réplication des ressources DITA | `com.adobe.fmdita.config.ConfigManager` | Réplication des ressources DITA | `publish.replicate` |
| Traitement des ressources | `com.adobe.fmdita.config.ConfigManager` | Activer la tâche planifiée de traitement des ressources Guides | `enable.asset.processing.scheduler` |

Pour plus d’informations sur ces paramètres de configuration, voir [Mises à jour de la configuration](../install-conf-guide/configuration-on-prem.md).







