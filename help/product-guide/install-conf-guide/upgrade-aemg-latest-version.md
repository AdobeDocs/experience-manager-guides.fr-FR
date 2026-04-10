---
title: Mettre à niveau Adobe Experience Manager Guides
description: Découvrez comment mettre à niveau Adobe Experience Manager Guides
feature: Installation
role: Admin
level: Experienced
source-git-commit: 453da51a42984b912547570f2e1de70806b41171
workflow-type: tm+mt
source-wordcount: '1661'
ht-degree: 0%

---

# Mise à niveau d’Adobe Experience Manager Guides vers les versions 4.6.0 et ultérieures

Cet article fournit des instructions pour mettre à niveau vos versions Experience Manager Guides pour 4.6.0 et les versions ultérieures.

>[!NOTE]
>
> Suivez les instructions de mise à niveau spécifiques à la version sous licence de votre produit.

Vous pouvez mettre à niveau votre version actuelle de Experience Manager Guides vers la version 5.1.0 Service Pack 3 :

- Si vous utilisez la version 5.1.0 ou 5.1.x , vous pouvez directement effectuer la mise à niveau vers la version 5.1.0 du pack de services 3.
- Si vous utilisez la version 4.6.0, 4.6.x, 5.0.0 ou 5.0.x, vous devez effectuer la mise à niveau vers la version 5.1.0.
- Si vous utilisez une version antérieure à la version 4.6.0, consultez [Mise à niveau d’Adobe Experience Manager Guides vers la version 4.4.0 et les versions antérieures](./upgrade-aemg-prev-versions.md) pour obtenir des instructions de mise à niveau détaillées.

>[!NOTE]
>
> Vous devez installer le pack de services AEM avant de mettre à niveau la version de Experience Manager Guides.

Pour plus d’informations, reportez-vous aux procédures suivantes :

