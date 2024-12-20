---
title: Mettre à niveau Adobe Experience Manager Guides
description: Découvrez comment mettre à niveau Adobe Experience Manager Guides
exl-id: f058b39f-7408-4874-942b-693e133886cf
feature: Installation
role: Admin
level: Experienced
source-git-commit: 2362870e0e3e6c08df03e8c547bb77de7faa0a02
workflow-type: tm+mt
source-wordcount: '7008'
ht-degree: 0%

---

# Mettre à niveau Adobe Experience Manager Guides {#id224MBE0M0XA}

>[!NOTE]
>
> Suivez les instructions de mise à niveau spécifiques à la version sous licence de votre produit.

Vous pouvez mettre à niveau votre version actuelle de Experience Manager Guides vers la version 4.6.0 Service Pack 1 :


- Si vous utilisez la version 4.6.0, vous pouvez directement effectuer la mise à niveau vers le Service Pack 1 4.6.0.
- Si vous utilisez la version 4.4, 4.3.1 ou 4.3.0 , vous devez effectuer la mise à niveau vers la version 4.6.0 avant de passer à la version 4.6.0 Service Pack 1.
- Si vous utilisez les versions 4.2, 4.2.1 (correctif 4.2.1.3), 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers la version 4.4 avant de passer à la version 4.6.0.
- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant de passer à la version 4.3.x.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à 3.8.5, reportez-vous à la section Mise à niveau de Experience Manager Guides dans le guide d’installation spécifique au produit disponible sur l’ [archive du PDF d’aide Adobe Experience Manager Guides](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).


>[!NOTE]
>
> Vous devez installer AEM Service Pack avant de mettre à niveau la version de Experience Manager Guides.

Pour plus de détails, consultez les procédures suivantes :

