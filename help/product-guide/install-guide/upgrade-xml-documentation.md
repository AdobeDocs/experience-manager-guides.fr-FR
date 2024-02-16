---
title: Mise à niveau des guides Adobe Experience Manager
description: Découvrez comment mettre à niveau les guides Adobe Experience Manager
exl-id: f058b39f-7408-4874-942b-693e133886cf
feature: Installation
role: Admin
level: Experienced
source-git-commit: 5a444e88b0adba7fa3d498437df39b729b10b5eb
workflow-type: tm+mt
source-wordcount: '5744'
ht-degree: 0%

---

# Mise à niveau des guides Adobe Experience Manager {#id224MBE0M0XA}

>[!NOTE]
>
> Suivez les instructions de mise à niveau spécifiques à la version sous licence de votre produit.

Vous pouvez mettre à niveau votre version actuelle des guides du Experience Manager vers la version 4.4.0 :

- Si vous utilisez la version 4.3.1, 4.3.0 ou 4.2.1 (correctif 4.2.1.3), vous pouvez directement effectuer la mise à niveau vers la version 4.4.0.
- Si vous utilisez les versions 4.2, 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers les versions 4.3.1, 4.3.0 ou 4.2.1 (correctif 4.2.1.3) avant de passer à la version 4.4.0.
- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant de passer à la version 4.3.x.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à 3.8.5, reportez-vous à la section Guides du Experience Manager de mise à niveau du guide d’installation spécifique au produit.


>[!NOTE]
>
> Vous devez installer AEM Service Pack avant de mettre à niveau la version des guides du Experience Manager.

Pour plus de détails, consultez les procédures suivantes :

