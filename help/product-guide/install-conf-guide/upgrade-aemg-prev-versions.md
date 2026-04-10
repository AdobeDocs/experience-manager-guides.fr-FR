---
title: Mise À Niveau Des Versions Précédentes D’Adobe Experience Manager Guides On-Premise
description: Découvrez comment mettre à niveau Adobe Experience Manager Guides
feature: Installation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '3159'
ht-degree: 0%

---

# Mise à niveau d’Adobe Experience Manager Guides On-Premise (version 4.4.0 et antérieure)

Cet article fournit des instructions pour mettre à niveau les versions d’**&#x200B;** **antérieures à la version 4.6.0** **(jusqu’à la version 4.4.0 incluse**).

Si vous utilisez une version **antérieure à la version 3.8.5**, reportez-vous à la section **Mettre à niveau Experience Manager Guides** du guide d’installation spécifique au produit disponible sur [l’archive PDF de l’aide d’Adobe Experience Manager Guides](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

Pour obtenir des instructions de mise à niveau pour les versions plus récentes, reportez-vous à [Mise à niveau d’Adobe Experience Manager Guides vers les versions 4.6.0 et ultérieures](./upgrade-aemg-latest-version.md).

## Avant de commencer

>[!NOTE]
>
> Vous devez suivre les instructions de mise à niveau spécifiques à la version sous licence de votre produit et installer le pack de services AEM avant de mettre à niveau la version de Experience Manager Guides.

>[!IMPORTANT]
>
> Avant de commencer la mise à niveau, effectuez une **sauvegarde complète du système** pour éviter toute perte de données.

## Chemins de mise à niveau abordés dans cet article

Cet article comprend des procédures pour :

- [Mise à niveau vers la version 4.4.0](#upgrade-to-version-440)
- [Mettre à niveau vers la version 4.3.1.5](#upgrade-to-version-4315)
- [Mise à niveau vers la version 4.3.1](#upgrade-to-version-431)
- [Mise à niveau vers la version 4.3.0](#upgrade-to-version-430)
- [Mise à niveau vers la version 4.2.1](#upgrade-to-version-421)
- [Mise à niveau vers la version 4.2](#upgrade-to-version-42)
- [Mise à niveau de 3.8.5 vers la version 4.0](#upgrade-from-version-385-to-version-40)


## Conditions préalables globales (s&#39;applique à toutes les mises à niveau sauf indication contraire d&#39;une procédure)

Avant d’exécuter le processus de mise à niveau, effectuez les tâches suivantes :

1. Importez les commentaires de révision dans les rubriques ouvertes à la révision.
2. Fermez tous les avis actifs.
3. Fermez toutes les tâches de traduction.
4. Désinstallez tous les correctifs Experience Manager Guides installés par-dessus la version précédente (version majeure ou correctif).

Certaines mises à niveau nécessitent également de définir le niveau de journal sur `INFO` pour une classe de mise à niveau de traduction et de consigner dans un fichier distinct ; ces exigences sont décrites dans la ou les procédures de mise à niveau appropriées.

## Mise à niveau de la version 3.8.5 vers la version 4.0

>[!NOTE]
>
> Ce processus de mise à niveau est applicable **uniquement** de la version **3.8.5** à la version **4.0**. Pour les mises à niveau de **3.4 ou version ultérieure** vers **3.8.5**, reportez-vous au guide d’installation spécifique au produit disponible sur [l’archive Adobe Experience Manager Guides Help PDF](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

Si vous utilisez la version **3.8.5 de Experience Manager Guides** vous pouvez effectuer la mise à niveau vers la version **4.0** sans désinstaller la version précédente.

### Avant l’installation de la version 4.0

1. Assurez-vous que Experience Manager Guides est sur la version **3.8.5**.
2. Téléchargez le package du script de mise à niveau : recherchez **« Package de mise à niveau de la solution XML Documentation 4.0 »** sur le portail de distribution de logiciels Adobe (télécharge un `.zip`).
3. Téléchargez le package dans AEM via **Gestionnaire de packages** et installez-le.
4. Une fois le package de mise à niveau installé, exécutez les scripts dans l’ordre décrit ci-dessous.

**Vérifier l’API de compatibilité de mise à niveau**

Cette API est conçue pour évaluer l’état actuel du système et signaler si la mise à niveau est possible ou non. Pour exécuter ce script, déclenchez le point d’entrée donné ci-dessous :

| Point d’entrée | /bin/dxml/upgrade/3xto4x/report |
| --- | --- |
| Type de demande | **&#x200B;**&#x200B;<br> **Remarque** : vous pouvez utiliser un navigateur web dans lequel vous êtes connecté à l’instance AEM en tant qu’administrateur. |
| Réponse attendue | -   Si tous les nœuds requis peuvent être déplacés, la vérification sera réussie. <br>-   Si un nœud est présent à l’emplacement cible, vous obtiendrez une erreur pertinente. Nettoyez le référentiel \(supprimez le nœud /var/dxml\), réinstallez le package de mise à niveau, puis déclenchez à nouveau ce point d’entrée. <br>**Remarque :** il ne s’agit pas d’une erreur courante, car l’emplacement cible n’est pas utilisé auparavant par Experience Manager Guides 3.x. <br> -   Si ce script échoue, ne continuez pas et signalez-le à votre équipe de succès client. |

**API System data migration**

Cette API est conçue pour migrer les données système comme indiqué dans la section **Mappage de migration**.

1. N’exécutez pas ce script si la vérification de la compatibilité de mise à niveau de l’API échoue \(ne pas continuer\).
1. Une fois que la vérification de la compatibilité de mise à niveau de l’API a réussi, vous pouvez exécuter le script de mise à niveau.

| Point d’entrée | /bin/dxml/upgrade/3xto4x |
| --- | --- |
| Type de demande | **POST** <br>**Remarque** : ce script est une requête POST et doit donc être exécuté par le biais d’agents tels que Postman. |
| Réponse attendue | -   Une fois la migration réussie, vous pouvez installer la solution XML Documentation version 4.0.<br>-   En cas d’erreur, restaurez le dernier point de contrôle et partagez les journaux d’erreurs ainsi que la sortie de l’API avec votre équipe du succès client. |


**Mappage de migration**

Cette API migre toutes les données de l’emplacement source vers l’emplacement cible.

| Source | Cible |
|------|------|
| /content/fmdita | /var/dxml |
| /content/dxml | /var/dxml |
| /etc/fmdita | /libs/fmdita |

### Installation version 4.0

1. Installez la version 4.0 uniquement si les étapes de mise à niveau ont réussi.
1. Téléchargez le package de la version 4.0 à partir du portail de distribution logicielle [&#128279;](https://experience.adobe.com/#/downloads/content/software-distribution/fr/aem.html) :

   - Si vous utilisez la version UUID du logiciel, recherchez « Version UUID 4.0 pour la solution XML Documentation pour AEM 6.5 ».
   - Si vous utilisez une version non UUID du logiciel, recherchez « Version 4.0 non UUID pour XML Documentation solution for AEM 6.5 ».
Téléchargez le package sur la ou les instances de serveur AEM existantes à l’aide du gestionnaire de packages CRX et installez-le.

     >[!NOTE]
     >
     > Attendez que tous les composants système démarrent.

1. Effacez la mémoire cache du navigateur après l’installation du package.
1. Si un Dispatcher est configuré sur l’instance d’auteur AEM, procédez comme suit :
   - Assurez-vous que les éléments suivants sont gérés dans les règles du Dispatcher :
   - Le modèle d’URL /home/users/\*/preferences figure sur la liste autorisée.
   - Le modèle d’URL /libs/cq/security/userinfo.json n’est pas mis en cache.
1. Effacez le cache du Dispatcher \(pour effacer tout `clientlibs` mis en cache\).

## Mise à niveau vers la version 4.2

Vous pouvez effectuer directement la mise à niveau vers la version **4.2** si vous utilisez la version **4.0**, **4.1** ou **4.1.x**.

### Avant l’installation de la version 4.2

Avant de lancer le processus de mise à niveau vers Experience Manager Guides 4.2, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides **4.0**, **4.1** ou **4.1.x**.
2. A fermé toutes les tâches de traduction.
3. Définissez le niveau du journal sur `INFO` pour les `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` et enregistrez-le dans un nouveau fichier journal (par exemple, `logs/translation_upgrade.log`).

   >[!NOTE]
   > 
   > Vous devriez fermer tous les avis actifs. Si les révisions ne sont pas fermées lors de la mise à niveau vers la version 4.2, les anciennes tâches de révision en cours peuvent continuer à ouvrir les anciennes pages de révision. Les nouvelles tâches de révision créées après la mise à niveau affichent les dernières mises à jour des fonctionnalités.

### Installer la version 4.2

1. Téléchargez le package **4.2** à partir du portail de distribution logicielle [Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
2. Installez le package 4.2.
3. Après l’installation, attendez le message suivant dans les journaux :

   `Completed the post deployment setup script`

   Le message ci-dessus indique que toutes les étapes d’installation sont terminées.

   Si vous rencontrez l’une des erreurs suivantes, signalez-les au service client :

   - `Error in post deployment setup script`
   - `Exception while porting the translation MAP`
   - `Unable to port translation map from v1 to v2 for property`

4. (Facultatif) Mise à niveau du plug-in du connecteur Oxygen publié avec la version 4.2.
5. Effacez la mémoire cache du navigateur après l’installation du package.
6. Continuez la mise à niveau des personnalisations comme décrit dans la section suivante.

### Après avoir installé la version 4.2

>[!IMPORTANT]
>
> Le modèle high-tech ne s’affiche pas sur le serveur mis à niveau. Pour inclure le modèle high-tech sur votre serveur, vous pouvez le copier : Source : `/libs/fmdita/pdf/Hi-Tech` Destination : `/content/dam/dita-templates/pdf`.

Effectuez ensuite les tâches partagées après la mise à niveau dans [Tâches communes après la mise à niveau (toutes les versions)](#common-postupgrade-tasks-all-versions).

## Mise à niveau vers la version 4.2.1

>[!TIP]
>
> Il est recommandé d’installer **correctif4.2.1.3** sur la version **4.2.1**.

Vous pouvez effectuer directement la mise à niveau vers la version **4.2.1** si vous utilisez **4.1**, **4.1.x** ou **4.2**.

>[!NOTE]
>
> Le post-traitement et l’indexation peuvent prendre quelques heures. Démarrez la mise à niveau pendant les heures creuses.

### Avant l’installation de la version 4.2.1

1. Mise à niveau vers Experience Manager Guides **4.1**, **4.1.x** ou **4.2**.
2. Fermez toutes les tâches de traduction.
3. Définissez le niveau de journal sur `INFO` pour les `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` et enregistrez-le dans un nouveau fichier (par exemple, `logs/translation_upgrade.log`).

>[!NOTE]
>
> Vous devez fermer tous les avis actifs (même comportement que 4.2).

### Installation de la version 4.2.1

1. Téléchargez le package **4.2.1** à partir du portail de distribution logicielle [Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
2. Installez le package 4.2.1.
3. Déclenchez éventuellement la tâche de mise à niveau de la carte de traduction. Pour plus d’informations, consultez [&#x200B; Activation du déclencheur de script via une servlet](#enable-trigger-of-script-via-a-servlet).

4. Après l’installation, attendez : `Completed the post deployment setup script` dans les journaux.

   Signalez ces erreurs au succès client :

   - `Error in post deployment setup script`
   - `Exception while porting the translation MAP`
   - `Unable to port translation map from v1 to v2 for property`
5. (Facultatif) Mise à niveau du plug-in Oxygen connector publié avec la version **4.2**
6. Effacez le cache du navigateur.
7. Poursuivez avec [Tâches courantes après la mise à niveau (toutes les versions)](#common-postupgrade-tasks-all-versions).

### Après avoir installé la version 4.2.1

>[!IMPORTANT]
>
> Le modèle high-tech ne s’affiche pas sur le serveur mis à niveau. Pour inclure le modèle high-tech sur votre serveur, vous pouvez le copier : Source : `/libs/fmdita/pdf/Hi-Tech` Destination : `/content/dam/dita-templates/pdf`.

Continuez avec [les tâches courantes après la mise à niveau (toutes les versions)](#common-postupgrade-tasks-all-versions) et (si nécessaire) [indexez le contenu existant pour mapper, rechercher et remplacer](#index-existing-content-for-map-find-and-replace).


## Mise à niveau vers la version 4.3.0

La mise à niveau vers la version 4.3.0 dépend de la version actuelle de Experience Manager Guides. Si vous utilisez la version 4.2 ou 4.2.x, vous pouvez directement effectuer la mise à niveau vers la version 4.3.0.

>[!NOTE]
>
>Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de démarrer le processus de mise à niveau pendant les heures creuses.

### Avant l’installation de la version 4.3.0

Avant de lancer le processus de mise à niveau vers Experience Manager Guides 4.3.0, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 4.2 ou 4.2.x et achèvement des étapes d’installation respectives.
1. A fermé toutes les tâches de traduction.

### Installation de la version 4.3.0

1. Téléchargez le package de la version 4.3.0 à partir du portail de distribution logicielle [&#128279;](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package de la version 4.3.0.
1. Effacez la mémoire cache du navigateur après l’installation du package.
1. Mettez à niveau le fichier `ui_config.json` à partir de l’onglet **Configuration de l’éditeur XML** dans le profil de dossier.

### Après avoir installé la version 4.3.0

Procédez comme suit :

- [Tâches courantes après la mise à niveau (toutes les versions)](#common-postupgrade-tasks-all-versions)
- Le cas échéant : [post-traitement du contenu existant pour le rapport de lien rompu](#post-process-existing-content-for-broken-link-report)

## Mise à niveau vers la version 4.3.1

La mise à niveau vers la version 4.3.1 dépend de la version actuelle de Experience Manager Guides. Si vous utilisez la version 4.3.0, 4.2 ou 4.2.1, vous pouvez directement effectuer la mise à niveau vers la version 4.3.1.

>[!NOTE]
>
>Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de démarrer le processus de mise à niveau pendant les heures creuses.

### Avant d’installer la version 4.3.1

Avant de lancer le processus de mise à niveau vers Experience Manager Guides 4.3.1, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 4.3.0, 4.2 ou 4.2.1 et achèvement des étapes d’installation respectives.
1. (Facultatif) A fermé toutes les tâches de traduction.
1. Modification du niveau de journal en **INFO** pour `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` classe et ajout de ces journaux dans un nouveau fichier journal, par exemple, `logs/translation_upgrade.log`.

### Installation de la version 4.3.1

1. Téléchargez le package de la version 4.3.1 à partir du portail de distribution logicielle [&#128279;](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package de la version 4.3.1.
1. Déclenchez éventuellement la tâche de mise à niveau de la carte de traduction. Pour plus d’informations, consultez [&#x200B; Activation du déclencheur de script via une servlet](#enable-trigger-of-script-via-a-servlet).
1. Après l’installation, attendez : `Completed the post deployment setup script` dans les journaux.
Signalez ces erreurs au succès client :\
   `Error in post deployment setup script`, `Exception while porting the translation MAP`, `Unable to port translation map from v1 to v2 for property`
1. (Facultatif) Mise à niveau du plug-in Oxygen connector publié avec la version **4.2**.
1. Effacez le cache du navigateur.

### Après avoir installé la version 4.3.1

Procédez comme suit :

- [Tâches courantes après la mise à niveau (toutes les versions)](#common-postupgrade-tasks-all-versions)
- Le cas échéant : [Indexer le contenu existant pour la recherche et le remplacement de carte](#index-existing-content-for-map-find-and-replace)
- Le cas échéant : [post-traitement du contenu existant pour le rapport de lien rompu](#post-process-existing-content-for-broken-link-report)


## Mettre à niveau vers la version 4.3.1.5

Vous pouvez mettre à niveau directement vers **4.3.1.5** si vous utilisez la version **4.3.1**.

### Installer la version 4.3.1.5

1. Téléchargez le package **4.3.1.5** à partir du portail de distribution logicielle [Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
2. Installez le package 4.3.1.5.
3. Attendez que le processus d’installation soit terminé.
4. Continuez la mise à niveau des personnalisations comme décrit dans la section suivante.

## Après l’installation de la version 4.3.1.5

>[!NOTE]
>
>Si vous souhaitez utiliser le bundle org.apache.velocity, effectuez les étapes suivantes avant de charger le bundle :
> 1. Accédez à `<server>:<port>/system/console/bundles`
> 1. Recherchez org.apache.velocity.
> 1. Désinstallez le lot recherché.
> 1. Installez le lot de vitesse requis.

1. Une fois la mise à niveau terminée, assurez-vous que toutes les personnalisations/superpositions sont validées et mises à jour pour correspondre au nouveau code de l’application. Voici quelques exemples :
   - Tous les composants superposés à partir de `/libs/fmdita` ou ` /libs` doivent être comparés au nouveau code de produit et les mises à jour doivent être effectuées dans les fichiers superposés sous `/apps` .
   - Toutes les catégories de bibliothèques clientes utilisées à partir du produit doivent être examinées pour les modifications. Toutes les configurations remplacées \(exemples ci-dessous\) doivent être comparées aux dernières afin d’obtenir les dernières fonctionnalités :
   - `elementmapping.xml`
   - `ui\_config.json\` (peut avoir été défini dans profils de dossier\)
   - `com.adobe.fmdita.config.ConfigManager` modifié


## Mise à niveau vers la version 4.4.0

Vous pouvez effectuer directement la mise à niveau vers **4.4.0** si vous utilisez : **4.3.1**, **4.3.0**, **4.2** ou **4.2.1 (correctif 4.2.1.3)**.

>[!NOTE]
>
>Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de démarrer le processus de mise à niveau pendant les heures creuses.

### Avant l’installation de la version 4.4.0

Avant de lancer le processus de mise à niveau vers Experience Manager Guides 4.4.0, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 4.3.1, 4.3.0 ou 4.2.1 (correctif 4.2.1.3) et achèvement des étapes d’installation respectives.
1. (Facultatif) A fermé toutes les tâches de traduction.
1. Modification du niveau de journal en **INFO** pour `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` classe et ajout de ces journaux dans un nouveau fichier journal, par exemple, `logs/translation_upgrade.log`.

### Installation de la version 4.4.0

1. Téléchargez le package de la version 4.4.0 à partir du portail de distribution logicielle [&#128279;](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
2. Installez le package 4.4.0.
3. Déclenchez éventuellement la tâche de mise à niveau de la carte de traduction. Pour plus d’informations, consultez [&#x200B; Activation du déclencheur de script via une servlet](#enable-trigger-of-script-via-a-servlet).
4. Une fois l’installation du package terminée, attendez le message suivant dans les journaux :

   `Completed the post deployment setup script`

   Le message ci-dessus indique que toutes les étapes d’installation sont terminées.

   Si vous rencontrez l’un des préfixes d’ERREUR suivants, signalez-le à votre équipe du succès client :

   - `Error in post deployment setup script`
   - `Exception while porting the translation MAP`
   - `Unable to port translation map from v1 to v2 for property`
5. (Facultatif) Mise à niveau du plug-in Oxygen connector publié avec la version **4.4.0**.
6. Effacez le cache du navigateur.
7. Continuer avec :

   - [Tâches courantes après la mise à niveau (toutes les versions)](#common-ppostupgrade-tasks-all-versions)
   - [Indexer le contenu existant pour la recherche et le remplacement de carte](#index-existing-content-for-map-find-and-replace) (Uniquement le cas échéant)
   - [Post-traitement du contenu existant pour le rapport sur les liens rompus](#post-process-existing-content-for-broken-link-report) (uniquement le cas échéant)
   - [Mise à niveau de la carte de traduction (déclencheur de servlet)](#translation-map-upgrade-servlet-trigger) (uniquement le cas échéant)


## Tâches courantes après la mise à niveau (toutes les versions)

Après l’installation de Experience Manager Guides, vous devrez peut-être fusionner les configurations applicables de la version nouvellement installée avec votre configuration.

>[!NOTE]
>
> Le modèle de workflow **Ressource de mise à jour de gestion des ressources numériques** peut être personnalisé. Si vous disposez de personnalisations, synchronisez-les avec les modifications Experience Manager Guides dans la copie de travail du modèle.

### Workflow Valider la ressource de mise à jour de gestion des ressources numériques (modifications post-traitement)

1. Ouvrez l’interface utilisateur Modèles de workflow AEM (exemple illustré dans la source) :\
   `http://<host>:4502/libs/cq/workflow/admin/console/content/models.html`
2. Sélectionnez **workflow Ressource de mise à jour de la gestion des ressources numériques**.
3. Sélectionnez **Modifier**.
4. Si le composant **DXML Post Process Initiator** est présent, assurez-vous que les personnalisations sont synchronisées.
5. Si le composant est absent, insérez-le :
   1. Cliquez sur **Insérer le composant** (responsable du post-traitement des guides comme étape finale).
   2. Configurez l’étape **Processus** :
      **Onglet courant**
- Titre : `DXML Post Process Initiator`
- Description : `DXML post process initiator step which will trigger a sling job for DXML post-processing of the modified/created asset`
      **Onglet Processus**
- Processus : sélectionnez `DXML Post Process Initiator`
- Sélectionner un `Handler Advance`
- Sélectionner un `Done`
   3. Cliquez sur **Synchronisation** en haut à droite après avoir effectué les modifications. Vous recevrez une notification de succès.

>[!NOTE]
>
> Actualisez et vérifiez que les modifications personnalisées et l’étape de post-traitement Experience Manager Guides sont présentes dans le modèle de workflow final.

### Validation des configurations du lanceur

1. Accédez à l’interface de workflow d’AEM et ouvrez **les lanceurs**.

```http
    http://localhost:4502/libs/cq/workflow/content/console.html
```

1. Recherchez les deux lanceurs suivants \(qui doivent être actifs\) correspondant au workflow **Ressource de mise à jour de la gestion des ressources numériques et apportez-y des modifications**(si nécessaire\) :

1. Lanceur de « *Node créé* » pour le **workflow Ressource de mise à jour de la gestion des ressources numériques**- pour la condition `"jcr:content/jcr:mimeType!=video"`, la valeur « Globbing » doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` aurait dû être `"event-user-data:changedByWorkflowProcess"`.
   - Lanceur pour *Nœud modifié* pour **Workflow Ressource de mise à jour de la gestion des ressources numériques -** pour la condition « `jcr:content/jcr:mimeType!=video` », la valeur « Globbing » doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` aurait dû être `"event-user-data:changedByWorkflowProcess"`.

### Validation des recouvrements et des personnalisations

Une fois la mise à niveau terminée :

1. Une fois la mise à niveau terminée, assurez-vous que toutes les personnalisations/superpositions sont validées et mises à jour pour correspondre au nouveau code de l’application. Voici quelques exemples :
   - Tous les composants superposés depuis /libs/editor/libs doivent être comparés au nouveau code de produit et les mises à jour doivent être effectuées dans les fichiers superposés sous /apps.
   - Toutes les catégories de bibliothèques clientes utilisées à partir du produit doivent être examinées pour les modifications. Toutes les configurations remplacées \(exemples ci-dessous\) doivent être comparées aux dernières afin d’obtenir les dernières fonctionnalités :
   - elementmapping.xml
   - ui\_config.json\(peut avoir été défini dans profils de dossier\)
   - `com.adobe.fmdita.config.ConfigManager` modifié

1. Si vous avez ajouté des personnalisations dans damAssetLucene, vous devrez peut-être les appliquer à nouveau. Après avoir effectué ces modifications, définissez la réindexation sur true. Cela réindexera tous les nœuds existants avec les personnalisations. Une fois l’opération terminée, l’indicateur de réindexation est de nouveau défini sur false. Cette opération peut prendre quelques heures en fonction du nombre de ressources dans le système.

## Indexer le contenu existant pour la recherche et le remplacement de carte

Cette section regroupe la procédure répétée **indexation** utilisée pour activer les nouvelles fonctionnalités de recherche et de remplacement au niveau de la carte **map**.

**Lorsque vous pouvez ignorer l’indexation**

La source inclut des notes « ignorer » en fonction de votre chemin de mise à niveau (par exemple, « Vous n’avez pas besoin d’effectuer ces étapes si vous effectuez une mise à niveau à partir de la version 4.3.0 ou 4.3.1 » et des notes similaires). Suivez la note d’omission indiquée dans votre section de mise à niveau.

Effectuez les étapes suivantes pour indexer le contenu existant et utiliser le nouveau texte de recherche et de remplacement au niveau du mappage :

1. Exécutez une requête POST (avec authentification) :

```http
POST http://<server:port>/bin/guides/map-find/indexing
```

Paramètres facultatifs pris en charge dans la source :

- Chemins de mappage spécifiques à l’index (indexe par défaut tous les mappages) :

  ```http
  POST http://<server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>
  ```

- Index DITA mappe sous un dossier racine (et ses sous-dossiers) :

  ```http
  POST http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test
  ```

  >[!NOTE]
  >
  > Si les `paths` et les `root` sont transmis, seul le `paths` est pris en compte.

1. L’API renvoie un `jobId`. Pour vérifier le statut, envoyez une requête GET :

   ```http
   GET http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}
   ```

   Comportement d’achèvement attendu :

   - Une fois l’opération terminée, GET répond avec succès et indique si des mappages ont échoué.
   - Confirmez les mappages correctement indexés dans les journaux du serveur.

### Vérifiez que l’indexation damAssetLucene est terminée (le cas échéant).

La source note que l’indexation damAssetLucene peut prendre des heures en fonction de la taille des données. Vous pouvez également confirmer l’achèvement de l’indexation lorsque `reindex` est `false` sous :

`http://<server:port>/oak:index/damAssetLucene`

Si vous avez ajouté des personnalisations dans `damAssetLucene`, vous devrez peut-être les appliquer à nouveau une fois la réindexation terminée.

### Solution de contournement de la « requête lue ou ayant traversé plus de 100000 nœuds » (si le traitement échoue)

Si la tâche d’indexation échoue et que l’erreur s’affiche :

« La requête a lu ou traversé plus de 100000 nœuds. Pour éviter d’affecter d’autres tâches, le traitement a été arrêté. »

Essayez cette solution à partir de la source :

1. Dans l’index `damAssetLucene` oak, ajoutez la propriété booléenne `indexNodeName=true` dans `/oak:index/damAssetLucene/indexRules/dam:Asset`.
2. Ajoutez un nouveau nœud nommé `excerpt` sous `/oak:index/damAssetLucene/indexRules/dam:Asset/properties` et définissez les propriétés comme indiqué dans la source :
   - `name=rep:excerpt`
   - `propertyIndex=true`
   - `notNullCheckEnabled=true`
3. Réindexez le `damAssetLucene` en définissant `reindex=true` et attendez qu’il soit à nouveau `false` (cela peut prendre des heures).
4. Réexécutez le script d’indexation (répétez les étapes POST et de suivi des tâches).

## Post-traitement du contenu existant pour le rapport sur les liens rompus

Cette section regroupe la procédure répétée **post-traitement** utilisée pour activer le rapport **lien rompu**.

**Lorsque vous pouvez ignorer le post-traitement**

La source inclut des notes « ignorer » en fonction de votre chemin de mise à niveau (par exemple, « Vous n’avez pas besoin d’effectuer ces étapes si vous effectuez une mise à niveau à partir de la version 4.3.0 » ou « à partir de la version 4.3.0 ou 4.3.1 »). Suivez la note d’omission indiquée dans votre section de mise à niveau.

Effectuez les étapes suivantes pour activer le rapport Lien rompu :

1. (Facultatif) Augmentez queryLimitReads d’Oak pour les référentiels volumineux

   S&#39;il existe plus de 100 000 fichiers DITA **, mettez à jour** sous `queryLimitReads` à une valeur supérieure au nombre de ressources (par exemple : `org.apache.jackrabbit.oak.query.QueryEngineSettingsService`), redéployez et continuez.`200000`

   | PID | Clé de la propriété | Valeur de la propriété |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valeur : 200000 <br> Valeur par défaut : 100000 |

1. Exécutez les API suivantes pour exécuter le post-traitement sur tous les fichiers :

   | Point d’entrée | /bin/guides/reports/upgrade |
   |---|---|
   | Type de demande | **POST** Ce script est une requête POST et doit donc être exécuté par des agents tels que Postman. |
   | Réponse attendue | L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée.<br> Exemple d&#39;URL : `http://<server:port>/bin/guides/reports/upgrade` |

   | Point d’entrée | /bin/guides/reports/upgrade |
   |---|---|
   | Type de demande | **&#x200B;**&#x200B;|
   | Param | jobId : transmettez le jobId reçu de la demande de publication précédente. |
   | Réponse attendue | - Une fois le traitement terminé, la requête GET répond avec succès. <br> - En cas d’erreur, partagez les journaux d’erreurs ainsi que la sortie de l’API avec votre équipe chargée du succès client.  <br>Exemple d’URL : `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |

1. Revenez à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifiée à l’étape 1.

## Activer le déclencheur de script via une servlet

Plusieurs versions incluent une étape facultative pour déclencher une tâche de mise à niveau de carte de traduction via une servlet. Cette section regroupe cette procédure répétée et inclut tous les détails fournis dans la source.


>[!NOTE]
>
> Vous n’avez pas besoin d’effectuer ces étapes si vous effectuez une mise à niveau à partir de la version 4.3.0 ou 4.3.1.

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

Dans la réponse JSON ci-dessus, la clé `lockNodePath` contient le chemin d’accès au nœud créé dans le référentiel pointant vers la tâche envoyée. Elle sera automatiquement supprimée une fois le traitement terminé. En attendant, vous pouvez vous référer à ce nœud pour connaître le statut actuel du traitement.

Recherchez des `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` et des `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` avant de passer aux étapes suivantes.

>[!NOTE]
>
> Vous devez vérifier si le nœud est toujours présent et le statut de la tâche.

**GET** : `http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json`


### Procédure à suivre pour gérer le conflit « fmdita rewriter »

Experience Manager Guides comprend un module de réécriture Sling personnalisé (`fmditarewriter`) pour gérer les liens générés en vue de la liaison entre cartes.

Si votre base de code contient un autre module de réécriture Sling personnalisé :

- Utilisez une valeur `order` **supérieure à 50** car Guides utilise `order=50`.
- Au cours de cette mise à niveau, la valeur `order` passe de `1000` à `50`. Vous devez donc fusionner votre réécriture personnalisée existante (le cas échéant) avec `fmditarewriter`.