- [Mise à niveau vers la version 5.1.0](#upgrade-to-version-510)
- [Mise à niveau vers la version 5.0.0](#upgrade-to-version-500)
- [Mise à niveau vers la version 4.6.0](#upgrade-to-version-460)

>[!IMPORTANT]
>
> Avant de commencer la mise à niveau, effectuez une sauvegarde complète du système pour éviter toute perte de données.


## Mise à niveau vers la version 5.1.0


>[!IMPORTANT]
>
> Si vous utilisez actuellement AEM 6.5 et envisagez de passer à AEM 6.5 LTS, veillez à effectuer d’abord la mise à niveau d’AEM avant de poursuivre la mise à niveau vers Experience Manager Guides 5.1.0. Pour plus d’informations, consultez la section [Mise à niveau vers Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/fr/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

**Conditions préalables**

>[!NOTE]
>
>Si vous effectuez une mise à niveau vers le pack de services 3 d’ 5.1.0, vous devez utiliser la version 5.1.0 ou 5.1.x de Experience Manager Guides. Le processus de mise à niveau vers la version 5.1.0 du pack de services 3 suit les mêmes étapes que pour la version 5.1.0.

Avant de lancer le processus de mise à niveau vers Experience Manager Guides 5.1.0, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 4.6.3, 4.6.4, 5.0.0 ou 5.0.0 Service Pack 1.
1. (Facultatif) A fermé toutes les tâches de traduction.
1. Modification du niveau de journal en **INFO** pour `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` classe et ajout de ces journaux dans un nouveau fichier journal, par exemple, `logs/translation_upgrade.log`.

>[!NOTE]
>
> Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de démarrer le processus de mise à niveau pendant les heures creuses.

**Installer la version 5.1.0**

Téléchargez le package de la version 5.1.0 à partir du portail de distribution logicielle [&#128279;](https://experience.adobe.com/#/downloads/content/software-distribution/fr/aem.html) et suivez les instructions fournies dans [Workflow de mise à niveau de l’installation et de la post-installation](#installation-and-post-installation-upgrade-workflow) pour terminer la mise à niveau.


## Mise à niveau vers la version 5.0.0

>[!TIP]
>
> La mise à niveau vers la version 5.0.0 du pack de services 3 dépend de la version actuelle de Experience Manager Guides. Si vous utilisez la version 5.0.0 Service Pack 2, 5.0.0 Service Pack 1 ou 5.0.0, vous pouvez directement mettre à niveau vers la version 5.0.0 Service Pack 3. Les étapes de mise à niveau sont identiques à celles de la version 5.0.0.

>[!NOTE]
>
> Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de démarrer le processus de mise à niveau pendant les heures creuses.

**Conditions préalables**

Avant de lancer le processus de mise à niveau vers Experience Manager Guides 5.0.0, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 4.6.3, 4.6.1, 4.6.0 ou 4.4.
1. (Facultatif) A fermé toutes les tâches de traduction.
1. Modification du niveau de journal en **INFO** pour `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` classe et ajout de ces journaux dans un nouveau fichier journal, par exemple, `logs/translation_upgrade.log`.


**Installer la version 5.0.0**

Téléchargez le package de la version 5.0.0 à partir du portail de distribution logicielle [&#128279;](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) et suivez les instructions fournies dans [Workflow de mise à niveau de l’installation et de la post-installation](#installation-and-post-installation-upgrade-workflow) pour terminer la mise à niveau.

## Mise à niveau vers la version 4.6.0

>[!TIP]
>
> Il est recommandé d’installer le pack de services 4.6.0 sur les versions 4.6.0 , 4.6.0 du pack de services 1 ou 4.6.0 du pack de services 3. Le processus de mise à niveau vers le pack de services 4.6.0 d’ suit les mêmes étapes que pour la version 4.6.0 d’.

La mise à niveau vers la version 4.6.0 dépend de la version actuelle de Experience Manager Guides. Si vous utilisez la version 4.4.0, 4.3.1, 4.3.0, 4.2 ou 4.2.1 (correctif 4.2.1.3), vous pouvez directement effectuer la mise à niveau vers la version 4.6.0.

>[!NOTE]
>
> Le post-traitement et l’indexation peuvent prendre quelques heures. Nous vous recommandons de démarrer le processus de mise à niveau pendant les heures creuses.

**Conditions préalables**

Avant de lancer le processus de mise à niveau vers Experience Manager Guides 4.6.0, vérifiez que vous disposez des éléments suivants :

1. Mise à niveau vers Experience Manager Guides version 4.3.1, 4.3.0 ou 4.2.1 (correctif 4.2.1.3).
1. (Facultatif) A fermé toutes les tâches de traduction.
1. Modification du niveau de journal en **INFO** pour `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` classe et ajout de ces journaux dans un nouveau fichier journal, par exemple, `logs/translation_upgrade.log`.

**Installer la version 4.6.0**

Téléchargez le package de la version 4.6.0 à partir du portail de distribution logicielle [&#128279;](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) et suivez les instructions fournies dans [Workflow de mise à niveau de l’installation et de la post-installation](#installation-and-post-installation-upgrade-workflow) pour terminer la mise à niveau.

## Workflow de mise à niveau de l’installation et post-installation

### Installation du package de version

Pour installer le package de version, procédez comme suit :

1. Installez le package de version sur lequel vous souhaitez effectuer la mise à niveau.
1. Vous pouvez choisir d’appuyer sur le déclencheur pour démarrer la tâche de mise à niveau de la carte de traduction. Pour plus d’informations, consultez [&#x200B; Activation du déclencheur de script via une servlet](#enable-trigger-of-script-via-a-servlet).

1. Une fois l’installation du package terminée, attendez le message suivant dans les journaux :

   `Completed the post deployment setup script`

   Le message ci-dessus indique que toutes les étapes d’installation sont terminées.

   Si vous rencontrez l’une des erreurs suivantes, signalez-les à votre équipe du succès client :

   - Erreur dans le script de configuration de post-déploiement
   - Exception lors du portage du MAP de traduction
   - Impossible de transférer la carte de traduction de v1 vers v2 pour la propriété
1. (Facultatif) Mise à niveau du plug-in Oxygen Connector fourni avec la version vers laquelle vous effectuez la mise à niveau.
1. Effacez la mémoire cache du navigateur après l’installation du package.

### Processus de post-installation

Après avoir installé Experience Manager Guides, vous pouvez fusionner les différentes configurations applicables de la version nouvellement installée avec votre configuration.

>[!NOTE]
>
> Le modèle dam-update-asset peut être personnalisé. Ainsi, si des personnalisations ont été effectuées, nous devons les synchroniser avec Experience Manager Guides dans la copie de travail du modèle.

**Workflow Ressource de mise à jour de la gestion des ressources numériques \(Modifications de post-traitement\):**

1. Ouvrir l’URL :

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Sélectionnez **workflow Ressource de mise à jour de la gestion des ressources numériques**.
1. Sélectionnez **Modifier**.
1. Si le composant **DXML Post Process Initiator** est présent, assurez-vous que les personnalisations sont synchronisées.
1. En l’absence du composant **DXML Post Process Initiator**, procédez comme suit pour l’insérer :

   - Sélectionnez **Insérer le composant** \(Responsable du post-traitement Experience Manager Guides comme étape finale du processus\).
   - Configurez l’**étape du processus** avec les détails suivants :

     **Onglet courant :**

      - **Title :** initiateur de post-processus DXML

      - **Description** : étape d’initialisation de post-traitement DXML qui déclenchera une tâche sling pour le post-traitement DXML de la ressource modifiée/créée

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
   - Tous les composants superposés à partir de `/libs/fmditaor/libsshould` doivent être comparés au nouveau code de produit et les mises à jour doivent être effectuées dans les fichiers superposés sous /apps.
   - Toutes les catégories de `clientlib` utilisées à partir du produit doivent être examinées pour les modifications. Toutes les configurations remplacées `\(examples below\)` doivent être comparées aux dernières afin d’obtenir les dernières fonctionnalités :
   - elementmapping.xml
   - `ui\_config.json\(may have been set in folder profiles\)`
   - `com.adobe.fmdita.config.ConfigManager` modifié

1. Si vous avez ajouté des personnalisations dans damAssetLucene, vous devrez peut-être les appliquer à nouveau. Après avoir effectué ces modifications, définissez la réindexation sur true. Cela réindexera tous les nœuds existants avec les personnalisations. Une fois l’opération terminée, l’indicateur de réindexation est de nouveau défini sur false. Cette opération peut prendre quelques heures en fonction du nombre de ressources dans le système.

### Procédure de réindexation des index Experience Manager Guides

1. Ouvrez `crx/de` et accédez au chemin d’accès de l’index : `/oak:index/guidesAssetProperties`
2. Définissez la propriété reindex sur `true` (`false` par défaut) et cliquez sur **Enregistrer tout**.
3. Une fois la réindexation terminée, la propriété Reindex est définie sur `false` et le nombre de réindex est incrémenté de 1.

   >[!NOTE]
   >
   > Cela peut prendre quelques minutes, selon la quantité de données présentes.
4. Suivez les mêmes étapes pour d’autres index ajoutés ou modifiés : `guidesBulkActivation`, `guidesPeerLinkIndex` et `guidesKonnectTemplateIndex`.

### Procédure d’indexation du contenu existant

Effectuez les étapes suivantes pour indexer le contenu existant :

- Exécutez une requête POST au serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des mappages pour les indexer. Par défaut, tous les mappages sont indexés || Exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- L’API renvoie un `jobId`. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée : `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(par exemple : ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`).

- Une fois la tâche terminée, la requête GET ci-dessus répond avec succès et mentionne si des mappages ont échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.


>[!NOTE]
>
> Si vous utilisez le schéma personnalisé, vous devez définir le chemin d’accès des fichiers DTD et XSD catalog.xml personnalisés dans le référentiel AEM dans l’option **Intégrer les catalogues**.

### Procédure à suivre pour gérer le conflit de `'fmdita rewriter'`

Experience Manager Guides dispose d’un module [**custom sling rewriter**](../install-conf-guide/conf-output-generation.md#custom-rewriter) qui gère les liens générés en cas de mappages croisés (liens entre les rubriques de deux mappages différents).

Si votre base de code contient un autre module de réécriture Sling personnalisé, utilisez une valeur de `'order'` supérieure à 50, car le module de réécriture Sling de Experience Manager Guides utilise `'order'` 50.  Pour remplacer cela, vous avez besoin d’une valeur >50. Pour plus d’informations, consultez la section [Pipelines de réécriture de sortie](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Lors de cette mise à niveau, puisque la valeur `'order'` est modifiée de 1 000 à 50, vous devez fusionner le module de réécriture personnalisé existant, le cas échéant, avec `'fmdita-rewriter'`.


### Procédure de réindexation de damAssetLucene

La définition d’index est mise à jour pour damAssetLucene avec AEM Guides. Après la mise à niveau vers la version requise, reportez-vous à [cet article](https://experienceleague.adobe.com/fr/docs/experience-cloud-kcs/kbarticles/ka-16460) pour réindexer damAssetLucene.

>[!NOTE]
>
> Tout en suivant la documentation, assurez-vous que les deux propriétés (`reindex=true` et `reindex-async=true` pour `/oak:index/damAssetLucene`) sont mises à jour simultanément via l’opération Enregistrer .