- [Mise à niveau de 3.8.5 vers la version 4.0](#id2256DK003E1)
- [Upgrade vers la version 4.2](#id22A3F500SXA)
- [Mise à niveau vers la version 4.2.1](#upgrade-version-4-2-1)
- [Mise à niveau vers la version 4.3.0](#upgrade-version-4-3)
- [Mise à niveau vers la version 4.3.1](#upgrade-version-4-3-1)
- [Mise à niveau vers la version 4.4.0](#upgrade-version-4-4-0)


>[!IMPORTANT]
>
> Avant de commencer la mise à niveau, effectuez une sauvegarde complète du système afin d’éviter toute perte de données.

## Mise à niveau de la version 3.8.5 vers la version 4.0 {#id2256DK003E1}

Si vous utilisez la version 3.8.5 des guides de Experience Manager, vous pouvez effectuer la mise à niveau vers la version 4.0 des guides de Experience Manager. Avec la fonction de mise à niveau, vous n’avez pas à désinstaller la version précédente des Guides du Experience Manager.

Avant d’exécuter le processus, vous devez effectuer certaines tâches. Les sous-sections suivantes décrivent les conditions préalables, la génération de rapports et le processus de migration. En outre, une fois que vous avez installé la version 4.0 des Guides du Experience Manager, vous pouvez personnaliser différentes configurations en fonction des paramètres du client.

>[!NOTE]
>
> Ce processus de mise à niveau s’applique uniquement de la version 3.8.5 à la version 4.0. Pour le processus de mise à niveau de la version 3.4 ou ultérieure vers la version 3.8.5, reportez-vous à la section *Guides du Experience Manager de mise à niveau* dans le guide d’installation spécifique au produit disponible dans la section [Page d’aide archivée](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

****Conditions préalables****

Avant de démarrer le processus de mise à niveau des guides du Experience Manager, vérifiez que vous disposez des éléments suivants :

1. Importation des commentaires de révision dans les rubriques ouvertes pour révision.
1. Fermer toutes les révisions actives.
1. Fermeture de toutes les tâches de traduction
1. Désinstallez tous les correctifs de Guides de Experience Manager installés en haut de la version précédente \(version majeure ou version de correctif\) des Guides de Experience Manager.

**Avant d’installer la version 4.0**

Avant d’installer la version 4.0, procédez comme suit :

1. Vérifiez qu’à ce stade, les guides du Experience Manager sont sur la version 3.8.5.
1. Téléchargez le package de script de mise à niveau. Pour ce faire, recherchez &quot;Package de mise à niveau de la solution XML Documentation 4.0&quot; sur [Portail de distribution de logiciels Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) qui téléchargera un fichier zip.
1. Téléchargez ce package vers AEM via Package Manager et installez ce package.
1. Une fois le package de mise à niveau installé, exécutez les scripts ci-dessous dans le même ordre et suivez les instructions données :

**Vérifier l&#39;API de compatibilité de mise à niveau**

Cette API est conçue pour évaluer l’état actuel du système et pour signaler si la mise à niveau est possible ou non. Pour exécuter ce script, déclenchez le point de terminaison ci-dessous :

| Point d’entrée | /bin/dxml/upgrade/3xto4x/report |
| --- | --- |
| Type de requête | **GET** Vous pouvez utiliser un navigateur web dans lequel vous êtes connecté en tant qu’administrateur à l’instance AEM. |
| Réponse attendue | - Si tous les noeuds requis peuvent être déplacés, vous obtiendrez une vérification transmise. <br>- Si un noeud est présent à l’emplacement cible, vous obtenez une erreur pertinente. Nettoyez le référentiel \(supprimez le noeud /var/dxml\), réinstallez le package de mise à niveau, puis déclenchez à nouveau ce point de terminaison. <br>**Remarque :** Il ne s’agit pas d’une erreur courante, car l’emplacement cible n’est pas utilisé précédemment par les Guides du Experience Manager 3.x. <br> - Si ce script échoue, ne procédez pas et signalez-le à votre équipe de réussite client. |

**API de migration des données système**

Cette API est conçue pour migrer les données système comme indiqué dans la section **Mappage de migration** .

1. N’exécutez pas ce script si l’API de vérification de la compatibilité de mise à niveau échoue \(ne procédez pas\).
1. Une fois que l’API Vérifier la compatibilité de mise à niveau renvoie la réussite, vous pouvez exécuter le script de mise à niveau.

| Point d’entrée | /bin/dxml/upgrade/3xto4x |
| --- | --- |
| Type de requête | **POST** Ce script est une requête de POST qui doit donc être exécutée via des agents tels que Postman. |
| Réponse attendue | - Une fois la migration réussie, vous pouvez installer la solution XML Documentation version 4.0.<br>- En cas d’erreur, restaurez au dernier point de contrôle et partagez les journaux d’erreur avec la sortie de l’API avec votre équipe de succès client. |

**Mappage de migration**: l’API ci-dessus migre toutes les données de l’emplacement source vers l’emplacement cible.

| Source | Target |
|------|------|
| /content/fmdita | /var/dxml |
| /content/dxml | /var/dxml |
| /etc/fmdita | /libs/fmdita |

## Installation de la version 4.0 {#id23598G006XA}

1. Installez la version 4.0 uniquement si les étapes de mise à niveau ont réussi.
1. Télécharger le package de version 4.0 depuis [Portail de distribution de logiciels Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html):

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
1. Effacer le cache du Dispatcher \(pour effacer tout `clientlibs` mis en cache\).

## Upgrade vers la version 4.2 {#id22A3F500SXA}

La mise à niveau vers la version 4.2 dépend de la version actuelle des Guides du Experience Manager.

Si vous utilisez la version 4.0, 4.1 ou 4.1.x, vous pouvez directement mettre à niveau vers la version 4.2.

****Conditions préalables****

Avant de démarrer le processus de mise à niveau vers Experience Manager Guides 4.2, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers les guides de Experience Manager version 4.0, 4.1 ou 4.1.x.
1. Fermeture de toutes les tâches de traduction
1. Modification du niveau de journal en **INFO** pour `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` et ajoutez ces journaux dans un nouveau fichier journal, par exemple : `logs/translation_upgrade.log.`

>[!NOTE]
>
> Vous devez fermer toutes les révisions actives. Si les tâches de révision ne sont pas fermées lors de la mise à niveau vers la version 4.2, les anciennes tâches de révision en cours continuent d’emmener les utilisateurs sur les anciennes pages de révision, et les tâches de révision créées après la mise à niveau afficheront les dernières mises à jour de la fonctionnalité.

## Installation de la version 4.2 {#id2245IK0E0EV}

1. Télécharger le package de version 4.2 depuis [Portail de distribution de logiciels Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
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
> Le modèle high-tech n’est pas affiché sur le serveur mis à niveau. Pour inclure le modèle high-tech sur votre serveur, vous pouvez le copier : Source : /libs/fmdita/pdf/Hi-Tech Destination: /content/dam/dita-templates/pdf

Après avoir installé Experience Manager Guides, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée à votre configuration.

>[!NOTE]
>
> Le modèle dam-update-asset peut être personnalisé. Ainsi, si des personnalisations ont été effectuées, nous devons synchroniser les personnalisations et les guides du Experience Manager dans la copie de travail du modèle.

1. **Processus de ressource de mise à jour de gestion des actifs numériques \(changements de post-traitement\) :**

1. URL d’ouverture :

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Sélectionner **Workflow Ressources de mise à jour de gestion des actifs numériques**.
1. Cliquez sur **Modifier**.
1. Si la variable **Initiateur de post-traitement DXML** est présent, assurez-vous que les personnalisations sont synchronisées.
1. Si la variable **Initiateur de post-traitement DXML** est absent du composant, effectuez les étapes suivantes pour l’insérer :

1. Cliquez sur **Insérer le composant** \(Responsable du post-traitement des guides du Experience Manager comme étape finale du processus\).
1. Configurez la variable **Étape du processus** avec les détails ci-dessous :

   **Onglet Courant**

   **Titre :** Initiateur de post-traitement DXML

   **Description**: étape de l’initiateur de post-processus DXML qui déclenchera une tâche Sling pour le post-traitement DXML de la ressource modifiée/créée.

   **Onglet Processus**

   - Sélectionner **Initiateur de post-traitement DXML** de la **Processus** menu déroulant

   - Sélectionner **Avance du gestionnaire**

   - Sélectionner **Terminé**

1. Cliquez sur **Synchronisation** en haut à droite après avoir terminé les modifications. Vous recevrez une notification de succès.

   >[!NOTE]
   >
   > Actualisez et vérifiez que les modifications personnalisées et l’étape de post-traitement des Guides du Experience Manager sont présentes dans le modèle de workflow final.

1. Une fois **Workflow Ressources de mise à jour de gestion des actifs numériques** est validé, vérifiez les configurations de lanceur correspondantes. Pour ce faire, accédez à AEM interface de workflow et ouvrez les lanceurs.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Recherchez et apportez des modifications \(si nécessaire\) aux deux lanceurs suivants \(qui doivent être actifs\) correspondant à **Workflow Ressources de mise à jour de gestion des actifs numériques**:

1. Lanceur pour &quot;*Noeud créé*&quot; pour **Workflow Ressources de mise à jour de gestion des actifs numériques**: condition `"jcr:content/jcr:mimeType!=video"`, la valeur &quot;Globbing&quot; doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; doit avoir `"event-user-data:changedByWorkflowProcess"`.
   - Lanceur pour &quot;*Noeud modifié*&quot; pour **Processus Ressources de mise à jour de gestion des actifs numériques -** pour la condition &quot;`jcr:content/jcr:mimeType!=video`&quot;,
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
   - modified `com.adobe.fmdita.config.ConfigManager`
   - Vérifiez si l’un des codes personnalisés utilisait d’anciens chemins d’accès \(comme indiqué dans la section [Mappage de migration](#id2244LE040XA) section\) - doit être mis à jour vers les nouveaux chemins afin que les personnalisations fonctionnent également comme prévu.
1. Découvrez toutes les nouvelles configurations apportées à la version actuelle \(vérifier) [Notes de mise à jour](../release-info/release-notes-4-3.md)\) et voir si une fonctionnalité est affectée, puis prendre les mesures appropriées. Un exemple peut être l’utilisation de l’option &quot;Amélioration de la gestion des fichiers et des versions&quot; introduite dans la version 4.0, pour laquelle vous devez activer une configuration.

## Étapes d’indexation du contenu existant pour utiliser la nouvelle recherche et remplacement :

Effectuez les étapes suivantes pour indexer le contenu existant et utilisez le nouveau texte de recherche et de remplacement au niveau de la carte :

- Exécutez une requête de POST sur le serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. \(Facultatif : vous pouvez transmettre des chemins d’accès spécifiques des cartes pour les indexer. Par défaut, toutes les cartes seront indexées \|\| Par exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`\)

- L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison :

`http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

- Une fois la tâche terminée, la requête de GET ci-dessus répond avec succès et indique si une correspondance a échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

Si la tâche de mise à niveau échoue et que le journal des erreurs affiche l’erreur suivante :

&quot;Le *query* lecture ou traversée supérieure à *Noeuds 100000*. Pour éviter d’affecter d’autres tâches, le traitement a été arrêté.&quot;

Cela peut se produire car l’index n’est pas correctement configuré pour la requête utilisée dans la mise à niveau. Vous pouvez essayer la solution suivante :

1. Dans l’index oak damAssetLucene, ajoutez la propriété booléenne . `indexNodeName` as `true` dans le noeud .
   `/oak:index/damAssetLucene/indexRules/dam:Asset`
1. Ajoutez un nouveau noeud avec l’extrait de nom sous le noeud .

   `/oak:index/damAssetLucene/indexRules/dam:Asset/properties`
et définissez les propriétés suivantes dans le noeud :

   ```
   name - rep:excerpt
   propertyIndex - {Boolean}true
   notNullCheckEnabled - {Boolean}true
   ```

   La structure de `damAssetLucene` doit ressembler à ce qui suit :

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

1. Réindexez la variable `damAssetLucene` index (en définissant l’indicateur reindex comme `true` Sous et attendez qu’il soit `false` de nouveau (cela indique que la réindexation est terminée). Notez que cela peut prendre quelques heures en fonction de la taille de l’index.
1. Exécutez à nouveau le script d’indexation en suivant les étapes précédentes.


## Mise à niveau vers la version 4.2.1 {#upgrade-version-4-2-1}

>[!TIP]
>
>Il est recommandé d’installer Hotfix 4.2.1.3 sur la version 4.2.1.

La mise à niveau vers la version 4.2.1 dépend de la version actuelle des Guides du Experience Manager. Si vous utilisez la version 4.1, 4.1.x ou 4.2, vous pouvez directement effectuer la mise à niveau vers la version 4.2.1.

>[!NOTE]
>
>Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de lancer le processus de mise à niveau aux heures creuses.

****Conditions préalables****

Avant de démarrer le processus de mise à niveau vers Experience Manager Guides 4.2.1, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers les guides de Experience Manager version 4.1, 4.1.x ou 4.2.
1. Fermeture de toutes les tâches de traduction
1. Modification du niveau de journal en **INFO** pour `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` et ajoutez ces journaux dans un nouveau fichier journal, par exemple : `logs/translation_upgrade.log.`

>[!NOTE]
>
> Vous devez fermer toutes les révisions actives. Si les tâches de révision ne sont pas fermées lors de la mise à niveau vers la version 4.2, les anciennes tâches de révision en cours continuent d’emmener les utilisateurs sur les anciennes pages de révision, et les tâches de révision créées après la mise à niveau afficheront les dernières mises à jour de la fonctionnalité.

## Installation de la version 4.2.1

1. Télécharger le package de version 4.2.1 depuis [Portail de distribution de logiciels Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package version 4.2.1.
1. Vous pouvez choisir d’ACCÉDER au déclencheur pour démarrer la tâche de mise à niveau de la carte de traduction. Pour plus d’informations, voir [Activation du déclencheur de script via une servlet](#enable-trigger-serverlet).


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

Exemple de journal : voici un exemple de journaux qui s’afficheront dans le fichier journal après le déclenchement du script.

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
> Le modèle high-tech n’est pas affiché sur le serveur mis à niveau. Pour inclure le modèle high-tech sur votre serveur, vous pouvez le copier : Source : /libs/fmdita/pdf/Hi-Tech Destination: /content/dam/dita-templates/pdf

Après avoir installé Experience Manager Guides, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée à votre configuration.

>[!NOTE]
>
> Le modèle dam-update-asset peut être personnalisé. Ainsi, si des personnalisations ont été effectuées, nous devons synchroniser les personnalisations et les guides du Experience Manager dans la copie de travail du modèle.

1. **Processus de ressource de mise à jour de gestion des actifs numériques \(changements de post-traitement\) :**

1. URL d’ouverture :

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Sélectionner **Workflow Ressources de mise à jour de gestion des actifs numériques**.
1. Cliquez sur **Modifier**.
1. Si la variable **Initiateur de post-traitement DXML** est présent, assurez-vous que les personnalisations sont synchronisées.
1. Si la variable **Initiateur de post-traitement DXML** est absent du composant, effectuez les étapes suivantes pour l’insérer :

1. Cliquez sur **Insérer le composant** \(Responsable du post-traitement des guides du Experience Manager comme étape finale du processus\).
1. Configurez la variable **Étape du processus** avec les détails ci-dessous :

   **Onglet Courant**

   **Titre :** Initiateur de post-traitement DXML

   **Description**: étape de l’initiateur de post-processus DXML qui déclenchera une tâche Sling pour le post-traitement DXML de la ressource modifiée/créée.

   **Onglet Processus**

   - Sélectionner **Initiateur de post-traitement DXML** de la **Processus** menu déroulant

   - Sélectionner **Avance du gestionnaire**

   - Sélectionner **Terminé**

1. Cliquez sur **Synchronisation** en haut à droite après avoir terminé les modifications. Vous recevrez une notification de succès.

   >[!NOTE]
   >
   > Actualisez et vérifiez que les modifications personnalisées et l’étape de post-traitement des Guides du Experience Manager sont présentes dans le modèle de workflow final.

1. Une fois **Workflow Ressources de mise à jour de gestion des actifs numériques** est validé, vérifiez les configurations de lanceur correspondantes. Pour ce faire, accédez à AEM interface de workflow et ouvrez les lanceurs.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Recherchez et apportez des modifications \(si nécessaire\) aux deux lanceurs suivants \(qui doivent être actifs\) correspondant à **Workflow Ressources de mise à jour de gestion des actifs numériques**:

1. Lanceur pour &quot;*Noeud créé*&quot; pour **Workflow Ressources de mise à jour de gestion des actifs numériques**: condition `"jcr:content/jcr:mimeType!=video"`, la valeur &quot;Globbing&quot; doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; doit avoir `"event-user-data:changedByWorkflowProcess"`.
   - Lanceur pour &quot;*Noeud modifié*&quot; pour **Processus Ressources de mise à jour de gestion des actifs numériques -** pour la condition &quot;`jcr:content/jcr:mimeType!=video`&quot;, la valeur &quot;Globbing&quot; doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` should `"event-user-data:changedByWorkflowProcess"`.

1. Une fois la mise à niveau terminée, vérifiez que toutes les personnalisations/superpositions sont validées et mises à jour pour correspondre au nouveau code de l’application. Voici quelques exemples :
   - Tous les composants superposés à partir de/libs/mditator/libs doivent être comparés au nouveau code de produit et les mises à jour doivent être effectuées dans les fichiers superposés sous/apps.
   - Toutes les catégories clientlib utilisées à partir du produit doivent être examinées pour les modifications. Toutes les configurations remplacées \(exemples ci-dessous\) doivent être comparées aux configurations les plus récentes afin d’obtenir les dernières fonctionnalités :
   - elementmapping.xml
   - ui\_config.json\(peut avoir été défini dans les profils de dossier\)
   - modified `com.adobe.fmdita.config.ConfigManager`
   - Vérifiez si l’un des codes personnalisés utilisait d’anciens chemins d’accès \(comme indiqué dans la section [Mappage de migration](#id2244LE040XA) section\) - doit être mis à jour vers les nouveaux chemins afin que les personnalisations fonctionnent également comme prévu.
1. Découvrez toutes les nouvelles configurations apportées à la version actuelle \(vérifier) [Notes de mise à jour](../release-info/release-notes-4-2-1.md)\) et voir si une fonctionnalité est affectée, puis prendre les mesures appropriées. Un exemple peut être l’utilisation de l’option &quot;Amélioration de la gestion des fichiers et des versions&quot; introduite dans la version 4.0, pour laquelle vous devez activer une configuration.

## Étapes d’indexation du contenu existant pour utiliser la nouvelle recherche et remplacement :

Effectuez les étapes suivantes pour indexer le contenu existant et utilisez le nouveau texte de recherche et de remplacement au niveau de la carte :

- Assurez-vous que la variable `damAssetLucene` l’indexation est terminée. Selon la quantité de données présentes sur le serveur, cette opération peut prendre jusqu’à quelques heures. Vous pouvez confirmer que la réindexation est terminée en vérifiant que le champ de réindexation est défini sur false dans
  `http://<server:port>/oak:index/damAssetLucene`.  En outre, si vous avez ajouté des personnalisations dans `damAssetLucene`, vous devrez peut-être les appliquer à nouveau.

- Exécutez une requête de POST sur le serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des cartes pour les indexer ; par défaut, toutes les cartes seront indexées \|\| Par exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- Vous pouvez également transmettre un dossier racine pour indexer les mappages DITA d’un dossier spécifique (et de ses sous-dossiers). Par exemple, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Notez que si les paramètres paths et root sont transmis, seul le paramètre paths est pris en compte.

- L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison : `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


- Une fois la tâche terminée, la requête de GET ci-dessus répond avec succès et indique si une correspondance a échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.


## Mise à niveau vers la version 4.3.0 {#upgrade-version-4-3}

La mise à niveau vers la version 4.3.0 dépend de la version actuelle des Guides du Experience Manager. Si vous utilisez la version 4.2 ou 4.2.x, vous pouvez directement effectuer la mise à niveau vers la version 4.3.0.

>[!NOTE]
>
>Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de lancer le processus de mise à niveau aux heures creuses.

****Conditions préalables****

Avant de démarrer le processus de mise à niveau vers Experience Manager Guides 4.3.0, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers les guides de Experience Manager version 4.2 ou 4.2.x et exécution de l’étape d’installation correspondante.
1. Fermeture de toutes les tâches de traduction



## Installation de la version 4.3.0

1. Télécharger le package de version 4.3.0 depuis [Portail de distribution de logiciels Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package version 4.3.0.
1. Effacez le cache du navigateur après l’installation du package.
1. Mettre à niveau `ui_config.json` du fichier **Configuration de l’éditeur XML** dans le profil du dossier.


## Après avoir installé la version 4.3.0

Après avoir installé Experience Manager Guides, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée à votre configuration.

## Étapes de post-traitement du contenu existant pour utiliser le rapport de lien rompu


Effectuez les étapes suivantes pour le post-traitement du contenu existant et l’utilisation du nouveau rapport de lien rompu :

1. (Facultatif) Si le système contient plus de 100 000 fichiers dita, mettez à jour la variable `queryLimitReads` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` à une valeur plus élevée (toute valeur supérieure au nombre de ressources présentes, par exemple 200 000), puis redéployez.

   | PID | Clé de propriété | Valeur de la propriété |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valeur : 200000 <br> Valeur par défaut : 100000 |

1. Exécutez les API suivantes pour exécuter le post-traitement sur tous les fichiers :

   | Point d’entrée | /bin/guides/reports/upgrade |
   |---|---|
   | Type de requête | **POST**  Ce script est une requête de POST qui doit donc être exécutée via des agents tels que Postman. |
   | Réponse attendue | L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison.<br> Exemple d’URL : `http://<server:port>/bin/guides/reports/upgrade` |

   | Point d’entrée | /bin/guides/reports/upgrade |
   |---|---|
   | Type de requête | **GET** |
   | Param | jobId : transmettez le jobId reçu de la requête de publication précédente. |
   | Réponse attendue | - Une fois la tâche terminée, la requête de GET répond avec succès. <br> - En cas d’erreur, partagez les journaux d’erreur avec la sortie de l’API avec votre équipe de succès client.  <br>Exemple d’URL : `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |


1. Revenir à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifié à l’étape 1.



## Mise à niveau vers la version 4.3.1 {#upgrade-version-4-3-1}

La mise à niveau vers la version 4.3.1 dépend de la version actuelle des Guides du Experience Manager. Si vous utilisez la version 4.3.0, 4.2 ou 4.2.1, vous pouvez directement effectuer la mise à niveau vers la version 4.3.1.

>[!NOTE]
>
>Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de lancer le processus de mise à niveau aux heures creuses.

****Conditions préalables****

Avant de démarrer le processus de mise à niveau vers Experience Manager Guides 4.3.1, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers les guides de Experience Manager version 4.3.0, 4.2 ou 4.2.1 et exécution de l’étape d’installation correspondante.
1. (Facultatif) Fermez toutes les tâches de traduction.
1. Modification du niveau de journal en **INFO** pour `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` et ajoutez ces journaux dans un nouveau fichier journal, par exemple : `logs/translation_upgrade.log`.


## Installation de la version 4.3.1

1. Télécharger le package de version 4.3.1 depuis [Portail de distribution de logiciels Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package version 4.3.1.
1. Vous pouvez choisir d’ACCÉDER au déclencheur pour démarrer la tâche de mise à niveau de la carte de traduction. Pour plus d’informations, voir [Activation du déclencheur de script via une servlet](#enable-trigger-serverlet-4-3-1).


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

Exemple de journal : voici un exemple de journaux qui s’afficheront dans le fichier journal après le déclenchement du script.

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



Après avoir installé Experience Manager Guides, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée à votre configuration.

>[!NOTE]
>
> Le modèle dam-update-asset peut être personnalisé. Ainsi, si des personnalisations ont été effectuées, nous devons synchroniser les personnalisations et les guides du Experience Manager dans la copie de travail du modèle.

1. **Processus de ressource de mise à jour de gestion des actifs numériques \(changements de post-traitement\) :**

1. URL d’ouverture :

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Sélectionner **Workflow Ressources de mise à jour de gestion des actifs numériques**.
1. Cliquez sur **Modifier**.
1. Si la variable **Initiateur de post-traitement DXML** est présent, assurez-vous que les personnalisations sont synchronisées.
1. Si la variable **Initiateur de post-traitement DXML** est absent du composant, effectuez les étapes suivantes pour l’insérer :

1. Cliquez sur **Insérer le composant** \(Responsable du post-traitement des guides du Experience Manager comme étape finale du processus\).
1. Configurez la variable **Étape du processus** avec les détails ci-dessous :

   **Onglet Courant**

   **Titre :** Initiateur de post-traitement DXML

   **Description**: étape de l’initiateur de post-processus DXML qui déclenchera une tâche Sling pour le post-traitement DXML de la ressource modifiée/créée.

   **Onglet Processus**

   - Sélectionner **Initiateur de post-traitement DXML** de la **Processus** menu déroulant

   - Sélectionner **Avance du gestionnaire**

   - Sélectionner **Terminé**

1. Cliquez sur **Synchronisation** en haut à droite après avoir terminé les modifications. Vous recevrez une notification de succès.

   >[!NOTE]
   >
   > Actualisez et vérifiez que les modifications personnalisées et l’étape de post-traitement des Guides du Experience Manager sont présentes dans le modèle de workflow final.

1. Une fois **Workflow Ressources de mise à jour de gestion des actifs numériques** est validé, vérifiez les configurations de lanceur correspondantes. Pour ce faire, accédez à AEM interface de workflow et ouvrez les lanceurs.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Recherchez et apportez des modifications \(si nécessaire\) aux deux lanceurs suivants \(qui doivent être actifs\) correspondant à **Workflow Ressources de mise à jour de gestion des actifs numériques**:

1. Lanceur pour &quot;*Noeud créé*&quot; pour **Workflow Ressources de mise à jour de gestion des actifs numériques**: condition `"jcr:content/jcr:mimeType!=video"`, la valeur &quot;Globbing&quot; doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; doit avoir `"event-user-data:changedByWorkflowProcess"`.
   - Lanceur pour &quot;*Noeud modifié*&quot; pour **Processus Ressources de mise à jour de gestion des actifs numériques -** pour la condition &quot;`jcr:content/jcr:mimeType!=video`&quot;, la valeur &quot;Globbing&quot; doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` should `"event-user-data:changedByWorkflowProcess"`.

1. Une fois la mise à niveau terminée, vérifiez que toutes les personnalisations/superpositions sont validées et mises à jour pour correspondre au nouveau code de l’application. Voici quelques exemples :
   - Tous les composants superposés à partir de/libs/mditator/libs doivent être comparés au nouveau code de produit et les mises à jour doivent être effectuées dans les fichiers superposés sous/apps.
   - Toutes les catégories clientlib utilisées à partir du produit doivent être examinées pour les modifications. Toutes les configurations remplacées \(exemples ci-dessous\) doivent être comparées aux configurations les plus récentes afin d’obtenir les dernières fonctionnalités :
   - elementmapping.xml
   - ui\_config.json\(peut avoir été défini dans les profils de dossier\)
   - modified `com.adobe.fmdita.config.ConfigManager`


## Étapes d’indexation du contenu existant

>[!NOTE]
>
> Vous n’avez pas besoin d’effectuer ces étapes si vous effectuez une mise à niveau à partir de la version 4.3.0 ou 4.2.1.

Effectuez les étapes suivantes pour indexer le contenu existant et utilisez le nouveau texte de recherche et de remplacement au niveau de la carte :


- Exécutez une requête de POST sur le serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des cartes pour les indexer ; par défaut, toutes les cartes seront indexées \|\| Par exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)


- L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison : `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


- Une fois la tâche terminée, la requête de GET ci-dessus répond avec succès et indique si une correspondance a échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Étapes de post-traitement du contenu existant pour utiliser le rapport de lien rompu

>[!NOTE]
>
> Vous n’avez pas besoin d’effectuer ces étapes si vous effectuez une mise à niveau à partir de la version 4.3.0.

Effectuez les étapes suivantes pour le post-traitement du contenu existant et l’utilisation du nouveau rapport de lien rompu :

1. (Facultatif) Si le système contient plus de 100 000 fichiers dita, mettez à jour la variable `queryLimitReads` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` à une valeur plus élevée (toute valeur supérieure au nombre de ressources présentes, par exemple 200 000), puis redéployez.

   | PID | Clé de propriété | Valeur de la propriété |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valeur : 200000 <br> Valeur par défaut : 100000 |

1. Exécutez les API suivantes pour exécuter le post-traitement sur tous les fichiers :

   | Point d’entrée | /bin/guides/reports/upgrade |
   |---|---|
   | Type de requête | **POST**  Ce script est une requête de POST qui doit donc être exécutée via des agents tels que Postman. |
   | Réponse attendue | L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison.<br> Exemple d’URL : `http://<server:port>/bin/guides/reports/upgrade` |

   | Point d’entrée | /bin/guides/reports/upgrade |
   |---|---|
   | Type de requête | **GET** |
   | Param | jobId : transmettez le jobId reçu de la requête de publication précédente. |
   | Réponse attendue | - Une fois la tâche terminée, la requête de GET répond avec succès. <br> - En cas d’erreur, partagez les journaux d’erreur avec la sortie de l’API avec votre équipe de succès client.  <br>Exemple d’URL : `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |


1. Revenir à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifié à l’étape 1.

## Mise à niveau vers la version 4.4.0 {#upgrade-version-4-4-0}

La mise à niveau vers la version 4.4.0 dépend de la version actuelle des Guides du Experience Manager. Si vous utilisez les versions 4.3.1, 4.3.0, 4.2 ou 4.2.1 (correctif 4.2.1.3), vous pouvez directement effectuer la mise à niveau vers la version 4.4.0.

>[!NOTE]
>
>Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de lancer le processus de mise à niveau aux heures creuses.

****Conditions préalables****

Avant de démarrer le processus de mise à niveau vers Experience Manager Guides 4.4.0, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers les Guides de Experience Manager version 4.3.1, 4.3.0 ou 4.2.1 (correctif 4.2.1.3) et terminé leurs étapes d’installation respectives.
1. (Facultatif) Fermez toutes les tâches de traduction.
1. Modification du niveau de journal en **INFO** pour `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` et ajoutez ces journaux dans un nouveau fichier journal, par exemple : `logs/translation_upgrade.log`.


## Installation de la version 4.4.0

1. Téléchargez le package de version 4.4.0 depuis [Portail de distribution de logiciels Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installez le package version 4.4.0.
1. Vous pouvez choisir d’ACCÉDER au déclencheur pour démarrer la tâche de mise à niveau de la carte de traduction. Pour plus d’informations, voir [Activation du déclencheur de script via une servlet](#enable-trigger-serverlet-4-4-0).

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

Après avoir installé Experience Manager Guides, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée à votre configuration.

>[!NOTE]
>
> Le modèle dam-update-asset peut être personnalisé. Ainsi, si des personnalisations ont été effectuées, nous devons synchroniser les personnalisations et les guides du Experience Manager dans la copie de travail du modèle.

1. **Processus de ressource de mise à jour de gestion des actifs numériques \(changements de post-traitement\) :**

1. URL d’ouverture :

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Sélectionner **Workflow Ressources de mise à jour de gestion des actifs numériques**.
1. Cliquez sur **Modifier**.
1. Si la variable **Initiateur de post-traitement DXML** est présent, assurez-vous que les personnalisations sont synchronisées.
1. Si la variable **Initiateur de post-traitement DXML** est absent du composant, effectuez les étapes suivantes pour l’insérer :

1. Cliquez sur **Insérer le composant** \(Responsable du post-traitement des guides du Experience Manager comme étape finale du processus\).
1. Configurez la variable **Étape du processus** avec les détails ci-dessous :

   **Onglet Courant**

   **Titre :** Initiateur de post-traitement DXML

   **Description**: étape de l’initiateur de post-processus DXML qui déclenchera une tâche Sling pour le post-traitement DXML de la ressource modifiée/créée.

   **Onglet Processus**

   - Sélectionner **Initiateur de post-traitement DXML** de la **Processus** menu déroulant

   - Sélectionner **Avance du gestionnaire**

   - Sélectionner **Terminé**

1. Cliquez sur **Synchronisation** en haut à droite après avoir terminé les modifications. Vous recevrez une notification de succès.

   >[!NOTE]
   >
   > Actualisez et vérifiez que les modifications personnalisées et l’étape de post-traitement des Guides du Experience Manager sont présentes dans le modèle de workflow final.

1. Une fois **Workflow Ressources de mise à jour de gestion des actifs numériques** est validé, vérifiez les configurations de lanceur correspondantes. Pour ce faire, accédez à AEM interface de workflow et ouvrez les lanceurs.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Recherchez et apportez des modifications \(si nécessaire\) aux deux lanceurs suivants \(qui doivent être actifs\) correspondant à **Workflow Ressources de mise à jour de gestion des actifs numériques**:

1. Lanceur pour &quot;*Noeud créé*&quot; pour **Workflow Ressources de mise à jour de gestion des actifs numériques**: condition `"jcr:content/jcr:mimeType!=video"`, la valeur &quot;Globbing&quot; doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; doit avoir `"event-user-data:changedByWorkflowProcess"`.
   - Lanceur pour &quot;*Noeud modifié*&quot; pour **Processus Ressources de mise à jour de gestion des actifs numériques -** pour la condition &quot;`jcr:content/jcr:mimeType!=video`&quot;, la valeur &quot;Globbing&quot; doit être :

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` should `"event-user-data:changedByWorkflowProcess"`.

1. Une fois la mise à niveau terminée, vérifiez que toutes les personnalisations/superpositions sont validées et mises à jour pour correspondre au nouveau code de l’application. Voici quelques exemples :
   - Tous les composants superposés à partir de/libs/mditator/libs doivent être comparés au nouveau code de produit et les mises à jour doivent être effectuées dans les fichiers superposés sous/apps.
   - Toutes les catégories clientlib utilisées à partir du produit doivent être examinées pour les modifications. Toutes les configurations remplacées \(exemples ci-dessous\) doivent être comparées aux configurations les plus récentes afin d’obtenir les dernières fonctionnalités :
   - elementmapping.xml
   - ui\_config.json\(peut avoir été défini dans les profils de dossier\)
   - modified `com.adobe.fmdita.config.ConfigManager`

1. Si vous avez ajouté des personnalisations dans damAssetLucene, vous devrez peut-être les appliquer à nouveau. Après avoir apporté ces modifications, définissez la réindexation sur true. Cela réindexera tous les noeuds existants avec les personnalisations. Une fois l’opération terminée, l’indicateur de réindexation est à nouveau défini sur false. Cette opération peut prendre quelques heures en fonction du nombre de ressources dans le système.

## Étapes d’indexation du contenu existant

>[!NOTE]
>
> Vous n’avez pas besoin d’effectuer ces étapes si vous effectuez une mise à niveau à partir de la version 4.3.0 ou 4.3.1.

Effectuez les étapes suivantes pour indexer le contenu existant et utilisez le nouveau texte de recherche et de remplacement au niveau de la carte :

- Exécutez une requête de POST sur le serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des cartes pour les indexer ; par défaut, toutes les cartes seront indexées \|\| Par exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison : `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

- Une fois la tâche terminée, la requête de GET ci-dessus répond avec succès et indique si une correspondance a échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Étapes de post-traitement du contenu existant pour utiliser le rapport de lien rompu

>[!NOTE]
>
> Vous n’avez pas besoin d’effectuer ces étapes si vous effectuez une mise à niveau à partir de la version 4.3.0 ou 4.3.1.

Effectuez les étapes suivantes pour le post-traitement du contenu existant et l’utilisation du nouveau rapport de lien rompu :

1. (Facultatif) Si le système contient plus de 100 000 fichiers dita, mettez à jour la variable `queryLimitReads` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` à une valeur plus élevée (toute valeur supérieure au nombre de ressources présentes, par exemple 200 000), puis redéployez.

   | PID | Clé de propriété | Valeur de la propriété |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valeur : 200000 <br> Valeur par défaut : 100000 |

1. Exécutez les API suivantes pour exécuter le post-traitement sur tous les fichiers :

   | Point d’entrée | /bin/guides/reports/upgrade |
   |---|---|
   | Type de requête | **POST**  Ce script est une requête de POST qui doit donc être exécutée via des agents tels que Postman. |
   | Réponse attendue | L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison.<br> Exemple d’URL : `http://<server:port>/bin/guides/reports/upgrade` |

   | Point d’entrée | /bin/guides/reports/upgrade |
   |---|---|
   | Type de requête | **GET** |
   | Param | jobId : transmettez le jobId reçu de la requête de publication précédente. |
   | Réponse attendue | - Une fois la tâche terminée, la requête de GET répond avec succès. <br> - En cas d’erreur, partagez les journaux d’erreur avec la sortie de l’API avec votre équipe de succès client.  <br>Exemple d’URL : `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |

1. Revenir à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifié à l’étape 1.

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

**GET**: `http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json`



## Procédure de gestion de la variable `'fmdita rewriter'` conflit

Les guides du Experience Manager comportent une [**réécriture sling personnalisée**](../cs-install-guide/conf-output-generation.md#custom-rewriter) module de gestion des liens générés en cas de croix (liens entre les rubriques de deux cartes différentes).

Si votre code base comporte un autre module de réécriture sling personnalisé, utilisez une `'order'` valeur supérieure à 50, comme l’utilise le module de réécriture sling de Guides de Experience Manager `'order'` 50.  Pour le remplacer, vous devez disposer d’une valeur supérieure à 50. Pour plus d’informations, voir [Pipelines de réécriture de sortie](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Au cours de cette mise à niveau, depuis la variable `'order'` est modifiée de 1000 à 50, vous devez fusionner le module de réécriture personnalisé existant, le cas échéant, avec `'fmdita-rewriter'`.


**Rubrique parente :**[ Télécharger et installer](download-install.md)
