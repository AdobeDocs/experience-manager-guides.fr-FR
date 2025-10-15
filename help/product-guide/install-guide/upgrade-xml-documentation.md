---
title: Mettre à niveau Adobe Experience Manager Guides
description: Découvrez comment mettre à niveau Adobe Experience Manager Guides
exl-id: f058b39f-7408-4874-942b-693e133886cf
feature: Installation
role: Admin
level: Experienced
source-git-commit: 140def886ff52d361d3c76a5e47607ab58408f04
workflow-type: tm+mt
source-wordcount: '9151'
ht-degree: 0%

---

# Mettre à niveau Adobe Experience Manager Guides {#id224MBE0M0XA}

>[!NOTE]
>
> Suivez les instructions de mise à niveau spécifiques à la version sous licence de votre produit.

Vous pouvez mettre à niveau votre version actuelle de Experience Manager Guides vers la version 5.1.0 Service Pack 1 :

- Si vous utilisez la version 5.1.0, vous pouvez directement effectuer la mise à niveau vers la version 5.1.0 du Service Pack 1.
- Si vous utilisez la version 4.6.0, 4.6.x, 5.0.0 ou 5.0.x, vous devez effectuer la mise à niveau vers la version 5.1.0.
- Si vous utilisez la version 4.6.3, 4.6.1, 4.6 ou 4.4, vous devez effectuer la mise à niveau vers la version 5.0.0.
- Si vous utilisez la version 4.3.x, 4.2, 4.2.1 (correctif 4.2.1.3), 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers la version 4.4 avant d’effectuer la mise à niveau vers la version 5.0.0.
- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant d’effectuer la mise à niveau vers la version 4.3.x.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à la version 3.8.5, reportez-vous à la section Mise à niveau de Experience Manager Guides dans le guide d’installation spécifique au produit disponible sur [l’archive PDF d’aide d’Adobe Experience Manager Guides](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).


>[!NOTE]
>
> Vous devez installer le pack de services AEM avant de mettre à niveau la version de Experience Manager Guides.

Pour plus d’informations, reportez-vous aux procédures suivantes :