- [Mise à niveau de 3.8.5 vers la version 4.0](#id2256DK003E1)
- [Upgrade vers la version 4.2](#id22A3F500SXA)
- [Mise à niveau vers la version 4.2.1](#upgrade-version-4-2-1)
- [Mise à niveau vers la version 4.3.0](#upgrade-version-4-3)
- [Mise à niveau vers la version 4.3.1](#upgrade-version-4-3-1)
- [Mise à niveau vers la version 4.3.1.5](#upgrade-version-4-3-1-5)
- [Mise à niveau vers la version 4.4.0](#upgrade-version-4-4-0)
- [Mise à niveau vers la version 4.6.0](#upgrade-version-4-6-0)



>[!IMPORTANT]
>
> Avant de commencer la mise à niveau, effectuez une sauvegarde complète du système afin d’éviter toute perte de données.

## Mise à niveau de la version 3.8.5 vers la version 4.0 {#id2256DK003E1}

Si vous utilisez Experience Manager Guides version 3.8.5, vous pouvez effectuer la mise à niveau vers la version 4.0 de Experience Manager Guides. Avec la fonction de mise à niveau, vous n’avez pas à désinstaller la version précédente de Experience Manager Guides.

Avant d’exécuter le processus, vous devez effectuer certaines tâches. Les sous-sections suivantes décrivent les conditions préalables, la génération de rapports et le processus de migration. En outre, après l’installation de Experience Manager Guides version 4.0, vous pouvez personnaliser différentes configurations, en fonction des paramètres du client.

>[!NOTE]
>
> Ce processus de mise à niveau s’applique uniquement de la version 3.8.5 à la version 4.0. Pour le processus de mise à niveau de la version 3.4 ou ultérieure vers la version 3.8.5, reportez-vous à la section *Mise à niveau de Experience Manager Guides* du guide d’installation spécifique au produit disponible dans l’ [archive du PDF d’aide Adobe Experience Manager Guides](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).



****Conditions préalables****

Avant de commencer la mise à niveau vers Experience Manager Guides, vérifiez que vous disposez des éléments suivants :

1. Importation des commentaires de révision dans les rubriques ouvertes pour révision.
1. Fermer toutes les révisions actives.
1. Fermeture de toutes les tâches de traduction
1. Désinstallez tous les correctifs Experience Manager Guides installés en haut de la version précédente \(version majeure ou version de correctif\) de Experience Manager Guides.

**Avant d’installer la version 4.0**

Avant d’installer la version 4.0, procédez comme suit :

1. Vérifiez que Experience Manager Guides est sur la version 3.8.5.
1. Téléchargez le package de script de mise à niveau. Pour ce faire, recherchez &quot;Package de mise à niveau de la solution XML Documentation 4.0&quot; sur [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) qui téléchargera un fichier zip.
1. Téléchargez ce package vers AEM via Package Manager et installez ce package.
1. Une fois le package de mise à niveau installé, exécutez les scripts ci-dessous dans le même ordre et suivez les instructions données :

**Vérifier l’API de compatibilité de mise à niveau**

Cette API est conçue pour évaluer l’état actuel du système et pour signaler si la mise à niveau est possible ou non. Pour exécuter ce script, déclenchez le point de terminaison ci-dessous :

| Point d’entrée | /bin/dxml/upgrade/3xto4x/report |
| --- | --- |
| Type de requête | **GET** Vous pouvez utiliser un navigateur web dans lequel vous êtes connecté en tant qu’administrateur à l’instance AEM. |
| Réponse attendue | -   Si tous les noeuds requis peuvent être déplacés, vous obtiendrez une vérification. <br>-   Si un noeud est présent à l’emplacement cible, vous obtenez une erreur pertinente. Nettoyez le référentiel \(supprimez le noeud /var/dxml\), réinstallez le package de mise à niveau, puis déclenchez à nouveau ce point de terminaison. <br>**Remarque :** Cette erreur n’est pas courante, car l’emplacement cible n’est pas utilisé plus tôt par Experience Manager Guides 3.x. <br> -   Si ce script échoue, ne procédez pas et signalez-le à votre équipe de réussite client. |

**API de migration des données système**

Cette API est conçue pour migrer les données système comme mentionné dans la section **Migration Mapping** .

1. N’exécutez pas ce script si l’API de vérification de la compatibilité de mise à niveau échoue \(ne procédez pas\).
1. Une fois que l’API Vérifier la compatibilité de mise à niveau renvoie la réussite, vous pouvez exécuter le script de mise à niveau.

| Point d’entrée | /bin/dxml/upgrade/3xto4x |
| --- | --- |
| Type de requête | **POST** Ce script est une requête de POST qui doit donc être exécutée via des agents tels que Postman. |
| Réponse attendue | -   Une fois la migration réussie, vous pouvez installer la solution XML Documentation version 4.0.<br>-   En cas d’erreur, restaurez au dernier point de contrôle et partagez les journaux d’erreur avec la sortie de l’API avec votre équipe de succès client. |

**Mappage de migration** : l’API ci-dessus migre toutes les données sous l’emplacement source vers l’emplacement cible.

| Source | Cible |
|------|------|
| /content/fmdita | /var/dxml |
| /content/dxml | /var/dxml |
| /etc/fmdita | /libs/fmdita |

## Installation de la version 4.0 {#id23598G006XA}

1. Installez la version 4.0 uniquement si les étapes de mise à niveau ont réussi.
1. Téléchargez le package de version 4.0 à partir du [portail de distribution de logiciels Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) :

   - Si vous utilisez la version UID du logiciel, recherchez &quot;Version 4.0 UUID pour la solution XML Documentation pour AEM 6.5&quot;.
   - Si vous utilisez une version non UUID du logiciel, recherchez &quot;Version 4.0 non UUID pour la solution XML Documentation pour AEM 6.5&quot;.
Téléchargez le package sur l’instance de serveur AEM existante à l’aide de CRX Package Manager et installez-le.

   >[!NOTE]
   >
   > Attendez que tous les composants système démarrent.

1. Effacez le cache du navigateur après l’installation du package.
1. Si un dispatcher est configuré sur l’instance d’auteur AEM, procédez comme suit :
   - Assurez-vous que les éléments suivants sont gérés dans les règles du Dispatcher :
   - Le modèle d’URL /home/users/\*/preferences est placé sur liste blanche.
   - Le modèle d’URL /libs/cq/security/userinfo.json n’est pas mis en cache.
1. Effacez le cache du Dispatcher \(pour effacer tout `clientlibs` mis en cache\).

## Upgrade vers la version 4.2 {#id22A3F500SXA}

La mise à niveau vers la version 4.2 dépend de la version actuelle de Experience Manager Guides.

Si vous utilisez la version 4.0, 4.1 ou 4.1.x, vous pouvez directement mettre à niveau vers la version 4.2.

****Conditions préalables****

Avant de démarrer le processus de mise à niveau vers Experience Manager Guides 4.2, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 4.0, 4.1 ou 4.1.x.
1. Fermeture de toutes les tâches de traduction
1. Modification du niveau de journal en **INFO** pour la classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` et ajout de ces journaux dans un nouveau fichier journal, par exemple `logs/translation_upgrade.log.`

>[!NOTE]
>
> Vous devez fermer toutes les révisions actives. Si les tâches de révision ne sont pas fermées lors de la mise à niveau vers la version 4.2, les anciennes tâches de révision en cours continuent d’emmener les utilisateurs sur les anciennes pages de révision, et les tâches de révision créées après la mise à niveau afficheront les dernières mises à jour de la fonctionnalité.

## Installation de la version 4.2 {#id2245IK0E0EV}

1. Téléchargez le package de version 4.2 à partir du [portail de distribution de logiciels Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package version 4.2.
1. Une fois l’installation du package terminée, attendez le ou les messages\(s\) suivants dans les journaux :

   `Completed the post deployment setup script`

   Le message ci-dessus indique que toutes les étapes de l’installation sont terminées.

   Si vous rencontrez l’un des préfixes ERROR suivants, signalez-les à votre équipe de réussite client :

   - Erreur dans le script de configuration après le déploiement
   - Exception lors de la génération de la traduction MAP
   - Impossible de transférer le mappage de traduction de la version 1 à la version 2 pour la propriété
1. Mettre à niveau le module externe du connecteur Oxygen publié avec la version 4.2 \(si nécessaire\).
1. Effacez le cache du navigateur après l’installation du package.
1. Poursuivez la mise à niveau des personnalisations, comme décrit dans la section suivante.

## Après avoir installé la version 4.2 {#id2326F02004K}

>[!IMPORTANT]
>
> Le modèle high-tech n’est pas affiché sur le serveur mis à niveau. Pour inclure le modèle high-tech sur votre serveur, vous pouvez le copier : Source: /libs/fmdita/pdf/Hi-Tech Destination: /content/dam/dita-templates/pdf

Une fois Experience Manager Guides installé, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée à votre configuration.

>[!NOTE]
>
> Le modèle dam-update-asset peut être personnalisé. Ainsi, si des personnalisations ont été effectuées, nous devons synchroniser les personnalisations et Experience Manager Guides dans la copie de travail du modèle.

1. **Workflow de mise à jour de gestion des actifs numériques \(Modifications de post-traitement\) :**

1. URL d’ouverture :

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Sélectionnez **Workflow de mise à jour des ressources de gestion des actifs numériques**.
1. Cliquez sur **Modifier**.
1. Si le composant **DXML Post Process Initiator** est présent, assurez-vous que les personnalisations sont synchronisées.
1. Si le composant **DXML Post Process Initiator** est absent, procédez comme suit pour l’insérer :

1. Cliquez sur **Insérer le composant** \(Responsable du post-traitement Experience Manager Guides comme dernière étape du processus\).
1. Configurez l’ **étape du processus** avec les détails suivants :

   **Onglet commun**

   **Titre :** Initiateur du post-processus DXML

   **Description** : étape de l’initiateur de post-processus DXML qui déclenche une tâche Sling pour le post-traitement DXML de la ressource modifiée/créée

   **Onglet Processus**

   - Sélectionnez **DXML Post Process Initiator** dans la liste déroulante **Process**

   - Sélectionnez **Avance du gestionnaire**

   - Sélectionnez **Done**

1. Cliquez sur **Synchroniser** en haut à droite après avoir terminé les modifications. Vous recevrez une notification de succès.

   >[!NOTE]
   >
   > Actualisez et vérifiez que les modifications personnalisées et l’étape de post-traitement de Experience Manager Guides sont présentes dans le modèle de workflow final.

1. Une fois que le **workflow Ressource de mise à jour de gestion des actifs numériques** est validé, vérifiez les configurations de lanceur correspondantes. Pour ce faire, accédez à AEM interface de workflow et ouvrez les lanceurs.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Recherchez et apportez des modifications \(si nécessaire\) aux deux lanceurs suivants \(qui doivent être actifs\) correspondant au **workflow Ressource de mise à jour de gestion des actifs numériques** :

1. Lanceur pour &quot;*Noeud créé*&quot; pour **Workflow de ressource de mise à jour de gestion des actifs numériques**- pour la condition `"jcr:content/jcr:mimeType!=video"`, la valeur &quot;Globbing&quot; doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; doit avoir `"event-user-data:changedByWorkflowProcess"`.
   - Lanceur pour &quot;*Node modifié*&quot; pour le **workflow Ressource de mise à jour de gestion des actifs numériques -** pour la condition &quot;`jcr:content/jcr:mimeType!=video`&quot;,
   - La valeur &quot;Globbing&quot; doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; doit avoir `"event-user-data:changedByWorkflowProcess"`.
1. Une fois la mise à niveau terminée, vérifiez que toutes les personnalisations/superpositions sont validées et mises à jour pour correspondre au nouveau code de l’application. Voici quelques exemples :
   - Tous les composants superposés à partir de/libs/mditator/libs doivent être comparés au nouveau code de produit et les mises à jour doivent être effectuées dans les fichiers superposés sous/apps.
   - Toutes les catégories clientlib utilisées à partir du produit doivent être examinées pour les modifications. Toutes les configurations remplacées \(exemples ci-dessous\) doivent être comparées aux configurations les plus récentes afin d’obtenir les dernières fonctionnalités :
   - elementmapping.xml
   - ui\_config.json\(peut avoir été défini dans les profils de dossier\)
   - `com.adobe.fmdita.config.ConfigManager` modifié
   - Vérifiez si l’un des codes personnalisés utilisait d’anciens chemins d’accès \(comme mentionné dans la section [Mappage de migration](#id2244LE040XA)\) - doivent être mis à jour vers les nouveaux chemins afin que les personnalisations fonctionnent également comme prévu.
1. Lisez les nouvelles configurations apportées à la version actuelle \(consultez les [notes de mise à jour](../release-info/release-notes-4-3.md)\) et vérifiez si des fonctionnalités sont affectées, puis prenez les mesures appropriées. Un exemple peut être l’utilisation de l’option &quot;Amélioration de la gestion des fichiers et des versions&quot; introduite dans la version 4.0, pour laquelle vous devez activer une configuration.

## Étapes d’indexation du contenu existant pour utiliser la nouvelle recherche et remplacement :

Effectuez les étapes suivantes pour indexer le contenu existant et utilisez le nouveau texte de recherche et de remplacement au niveau de la carte :

- Exécutez une requête de POST sur le serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. \(Facultatif : vous pouvez transmettre des chemins d’accès spécifiques des cartes pour les indexer. Par défaut, toutes les cartes seront indexées \|\| Par exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`\)

- L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison :

`http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

- Une fois la tâche terminée, la requête de GET ci-dessus répond avec succès et indique si une correspondance a échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

Si la tâche de mise à niveau échoue et que le journal des erreurs affiche l’erreur suivante :

&quot;La *requête* a lu ou parcouru plus de *100000 noeuds*. Pour éviter d’affecter d’autres tâches, le traitement a été arrêté.&quot;

Cela peut se produire car l’index n’est pas correctement configuré pour la requête utilisée dans la mise à niveau. Vous pouvez essayer la solution suivante :

1. Dans l’index oak damAssetLucene, ajoutez la propriété booléenne `indexNodeName` en tant que `true` dans le noeud .
   `/oak:index/damAssetLucene/indexRules/dam:Asset`
1. Ajoutez un nouveau noeud avec l’extrait de nom sous le noeud .

   `/oak:index/damAssetLucene/indexRules/dam:Asset/properties`
et définissez les propriétés suivantes dans le noeud :

   ```
   name - rep:excerpt
   propertyIndex - {Boolean}true
   notNullCheckEnabled - {Boolean}true
   ```

   La structure de `damAssetLucene` doit ressembler à quelque chose comme :

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


   (ainsi que d’autres noeuds et propriétés existants)

1. Réindexez l’index `damAssetLucene` (en définissant l’indicateur de réindexation sur `true` sous
et attendez qu’il soit de nouveau `false` (cela indique que la réindexation est terminée). Notez que cela peut prendre quelques heures en fonction de la taille de l’index.
1. Exécutez à nouveau le script d’indexation en suivant les étapes précédentes.


## Mise à niveau vers la version 4.2.1 {#upgrade-version-4-2-1}

>[!TIP]
>
>Il est recommandé d’installer Hotfix 4.2.1.3 sur la version 4.2.1.

La mise à niveau vers la version 4.2.1 dépend de la version actuelle de Experience Manager Guides. Si vous utilisez la version 4.1, 4.1.x ou 4.2, vous pouvez directement effectuer la mise à niveau vers la version 4.2.1.

>[!NOTE]
>
>Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de lancer le processus de mise à niveau aux heures creuses.

****Conditions préalables****

Avant de démarrer le processus de mise à niveau vers Experience Manager Guides 4.2.1, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 4.1, 4.1.x ou 4.2.
1. Fermeture de toutes les tâches de traduction
1. Modification du niveau de journal en **INFO** pour la classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` et ajout de ces journaux dans un nouveau fichier journal, par exemple `logs/translation_upgrade.log.`

>[!NOTE]
>
> Vous devez fermer toutes les révisions actives. Si les tâches de révision ne sont pas fermées lors de la mise à niveau vers la version 4.2, les anciennes tâches de révision en cours continuent d’emmener les utilisateurs sur les anciennes pages de révision, et les tâches de révision créées après la mise à niveau afficheront les dernières mises à jour de la fonctionnalité.

## Installation de la version 4.2.1

1. Téléchargez le package de version 4.2.1 depuis le [portail de distribution de logiciels Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package version 4.2.1.
1. Vous pouvez choisir d’ACCÉDER au déclencheur pour démarrer la tâche de mise à niveau de la carte de traduction. Pour plus d’informations, voir [Activation du déclencheur de script via un servlet](#enable-trigger-serverlet).


1. Une fois l’installation du package terminée, attendez le ou les messages\(s\) suivants dans les journaux :

   `Completed the post deployment setup script`

   Le message ci-dessus indique que toutes les étapes de l’installation sont terminées.

   Si vous rencontrez l’un des préfixes ERROR suivants, signalez-les à votre équipe de réussite client :

   - Erreur dans le script de configuration après le déploiement
   - Exception lors de la génération de la traduction MAP
   - Impossible de transférer le mappage de traduction de la version 1 à la version 2 pour la propriété
1. Mettre à niveau le module externe du connecteur Oxygen publié avec la version 4.2 \(si nécessaire\).
1. Effacez le cache du navigateur après l’installation du package.
1. Poursuivez la mise à niveau des personnalisations, comme décrit dans la section suivante.

### Activation du déclencheur de script via une servlet{#enable-trigger-serverlet}

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

Dans la réponse JSON ci-dessus, la clé `lockNodePath` contient le chemin d’accès au noeud créé dans le référentiel pointant vers la tâche envoyée. Il sera automatiquement supprimé une fois la tâche terminée. Vous pourrez alors vous référer à ce noeud pour connaître l’état actuel de la tâche.

Exemple de journal :
Voici un exemple de journaux qui s’afficheront dans le fichier journal après le déclenchement du script.

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

Recherchez `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` et `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` avant de passer aux étapes suivantes.



## Après avoir installé la version 4.2.1

>[!IMPORTANT]
>
> Le modèle high-tech n’est pas affiché sur le serveur mis à niveau. Pour inclure le modèle high-tech sur votre serveur, vous pouvez le copier : Source: /libs/fmdita/pdf/Hi-Tech Destination: /content/dam/dita-templates/pdf

Une fois Experience Manager Guides installé, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée à votre configuration.

>[!NOTE]
>
> Le modèle dam-update-asset peut être personnalisé. Ainsi, si des personnalisations ont été effectuées, nous devons synchroniser les personnalisations et Experience Manager Guides dans la copie de travail du modèle.

1. **Workflow de mise à jour de gestion des actifs numériques \(Modifications de post-traitement\) :**

1. URL d’ouverture :

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Sélectionnez **Workflow de mise à jour des ressources de gestion des actifs numériques**.
1. Cliquez sur **Modifier**.
1. Si le composant **DXML Post Process Initiator** est présent, assurez-vous que les personnalisations sont synchronisées.
1. Si le composant **DXML Post Process Initiator** est absent, procédez comme suit pour l’insérer :

1. Cliquez sur **Insérer le composant** \(Responsable du post-traitement Experience Manager Guides comme dernière étape du processus\).
1. Configurez l’ **étape du processus** avec les détails suivants :

   **Onglet commun**

   **Titre :** Initiateur du post-processus DXML

   **Description** : étape de l’initiateur de post-processus DXML qui déclenche une tâche Sling pour le post-traitement DXML de la ressource modifiée/créée

   **Onglet Processus**

   - Sélectionnez **DXML Post Process Initiator** dans la liste déroulante **Process**

   - Sélectionnez **Avance du gestionnaire**

   - Sélectionnez **Done**

1. Cliquez sur **Synchroniser** en haut à droite après avoir terminé les modifications. Vous recevrez une notification de succès.

   >[!NOTE]
   >
   > Actualisez et vérifiez que les modifications personnalisées et l’étape de post-traitement de Experience Manager Guides sont présentes dans le modèle de workflow final.

1. Une fois que le **workflow Ressource de mise à jour de gestion des actifs numériques** est validé, vérifiez les configurations de lanceur correspondantes. Pour ce faire, accédez à AEM interface de workflow et ouvrez les lanceurs.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Recherchez et apportez des modifications \(si nécessaire\) aux deux lanceurs suivants \(qui doivent être actifs\) correspondant au **workflow Ressource de mise à jour de gestion des actifs numériques** :

1. Lanceur pour &quot;*Noeud créé*&quot; pour **Workflow de ressource de mise à jour de gestion des actifs numériques**- pour la condition `"jcr:content/jcr:mimeType!=video"`, la valeur &quot;Globbing&quot; doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; doit avoir `"event-user-data:changedByWorkflowProcess"`.
   - Lanceur pour &quot;*Node Modified*&quot; pour **Workflow de ressource de mise à jour de gestion des actifs numériques -** pour la condition &quot;`jcr:content/jcr:mimeType!=video`&quot;, la valeur &quot;Globbing&quot; doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` doit avoir `"event-user-data:changedByWorkflowProcess"`.

1. Une fois la mise à niveau terminée, vérifiez que toutes les personnalisations/superpositions sont validées et mises à jour pour correspondre au nouveau code de l’application. Voici quelques exemples :
   - Tous les composants superposés à partir de/libs/mditator/libs doivent être comparés au nouveau code de produit et les mises à jour doivent être effectuées dans les fichiers superposés sous/apps.
   - Toutes les catégories clientlib utilisées à partir du produit doivent être examinées pour les modifications. Toutes les configurations remplacées \(exemples ci-dessous\) doivent être comparées aux configurations les plus récentes afin d’obtenir les dernières fonctionnalités :
   - elementmapping.xml
   - ui\_config.json\(peut avoir été défini dans les profils de dossier\)
   - `com.adobe.fmdita.config.ConfigManager` modifié
   - Vérifiez si l’un des codes personnalisés utilisait d’anciens chemins d’accès \(comme mentionné dans la section [Mappage de migration](#id2244LE040XA)\) - doivent être mis à jour vers les nouveaux chemins afin que les personnalisations fonctionnent également comme prévu.
1. Lisez les nouvelles configurations apportées à la version actuelle \(consultez les [notes de mise à jour](../release-info/release-notes-4-2-1.md)\) et vérifiez si des fonctionnalités sont affectées, puis prenez les mesures appropriées. Un exemple peut être l’utilisation de l’option &quot;Amélioration de la gestion des fichiers et des versions&quot; introduite dans la version 4.0, pour laquelle vous devez activer une configuration.

## Étapes d’indexation du contenu existant pour utiliser la nouvelle recherche et remplacement :

Effectuez les étapes suivantes pour indexer le contenu existant et utilisez le nouveau texte de recherche et de remplacement au niveau de la carte :

- Assurez-vous que l&#39;indexation `damAssetLucene` est terminée. Selon la quantité de données présentes sur le serveur, cette opération peut prendre jusqu’à quelques heures. Vous pouvez confirmer que la réindexation est terminée en vérifiant que le champ de réindexation est défini sur false dans
  `http://<server:port>/oak:index/damAssetLucene`.  En outre, si vous avez ajouté des personnalisations dans `damAssetLucene`, vous devrez peut-être les appliquer à nouveau.

- Exécutez une requête de POST sur le serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des cartes pour les indexer ; par défaut, toutes les cartes seront indexées \|\| Par exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- Vous pouvez également transmettre un dossier racine pour indexer les mappages DITA d’un dossier spécifique (et de ses sous-dossiers). Par exemple, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Notez que si les paramètres paths et root sont transmis, seul le paramètre paths est pris en compte.

- L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


- Une fois la tâche terminée, la requête de GET ci-dessus répond avec succès et indique si une correspondance a échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.


## Mise à niveau vers la version 4.3.0 {#upgrade-version-4-3}

La mise à niveau vers la version 4.3.0 dépend de la version actuelle de Experience Manager Guides. Si vous utilisez la version 4.2 ou 4.2.x, vous pouvez directement effectuer la mise à niveau vers la version 4.3.0.

>[!NOTE]
>
>Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de lancer le processus de mise à niveau aux heures creuses.

****Conditions préalables****

Avant de démarrer le processus de mise à niveau vers Experience Manager Guides 4.3.0, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 4.2 ou 4.2.x et exécution de l’étape d’installation correspondante.
1. Fermeture de toutes les tâches de traduction



## Installation de la version 4.3.0

1. Téléchargez le package de version 4.3.0 à partir du [portail de distribution de logiciels Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package version 4.3.0.
1. Effacez le cache du navigateur après l’installation du package.
1. Mettez à niveau le fichier `ui_config.json` à partir de l’onglet **Configuration de l’éditeur XML** dans le profil du dossier.


## Après avoir installé la version 4.3.0

Une fois Experience Manager Guides installé, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée à votre configuration.

## Étapes de post-traitement du contenu existant pour utiliser le rapport de lien rompu


Effectuez les étapes suivantes pour le post-traitement du contenu existant et l’utilisation du nouveau rapport de lien rompu :

1. (Facultatif) S’il existe plus de 100 000 fichiers dita dans le système, mettez à jour la valeur `queryLimitReads` sous `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` vers une valeur plus grande (toute valeur supérieure au nombre de ressources présentes, par exemple 200 000), puis redéployez.

   | PID | Clé de propriété | Valeur de la propriété |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valeur : 200000 <br> Valeur par défaut : 100000 |

1. Exécutez les API suivantes pour exécuter le post-traitement sur tous les fichiers :

   | Point d’entrée | /bin/guides/reports/upgrade |
   |---|---|
   | Type de requête | **POST** Ce script est une requête de POST qui doit donc être exécutée via des agents tels que Postman. |
   | Réponse attendue | L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison.<br> Exemple d’URL : `http://<server:port>/bin/guides/reports/upgrade` |

   | Point d’entrée | /bin/guides/reports/upgrade |
   |---|---|
   | Type de requête | **GET** |
   | Param | jobId : transmettez le jobId reçu de la requête de publication précédente. |
   | Réponse attendue | - Une fois la tâche terminée, la requête de GET répond avec succès. <br> - En cas d’erreur, partagez les journaux d’erreur avec la sortie de l’API avec votre équipe de succès client.  <br>Exemple d’URL : `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |


1. Revenez à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifiée à l’étape 1.



## Mise à niveau vers la version 4.3.1 {#upgrade-version-4-3-1}

La mise à niveau vers la version 4.3.1 dépend de la version actuelle de Experience Manager Guides. Si vous utilisez la version 4.3.0, 4.2 ou 4.2.1, vous pouvez directement effectuer la mise à niveau vers la version 4.3.1.

>[!NOTE]
>
>Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de lancer le processus de mise à niveau aux heures creuses.

****Conditions préalables****

Avant de démarrer le processus de mise à niveau vers Experience Manager Guides 4.3.1, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers la version 4.3.0, 4.2 ou 4.2.1 de Experience Manager Guides et exécution de l’étape d’installation correspondante.
1. (Facultatif) Fermez toutes les tâches de traduction.
1. Le niveau de journal a été remplacé par **INFO** pour la classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` et ajoutez ces journaux dans un nouveau fichier journal, par exemple `logs/translation_upgrade.log`.


## Installation de la version 4.3.1

1. Téléchargez le package de version 4.3.1 depuis le [portail de distribution de logiciels Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package version 4.3.1.
1. Vous pouvez choisir d’ACCÉDER au déclencheur pour démarrer la tâche de mise à niveau de la carte de traduction. Pour plus d’informations, voir [Activation du déclencheur de script via un servlet](#enable-trigger-serverlet-4-3-1).


1. Une fois l’installation du package terminée, attendez le ou les messages\(s\) suivants dans les journaux :

   `Completed the post deployment setup script`

   Le message ci-dessus indique que toutes les étapes de l’installation sont terminées.

   Si vous rencontrez l’un des préfixes ERROR suivants, signalez-les à votre équipe de réussite client :

   - Erreur dans le script de configuration après le déploiement
   - Exception lors de la génération de la traduction MAP
   - Impossible de transférer le mappage de traduction de la version 1 à la version 2 pour la propriété
1. Mettre à niveau le module externe du connecteur Oxygen publié avec la version 4.2 \(si nécessaire\).
1. Effacez le cache du navigateur après l’installation du package.
1. Poursuivez la mise à niveau des personnalisations, comme décrit dans la section suivante.

### Activation du déclencheur de script via une servlet{#enable-trigger-serverlet-4-3-1}

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

Dans la réponse JSON ci-dessus, la clé `lockNodePath` contient le chemin d’accès au noeud créé dans le référentiel pointant vers la tâche envoyée. Il sera automatiquement supprimé une fois la tâche terminée. Vous pourrez alors vous référer à ce noeud pour connaître l’état actuel de la tâche.

Exemple de journal :
Voici un exemple de journaux qui s’afficheront dans le fichier journal après le déclenchement du script.

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

Recherchez `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` et `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` avant de passer aux étapes suivantes.

## Après avoir installé la version 4.3.1



Une fois Experience Manager Guides installé, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée à votre configuration.

>[!NOTE]
>
> Le modèle dam-update-asset peut être personnalisé. Ainsi, si des personnalisations ont été effectuées, nous devons synchroniser les personnalisations et Experience Manager Guides dans la copie de travail du modèle.

1. **Workflow de mise à jour de gestion des actifs numériques \(Modifications de post-traitement\) :**

1. URL d’ouverture :

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Sélectionnez **Workflow de mise à jour des ressources de gestion des actifs numériques**.
1. Cliquez sur **Modifier**.
1. Si le composant **DXML Post Process Initiator** est présent, assurez-vous que les personnalisations sont synchronisées.
1. Si le composant **DXML Post Process Initiator** est absent, procédez comme suit pour l’insérer :

1. Cliquez sur **Insérer le composant** \(Responsable du post-traitement Experience Manager Guides comme dernière étape du processus\).
1. Configurez l’ **étape du processus** avec les détails suivants :

   **Onglet commun**

   **Titre :** Initiateur du post-processus DXML

   **Description** : étape de l’initiateur de post-processus DXML qui déclenche une tâche Sling pour le post-traitement DXML de la ressource modifiée/créée

   **Onglet Processus**

   - Sélectionnez **DXML Post Process Initiator** dans la liste déroulante **Process**

   - Sélectionnez **Avance du gestionnaire**

   - Sélectionnez **Done**

1. Cliquez sur **Synchroniser** en haut à droite après avoir terminé les modifications. Vous recevrez une notification de succès.

   >[!NOTE]
   >
   > Actualisez et vérifiez que les modifications personnalisées et l’étape de post-traitement de Experience Manager Guides sont présentes dans le modèle de workflow final.

1. Une fois que le **workflow Ressource de mise à jour de gestion des actifs numériques** est validé, vérifiez les configurations de lanceur correspondantes. Pour ce faire, accédez à AEM interface de workflow et ouvrez les lanceurs.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Recherchez et apportez des modifications \(si nécessaire\) aux deux lanceurs suivants \(qui doivent être actifs\) correspondant au **workflow Ressource de mise à jour de gestion des actifs numériques** :

1. Lanceur pour &quot;*Noeud créé*&quot; pour **Workflow de ressource de mise à jour de gestion des actifs numériques**- pour la condition `"jcr:content/jcr:mimeType!=video"`, la valeur &quot;Globbing&quot; doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; doit avoir `"event-user-data:changedByWorkflowProcess"`.
   - Lanceur pour &quot;*Node Modified*&quot; pour **Workflow de ressource de mise à jour de gestion des actifs numériques -** pour la condition &quot;`jcr:content/jcr:mimeType!=video`&quot;, la valeur &quot;Globbing&quot; doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` doit avoir `"event-user-data:changedByWorkflowProcess"`.

1. Une fois la mise à niveau terminée, vérifiez que toutes les personnalisations/superpositions sont validées et mises à jour pour correspondre au nouveau code de l’application. Voici quelques exemples :
   - Tous les composants superposés à partir de/libs/mditator/libs doivent être comparés au nouveau code de produit et les mises à jour doivent être effectuées dans les fichiers superposés sous/apps.
   - Toutes les catégories clientlib utilisées à partir du produit doivent être examinées pour les modifications. Toutes les configurations remplacées \(exemples ci-dessous\) doivent être comparées aux configurations les plus récentes afin d’obtenir les dernières fonctionnalités :
   - elementmapping.xml
   - ui\_config.json\(peut avoir été défini dans les profils de dossier\)
   - `com.adobe.fmdita.config.ConfigManager` modifié


## Étapes d’indexation du contenu existant

>[!NOTE]
>
> Vous n’avez pas besoin d’effectuer ces étapes si vous effectuez une mise à niveau à partir de la version 4.3.0 ou 4.2.1.

Effectuez les étapes suivantes pour indexer le contenu existant et utilisez le nouveau texte de recherche et de remplacement au niveau de la carte :


- Exécutez une requête de POST sur le serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des cartes pour les indexer ; par défaut, toutes les cartes seront indexées \|\| Par exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)


- L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


- Une fois la tâche terminée, la requête de GET ci-dessus répond avec succès et indique si une correspondance a échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Étapes de post-traitement du contenu existant pour utiliser le rapport de lien rompu

>[!NOTE]
>
> Vous n’avez pas besoin d’effectuer ces étapes si vous effectuez une mise à niveau à partir de la version 4.3.0.

Effectuez les étapes suivantes pour le post-traitement du contenu existant et l’utilisation du nouveau rapport de lien rompu :

1. (Facultatif) S’il existe plus de 100 000 fichiers dita dans le système, mettez à jour la valeur `queryLimitReads` sous `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` vers une valeur plus grande (toute valeur supérieure au nombre de ressources présentes, par exemple 200 000), puis redéployez.

   | PID | Clé de propriété | Valeur de la propriété |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valeur : 200000 <br> Valeur par défaut : 100000 |

1. Exécutez les API suivantes pour exécuter le post-traitement sur tous les fichiers :

   | Point d’entrée | /bin/guides/reports/upgrade |
   |---|---|
   | Type de requête | **POST** Ce script est une requête de POST qui doit donc être exécutée via des agents tels que Postman. |
   | Réponse attendue | L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison.<br> Exemple d’URL : `http://<server:port>/bin/guides/reports/upgrade` |

   | Point d’entrée | /bin/guides/reports/upgrade |
   |---|---|
   | Type de requête | **GET** |
   | Param | jobId : transmettez le jobId reçu de la requête de publication précédente. |
   | Réponse attendue | - Une fois la tâche terminée, la requête de GET répond avec succès. <br> - En cas d’erreur, partagez les journaux d’erreur avec la sortie de l’API avec votre équipe de succès client.  <br>Exemple d’URL : `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |


1. Revenez à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifiée à l’étape 1.



## Mise à niveau vers la version 4.3.1.5 {#upgrade-version-4-3-1-5}

La mise à niveau vers la version 4.3.1.5 dépend de la version actuelle de Experience Manager Guides. Si vous utilisez la version 4.3.1, vous pouvez directement effectuer la mise à niveau vers la version 4.3.1.5.



## Installation de la version 4.3.1.5

1. Téléchargez le package de version 4.3.1.5 à partir du [portail de distribution de logiciels Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package version 4.3.1.5.

1. Attendez que le processus d’installation soit terminé.
1. Poursuivez la mise à niveau des personnalisations, comme décrit dans la section suivante.


## Après avoir installé la version 4.3.1.5


>[!NOTE]
>
>Si vous souhaitez utiliser le lot org.apache.velocity, effectuez les étapes suivantes avant de télécharger le lot :
> 1. Accédez à `<server>:<port>/system/console/bundles`.
> 1. Recherchez org.apache.velocity.
> 1. Désinstallez le lot recherché.
> 1. Installez le lot de vitesse requis.


1. Une fois la mise à niveau terminée, vérifiez que toutes les personnalisations/superpositions sont validées et mises à jour pour correspondre au nouveau code de l’application. Voici quelques exemples :
   - Tous les composants superposés à partir de `/libs/fmdita` ou ` /libs` doivent être comparés au nouveau code de produit et les mises à jour doivent être effectuées dans les fichiers superposés sous `/apps` .
   - Toutes les catégories clientlib utilisées à partir du produit doivent être examinées pour les modifications. Toutes les configurations remplacées \(exemples ci-dessous\) doivent être comparées aux configurations les plus récentes afin d’obtenir les dernières fonctionnalités :
   - `elementmapping.xml`
   - `ui\_config.json\` (peut avoir été défini dans les profils de dossier\)
   - `com.adobe.fmdita.config.ConfigManager` modifié







## Mise à niveau vers la version 4.4.0 {#upgrade-version-4-4-0}

La mise à niveau vers la version 4.4.0 dépend de la version actuelle de Experience Manager Guides. Si vous utilisez les versions 4.3.1, 4.3.0, 4.2 ou 4.2.1 (correctif 4.2.1.3), vous pouvez directement effectuer la mise à niveau vers la version 4.4.0.

>[!NOTE]
>
>Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de lancer le processus de mise à niveau aux heures creuses.

****Conditions préalables****

Avant de démarrer le processus de mise à niveau vers Experience Manager Guides 4.4.0, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers la version 4.3.1, 4.3.0 ou 4.2.1 de Experience Manager Guides (correctif 4.2.1.3) et terminé leurs étapes d’installation respectives.
1. (Facultatif) Fermez toutes les tâches de traduction.
1. Le niveau de journal a été remplacé par **INFO** pour la classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` et ajoutez ces journaux dans un nouveau fichier journal, par exemple `logs/translation_upgrade.log`.


## Installation de la version 4.4.0

1. Téléchargez le package de version 4.4.0 à partir du [portail de distribution de logiciels Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package version 4.4.0.
1. Vous pouvez choisir d’ACCÉDER au déclencheur pour démarrer la tâche de mise à niveau de la carte de traduction. Pour plus d’informations, voir [Activation du déclencheur de script via un servlet](#enable-trigger-serverlet-4-4-0).

1. Une fois l’installation du package terminée, attendez le ou les messages\(s\) suivants dans les journaux :

   `Completed the post deployment setup script`

   Le message ci-dessus indique que toutes les étapes de l’installation sont terminées.

   Si vous rencontrez l’un des préfixes ERROR suivants, signalez-les à votre équipe de réussite client :

   - Erreur dans le script de configuration après le déploiement
   - Exception lors de la génération de la traduction MAP
   - Impossible de transférer le mappage de traduction de la version 1 à la version 2 pour la propriété
1. Mettre à niveau le module externe du connecteur Oxygen publié avec la version 4.4.0 \(si nécessaire\).
1. Effacez le cache du navigateur après l’installation du package.
1. Poursuivez la mise à niveau des personnalisations, comme décrit dans la section suivante.


## Après avoir installé la version 4.4.0

Une fois Experience Manager Guides installé, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée à votre configuration.

>[!NOTE]
>
> Le modèle dam-update-asset peut être personnalisé. Ainsi, si des personnalisations ont été effectuées, nous devons synchroniser les personnalisations et Experience Manager Guides dans la copie de travail du modèle.

1. **Workflow de mise à jour de gestion des actifs numériques \(Modifications de post-traitement\) :**

1. URL d’ouverture :

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Sélectionnez **Workflow de mise à jour des ressources de gestion des actifs numériques**.
1. Cliquez sur **Modifier**.
1. Si le composant **DXML Post Process Initiator** est présent, assurez-vous que les personnalisations sont synchronisées.
1. Si le composant **DXML Post Process Initiator** est absent, procédez comme suit pour l’insérer :

1. Cliquez sur **Insérer le composant** \(Responsable du post-traitement Experience Manager Guides comme dernière étape du processus\).
1. Configurez l’ **étape du processus** avec les détails suivants :

   **Onglet commun**

   **Titre :** Initiateur du post-processus DXML

   **Description** : étape de l’initiateur de post-processus DXML qui déclenche une tâche Sling pour le post-traitement DXML de la ressource modifiée/créée

   **Onglet Processus**

   - Sélectionnez **DXML Post Process Initiator** dans la liste déroulante **Process**

   - Sélectionnez **Avance du gestionnaire**

   - Sélectionnez **Done**

1. Cliquez sur **Synchroniser** en haut à droite après avoir terminé les modifications. Vous recevrez une notification de succès.

   >[!NOTE]
   >
   > Actualisez et vérifiez que les modifications personnalisées et l’étape de post-traitement de Experience Manager Guides sont présentes dans le modèle de workflow final.

1. Une fois que le **workflow Ressource de mise à jour de gestion des actifs numériques** est validé, vérifiez les configurations de lanceur correspondantes. Pour ce faire, accédez à AEM interface de workflow et ouvrez les lanceurs.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Recherchez et apportez des modifications \(si nécessaire\) aux deux lanceurs suivants \(qui doivent être actifs\) correspondant au **workflow Ressource de mise à jour de gestion des actifs numériques** :

1. Lanceur pour &quot;*Noeud créé*&quot; pour **Workflow de ressource de mise à jour de gestion des actifs numériques**- pour la condition `"jcr:content/jcr:mimeType!=video"`, la valeur &quot;Globbing&quot; doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; doit avoir `"event-user-data:changedByWorkflowProcess"`.
   - Lanceur pour &quot;*Node Modified*&quot; pour **Workflow de ressource de mise à jour de gestion des actifs numériques -** pour la condition &quot;`jcr:content/jcr:mimeType!=video`&quot;, la valeur &quot;Globbing&quot; doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` doit avoir `"event-user-data:changedByWorkflowProcess"`.

1. Une fois la mise à niveau terminée, vérifiez que toutes les personnalisations/superpositions sont validées et mises à jour pour correspondre au nouveau code de l’application. Voici quelques exemples :
   - Tous les composants superposés à partir de/libs/mditator/libs doivent être comparés au nouveau code de produit et les mises à jour doivent être effectuées dans les fichiers superposés sous/apps.
   - Toutes les catégories clientlib utilisées à partir du produit doivent être examinées pour les modifications. Toutes les configurations remplacées \(exemples ci-dessous\) doivent être comparées aux configurations les plus récentes afin d’obtenir les dernières fonctionnalités :
   - elementmapping.xml
   - ui\_config.json\(peut avoir été défini dans les profils de dossier\)
   - `com.adobe.fmdita.config.ConfigManager` modifié

1. Si vous avez ajouté des personnalisations dans damAssetLucene, vous devrez peut-être les appliquer à nouveau. Après avoir apporté ces modifications, définissez la réindexation sur true. Cela réindexera tous les noeuds existants avec les personnalisations. Une fois l’opération terminée, l’indicateur de réindexation est à nouveau défini sur false. Cette opération peut prendre quelques heures en fonction du nombre de ressources dans le système.

## Étapes d’indexation du contenu existant

>[!NOTE]
>
> Vous n’avez pas besoin d’effectuer ces étapes si vous effectuez une mise à niveau à partir de la version 4.3.0 ou 4.3.1.

Effectuez les étapes suivantes pour indexer le contenu existant et utilisez le nouveau texte de recherche et de remplacement au niveau de la carte :

- Exécutez une requête de POST sur le serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des cartes pour les indexer ; par défaut, toutes les cartes seront indexées \|\| Par exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

- Une fois la tâche terminée, la requête de GET ci-dessus répond avec succès et indique si une correspondance a échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Étapes de post-traitement du contenu existant pour utiliser le rapport de lien rompu

>[!NOTE]
>
> Vous n’avez pas besoin d’effectuer ces étapes si vous effectuez une mise à niveau à partir de la version 4.3.0 ou 4.3.1.

Effectuez les étapes suivantes pour le post-traitement du contenu existant et l’utilisation du nouveau rapport de lien rompu :

1. (Facultatif) S’il existe plus de 100 000 fichiers dita dans le système, mettez à jour la valeur `queryLimitReads` sous `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` vers une valeur plus grande (toute valeur supérieure au nombre de ressources présentes, par exemple 200 000), puis redéployez.

   | PID | Clé de propriété | Valeur de la propriété |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valeur : 200000 <br> Valeur par défaut : 100000 |

1. Exécutez les API suivantes pour exécuter le post-traitement sur tous les fichiers :

   | Point d’entrée | /bin/guides/reports/upgrade |
   |---|---|
   | Type de requête | **POST** Ce script est une requête de POST qui doit donc être exécutée via des agents tels que Postman. |
   | Réponse attendue | L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison.<br> Exemple d’URL : `http://<server:port>/bin/guides/reports/upgrade` |

   | Point d’entrée | /bin/guides/reports/upgrade |
   |---|---|
   | Type de requête | **GET** |
   | Param | jobId : transmettez le jobId reçu de la requête de publication précédente. |
   | Réponse attendue | - Une fois la tâche terminée, la requête de GET répond avec succès. <br> - En cas d’erreur, partagez les journaux d’erreur avec la sortie de l’API avec votre équipe de succès client.  <br>Exemple d’URL : `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |

1. Revenez à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifiée à l’étape 1.

### Activation du déclencheur de script via une servlet{#enable-trigger-serverlet-4-4-0}

>[!NOTE]
>
> Vous n’avez pas besoin d’effectuer ces étapes si vous effectuez une mise à niveau à partir de la version 4.3.0 ou 4.3.1.

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

Dans la réponse JSON ci-dessus, la clé `lockNodePath` contient le chemin d’accès au noeud créé dans le référentiel pointant vers la tâche envoyée. Il sera automatiquement supprimé une fois la tâche terminée. Vous pourrez alors vous référer à ce noeud pour connaître l’état actuel de la tâche.

Recherchez `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` et `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` avant de passer aux étapes suivantes.

>[!NOTE]
>
> Vous devez vérifier si le noeud est toujours présent et l’état de la tâche.

**GET** : `http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json`



## Procédure de gestion du conflit `'fmdita rewriter'`

Experience Manager Guides dispose d’un module [**de réécriture sling personnalisée**](../cs-install-guide/conf-output-generation.md#custom-rewriter) pour gérer les liens générés en cas de mappage croisé (liens entre les rubriques de deux cartes différentes).

Si votre code base comporte un autre module de réécriture sling personnalisé, utilisez une valeur `'order'` supérieure à 50, car Experience Manager Guides sling rewriter utilise `'order'` 50.  Pour le remplacer, vous devez disposer d’une valeur supérieure à 50. Pour plus d’informations, voir [ Pipelines de réécriture de sortie](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Pendant cette mise à niveau, puisque la valeur `'order'` est passée de 1000 à 50, vous devez fusionner le module de réécriture personnalisé existant, le cas échéant, avec `'fmdita-rewriter'`.


**Rubrique parente :**[ Télécharger et installer](download-install.md)


## Mise à niveau vers la version 4.6.0 {#upgrade-version-4-6-0}

>[!TIP]
>
> Il est recommandé d’installer le Service Pack 1 4.6.0 sur la version 4.6.0. Le processus de mise à niveau de la version 4.6.0 Service Pack 1 suit les mêmes étapes que la version 4.6.0.

La mise à niveau vers la version 4.6.0 dépend de la version actuelle de Experience Manager Guides. Si vous utilisez les versions 4.4.0, 4.3.1, 4.3.0, 4.2 ou 4.2.1 (correctif 4.2.1.3), vous pouvez directement mettre à niveau vers la version 4.6.0.

>[!NOTE]
>
> Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de lancer le processus de mise à niveau aux heures creuses.

****Conditions préalables****

Avant de démarrer le processus de mise à niveau vers Experience Manager Guides 4.6.0, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers la version 4.3.1, 4.3.0 ou 4.2.1 de Experience Manager Guides (correctif 4.2.1.3) et terminé leurs étapes d’installation respectives.
1. (Facultatif) Fermez toutes les tâches de traduction.
1. Le niveau de journal a été remplacé par **INFO** pour la classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` et ajoutez ces journaux dans un nouveau fichier journal, par exemple `logs/translation_upgrade.log`.


## Installation de la version 4.6.0

1. Téléchargez le package de version 4.6.0 à partir du [portail de distribution de logiciels Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/fr/aem.html).
1. Installez le package version 4.6.0.
1. Vous pouvez choisir d’ACCÉDER au déclencheur pour démarrer la tâche de mise à niveau de la carte de traduction. Pour plus d’informations, voir [Activation du déclencheur de script via un servlet](#enable-trigger-serverlet-4-6-0).

1. Une fois l’installation du package terminée, attendez le ou les messages\(s\) suivants dans les journaux :

   `Completed the post deployment setup script`

   Le message ci-dessus indique que toutes les étapes de l’installation sont terminées.

   Si vous rencontrez l’un des préfixes ERROR suivants, signalez-les à votre équipe de réussite client :

   - Erreur dans le script de configuration après le déploiement
   - Exception lors de la génération de la traduction MAP
   - Impossible de transférer le mappage de traduction de la version 1 à la version 2 pour la propriété
1. Mettre à niveau le module externe du connecteur Oxygen publié avec la version 4.6.0 \(si nécessaire\).
1. Effacez le cache du navigateur après l’installation du package.

## Après avoir installé la version 4.6.0

Une fois Experience Manager Guides installé, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée à votre configuration.

>[!NOTE]
>
> Le modèle dam-update-asset peut être personnalisé. Ainsi, si des personnalisations ont été effectuées, nous devons synchroniser les personnalisations et Experience Manager Guides dans la copie de travail du modèle.

1. **Workflow de mise à jour de gestion des actifs numériques \(Modifications de post-traitement\) :**

1. URL d’ouverture :

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Sélectionnez **Workflow de mise à jour des ressources de gestion des actifs numériques**.
1. Cliquez sur **Modifier**.
1. Si le composant **DXML Post Process Initiator** est présent, assurez-vous que les personnalisations sont synchronisées.
1. Si le composant **DXML Post Process Initiator** est absent, procédez comme suit pour l’insérer :

1. Cliquez sur **Insérer le composant** \(Responsable du post-traitement Experience Manager Guides comme dernière étape du processus\).
1. Configurez l’ **étape du processus** avec les détails suivants :

   **Onglet commun**

   **Titre :** Initiateur du post-processus DXML

   **Description** : étape de l’initiateur de post-processus DXML qui déclenche une tâche Sling pour le post-traitement DXML de la ressource modifiée/créée

   **Onglet Processus**

   - Sélectionnez **DXML Post Process Initiator** dans la liste déroulante **Process**

   - Sélectionnez **Avance du gestionnaire**

   - Sélectionnez **Done**

1. Cliquez sur **Synchroniser** en haut à droite après avoir terminé les modifications. Vous recevrez une notification de succès.

   >[!NOTE]
   >
   > Actualisez et vérifiez que les modifications personnalisées et l’étape de post-traitement de Experience Manager Guides sont présentes dans le modèle de workflow final.

1. Une fois que le **workflow Ressource de mise à jour de gestion des actifs numériques** est validé, vérifiez les configurations de lanceur correspondantes. Pour ce faire, accédez à AEM interface de workflow et ouvrez les lanceurs.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Recherchez et apportez des modifications \(si nécessaire\) aux deux lanceurs suivants \(qui doivent être actifs\) correspondant au **workflow Ressource de mise à jour de gestion des actifs numériques** :

1. Lanceur pour &quot;*Noeud créé*&quot; pour **Workflow de ressource de mise à jour de gestion des actifs numériques**- pour la condition `"jcr:content/jcr:mimeType!=video"`, la valeur &quot;Globbing&quot; doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; doit avoir `"event-user-data:changedByWorkflowProcess"`.
   - Lanceur pour &quot;*Node Modified*&quot; pour **Workflow de ressource de mise à jour de gestion des actifs numériques -** pour la condition &quot;`jcr:content/jcr:mimeType!=video`&quot;, la valeur &quot;Globbing&quot; doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` doit avoir `"event-user-data:changedByWorkflowProcess"`.

1. Une fois la mise à niveau terminée, vérifiez que toutes les personnalisations/superpositions sont validées et mises à jour pour correspondre au nouveau code de l’application. Voici quelques exemples :
   - Tous les composants superposés à partir de/libs/mditator/libs doivent être comparés au nouveau code de produit et les mises à jour doivent être effectuées dans les fichiers superposés sous/apps.
   - Toutes les catégories clientlib utilisées à partir du produit doivent être examinées pour les modifications. Toutes les configurations remplacées \(exemples ci-dessous\) doivent être comparées aux configurations les plus récentes afin d’obtenir les dernières fonctionnalités :
   - elementmapping.xml
   - ui\_config.json\(peut avoir été défini dans les profils de dossier\)
   - `com.adobe.fmdita.config.ConfigManager` modifié

1. Si vous avez ajouté des personnalisations dans damAssetLucene, vous devrez peut-être les appliquer à nouveau. Après avoir apporté ces modifications, définissez la réindexation sur true. Cela réindexera tous les noeuds existants avec les personnalisations. Une fois l’opération terminée, l’indicateur de réindexation est à nouveau défini sur false. Cette opération peut prendre quelques heures en fonction du nombre de ressources dans le système.

## Procédure de réindexation des index Experience Manager Guides

1. Ouvrez `crx/de` et accédez au chemin de l’index : `/oak:index/guidesAssetProperties`
2. Définissez la propriété reindex sur `true` (`false` par défaut) et cliquez sur **Enregistrer tout**.
3. Une fois la réindexation terminée, la propriété reindex est de nouveau définie sur `false` et le nombre de réindex est incrémenté de 1.

   >[!NOTE]
   >
   > Cette opération peut prendre quelques minutes, selon la quantité de données présentes.
4. Suivez les mêmes étapes pour d’autres index ajoutés ou modifiés : `guidesBulkActivation`, `guidesPeerLinkIndex` et `guidesKonnectTemplateIndex`.

## Étapes d’indexation du contenu existant



Effectuez les étapes suivantes pour indexer le contenu existant :

- Exécutez une requête de POST sur le serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des cartes pour les indexer ; par défaut, toutes les cartes seront indexées. || Exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(par exemple : ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

- Une fois la tâche terminée, la requête de GET ci-dessus répond avec succès et indique si une correspondance a échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.


>[!NOTE]
>
> Si vous utilisez le schéma personnalisé, vous devez définir le chemin d’accès des fichiers DTD et XSD catalog.xml dans le référentiel AEM dans l’option **Intégrer les catalogues** .




## Procédure de gestion du conflit `'fmdita rewriter'`

Experience Manager Guides dispose d’un module [**de réécriture sling personnalisée**](../cs-install-guide/conf-output-generation.md#custom-rewriter) pour gérer les liens générés en cas de mappage croisé (liens entre les rubriques de deux cartes différentes).

Si votre code base comporte un autre module de réécriture sling personnalisé, utilisez une valeur `'order'` supérieure à 50, car Experience Manager Guides sling rewriter utilise `'order'` 50.  Pour le remplacer, vous devez disposer d’une valeur supérieure à 50. Pour plus d’informations, voir [ Pipelines de réécriture de sortie](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Pendant cette mise à niveau, puisque la valeur `'order'` est passée de 1000 à 50, vous devez fusionner le module de réécriture personnalisé existant, le cas échéant, avec `'fmdita-rewriter'`.






**Rubrique parente :** [Télécharger et installer](download-install.md)
