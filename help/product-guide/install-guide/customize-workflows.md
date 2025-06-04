---
title: Configuration et personnalisation de workflows
description: Découvrez comment configurer et personnaliser des workflows
exl-id: 3be387b9-6ac2-4b61-afdf-fbe9d8b6cc1e
feature: Workflow Configuration
role: Admin
level: Experienced
source-git-commit: 3f61aa6615a1b9765154d55249a33136443dfa33
workflow-type: tm+mt
source-wordcount: '1856'
ht-degree: 4%

---

# Configuration et personnalisation de workflows {#id181AI0OJ0RO}

Les workflows vous permettent d’automatiser les activités Adobe Experience Manager \(AEM\). Un workflow se compose d’une série d’étapes exécutées dans un ordre spécifique. Vous pouvez définir une activité distincte à exécuter sur chaque étape. Par exemple, vous pouvez envoyer une notification par e-mail à tous les réviseurs et réviseuses d’un groupe lors de la création d’une révision de rubrique. Vous pouvez également envoyer une notification à l’éditeur lorsqu’une tâche de génération de sortie est terminée.

Pour plus d’informations sur les workflows dans AEM, voir :

- [Administration des workflows](https://helpx.adobe.com/fr/experience-manager/6-5/sites/administering/using/workflows.html)

- Demande de workflow et participation à des workflows : [Utilisation des workflows](https://helpx.adobe.com/fr/experience-manager/6-5/sites/authoring/using/workflows.html).

- Création de modèles de workflows et extension de la fonctionnalité de workflow : [Développement et extension des workflows](https://helpx.adobe.com/fr/experience-manager/6-5/sites/developing/using/workflows.html).

- Amélioration des performances des workflows qui utilisent des ressources de serveur importantes : [Traitement de workflows simultanés](https://helpx.adobe.com/fr/experience-manager/6-5/sites/deploying/using/configuring-performance.html#ConfiguringforPerformance).


Les sections de cette rubrique vous guideront à travers différentes personnalisations que vous pouvez effectuer dans les workflows par défaut fournis dans AEM Guides.

## Personnaliser le workflow de révision {#id176NE0C00HS}

L’équipe de création de contenu de chaque organisation travaille d’une manière spécifique pour répondre aux besoins de son entreprise. Dans certaines organisations, il y a un éditeur spécialisé, tandis que dans d&#39;autres organisations, il pourrait y avoir un système automatisé de révision éditoriale. Par exemple, dans une organisation, un workflow de création et de publication standard peut inclure des tâches telles que : chaque fois qu’un auteur crée du contenu, il passe automatiquement aux réviseurs et, une fois la révision terminée, il passe à l’éditeur pour générer la sortie finale. Dans AEM, les activités que vous effectuez sur votre contenu et vos ressources peuvent être regroupées sous la forme d’un processus et mappées à un workflow AEM. Pour plus d’informations sur les workflows dans AEM, consultez la section [Administration des workflows](https://helpx.adobe.com/fr/experience-manager/6-5/sites/administering/using/workflows.html) dans la documentation AEM.

AEM Guides vous permet de personnaliser le workflow de révision par défaut. Vous pouvez utiliser les quatre processus personnalisés suivants liés aux révisions avec vos autres workflows de création ou de publication.

- **Créer une révision** : ce processus prépare les métadonnées nécessaires à la création d’une tâche de révision. Par exemple, il attribuera des autorisations de révision aux réviseurs, définira le statut des rubriques sur en cours de révision, définira les délais de révision, etc. Sur les quatre processus, il s’agit du seul processus obligatoire qui doit être inclus dans votre workflow personnalisé. Dans votre workflow, vous pouvez choisir d’inclure ou d’exclure les trois autres processus.

- **Affecter une tâche de révision** : ce processus crée la tâche de révision et envoie la notification de tâche à l’initiateur et aux réviseurs.

- **Envoyer un e-mail de révision** : ce processus envoie l’e-mail de révision à l’initiateur et aux réviseurs.

- **Planifier la tâche pour fermer la révision** : ce processus garantit que le processus de révision se termine une fois l’échéance atteinte.


Lorsque vous créez un workflow de révision personnalisé, la première tâche consiste à définir les métadonnées nécessaires au processus de création d’une révision. Pour ce faire, vous pouvez créer un script ECMA. Vous trouverez ci-dessous un exemple de script ECMA qui attribue les métadonnées pour la rubrique et pour le mappage.

**Pour rubrique**

```json
var workflowdata=workItem.getWorkflowData();
workflowdata.getMetaDataMap().put("initiator","admin");
workflowdata.getMetaDataMap().put("operation","AEM_REVIEW");
workflowdata.getMetaDataMap().put("orgTopics","/content/dam/xml-solution/review.xml");
workflowdata.getMetaDataMap().put("payloadJson","{\"base\":\"/content/dam/xml-solution\",\"asset\":[\"/content/dam/xml-solution/review.xml\"],\"referrer\":\""}");
workflowdata.getMetaDataMap().put("deadline","2017-06-27T13:19:00.000+05:30");
workflowdata.getMetaDataMap().put("title","Review through custom workflow");
workflowdata.getMetaDataMap().put("description","Initiate this review process using the AEM workflow");
workflowdata.getMetaDataMap().put("assignee","user-one", "user-two");
workflowdata.getMetaDataMap().put("status","1");
workflowdata.getMetaDataMap().put("projectPath","/content/projects/review");
workflowdata.getMetaDataMap().put("startTime", System.currentTimeMillis());
workflowdata.getMetaDataMap().put("reviewType", "AEM");
workflowdata.getMetaDataMap().put("versionJson", "[{\"path\":\"GUID-ca6ae229-889a-4d98-a1c6-60b08a820bb3.dita\",\"review\":true,\"version\":\"1.0\",\"reviewers\":[\"projects-samplereviewproject-owner\"]}]");
workflowdata.getMetaDataMap().put("isDitamap","false");
```

**Pour la carte**

```json
var workflowdata = workItem.getWorkflowData();
workflowdata.getMetaDataMap().put("initiator", "admin");
workflowdata.getMetaDataMap().put("operation", "AEM_REVIEW");
workflowdata.getMetaDataMap().put("orgTopics", "GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita|GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita|GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita|");
var payloadJson = "{\"referrer\":\"\",\"rootMap\":\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\",\"asset\":[\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\"],\"base\":\"/content/dam\"}";
workflowdata.getMetaDataMap().put("payloadJson", payloadJson);
workflowdata.getMetaDataMap().put("deadline", "2047-06-27T13:19:00.000+05:30");
workflowdata.getMetaDataMap().put("title", "Review task via workflow with map");
workflowdata.getMetaDataMap().put("description", "Review task via workflow with map Description");
workflowdata.getMetaDataMap().put("assignee", "user-one");
workflowdata.getMetaDataMap().put("status", "1");
workflowdata.getMetaDataMap().put("projectPath", "/content/projects/review_project_via_workflow");
workflowdata.getMetaDataMap().put("startTime", new Date().getTime());
var versionJson = "[{\"path\":\"GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]},{\"path\":\"GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]},{\"path\":\"GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]}]";
workflowdata.getMetaDataMap().put("versionJson", versionJson);
workflowdata.getMetaDataMap().put("notifyViaEmail", "true");
workflowdata.getMetaDataMap().put("allowAllReviewers", "false");
workflowdata.getMetaDataMap().put("isDitamap", "true");
workflowdata.getMetaDataMap().put("ditamap", "GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap");
var ditamapHierarchy = "[{\"path\":\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\",\"items\":[{\"path\":\"GUID-db5787bb-5467-4dc3-b3e5-cfde562ee745.ditamap\",\"items\":[{\"path\":\"GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita\",\"items\":[],\"title\":\"\"},{\"path\":\"GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita\",\"items\":[],\"title\":\"\"}],\"title\":\"\"},{\"path\":\"GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita\",\"items\":[],\"title\":\"\"}]}]";
workflowdata.getMetaDataMap().put("ditamapHierarchy", ditamapHierarchy);
```

Vous pouvez créer ce script dans le nœud `/etc/workflows/scripts` . Le tableau suivant décrit les propriétés affectées par ce script ECMA :

| Propriété | Type | Description |
|--------|----|-----------|
| `initiator` | Chaîne | ID de l’utilisateur qui a lancé la tâche de révision. |
| `operation` | Chaîne | Valeur statique définie comme `AEM_REVIEW`. |
| `orgTopics` | Chaîne | Chemin d’accès aux rubriques partagées pour la révision. Spécifiez plusieurs rubriques séparées par des virgules. |
| `payloadJson` | Objet JSON | Spécifiez les valeurs suivantes : <br> - `base` : chemin d’accès du dossier parent contenant la rubrique envoyée pour révision.<br>- `asset` : chemin d’accès du sujet envoyé pour révision. <br>- `referrer` : laissez ce champ vide. |
| `deadline` | Chaîne | Spécifiez l’heure au format `yyyy-MM-dd'T'HH:mm:ss.SSSXXX`. |
| `title` | Chaîne | Saisissez un titre pour la tâche de révision. |
| `description` | Chaîne | Saisissez une description pour la tâche de révision. |
| `assignee` | Chaîne | ID utilisateur des utilisateurs auxquels vous souhaitez envoyer le(s) topic\(s) pour révision. |
| `status` | Entier | Une valeur statique définie sur 1. |
| `startTime` | Long | Utilisez la fonction `System.currentTimeMillis()` pour obtenir l’heure actuelle du système. |
| `projectPath` | Chaîne | Chemin du projet de révision auquel la tâche de révision sera affectée, par exemple : /content/projects/samplereviewproject. |
| `reviewType` | Chaîne | Valeur statique « AEM ». |
| `versionJson` | Objet JSON | versionJson est une liste de rubriques allant dans la révision où chaque objet de rubrique possède la structure suivante { « path »: « /content/dam/1-topic.dita », « version »: « 1.1 », « review »: true, « reviewers »: [« projects-we_retail-editor »] } |
| `isDitamap` | Booléen | false/true |
| `ditamapHierarchy` | Objet JSON | Si la carte est envoyée pour révision, la valeur doit être la suivante :[ { « path »: « GUID-f0df1513-fe07-473f-9960-477d4df29c87.ditamap », « items »: [ { « path »: « GUID-9747e8ab-8cf1-45dd-9e20-d47d482f667d.dita », « title »: «  », « items »: [] } ] } ]. |
| `ditamap` | Chaîne | Spécifiez le chemin d’accès du ditamap de la tâche de révision |
| `allowAllReviewers` | Booléen | false/true |
| `notifyViaEmail` | Booléen | false/true |


Une fois le script créé, appelez-le avant d’appeler le processus Créer une révision dans votre workflow. Ensuite, en fonction de vos besoins, vous pouvez appeler les autres processus de workflow de révision.

### Supprimer le workflow de révision de la configuration de purge

Pour améliorer les performances du moteur de workflow, vous pouvez purger régulièrement les instances de workflow terminées du référentiel AEM. Si vous utilisez les configurations AEM par défaut, toutes les instances de workflow terminées sont nettoyées après une période spécifique. Cela entraîne également la purge de tous les workflows de révision du référentiel AEM.

Vous pouvez empêcher les workflows de révision de se purger automatiquement en supprimant le modèle de workflow de révision \(informations\) de la configuration de purge automatique. Vous devez utiliser la **configuration de la purge du workflow Adobe Granite** pour supprimer les modèles de workflow de révision de la liste de purge automatique.

Dans la configuration de la purge du workflow Adobe Granite **&#x200B;**, veillez à répertorier au moins un workflow que vous pouvez purger en toute sécurité. Par exemple, vous pouvez utiliser l’un des workflows suivants créés par AEM Guides :

- /etc/workflow/models/publishditamap/jcr:content/model
- /etc/workflow/models/post-data-project-creation-tasks/ jcr:content/model

L’ajout d’un workflow à la **Configuration de la purge du workflow Adobe Granite** garantit qu’AEM purge uniquement les workflows répertoriés dans la configuration. Cela empêche AEM de purger les informations du workflow de révision.

Pour plus d’informations sur la configuration de la configuration de la purge du workflow Adobe Granite **&#x200B;**, voir *Administration d’instances de workflow* dans la documentation AEM.

### Personnaliser les modèles d’e-mail

Un certain nombre de workflows AEM Guides utilisent les notifications par e-mail. Par exemple, si vous lancez une tâche de révision, une notification est envoyée par e-mail aux réviseurs. Cependant, pour vous assurer que la notification par e-mail est envoyée, vous devez activer cette fonctionnalité dans AEM. Pour activer les notifications par e-mail dans AEM, consultez l’article [Configuration des notifications par e-mail](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=fr) dans la documentation AEM.

AEM Guides contient un ensemble de modèles d’e-mail que vous pouvez personnaliser. Pour personnaliser ces modèles, procédez comme suit :

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite .

1. Dans l’onglet Navigateur , accédez à l’emplacement suivant :

   `/libs/fmdita/mail`

   >[!NOTE]
   >
   > Ne rendez aucune personnalisation dans les fichiers de configuration par défaut disponibles dans le nœud ``libs``. Vous devez créer un recouvrement du nœud ``libs`` dans le nœud ``apps`` et mettre à jour les fichiers requis dans le nœud ``apps`` uniquement.

1. Le dossier d’e-mails contient les modèles personnalisables suivants :

   | Nom de fichier du modèle | Description |
   |-----------------|-----------|
   | closereview.html | Ce modèle d’e-mail est utilisé lorsqu’une tâche de révision est fermée. |
   | createreview.html | Ce modèle d’e-mail est utilisé lorsqu’une nouvelle tâche de révision est créée. |
   | reviewapproval.css | Ce fichier CSS contient le style des modèles d’e-mail. |


## Personnalisation du workflow de génération après sortie {#id17A6GI004Y4}

AEM Guides vous offre la possibilité de spécifier un workflow de génération post-sortie. Vous pouvez effectuer certaines tâches de post-traitement sur la sortie générée à l’aide d’AEM Guides. Par exemple, vous pouvez appliquer certaines balises CQ sur la sortie de site AEM générée, définir certaines propriétés sur la sortie PDF ou envoyer un e-mail à un ensemble d’utilisateurs une fois la sortie générée.

Vous pouvez créer un nouveau modèle de workflow à utiliser comme workflow de génération post-sortie. Lorsqu’un workflow de génération post-sortie est déclenché, il partage des informations contextuelles par le biais du mappage de métadonnées de workflow, que vous pouvez utiliser pour effectuer un traitement sur la sortie générée. Le tableau suivant décrit les informations contextuelles partagées en tant que métadonnées :

| Propriété | Type | Description |
|--------|----|-----------|
| ``outputName`` | Chaîne | Nom du préréglage de sortie utilisé pour générer la sortie. |
| `generatedPath` | Chaîne | Chemin dans la gestion des ressources numériques où est stockée la sortie générée. |
| `outputType` | com.adobe.fmdita.output.OutputType | Type du paramètre prédéfini de sortie. |
| `outputTitle` | Chaîne | Titre du paramètre prédéfini de sortie. |
| `outputHistoryPath` | Chaîne | Chemin du référentiel du nœud d’historique. |
| `isSuccess` | Booléen | Indicateur décrivant le statut final du processus de génération de sortie - succès ou échec. |
| `logPath` | Chaîne | Chemin dans la gestion des ressources numériques où sont enregistrés les logs de génération de sortie. |
| `generatedTime` | Long | Heure à laquelle le processus de génération de sortie a été déclenché. |
| `initiator` | Chaîne | ID de l’utilisateur qui a déclenché le workflow de génération de sortie. |

Pour utiliser les métadonnées de génération de sortie, vous pouvez créer un script ECMA ou un lot OSGi. Vous trouverez ci-dessous un exemple de script ECMA qui utilise les métadonnées :

>[!NOTE]
>
> Vous pouvez créer ce script dans le nœud ``/etc/workflows/scripts`` .

```json
var session = workflowSession.getSession(); // Obtain session object to read/write the repository.
var payload = workItem.getWorkflowData().getPayload().toString(); // Get the workflow payload (the ditamap file on which the generation was triggered)
var metadata = workItem.getWorkflowData().getMetaDataMap(); // Get the workflow metadata object
var generatedPath = metadata.get("generatedPath"); // supplied by AEM Guides
var username = metadata.get("initiator"); // supplied by AEM Guides
var successful = metadata.get("isSuccess"); // supplied by AEM Guides
var title = metadata.get("outputTitle"); // supplied by AEM Guides
var subject = "Output Generation Finished";
var message = "Generation of output " + title + " just finished " + 
(successful ? "successfully. " : "unsuccessfully. ");
    message += "It was triggered by " + username;    
if (successful) {
    message += "<br/><br/>The path to the generated output is " + 
generatedPath;
}
/*
    MailerAPI.sendMail("dl-docs-authors", subject, message);
*/
```

Une fois le script créé, appelez le script personnalisé dans votre workflow. Ensuite, en fonction de vos besoins, vous pouvez appeler les autres processus de workflow. Une fois que vous avez conçu votre workflow personnalisé, appelez la *Finaliser la post-génération* comme dernière étape de votre processus de workflow. L’étape *Finaliser la post-génération* garantit que le statut de la tâche de génération de sortie est mis à jour sur *Terminé* à la fin du processus de génération de sortie. Après avoir créé un workflow personnalisé de génération post-sortie, vous pouvez le configurer avec n’importe lequel de vos paramètres prédéfinis de génération de sortie. Sélectionnez le workflow requis dans la propriété *Exécuter le workflow de post-génération* du paramètre prédéfini requis. Lorsque vous exécutez une tâche de génération de sortie à l’aide du paramètre prédéfini de sortie configuré, le statut de la tâche \(dans l’onglet Sortie\) passe à *Post-traitement*.

## Personnaliser le workflow de mise à jour de ressource {#id18C3D0I0B5Z}

Par défaut, le workflow *Ressource de mise à jour de gestion des ressources numériques* se déclenche chaque fois que vous créez ou mettez à jour une ressource AEM \(XML ou non-XML\). Par exemple, lorsque vous créez une rubrique ou que vous la mettez à jour, le workflow *Ressource de mise à jour de gestion des ressources numériques* est exécuté. Le workflow *Ressource de mise à jour de gestion des ressources numériques* tente d’extraire les métadonnées pertinentes d’Assets. Le workflow de mise à jour des ressources prêt à l’emploi *Asset Update Workflow* ne comporte aucune étape pour extraire des métadonnées pertinentes d’un fichier DITA et le workflow *Ressource de mise à jour de gestion des ressources numériques* génère un grand nombre de journaux au moment de l’exécution. Si vous souhaitez éviter la création de journaux supplémentaires, vous pouvez configurer le workflow de sorte à ignorer le traitement de tous les fichiers XML.

Effectuez les étapes suivantes pour personnaliser le workflow *Ressource de mise à jour de gestion des ressources numériques* :

1. ouvrez la page **Lanceurs de workflow**.

   L’URL par défaut pour accéder à la page Lanceurs de workflow est :

   ```http
   http://<server name>:<port>/libs/cq/workflow/admin/console/content/launchers.html
   ```

1. Dans la liste des lanceurs de workflow, ouvrez les propriétés du workflow **Ressource de mise à jour de gestion des ressources numériques**.

1. Ajoutez une condition avec l’expression suivante :

   ```json
   jcr:content/metadata/dc:format!=application/xml
   ```

1. Cliquez sur **Enregistrer et fermer**.


## Configuration du workflow XML de post-traitement {#id18CJB03J0Y4}

AEM Guides crée un ensemble de workflows qui vous permettent d&#39;utiliser du contenu DITA dans AEM. Par exemple, certains workflows sont exécutés lorsque vous chargez du contenu DITA ou mettez à jour du contenu existant. Ces workflows analysent les documents DITA et effectuent diverses tâches, telles que la définition des métadonnées, l&#39;ajout de paramètres prédéfinis de sortie par défaut aux nouveaux mappages DITA et d&#39;autres tâches associées.

>[!NOTE]
>
> Pour personnaliser ou étendre les workflows de post-traitement par défaut, vous pouvez utiliser le gestionnaire d’événements de post-traitement décrit dans la section *Référence d’API pour Adobe Experience Manager Guides*.

Les propriétés suivantes régissent l’exécution des workflows de post-traitement par AEM Guides :

>[!NOTE]
>
> Les propriétés suivantes sont accessibles via la console web : http://&lt;nom du serveur\>:&lt;port\>/system/console/configMgr.

| Propriété | Nom du lot | Description |
|--------|-----------|-----------|
| Sorties dynamiques | `com.adobe.fmdita.postprocess.PostProcessObservation` | Pour tous les fichiers sur lesquels le post-traitement n&#39;a pas été effectué, il récupère les références sortantes en analysant les fichiers de rubrique. Il est recommandé de garder cette option désactivée, car elle peut surcharger le système si le nombre de fichiers à traiter est important. |
| Threads de post-traitement | `com.adobe.fmdita.config.ConfigManager` | Définit le nombre de threads de post-traitement à utiliser pour le workflow de post-traitement. <br>La valeur par défaut est 1. |