- [Mise à niveau vers la version 5.1.0](#upgrade-to-version-510)
- [Mise à niveau vers la version 5.0.0](#upgrade-to-version-500)
- [Mise à niveau vers la version 4.6.0](#upgrade-to-version-460)
- [Mise à niveau vers la version 4.4.0](#upgrade-to-version-440)
- [Mettre à niveau vers la version 4.3.1.5](#upgrade-to-version-4315)
- [Mise à niveau vers la version 4.3.1](#upgrade-to-version-431)
- [Mise à niveau vers la version 4.3.0](#upgrade-to-version-430)
- [Mise à niveau vers la version 4.2.1](#upgrade-to-version-421)
- [Mise à niveau vers la version 4.2](#upgrade-to-version-42)
- [Mise à niveau de 3.8.5 vers la version 4.0](#upgrade-from-version-385-to-version-40)


>[!IMPORTANT]
>
> Avant de commencer la mise à niveau, effectuez une sauvegarde complète du système pour éviter toute perte de données.

## Mise à niveau de la version 3.8.5 vers la version 4.0

Si vous utilisez Experience Manager Guides version 3.8.5, vous pouvez effectuer une mise à niveau vers la version 4.0 de Experience Manager Guides. Avec la fonction de mise à niveau, vous n’avez pas à désinstaller la version précédente de Experience Manager Guides.

Avant d’exécuter le processus, vous devez effectuer certaines tâches. Les sous-sections suivantes vous guideront tout au long des conditions préalables, de la génération de rapports et du processus de migration. En outre, après avoir installé Experience Manager Guides version 4.0, vous pouvez personnaliser diverses configurations, en fonction des paramètres du client.

>[!NOTE]
>
> Ce processus de mise à niveau s’applique uniquement de la version 3.8.5 à la version 4.0. Pour le processus de mise à niveau de la version 3.4 ou ultérieure vers la version 3.8.5, reportez-vous à la section *Mettre à niveau Experience Manager Guides* du guide d’installation spécifique au produit disponible sur [l’archive PDF de l’aide d’Adobe Experience Manager Guides](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).



****Conditions préalables****

Avant de commencer le processus de mise à niveau de Experience Manager Guides, vérifiez que vous disposez des éléments suivants :

1. Importation des commentaires de révision dans les rubriques ouvertes à la révision.
1. Fermeture de tous les avis actifs.
1. A fermé toutes les tâches de traduction.
1. Désinstallez tous les correctifs Experience Manager Guides installés en haut de la version précédente \(version majeure ou correctif\) de Experience Manager Guides.

**Avant d’installer la version 4.0**

Avant d’installer la version 4.0, procédez comme suit :

1. Assurez-vous à ce stade que Experience Manager Guides est sur la version 3.8.5.
1. Téléchargez le package de script de mise à niveau. Pour ce faire, recherchez « Package de mise à niveau de la solution XML Documentation 4.0 » sur [le portail de distribution de logiciels Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) qui téléchargera un fichier zip.
1. Téléchargez ce package dans AEM via le gestionnaire de packages et installez-le.
1. Une fois le package de mise à niveau installé, exécutez les scripts donnés ci-dessous dans le même ordre et suivez les instructions données :

**Vérifier l’API de compatibilité de mise à niveau**

Cette API est conçue pour évaluer l’état actuel du système et signaler si la mise à niveau est possible ou non. Pour exécuter ce script, déclenchez le point d’entrée donné ci-dessous :

| Point d’entrée | /bin/dxml/upgrade/3xto4x/report |
| --- | --- |
| Type de demande | **GET** Vous pouvez utiliser un navigateur web dans lequel vous êtes connecté à l&#39;instance AEM en tant qu&#39;administrateur. |
| Réponse attendue | -   Si tous les nœuds requis peuvent être déplacés, la vérification sera réussie. <br>-   Si un nœud est présent à l’emplacement cible, vous obtiendrez une erreur pertinente. Nettoyez le référentiel \(supprimez le nœud /var/dxml\), réinstallez le package de mise à niveau, puis déclenchez à nouveau ce point d’entrée. <br>**Remarque :** il ne s’agit pas d’une erreur courante, car l’emplacement cible n’est pas utilisé auparavant par Experience Manager Guides 3.x. <br> -   Si ce script échoue, ne continuez pas et signalez-le à votre équipe de succès client. |

**API System data migration**

Cette API est conçue pour migrer les données système comme indiqué dans la section **Mappage de migration**.

1. N’exécutez pas ce script si la vérification de la compatibilité de mise à niveau de l’API échoue \(ne pas continuer\).
1. Une fois que la vérification de la compatibilité de mise à niveau de l’API a réussi, vous pouvez exécuter le script de mise à niveau.

| Point d’entrée | /bin/dxml/upgrade/3xto4x |
| --- | --- |
| Type de demande | **POST** Ce script est une requête POST et doit donc être exécuté par des agents tels que Postman. |
| Réponse attendue | -   Une fois la migration réussie, vous pouvez installer la solution XML Documentation version 4.0.<br>-   En cas d’erreur, restaurez le dernier point de contrôle et partagez les journaux d’erreurs ainsi que la sortie de l’API avec votre équipe du succès client. |

**Mappage de migration** : l’API ci-dessus migre toutes les données de l’emplacement source vers l’emplacement cible.

| Source | Cible |
|------|------|
| /content/fmdita | /var/dxml |
| /content/dxml | /var/dxml |
| /etc/fmdita | /libs/fmdita |

## Installation version 4.0 {#id23598G006XA}

1. Installez la version 4.0 uniquement si les étapes de mise à niveau ont réussi.
1. Téléchargez le package de la version 4.0 à partir du portail de distribution logicielle [Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) :

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

La mise à niveau vers la version 4.2 dépend de la version actuelle de Experience Manager Guides.

Si vous utilisez la version 4.0, 4.1 ou 4.1.x, vous pouvez directement effectuer la mise à niveau vers la version 4.2.

****Conditions préalables****

Avant de lancer le processus de mise à niveau vers Experience Manager Guides 4.2, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 4.0, 4.1 ou 4.1.x.
1. A fermé toutes les tâches de traduction.
1. Modification du niveau de journal en **INFO** pour `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` classe et ajout de ces journaux dans un nouveau fichier journal, par exemple, `logs/translation_upgrade.log.`

>[!NOTE]
>
> Vous devriez fermer tous les avis actifs. Si les tâches de révision ne sont pas fermées lors de la mise à niveau vers la version 4.2, les anciennes tâches de révision en cours continuent d’entraîner les utilisateurs sur les anciennes pages de révision, et les tâches de révision créées après la mise à niveau afficheront les dernières mises à jour de la fonctionnalité.

## Installer la version 4.2 {#id2245IK0E0EV}

1. Téléchargez le package de la version 4.2 à partir du portail de distribution logicielle [Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package de la version 4.2.
1. Une fois l’installation du package terminée, attendez le(s) message(s) suivant(s) dans les journaux :

   `Completed the post deployment setup script`

   Le message ci-dessus indique que toutes les étapes d’installation sont terminées.

   Si vous rencontrez l’un des préfixes d’ERREUR suivants, signalez-le à votre équipe du succès client :

   - Erreur dans le script de configuration de post-déploiement
   - Exception lors du portage du MAP de traduction
   - Impossible de transférer la carte de traduction de v1 vers v2 pour la propriété
1. Mise à niveau du plug-in Oxygen connector publié avec la version 4.2 \(si nécessaire\).
1. Effacez la mémoire cache du navigateur après l’installation du package.
1. Continuez la mise à niveau des personnalisations comme décrit dans la section suivante.

## Après avoir installé la version 4.2 {#id2326F02004K}

>[!IMPORTANT]
>
> Le modèle high-tech ne s’affiche pas sur le serveur mis à niveau. Pour inclure le modèle high-tech sur votre serveur, vous pouvez le copier : Source : /libs/fmdita/pdf/Hi-Tech Destination : /content/dam/dita-templates/pdf

Après avoir installé Experience Manager Guides, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée avec votre configuration.

>[!NOTE]
>
> Le modèle dam-update-asset peut être personnalisé. Ainsi, si des personnalisations ont été effectuées, nous devons les synchroniser avec Experience Manager Guides dans la copie de travail du modèle.

1. **Workflow Ressource de mise à jour de la gestion des ressources numériques \(Modifications de post-traitement\):**

1. Ouvrir l’URL :

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Sélectionnez **workflow Ressource de mise à jour de la gestion des ressources numériques**.
1. Cliquez sur **Modifier**.
1. Si le composant **DXML Post Process Initiator** est présent, assurez-vous que les personnalisations sont synchronisées.
1. En l’absence du composant **DXML Post Process Initiator**, procédez comme suit pour l’insérer :

1. Cliquez sur **Insérer le composant** \(Responsable du post-traitement Experience Manager Guides en tant qu’étape finale du processus\).
1. Configurez l’**étape du processus** avec les détails suivants :

   **Onglet courant**

   **Title :** initiateur de post-processus DXML

   **Description** : étape d’initialisation de post-traitement DXML qui déclenchera une tâche sling pour le post-traitement DXML de la ressource modifiée/créée

   **Onglet Processus**

   - Sélectionnez **DXML Post Process Initiator** dans le menu déroulant **Process**

   - Sélectionnez **Avance du gestionnaire**

   - Sélectionnez **Terminé**

1. Cliquez sur **Synchronisation** en haut à droite après avoir effectué les modifications. Vous recevrez une notification de succès.

   >[!NOTE]
   >
   > Actualisez et vérifiez que les modifications personnalisées et l’étape de post-traitement Experience Manager Guides sont présentes dans le modèle de workflow final.

1. Une fois que le **workflow Ressource de mise à jour de gestion des ressources numériques** est validé, vérifiez les configurations de lanceur correspondantes. Pour ce faire, accédez à l’interface de workflow d’AEM et ouvrez les lanceurs.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Recherchez les deux lanceurs suivants \(qui doivent être actifs\) correspondant au workflow **Ressource de mise à jour de la gestion des ressources numériques et apportez-y des modifications**(si nécessaire\) :

1. Lanceur de « *Node créé* » pour le **workflow Ressource de mise à jour de la gestion des ressources numériques**- pour la condition `"jcr:content/jcr:mimeType!=video"`, la valeur « Globbing » doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; doit avoir des `"event-user-data:changedByWorkflowProcess"`.
   - Lanceur pour « *Nœud modifié* » pour **workflow Ressource de mise à jour de la gestion des ressources numériques -** pour la condition « `jcr:content/jcr:mimeType!=video` »,
   - la valeur &#39;Globbing&#39; doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; doit avoir des `"event-user-data:changedByWorkflowProcess"`.
1. Une fois la mise à niveau terminée, assurez-vous que toutes les personnalisations/superpositions sont validées et mises à jour pour correspondre au nouveau code de l’application. Voici quelques exemples :
   - Tous les composants superposés depuis /libs/editor/libs doivent être comparés au nouveau code de produit et les mises à jour doivent être effectuées dans les fichiers superposés sous /apps.
   - Toutes les catégories de bibliothèques clientes utilisées à partir du produit doivent être examinées pour les modifications. Toutes les configurations remplacées \(exemples ci-dessous\) doivent être comparées aux dernières afin d’obtenir les dernières fonctionnalités :
   - elementmapping.xml
   - ui\_config.json\(peut avoir été défini dans profils de dossier\)
   - `com.adobe.fmdita.config.ConfigManager` modifié
   - Vérifiez si l’un des codes personnalisés utilisait d’anciens chemins \(comme mentionné dans la [section Mappage de migration](#id2244LE040XA)\) - doit être mis à jour vers les nouveaux chemins afin que les personnalisations fonctionnent également comme prévu.
1. Découvrez les nouvelles configurations introduites dans la version actuelle \(vérifiez [Notes de mise à jour](../release-info/release-notes-4-3.md)\) et vérifiez si des fonctionnalités sont affectées, puis prenez les mesures appropriées. Par exemple, vous pouvez utiliser la fonctionnalité « Gestion améliorée des fichiers et des versions » introduite dans la version 4.0, pour laquelle vous devez activer une configuration.

## Procédure à suivre pour indexer le contenu existant afin d’utiliser la nouvelle recherche et le remplacement :

Effectuez les étapes suivantes pour indexer le contenu existant et utiliser le nouveau texte de recherche et de remplacement au niveau du mappage :

- Exécutez une requête POST au serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. \(Facultatif) Vous pouvez transmettre des chemins spécifiques des mappages pour les indexer. Par défaut, tous les mappages sont indexés \|\| Par exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`\)

- L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée -

`http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

- Une fois la tâche terminée, la requête GET ci-dessus répond avec succès et mentionne si des mappages ont échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

Si la tâche de mise à niveau échoue et que le journal des erreurs affiche l’erreur suivante :

« La *requête* a lu ou traversé plus de *100000 nœuds*. Pour éviter d’affecter d’autres tâches, le traitement a été arrêté. »

Cela peut être dû au fait que l’index n’est pas correctement configuré pour la requête utilisée lors de la mise à niveau. Vous pouvez essayer la solution suivante :

1. Dans l’index oak damAssetLucene, ajoutez la propriété booléenne `indexNodeName` comme `true` dans le nœud .
   `/oak:index/damAssetLucene/indexRules/dam:Asset`
1. Ajoutez un nouveau nœud avec l’extrait de nom sous le nœud .

   `/oak:index/damAssetLucene/indexRules/dam:Asset/properties`
et définissez les propriétés suivantes dans le nœud :

   ```
   name - rep:excerpt
   propertyIndex - {Boolean}true
   notNullCheckEnabled - {Boolean}true
   ```

   La structure de `damAssetLucene` doit se présenter comme suit :

   ```
   <damAssetLucene compatVersion="{Long}2" async="async, nrt" jcr:primaryType="oak:QueryIndexDefinition" evaluatePathRestrictions="{Boolean}true" type="lucene">
   <indexRules jcr:primaryType="nt:unstructured">
     <dam:Asset indexNodeName="{Boolean}true" jcr:primaryType="nt:unstructured">
       <properties jcr:primaryType="nt:unstructured">
         <excerpt name="rep:excerpt" propertyIndex="{Boolean}true" jcr:primaryType="nt:unstructured" notNullCheckEnabled="{Boolean}true"/>
       </properties>
       </dam:Asset>
     </indexRules>
   </damAssetLucene>    
   ```


   (avec d’autres nœuds et propriétés existants)

1. Réindexez l’index `damAssetLucene` (en définissant l’indicateur de réindexation comme `true` sous .
et attendez qu’il soit à nouveau `false` (cela indique que la réindexation est terminée). Notez que cela peut prendre quelques heures selon la taille de l’index.
1. Exécutez à nouveau le script d’indexation en suivant les étapes précédentes.


## Mise à niveau vers la version 4.2.1

>[!TIP]
>
>Il est recommandé d’installer le correctif 4.2.1.3 sur la version 4.2.1.

La mise à niveau vers la version 4.2.1 dépend de la version actuelle de Experience Manager Guides. Si vous utilisez la version 4.1, 4.1.x ou 4.2, vous pouvez directement effectuer la mise à niveau vers la version 4.2.1.

>[!NOTE]
>
>Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de démarrer le processus de mise à niveau pendant les heures creuses.

****Conditions préalables****

Avant de lancer le processus de mise à niveau vers Experience Manager Guides 4.2.1, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 4.1, 4.1.x ou 4.2.
1. A fermé toutes les tâches de traduction.
1. Modification du niveau de journal en **INFO** pour `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` classe et ajout de ces journaux dans un nouveau fichier journal, par exemple, `logs/translation_upgrade.log.`

>[!NOTE]
>
> Vous devriez fermer tous les avis actifs. Si les tâches de révision ne sont pas fermées lors de la mise à niveau vers la version 4.2, les anciennes tâches de révision en cours continuent d’entraîner les utilisateurs sur les anciennes pages de révision, et les tâches de révision créées après la mise à niveau afficheront les dernières mises à jour de la fonctionnalité.

## Installation de la version 4.2.1

1. Téléchargez le package de la version 4.2.1 à partir du portail de distribution logicielle [Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package de la version 4.2.1.
1. Vous pouvez choisir d’APPUYER sur le déclencheur pour démarrer la tâche de mise à niveau de la carte de traduction. Pour plus d’informations, consultez [ Activation du déclencheur de script via une servlet](#enable-trigger-of-script-via-a-servlet-for-421).


1. Une fois l’installation du package terminée, attendez le(s) message(s) suivant(s) dans les journaux :

   `Completed the post deployment setup script`

   Le message ci-dessus indique que toutes les étapes d’installation sont terminées.

   Si vous rencontrez l’un des préfixes d’ERREUR suivants, signalez-le à votre équipe du succès client :

   - Erreur dans le script de configuration de post-déploiement
   - Exception lors du portage du MAP de traduction
   - Impossible de transférer la carte de traduction de v1 vers v2 pour la propriété
1. Mise à niveau du plug-in Oxygen connector publié avec la version 4.2 \(si nécessaire\).
1. Effacez la mémoire cache du navigateur après l’installation du package.
1. Continuez la mise à niveau des personnalisations comme décrit dans la section suivante.

### Activer le déclenchement du script via une servlet (pour la version 4.2.1)

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

Exemple de journal :
Voici un exemple de journaux qui apparaîtront dans le fichier journal après le déclenchement du script.

```
04.05.2023 14:17:12.876 *INFO* [[0:0:0:0:0:0:0:1] [1683190032736] POST /bin/guides/script/start HTTP/1.1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Acquiring lock for job : translation-map-upgrade
04.05.2023 14:17:12.897 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Starting the thread to upgrade translation map from V1 to V2
04.05.2023 14:17:12.899 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Initiating lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.901 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Starting porting of translation map from V1 to V2
04.05.2023 14:17:12.904 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Memory increase is of : 764 kB
04.05.2023 14:17:12.906 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2
04.05.2023 14:17:12.907 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Releasing lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.909 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2
```

Recherchez des `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` et des `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` avant de passer aux étapes suivantes.



## Après avoir installé la version 4.2.1

>[!IMPORTANT]
>
> Le modèle high-tech ne s’affiche pas sur le serveur mis à niveau. Pour inclure le modèle high-tech sur votre serveur, vous pouvez le copier : Source : /libs/fmdita/pdf/Hi-Tech Destination : /content/dam/dita-templates/pdf

Après avoir installé Experience Manager Guides, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée avec votre configuration.

>[!NOTE]
>
> Le modèle dam-update-asset peut être personnalisé. Ainsi, si des personnalisations ont été effectuées, nous devons les synchroniser avec Experience Manager Guides dans la copie de travail du modèle.

1. **Workflow Ressource de mise à jour de la gestion des ressources numériques \(Modifications de post-traitement\):**

1. Ouvrir l’URL :

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Sélectionnez **workflow Ressource de mise à jour de la gestion des ressources numériques**.
1. Cliquez sur **Modifier**.
1. Si le composant **DXML Post Process Initiator** est présent, assurez-vous que les personnalisations sont synchronisées.
1. En l’absence du composant **DXML Post Process Initiator**, procédez comme suit pour l’insérer :

1. Cliquez sur **Insérer le composant** \(Responsable du post-traitement Experience Manager Guides en tant qu’étape finale du processus\).
1. Configurez l’**étape du processus** avec les détails suivants :

   **Onglet courant**

   **Title :** initiateur de post-processus DXML

   **Description** : étape d’initialisation de post-traitement DXML qui déclenchera une tâche sling pour le post-traitement DXML de la ressource modifiée/créée

   **Onglet Processus**

   - Sélectionnez **DXML Post Process Initiator** dans le menu déroulant **Process**

   - Sélectionnez **Avance du gestionnaire**

   - Sélectionnez **Terminé**

1. Cliquez sur **Synchronisation** en haut à droite après avoir effectué les modifications. Vous recevrez une notification de succès.

   >[!NOTE]
   >
   > Actualisez et vérifiez que les modifications personnalisées et l’étape de post-traitement Experience Manager Guides sont présentes dans le modèle de workflow final.

1. Une fois que le **workflow Ressource de mise à jour de gestion des ressources numériques** est validé, vérifiez les configurations de lanceur correspondantes. Pour ce faire, accédez à l’interface de workflow d’AEM et ouvrez les lanceurs.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Recherchez les deux lanceurs suivants \(qui doivent être actifs\) correspondant au workflow **Ressource de mise à jour de la gestion des ressources numériques et apportez-y des modifications**(si nécessaire\) :

1. Lanceur de « *Node créé* » pour le **workflow Ressource de mise à jour de la gestion des ressources numériques**- pour la condition `"jcr:content/jcr:mimeType!=video"`, la valeur « Globbing » doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; doit avoir des `"event-user-data:changedByWorkflowProcess"`.
   - Lanceur pour « *Node modifié* » pour **workflow Ressource de mise à jour de la gestion des ressources numériques -** pour la condition « `jcr:content/jcr:mimeType!=video` », la valeur « Globbing » doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` aurait dû être `"event-user-data:changedByWorkflowProcess"`.

1. Une fois la mise à niveau terminée, assurez-vous que toutes les personnalisations/superpositions sont validées et mises à jour pour correspondre au nouveau code de l’application. Voici quelques exemples :
   - Tous les composants superposés depuis /libs/editor/libs doivent être comparés au nouveau code de produit et les mises à jour doivent être effectuées dans les fichiers superposés sous /apps.
   - Toutes les catégories de bibliothèques clientes utilisées à partir du produit doivent être examinées pour les modifications. Toutes les configurations remplacées \(exemples ci-dessous\) doivent être comparées aux dernières afin d’obtenir les dernières fonctionnalités :
   - elementmapping.xml
   - ui\_config.json\(peut avoir été défini dans profils de dossier\)
   - `com.adobe.fmdita.config.ConfigManager` modifié
   - Vérifiez si l’un des codes personnalisés utilisait d’anciens chemins \(comme mentionné dans la [section Mappage de migration](#id2244LE040XA)\) - doit être mis à jour vers les nouveaux chemins afin que les personnalisations fonctionnent également comme prévu.
1. Découvrez les nouvelles configurations introduites dans la version actuelle \(vérifiez [Notes de mise à jour](../release-info/release-notes-4-2-1.md)\) et vérifiez si des fonctionnalités sont affectées, puis prenez les mesures appropriées. Par exemple, vous pouvez utiliser la fonctionnalité « Gestion améliorée des fichiers et des versions » introduite dans la version 4.0, pour laquelle vous devez activer une configuration.

## Procédure à suivre pour indexer le contenu existant afin d’utiliser la nouvelle recherche et le remplacement :

Effectuez les étapes suivantes pour indexer le contenu existant et utiliser le nouveau texte de recherche et de remplacement au niveau du mappage :

- Vérifiez que l’indexation `damAssetLucene` est terminée. Cela peut prendre jusqu’à quelques heures, selon la quantité de données présentes sur le serveur. Vous pouvez confirmer que la réindexation est terminée en vérifiant que le champ de réindexation est défini sur false dans .
  `http://<server:port>/oak:index/damAssetLucene`.  En outre, si vous avez ajouté des personnalisations dans `damAssetLucene`, vous devrez peut-être les appliquer à nouveau.

- Exécutez une requête POST au serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des mappages pour les indexer. Par défaut, tous les mappages sont indexés \|\| Par exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- Vous pouvez également transmettre un dossier racine pour indexer les plans DITA d&#39;un dossier spécifique (et de ses sous-dossiers). Par exemple, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Notez que si le paramètre de chemins d’accès et le paramètre racine sont transmis, seul le paramètre de chemins d’accès est pris en compte.

- L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée : `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\).


- Une fois la tâche terminée, la requête GET ci-dessus répond avec succès et mentionne si des mappages ont échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.


## Mise à niveau vers la version 4.3.0

La mise à niveau vers la version 4.3.0 dépend de la version actuelle de Experience Manager Guides. Si vous utilisez la version 4.2 ou 4.2.x, vous pouvez directement effectuer la mise à niveau vers la version 4.3.0.

>[!NOTE]
>
>Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de démarrer le processus de mise à niveau pendant les heures creuses.

****Conditions préalables****

Avant de lancer le processus de mise à niveau vers Experience Manager Guides 4.3.0, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 4.2 ou 4.2.x et achèvement des étapes d’installation respectives.
1. A fermé toutes les tâches de traduction.



## Installation de la version 4.3.0

1. Téléchargez le package de la version 4.3.0 à partir du portail de distribution logicielle [Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package de la version 4.3.0.
1. Effacez la mémoire cache du navigateur après l’installation du package.
1. Mettez à niveau le fichier `ui_config.json` à partir de l’onglet **Configuration de l’éditeur XML** dans le profil de dossier.


## Après avoir installé la version 4.3.0

Après avoir installé Experience Manager Guides, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée avec votre configuration.

## Étapes de post-traitement du contenu existant pour utiliser le rapport de lien rompu


Effectuez les étapes suivantes pour post-traiter le contenu existant et utiliser le nouveau rapport de lien rompu :

1. (Facultatif) S’il existe plus de 100 000 fichiers dita dans le système, mettez à jour le `queryLimitReads` sous `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` avec une valeur plus élevée (toute valeur supérieure au nombre de ressources présentes, par exemple 200 000), puis redéployez.

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
   | Type de demande | **GET** |
   | Param | jobId : transmettez le jobId reçu de la demande de publication précédente. |
   | Réponse attendue | - Une fois le traitement terminé, la requête GET répond avec succès. <br> - En cas d’erreur, partagez les journaux d’erreurs ainsi que la sortie de l’API avec votre équipe chargée du succès client.  <br>Exemple d’URL : `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |


1. Revenez à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifiée à l’étape 1.



## Mise à niveau vers la version 4.3.1

La mise à niveau vers la version 4.3.1 dépend de la version actuelle de Experience Manager Guides. Si vous utilisez la version 4.3.0, 4.2 ou 4.2.1, vous pouvez directement effectuer la mise à niveau vers la version 4.3.1.

>[!NOTE]
>
>Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de démarrer le processus de mise à niveau pendant les heures creuses.

****Conditions préalables****

Avant de lancer le processus de mise à niveau vers Experience Manager Guides 4.3.1, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 4.3.0, 4.2 ou 4.2.1 et achèvement des étapes d’installation respectives.
1. (Facultatif) A fermé toutes les tâches de traduction.
1. Modification du niveau de journal en **INFO** pour `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` classe et ajout de ces journaux dans un nouveau fichier journal, par exemple, `logs/translation_upgrade.log`.


## Installation de la version 4.3.1

1. Téléchargez le package de la version 4.3.1 à partir du portail de distribution logicielle [Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package de la version 4.3.1.
1. Vous pouvez choisir d’APPUYER sur le déclencheur pour démarrer la tâche de mise à niveau de la carte de traduction. Pour plus d’informations, consultez [ Activation du déclencheur de script via une servlet](#enable-trigger-of-script-via-a-servlet-for-431).


1. Une fois l’installation du package terminée, attendez le(s) message(s) suivant(s) dans les journaux :

   `Completed the post deployment setup script`

   Le message ci-dessus indique que toutes les étapes d’installation sont terminées.

   Si vous rencontrez l’un des préfixes d’ERREUR suivants, signalez-le à votre équipe du succès client :

   - Erreur dans le script de configuration de post-déploiement
   - Exception lors du portage du MAP de traduction
   - Impossible de transférer la carte de traduction de v1 vers v2 pour la propriété
1. Mise à niveau du plug-in Oxygen connector publié avec la version 4.2 \(si nécessaire\).
1. Effacez la mémoire cache du navigateur après l’installation du package.
1. Continuez la mise à niveau des personnalisations comme décrit dans la section suivante.

### Activer le déclenchement du script via une servlet (pour la version 4.3.1)

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

Exemple de journal :
Voici un exemple de journaux qui apparaîtront dans le fichier journal après le déclenchement du script.

```
04.05.2023 14:17:12.876 *INFO* [[0:0:0:0:0:0:0:1] [1683190032736] POST /bin/guides/script/start HTTP/1.1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Acquiring lock for job : translation-map-upgrade
04.05.2023 14:17:12.897 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Starting the thread to upgrade translation map from V1 to V2
04.05.2023 14:17:12.899 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Initiating lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.901 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Starting porting of translation map from V1 to V2
04.05.2023 14:17:12.904 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Memory increase is of : 764 kB
04.05.2023 14:17:12.906 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2
04.05.2023 14:17:12.907 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Releasing lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.909 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2
```

Recherchez des `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` et des `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` avant de passer aux étapes suivantes.

## Après avoir installé la version 4.3.1



Après avoir installé Experience Manager Guides, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée avec votre configuration.

>[!NOTE]
>
> Le modèle dam-update-asset peut être personnalisé. Ainsi, si des personnalisations ont été effectuées, nous devons les synchroniser avec Experience Manager Guides dans la copie de travail du modèle.

1. **Workflow Ressource de mise à jour de la gestion des ressources numériques \(Modifications de post-traitement\):**

1. Ouvrir l’URL :

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Sélectionnez **workflow Ressource de mise à jour de la gestion des ressources numériques**.
1. Cliquez sur **Modifier**.
1. Si le composant **DXML Post Process Initiator** est présent, assurez-vous que les personnalisations sont synchronisées.
1. En l’absence du composant **DXML Post Process Initiator**, procédez comme suit pour l’insérer :

1. Cliquez sur **Insérer le composant** \(Responsable du post-traitement Experience Manager Guides en tant qu’étape finale du processus\).
1. Configurez l’**étape du processus** avec les détails suivants :

   **Onglet courant**

   **Title :** initiateur de post-processus DXML

   **Description** : étape d’initialisation de post-traitement DXML qui déclenchera une tâche sling pour le post-traitement DXML de la ressource modifiée/créée

   **Onglet Processus**

   - Sélectionnez **DXML Post Process Initiator** dans le menu déroulant **Process**

   - Sélectionnez **Avance du gestionnaire**

   - Sélectionnez **Terminé**

1. Cliquez sur **Synchronisation** en haut à droite après avoir effectué les modifications. Vous recevrez une notification de succès.

   >[!NOTE]
   >
   > Actualisez et vérifiez que les modifications personnalisées et l’étape de post-traitement Experience Manager Guides sont présentes dans le modèle de workflow final.

1. Une fois que le **workflow Ressource de mise à jour de gestion des ressources numériques** est validé, vérifiez les configurations de lanceur correspondantes. Pour ce faire, accédez à l’interface de workflow d’AEM et ouvrez les lanceurs.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Recherchez les deux lanceurs suivants \(qui doivent être actifs\) correspondant au workflow **Ressource de mise à jour de la gestion des ressources numériques et apportez-y des modifications**(si nécessaire\) :

1. Lanceur de « *Node créé* » pour le **workflow Ressource de mise à jour de la gestion des ressources numériques**- pour la condition `"jcr:content/jcr:mimeType!=video"`, la valeur « Globbing » doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; doit avoir des `"event-user-data:changedByWorkflowProcess"`.
   - Lanceur pour « *Node modifié* » pour **workflow Ressource de mise à jour de la gestion des ressources numériques -** pour la condition « `jcr:content/jcr:mimeType!=video` », la valeur « Globbing » doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` aurait dû être `"event-user-data:changedByWorkflowProcess"`.

1. Une fois la mise à niveau terminée, assurez-vous que toutes les personnalisations/superpositions sont validées et mises à jour pour correspondre au nouveau code de l’application. Voici quelques exemples :
   - Tous les composants superposés depuis /libs/editor/libs doivent être comparés au nouveau code de produit et les mises à jour doivent être effectuées dans les fichiers superposés sous /apps.
   - Toutes les catégories de bibliothèques clientes utilisées à partir du produit doivent être examinées pour les modifications. Toutes les configurations remplacées \(exemples ci-dessous\) doivent être comparées aux dernières afin d’obtenir les dernières fonctionnalités :
   - elementmapping.xml
   - ui\_config.json\(peut avoir été défini dans profils de dossier\)
   - `com.adobe.fmdita.config.ConfigManager` modifié


## Procédure d’indexation du contenu existant

>[!NOTE]
>
> Vous n’avez pas besoin d’effectuer ces étapes si vous effectuez une mise à niveau à partir de la version 4.3.0 ou 4.2.1.

Effectuez les étapes suivantes pour indexer le contenu existant et utiliser le nouveau texte de recherche et de remplacement au niveau du mappage :


- Exécutez une requête POST au serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des mappages pour les indexer. Par défaut, tous les mappages sont indexés \|\| Par exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)


- L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée : `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\).


- Une fois la tâche terminée, la requête GET ci-dessus répond avec succès et mentionne si des mappages ont échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Étapes de post-traitement du contenu existant pour utiliser le rapport de lien rompu

>[!NOTE]
>
> Vous n’avez pas besoin d’effectuer ces étapes si vous effectuez une mise à niveau à partir de la version 4.3.0

Effectuez les étapes suivantes pour post-traiter le contenu existant et utiliser le nouveau rapport de lien rompu :

1. (Facultatif) S’il existe plus de 100 000 fichiers dita dans le système, mettez à jour le `queryLimitReads` sous `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` avec une valeur plus élevée (toute valeur supérieure au nombre de ressources présentes, par exemple 200 000), puis redéployez.

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
   | Type de demande | **GET** |
   | Param | jobId : transmettez le jobId reçu de la demande de publication précédente. |
   | Réponse attendue | - Une fois le traitement terminé, la requête GET répond avec succès. <br> - En cas d’erreur, partagez les journaux d’erreurs ainsi que la sortie de l’API avec votre équipe chargée du succès client.  <br>Exemple d’URL : `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |


1. Revenez à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifiée à l’étape 1.



## Mettre à niveau vers la version 4.3.1.5

La mise à niveau vers la version 4.3.1.5 dépend de la version actuelle de Experience Manager Guides. Si vous utilisez la version 4.3.1, vous pouvez directement effectuer la mise à niveau vers la version 4.3.1.5.



## Installer la version 4.3.1.5

1. Téléchargez 4.3.1.5 package de version à partir du portail de distribution logicielle [Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package de la version 4.3.1.5.

1. Attendez que le processus d’installation soit terminé.
1. Continuez la mise à niveau des personnalisations comme décrit dans la section suivante.


## Après avoir installé la version 4.3.1.5


>[!NOTE]
>
>Si vous souhaitez utiliser le bundle org.apache.velocity, effectuez les étapes suivantes avant de charger le bundle :
> 1. Accédez à `<server>:<port>/system/console/bundles`.
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

La mise à niveau vers la version 4.4.0 dépend de la version actuelle de Experience Manager Guides. Si vous utilisez la version 4.3.1, 4.3.0, 4.2 ou 4.2.1 (correctif 4.2.1.3), vous pouvez directement effectuer la mise à niveau vers la version 4.4.0

>[!NOTE]
>
>Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de démarrer le processus de mise à niveau pendant les heures creuses.

****Conditions préalables****

Avant de lancer le processus de mise à niveau vers Experience Manager Guides 4.4.0, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 4.3.1, 4.3.0 ou 4.2.1 (correctif 4.2.1.3) et achèvement des étapes d’installation respectives.
1. (Facultatif) A fermé toutes les tâches de traduction.
1. Modification du niveau de journal en **INFO** pour `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` classe et ajout de ces journaux dans un nouveau fichier journal, par exemple, `logs/translation_upgrade.log`.


## Installation de la version 4.4.0

1. Téléchargez le package de la version 4.4.0 à partir du portail de distribution logicielle [Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package de la version 4.4.0.
1. Vous pouvez choisir d’APPUYER sur le déclencheur pour démarrer la tâche de mise à niveau de la carte de traduction. Pour plus d’informations, consultez [ Activation du déclencheur de script via une servlet](#enable-trigger-of-script-via-a-servlet).

1. Une fois l’installation du package terminée, attendez le(s) message(s) suivant(s) dans les journaux :

   `Completed the post deployment setup script`

   Le message ci-dessus indique que toutes les étapes d’installation sont terminées.

   Si vous rencontrez l’un des préfixes d’ERREUR suivants, signalez-le à votre équipe du succès client :

   - Erreur dans le script de configuration de post-déploiement
   - Exception lors du portage du MAP de traduction
   - Impossible de transférer la carte de traduction de v1 vers v2 pour la propriété
1. Mise à niveau du plug-in Oxygen connector publié avec la version 4.4.0 \(si nécessaire\).
1. Effacez la mémoire cache du navigateur après l’installation du package.
1. Continuez la mise à niveau des personnalisations comme décrit dans la section suivante.


## Après avoir installé la version 4.4.0

Après avoir installé Experience Manager Guides, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée avec votre configuration.

>[!NOTE]
>
> Le modèle dam-update-asset peut être personnalisé. Ainsi, si des personnalisations ont été effectuées, nous devons les synchroniser avec Experience Manager Guides dans la copie de travail du modèle.

1. **Workflow Ressource de mise à jour de la gestion des ressources numériques \(Modifications de post-traitement\):**

1. Ouvrir l’URL :

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Sélectionnez **workflow Ressource de mise à jour de la gestion des ressources numériques**.
1. Cliquez sur **Modifier**.
1. Si le composant **DXML Post Process Initiator** est présent, assurez-vous que les personnalisations sont synchronisées.
1. En l’absence du composant **DXML Post Process Initiator**, procédez comme suit pour l’insérer :

1. Cliquez sur **Insérer le composant** \(Responsable du post-traitement Experience Manager Guides en tant qu’étape finale du processus\).
1. Configurez l’**étape du processus** avec les détails suivants :

   **Onglet courant**

   **Title :** initiateur de post-processus DXML

   **Description** : étape d’initialisation de post-traitement DXML qui déclenchera une tâche sling pour le post-traitement DXML de la ressource modifiée/créée

   **Onglet Processus**

   - Sélectionnez **DXML Post Process Initiator** dans le menu déroulant **Process**

   - Sélectionnez **Avance du gestionnaire**

   - Sélectionnez **Terminé**

1. Cliquez sur **Synchronisation** en haut à droite après avoir effectué les modifications. Vous recevrez une notification de succès.

   >[!NOTE]
   >
   > Actualisez et vérifiez que les modifications personnalisées et l’étape de post-traitement Experience Manager Guides sont présentes dans le modèle de workflow final.

1. Une fois que le **workflow Ressource de mise à jour de gestion des ressources numériques** est validé, vérifiez les configurations de lanceur correspondantes. Pour ce faire, accédez à l’interface de workflow d’AEM et ouvrez les lanceurs.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Recherchez les deux lanceurs suivants \(qui doivent être actifs\) correspondant au workflow **Ressource de mise à jour de la gestion des ressources numériques et apportez-y des modifications**(si nécessaire\) :

1. Lanceur de « *Node créé* » pour le **workflow Ressource de mise à jour de la gestion des ressources numériques**- pour la condition `"jcr:content/jcr:mimeType!=video"`, la valeur « Globbing » doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; doit avoir des `"event-user-data:changedByWorkflowProcess"`.
   - Lanceur pour « *Node modifié* » pour **workflow Ressource de mise à jour de la gestion des ressources numériques -** pour la condition « `jcr:content/jcr:mimeType!=video` », la valeur « Globbing » doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` aurait dû être `"event-user-data:changedByWorkflowProcess"`.

1. Une fois la mise à niveau terminée, assurez-vous que toutes les personnalisations/superpositions sont validées et mises à jour pour correspondre au nouveau code de l’application. Voici quelques exemples :
   - Tous les composants superposés depuis /libs/editor/libs doivent être comparés au nouveau code de produit et les mises à jour doivent être effectuées dans les fichiers superposés sous /apps.
   - Toutes les catégories de bibliothèques clientes utilisées à partir du produit doivent être examinées pour les modifications. Toutes les configurations remplacées \(exemples ci-dessous\) doivent être comparées aux dernières afin d’obtenir les dernières fonctionnalités :
   - elementmapping.xml
   - ui\_config.json\(peut avoir été défini dans profils de dossier\)
   - `com.adobe.fmdita.config.ConfigManager` modifié

1. Si vous avez ajouté des personnalisations dans damAssetLucene, vous devrez peut-être les appliquer à nouveau. Après avoir effectué ces modifications, définissez la réindexation sur true. Cela réindexera tous les nœuds existants avec les personnalisations. Une fois l’opération terminée, l’indicateur de réindexation est de nouveau défini sur false. Cette opération peut prendre quelques heures en fonction du nombre de ressources dans le système.

## Procédure d’indexation du contenu existant

>[!NOTE]
>
> Vous n’avez pas besoin d’effectuer ces étapes si vous effectuez une mise à niveau à partir de la version 4.3.0 ou 4.3.1.

Effectuez les étapes suivantes pour indexer le contenu existant et utiliser le nouveau texte de recherche et de remplacement au niveau du mappage :

- Exécutez une requête POST au serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des mappages pour les indexer. Par défaut, tous les mappages sont indexés \|\| Par exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée : `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\).

- Une fois la tâche terminée, la requête GET ci-dessus répond avec succès et mentionne si des mappages ont échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Étapes de post-traitement du contenu existant pour utiliser le rapport de lien rompu

>[!NOTE]
>
> Vous n’avez pas besoin d’effectuer ces étapes si vous effectuez une mise à niveau à partir de la version 4.3.0 ou 4.3.1.

Effectuez les étapes suivantes pour post-traiter le contenu existant et utiliser le nouveau rapport de lien rompu :

1. (Facultatif) S’il existe plus de 100 000 fichiers dita dans le système, mettez à jour le `queryLimitReads` sous `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` avec une valeur plus élevée (toute valeur supérieure au nombre de ressources présentes, par exemple 200 000), puis redéployez.

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
   | Type de demande | **GET** |
   | Param | jobId : transmettez le jobId reçu de la demande de publication précédente. |
   | Réponse attendue | - Une fois le traitement terminé, la requête GET répond avec succès. <br> - En cas d’erreur, partagez les journaux d’erreurs ainsi que la sortie de l’API avec votre équipe chargée du succès client.  <br>Exemple d’URL : `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |

1. Revenez à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifiée à l’étape 1.

### Activer le déclencheur de script via une servlet

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



## Procédure à suivre pour gérer le conflit de `'fmdita rewriter'`

Experience Manager Guides dispose d’un module [**custom sling rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter) qui gère les liens générés en cas de mappages croisés (liens entre les rubriques de deux mappages différents).

Si votre base de code contient un autre module de réécriture Sling personnalisé, utilisez une valeur de `'order'` supérieure à 50, car le module de réécriture Sling de Experience Manager Guides utilise `'order'` 50.  Pour remplacer cela, vous avez besoin d’une valeur >50. Pour plus d’informations, consultez la section [Pipelines de réécriture de sortie](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Lors de cette mise à niveau, puisque la valeur `'order'` est modifiée de 1 000 à 50, vous devez fusionner le module de réécriture personnalisé existant, le cas échéant, avec `'fmdita-rewriter'`.


**Rubrique parente :**[ Télécharger et installer](download-install.md)


## Mise à niveau vers la version 4.6.0

>[!TIP]
>
> Il est recommandé d’installer le pack de services 4.6.0 sur les versions 4.6.0 , 4.6.0 du pack de services 1 ou 4.6.0 du pack de services 3. Le processus de mise à niveau vers le pack de services 4.6.0 d’ suit les mêmes étapes que pour la version 4.6.0 d’.

La mise à niveau vers la version 4.6.0 dépend de la version actuelle de Experience Manager Guides. Si vous utilisez la version 4.4.0, 4.3.1, 4.3.0, 4.2 ou 4.2.1 (correctif 4.2.1.3), vous pouvez directement effectuer la mise à niveau vers la version 4.6.0.

>[!NOTE]
>
> Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de démarrer le processus de mise à niveau pendant les heures creuses.

****Conditions préalables****

Avant de lancer le processus de mise à niveau vers Experience Manager Guides 4.6.0, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 4.3.1, 4.3.0 ou 4.2.1 (correctif 4.2.1.3) et achèvement des étapes d’installation respectives.
1. (Facultatif) A fermé toutes les tâches de traduction.
1. Modification du niveau de journal en **INFO** pour `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` classe et ajout de ces journaux dans un nouveau fichier journal, par exemple, `logs/translation_upgrade.log`.


## Installation de la version 4.6.0

1. Téléchargez le package de la version 4.6.0 à partir du portail de distribution logicielle [Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package de la version 4.6.0.
1. Vous pouvez choisir d’APPUYER sur le déclencheur pour démarrer la tâche de mise à niveau de la carte de traduction. Pour plus d’informations, consultez [ Activation du déclencheur de script via une servlet](#enable-trigger-of-script-via-a-servlet).

1. Une fois l’installation du package terminée, attendez le(s) message(s) suivant(s) dans les journaux :

   `Completed the post deployment setup script`

   Le message ci-dessus indique que toutes les étapes d’installation sont terminées.

   Si vous rencontrez l’un des préfixes d’ERREUR suivants, signalez-le à votre équipe du succès client :

   - Erreur dans le script de configuration de post-déploiement
   - Exception lors du portage du MAP de traduction
   - Impossible de transférer la carte de traduction de v1 vers v2 pour la propriété
1. Mise à niveau du plug-in Oxygen connector publié avec la version 4.6.0 \(si nécessaire\).
1. Effacez la mémoire cache du navigateur après l’installation du package.

## Après avoir installé la version 4.6.0

Après avoir installé Experience Manager Guides, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée avec votre configuration.

>[!NOTE]
>
> Le modèle dam-update-asset peut être personnalisé. Ainsi, si des personnalisations ont été effectuées, nous devons les synchroniser avec Experience Manager Guides dans la copie de travail du modèle.

1. **Workflow Ressource de mise à jour de la gestion des ressources numériques \(Modifications de post-traitement\):**

1. Ouvrir l’URL :

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Sélectionnez **workflow Ressource de mise à jour de la gestion des ressources numériques**.
1. Cliquez sur **Modifier**.
1. Si le composant **DXML Post Process Initiator** est présent, assurez-vous que les personnalisations sont synchronisées.
1. En l’absence du composant **DXML Post Process Initiator**, procédez comme suit pour l’insérer :

1. Cliquez sur **Insérer le composant** \(Responsable du post-traitement Experience Manager Guides en tant qu’étape finale du processus\).
1. Configurez l’**étape du processus** avec les détails suivants :

   **Onglet courant**

   **Title :** initiateur de post-processus DXML

   **Description** : étape d’initialisation de post-traitement DXML qui déclenchera une tâche sling pour le post-traitement DXML de la ressource modifiée/créée

   **Onglet Processus**

   - Sélectionnez **DXML Post Process Initiator** dans le menu déroulant **Process**

   - Sélectionnez **Avance du gestionnaire**

   - Sélectionnez **Terminé**

1. Cliquez sur **Synchronisation** en haut à droite après avoir effectué les modifications. Vous recevrez une notification de succès.

   >[!NOTE]
   >
   > Actualisez et vérifiez que les modifications personnalisées et l’étape de post-traitement Experience Manager Guides sont présentes dans le modèle de workflow final.

1. Une fois que le **workflow Ressource de mise à jour de gestion des ressources numériques** est validé, vérifiez les configurations de lanceur correspondantes. Pour ce faire, accédez à l’interface de workflow d’AEM et ouvrez les lanceurs.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Recherchez les deux lanceurs suivants \(qui doivent être actifs\) correspondant au workflow **Ressource de mise à jour de la gestion des ressources numériques et apportez-y des modifications**(si nécessaire\) :

1. Lanceur de « *Node créé* » pour le **workflow Ressource de mise à jour de la gestion des ressources numériques**- pour la condition `"jcr:content/jcr:mimeType!=video"`, la valeur « Globbing » doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; doit avoir des `"event-user-data:changedByWorkflowProcess"`.
   - Lanceur pour « *Node modifié* » pour **workflow Ressource de mise à jour de la gestion des ressources numériques -** pour la condition « `jcr:content/jcr:mimeType!=video` », la valeur « Globbing » doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` aurait dû être `"event-user-data:changedByWorkflowProcess"`.

1. Une fois la mise à niveau terminée, assurez-vous que toutes les personnalisations/superpositions sont validées et mises à jour pour correspondre au nouveau code de l’application. Voici quelques exemples :
   - Tous les composants superposés depuis /libs/editor/libs doivent être comparés au nouveau code de produit et les mises à jour doivent être effectuées dans les fichiers superposés sous /apps.
   - Toutes les catégories de bibliothèques clientes utilisées à partir du produit doivent être examinées pour les modifications. Toutes les configurations remplacées \(exemples ci-dessous\) doivent être comparées aux dernières afin d’obtenir les dernières fonctionnalités :
   - elementmapping.xml
   - ui\_config.json\(peut avoir été défini dans profils de dossier\)
   - `com.adobe.fmdita.config.ConfigManager` modifié

1. Si vous avez ajouté des personnalisations dans damAssetLucene, vous devrez peut-être les appliquer à nouveau. Après avoir effectué ces modifications, définissez la réindexation sur true. Cela réindexera tous les nœuds existants avec les personnalisations. Une fois l’opération terminée, l’indicateur de réindexation est de nouveau défini sur false. Cette opération peut prendre quelques heures en fonction du nombre de ressources dans le système.

## Procédure de réindexation des index Experience Manager Guides

1. Ouvrez `crx/de` et accédez au chemin d’accès de l’index : `/oak:index/guidesAssetProperties`
2. Définissez la propriété reindex sur `true` (`false` par défaut) et cliquez sur **Enregistrer tout**.
3. Une fois la réindexation terminée, la propriété Reindex est définie sur `false` et le nombre de réindex est incrémenté de 1.

   >[!NOTE]
   >
   > Cela peut prendre quelques minutes, selon la quantité de données présentes.
4. Suivez les mêmes étapes pour d’autres index ajoutés ou modifiés : `guidesBulkActivation`, `guidesPeerLinkIndex` et `guidesKonnectTemplateIndex`.

## Procédure d’indexation du contenu existant



Effectuez les étapes suivantes pour indexer le contenu existant :

- Exécutez une requête POST au serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facultatif) Vous pouvez transmettre des chemins spécifiques des mappages pour les indexer. Par défaut, tous les mappages sont indexés || Exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée : `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(par exemple : ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`).

- Une fois la tâche terminée, la requête GET ci-dessus répond avec succès et mentionne si des mappages ont échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.


>[!NOTE]
>
> Si vous utilisez le schéma personnalisé, vous devez définir le chemin d’accès des fichiers DTD et XSD catalog.xml personnalisés dans le référentiel AEM dans l’option **Intégrer les catalogues**.




## Procédure à suivre pour gérer le conflit de `'fmdita rewriter'`

Experience Manager Guides dispose d’un module [**custom sling rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter) qui gère les liens générés en cas de mappages croisés (liens entre les rubriques de deux mappages différents).

Si votre base de code contient un autre module de réécriture Sling personnalisé, utilisez une valeur de `'order'` supérieure à 50, car le module de réécriture Sling de Experience Manager Guides utilise `'order'` 50.  Pour remplacer cela, vous avez besoin d’une valeur >50. Pour plus d’informations, consultez la section [Pipelines de réécriture de sortie](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Lors de cette mise à niveau, puisque la valeur `'order'` est modifiée de 1 000 à 50, vous devez fusionner le module de réécriture personnalisé existant, le cas échéant, avec `'fmdita-rewriter'`.


## Mise à niveau vers la version 5.0.0

>[!TIP]
>
> La mise à niveau vers la version 5.0.0 du pack de services 2 dépend de la version actuelle de Experience Manager Guides. Si vous utilisez la version 5.0.0 Service Pack 1 ou 5.0.0, vous pouvez directement effectuer la mise à niveau vers la version 5.0.0 Service Pack 2.

>[!NOTE]
>
> Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de démarrer le processus de mise à niveau pendant les heures creuses.

****Conditions préalables****

Avant de lancer le processus de mise à niveau vers Experience Manager Guides 5.0.0, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 4.6.3, 4.6.1, 4.6.0 ou 4.4 et achèvement des étapes d’installation respectives.
1. (Facultatif) A fermé toutes les tâches de traduction.
1. Modification du niveau de journal en **INFO** pour `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` classe et ajout de ces journaux dans un nouveau fichier journal, par exemple, `logs/translation_upgrade.log`.


## Installation version 5.0.0

1. Téléchargez le package de la version 5.0.0 à partir du portail de distribution logicielle [Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package de la version 5.0.0.
1. Vous pouvez choisir d’APPUYER sur le déclencheur pour démarrer la tâche de mise à niveau de la carte de traduction. Pour plus d’informations, consultez [ Activation du déclencheur de script via une servlet](#enable-trigger-of-script-via-a-servlet).

1. Une fois l’installation du package terminée, attendez le(s) message(s) suivant(s) dans les journaux :

   `Completed the post deployment setup script`

   Le message ci-dessus indique que toutes les étapes d’installation sont terminées.

   Si vous rencontrez l’un des préfixes d’ERREUR suivants, signalez-le à votre équipe du succès client :

   - Erreur dans le script de configuration de post-déploiement
   - Exception lors du portage du MAP de traduction
   - Impossible de transférer la carte de traduction de v1 vers v2 pour la propriété
1. Mise à niveau du plug-in Oxygen connector avec la version 5.0.0 \(si nécessaire\).
1. Effacez la mémoire cache du navigateur après l’installation du package.

## Après avoir installé la version 5.0.0

Après avoir installé Experience Manager Guides, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée avec votre configuration.

>[!NOTE]
>
> Le modèle dam-update-asset peut être personnalisé. Ainsi, si des personnalisations ont été effectuées, nous devons les synchroniser avec Experience Manager Guides dans la copie de travail du modèle.

1. **Workflow Ressource de mise à jour de la gestion des ressources numériques \(Modifications de post-traitement\):**

1. Ouvrir l’URL :

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Sélectionnez **workflow Ressource de mise à jour de la gestion des ressources numériques**.
1. Cliquez sur **Modifier**.
1. Si le composant **DXML Post Process Initiator** est présent, assurez-vous que les personnalisations sont synchronisées.
1. En l’absence du composant **DXML Post Process Initiator**, procédez comme suit pour l’insérer :

1. Cliquez sur **Insérer le composant** \(Responsable du post-traitement Experience Manager Guides en tant qu’étape finale du processus\).
1. Configurez l’**étape du processus** avec les détails suivants :

   **Onglet courant**

   **Title :** initiateur de post-processus DXML

   **Description** : étape d’initialisation de post-traitement DXML qui déclenchera une tâche sling pour le post-traitement DXML de la ressource modifiée/créée

   **Onglet Processus**

   - Sélectionnez **DXML Post Process Initiator** dans le menu déroulant **Process**

   - Sélectionnez **Avance du gestionnaire**

   - Sélectionnez **Terminé**

1. Cliquez sur **Synchronisation** en haut à droite après avoir effectué les modifications. Vous recevrez une notification de succès.

   >[!NOTE]
   >
   > Actualisez et vérifiez que les modifications personnalisées et l’étape de post-traitement Experience Manager Guides sont présentes dans le modèle de workflow final.

1. Une fois que le **workflow Ressource de mise à jour de gestion des ressources numériques** est validé, vérifiez les configurations de lanceur correspondantes. Pour ce faire, accédez à l’interface de workflow d’AEM et ouvrez les lanceurs.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Recherchez les deux lanceurs suivants \(qui doivent être actifs\) correspondant au workflow **Ressource de mise à jour de la gestion des ressources numériques et apportez-y des modifications**(si nécessaire\) :

1. Lanceur de « *Node créé* » pour le **workflow Ressource de mise à jour de la gestion des ressources numériques**- pour la condition `"jcr:content/jcr:mimeType!=video"`, la valeur « Globbing » doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; doit avoir des `"event-user-data:changedByWorkflowProcess"`.
   - Lanceur pour « *Node modifié* » pour **workflow Ressource de mise à jour de la gestion des ressources numériques -** pour la condition « `jcr:content/jcr:mimeType!=video` », la valeur « Globbing » doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` aurait dû être `"event-user-data:changedByWorkflowProcess"`.

1. Une fois la mise à niveau terminée, assurez-vous que toutes les personnalisations/superpositions sont validées et mises à jour pour correspondre au nouveau code de l’application. Voici quelques exemples :
   - Tous les composants superposés depuis /libs/editor/libs doivent être comparés au nouveau code de produit et les mises à jour doivent être effectuées dans les fichiers superposés sous /apps.
   - Toutes les catégories de bibliothèques clientes utilisées à partir du produit doivent être examinées pour les modifications. Toutes les configurations remplacées \(exemples ci-dessous\) doivent être comparées aux dernières afin d’obtenir les dernières fonctionnalités :
   - elementmapping.xml
   - ui\_config.json\(peut avoir été défini dans profils de dossier\)
   - `com.adobe.fmdita.config.ConfigManager` modifié

1. Si vous avez ajouté des personnalisations dans damAssetLucene, vous devrez peut-être les appliquer à nouveau. Après avoir effectué ces modifications, définissez la réindexation sur true. Cela réindexera tous les nœuds existants avec les personnalisations. Une fois l’opération terminée, l’indicateur de réindexation est de nouveau défini sur false. Cette opération peut prendre quelques heures en fonction du nombre de ressources dans le système.

## Procédure de réindexation des index Experience Manager Guides

1. Ouvrez `crx/de` et accédez au chemin d’accès de l’index : `/oak:index/guidesAssetProperties`
2. Définissez la propriété reindex sur `true` (`false` par défaut) et cliquez sur **Enregistrer tout**.
3. Une fois la réindexation terminée, la propriété Reindex est définie sur `false` et le nombre de réindex est incrémenté de 1.

   >[!NOTE]
   >
   > Cela peut prendre quelques minutes, selon la quantité de données présentes.
4. Suivez les mêmes étapes pour d’autres index ajoutés ou modifiés : `guidesBulkActivation`, `guidesPeerLinkIndex` et `guidesKonnectTemplateIndex`.

## Procédure d’indexation du contenu existant



Effectuez les étapes suivantes pour indexer le contenu existant :

- Exécutez une requête POST au serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facultatif) Vous pouvez transmettre des chemins spécifiques des mappages pour les indexer. Par défaut, tous les mappages sont indexés || Exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée : `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(par exemple : ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`).

- Une fois la tâche terminée, la requête GET ci-dessus répond avec succès et mentionne si des mappages ont échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.


>[!NOTE]
>
> Si vous utilisez le schéma personnalisé, vous devez définir le chemin d’accès des fichiers DTD et XSD catalog.xml personnalisés dans le référentiel AEM dans l’option **Intégrer les catalogues**.




## Procédure à suivre pour gérer le conflit de `'fmdita rewriter'`

Experience Manager Guides dispose d’un module [**custom sling rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter) qui gère les liens générés en cas de mappages croisés (liens entre les rubriques de deux mappages différents).

Si votre base de code contient un autre module de réécriture Sling personnalisé, utilisez une valeur de `'order'` supérieure à 50, car le module de réécriture Sling de Experience Manager Guides utilise `'order'` 50.  Pour remplacer cela, vous avez besoin d’une valeur >50. Pour plus d’informations, consultez la section [Pipelines de réécriture de sortie](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Lors de cette mise à niveau, puisque la valeur `'order'` est modifiée de 1 000 à 50, vous devez fusionner le module de réécriture personnalisé existant, le cas échéant, avec `'fmdita-rewriter'`.



## Procédure de réindexation de damAssetLucene

La définition d’index est mise à jour pour damAssetLucene avec des guides. Consultez [cet article](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-16460) pour réindexer damAssetLucene après la mise à niveau vers la version 5.0.0.

>[!NOTE]
>
> Tout en suivant la documentation, assurez-vous que les deux propriétés (reindex=true et reindex-async=true pour /oak:index/damAssetLucene) sont mises à jour simultanément via l’opération d’enregistrement.

## Mise à niveau vers la version 5.1.0

>[!IMPORTANT]
>
> Si vous utilisez actuellement AEM 6.5 et envisagez de passer à AEM 6.5 LTS, veillez à effectuer d’abord la mise à niveau d’AEM avant de poursuivre la mise à niveau vers Experience Manager Guides 5.1.0. Pour plus d’informations, consultez la section [Mise à niveau vers Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

**Conditions préalables**

>[!NOTE]
>
>Si vous effectuez une mise à niveau vers le pack de services 1 d’ 5.1.0, vous devez utiliser la version 5.1.0 de Experience Manager Guides.

Avant de lancer le processus de mise à niveau vers Experience Manager Guides 5.1.0, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 4.6.3, 4.6.4, 5.0.0 ou 5.0.0 Service Pack 1 et achèvement de l’étape d’installation correspondante.
1. (Facultatif) A fermé toutes les tâches de traduction.
1. Modification du niveau de journal en **INFO** pour `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` classe et ajout de ces journaux dans un nouveau fichier journal, par exemple, `logs/translation_upgrade.log`.

>[!NOTE]
>
> Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de démarrer le processus de mise à niveau pendant les heures creuses.

## Installer la version 5.1.0

1. Téléchargez le package de la version 5.1.0 à partir du portail de distribution logicielle [Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package de la version 5.1.0.
1. Vous pouvez choisir d’APPUYER sur le déclencheur pour démarrer la tâche de mise à niveau de la carte de traduction. Pour plus d’informations, consultez [ Activation du déclencheur de script via une servlet](#enable-trigger-of-script-via-a-servlet).

1. Une fois l’installation du package terminée, attendez le(s) message(s) suivant(s) dans les journaux :

   `Completed the post deployment setup script`

   Le message ci-dessus indique que toutes les étapes d’installation sont terminées.

   Si vous rencontrez l’un des préfixes d’ERREUR suivants, signalez-le à votre équipe du succès client :

   - Erreur dans le script de configuration de post-déploiement
   - Exception lors du portage du MAP de traduction
   - Impossible de transférer la carte de traduction de v1 vers v2 pour la propriété
1. Mise à niveau du plug-in Oxygen connector publié avec la version 5.1.0 \(si nécessaire\).
1. Effacez la mémoire cache du navigateur après l’installation du package.

## Après avoir installé la version 5.1.0

Après avoir installé Experience Manager Guides, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée avec votre configuration.

>[!NOTE]
>
> Le modèle dam-update-asset peut être personnalisé. Ainsi, si des personnalisations ont été effectuées, nous devons les synchroniser avec Experience Manager Guides dans la copie de travail du modèle.

1. **Workflow Ressource de mise à jour de la gestion des ressources numériques \(Modifications de post-traitement\):**

1. Ouvrir l’URL :

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Sélectionnez **workflow Ressource de mise à jour de la gestion des ressources numériques**.
1. Sélectionnez **Modifier**.
1. Si le composant **DXML Post Process Initiator** est présent, assurez-vous que les personnalisations sont synchronisées.
1. En l’absence du composant **DXML Post Process Initiator**, procédez comme suit pour l’insérer :

1. Sélectionnez **Insérer le composant** \(Responsable du post-traitement Experience Manager Guides comme étape finale du processus\).
1. Configurez l’**étape du processus** avec les détails suivants :

   **Onglet courant**

   **Title :** initiateur de post-processus DXML

   **Description** : étape d’initialisation de post-traitement DXML qui déclenchera une tâche sling pour le post-traitement DXML de la ressource modifiée/créée

   **Onglet Processus**

   - Sélectionnez **DXML Post Process Initiator** dans le menu déroulant **Process**

   - Sélectionnez **Avance du gestionnaire**

   - Sélectionnez **Terminé**

1. Sélectionnez **Synchronisation** en haut à droite après avoir effectué les modifications. Vous recevrez une notification de succès.

   >[!NOTE]
   >
   > Actualisez et vérifiez que les modifications personnalisées et l’étape de post-traitement Experience Manager Guides sont présentes dans le modèle de workflow final.

1. Une fois que le **workflow Ressource de mise à jour de gestion des ressources numériques** est validé, vérifiez les configurations de lanceur correspondantes. Pour ce faire, accédez à l’interface de workflow d’AEM et ouvrez les lanceurs.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Recherchez les deux lanceurs suivants \(qui doivent être actifs\) correspondant au workflow **Ressource de mise à jour de la gestion des ressources numériques et apportez-y des modifications**(si nécessaire\) :

1. Lanceur de « *Node créé* » pour le **workflow Ressource de mise à jour de la gestion des ressources numériques**- pour la condition `"jcr:content/jcr:mimeType!=video"`, la valeur « Globbing » doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; doit avoir des `"event-user-data:changedByWorkflowProcess"`.
   - Lanceur pour « *Node modifié* » pour **workflow Ressource de mise à jour de la gestion des ressources numériques -** pour la condition « `jcr:content/jcr:mimeType!=video` », la valeur « Globbing » doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` aurait dû être `"event-user-data:changedByWorkflowProcess"`.

1. Une fois la mise à niveau terminée, assurez-vous que toutes les personnalisations/superpositions sont validées et mises à jour pour correspondre au nouveau code de l’application. Voici quelques exemples :
   - Tous les composants superposés depuis /libs/editor/libs doivent être comparés au nouveau code de produit et les mises à jour doivent être effectuées dans les fichiers superposés sous /apps.
   - Toutes les catégories de bibliothèques clientes utilisées à partir du produit doivent être examinées pour les modifications. Toutes les configurations remplacées \(exemples ci-dessous\) doivent être comparées aux dernières afin d’obtenir les dernières fonctionnalités :
   - elementmapping.xml
   - ui\_config.json\(peut avoir été défini dans profils de dossier\)
   - `com.adobe.fmdita.config.ConfigManager` modifié

1. Si vous avez ajouté des personnalisations dans damAssetLucene, vous devrez peut-être les appliquer à nouveau. Après avoir effectué ces modifications, définissez la réindexation sur true. Cela réindexera tous les nœuds existants avec les personnalisations. Une fois l’opération terminée, l’indicateur de réindexation est de nouveau défini sur false. Cette opération peut prendre quelques heures en fonction du nombre de ressources dans le système.

## Procédure de réindexation des index Experience Manager Guides

1. Ouvrez `crx/de` et accédez au chemin d’accès de l’index : `/oak:index/guidesAssetProperties`
2. Définissez la propriété reindex sur `true` (`false` par défaut) et cliquez sur **Enregistrer tout**.
3. Une fois la réindexation terminée, la propriété Reindex est définie sur `false` et le nombre de réindex est incrémenté de 1.

   >[!NOTE]
   >
   > Cela peut prendre quelques minutes, selon la quantité de données présentes.
4. Suivez les mêmes étapes pour d’autres index ajoutés ou modifiés : `guidesBulkActivation`, `guidesPeerLinkIndex` et `guidesKonnectTemplateIndex`.

## Procédure d’indexation du contenu existant



Effectuez les étapes suivantes pour indexer le contenu existant :

- Exécutez une requête POST au serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facultatif) Vous pouvez transmettre des chemins spécifiques des mappages pour les indexer. Par défaut, tous les mappages sont indexés || Exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée : `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(par exemple : ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`).

- Une fois la tâche terminée, la requête GET ci-dessus répond avec succès et mentionne si des mappages ont échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.


>[!NOTE]
>
> Si vous utilisez le schéma personnalisé, vous devez définir le chemin d’accès des fichiers DTD et XSD catalog.xml personnalisés dans le référentiel AEM dans l’option **Intégrer les catalogues**.




## Procédure à suivre pour gérer le conflit de `'fmdita rewriter'`

Experience Manager Guides dispose d’un module [**custom sling rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter) qui gère les liens générés en cas de mappages croisés (liens entre les rubriques de deux mappages différents).

Si votre base de code contient un autre module de réécriture Sling personnalisé, utilisez une valeur de `'order'` supérieure à 50, car le module de réécriture Sling de Experience Manager Guides utilise `'order'` 50.  Pour remplacer cela, vous avez besoin d’une valeur >50. Pour plus d’informations, consultez la section [Pipelines de réécriture de sortie](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Lors de cette mise à niveau, puisque la valeur `'order'` est modifiée de 1 000 à 50, vous devez fusionner le module de réécriture personnalisé existant, le cas échéant, avec `'fmdita-rewriter'`.



## Procédure de réindexation de damAssetLucene

La définition d’index est mise à jour pour damAssetLucene avec des guides. Consultez [cet article](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-16460) pour réindexer damAssetLucene après la mise à niveau vers la version 5.1.0.

>[!NOTE]
>
> Tout en suivant la documentation, assurez-vous que les deux propriétés (reindex=true et reindex-async=true pour /oak:index/damAssetLucene) sont mises à jour simultanément via l’opération d’enregistrement.



**Rubrique parente :** [Télécharger et installer](download-install.md)
