---
title: Configuration et personnalisation des workflows
description: Découvrez comment configurer et personnaliser des workflows
exl-id: a5742082-cc0b-49d9-9921-d0da1b272ea5
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1362'
ht-degree: 1%

---

# Configuration et personnalisation des workflows {#id181AI0OJ0RO}

Les workflows vous permettent d’automatiser les activités Adobe Experience Manager \(AEM\). Un workflow se compose d’une série d’étapes exécutées dans un ordre spécifique. Vous pouvez définir une activité distincte à exécuter à chaque étape. Vous pouvez, par exemple, envoyer une notification électronique à tous les réviseurs d’un groupe lorsqu’une révision de rubrique est créée. Ou envoyez une notification à l’éditeur lorsqu’une tâche de génération de sortie est terminée.

Pour plus d’informations sur les workflows dans AEM, voir :

- [Administration des instances de workflow](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/workflows-administering.html?lang=fr)

- Application et participation aux workflows : [Utilisation des workflows de projet](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/projects/workflows.html).


Les sections de cette rubrique vous guideront tout au long des différentes personnalisations que vous pouvez effectuer dans les workflows par défaut fournis dans les AEM Guides.

## Personnalisation du processus de révision {#id176NE0C00HS}

L’équipe de création de contenu de chaque entreprise travaille de manière spécifique pour répondre aux besoins de son entreprise. Dans certaines organisations, il existe un éditeur dédié, tandis que d’autres pourraient avoir mis en place un système automatisé d’examen éditorial. Par exemple, dans une organisation, un processus de création et de publication type peut inclure des tâches comme : chaque fois qu’un auteur a terminé la création de contenu, il est automatiquement envoyé aux réviseurs, et lorsque la révision est terminée, il est envoyé à l’éditeur pour générer la sortie finale. Dans AEM, les activités que vous effectuez sur votre contenu et vos ressources peuvent être combinées sous la forme d’un processus et mappées à un workflow AEM. Pour plus d’informations sur les workflows dans AEM, voir [Administration des workflows](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/workflows-administering.html?lang=fr) dans la documentation AEM.

AEM Guides vous permet de personnaliser le processus de révision par défaut. Vous pouvez utiliser les quatre processus personnalisés suivants liés à la révision avec vos autres processus de création ou de publication.

- **Créer une révision**: ce processus prépare les métadonnées requises pour créer une tâche de révision. Par exemple, il attribuera des autorisations de révision aux réviseurs, définira le statut des rubriques à réviser, définira les chronologies de révision, etc. Sur les quatre processus, il s’agit du seul processus obligatoire qui doit être inclus dans votre workflow personnalisé. Dans votre workflow, vous pouvez choisir d&#39;inclure ou d&#39;exclure les trois autres processus.

- **Affecter une tâche de révision**: ce processus crée la tâche de révision et envoie la notification de la tâche à l&#39;initiateur et aux réviseurs.

- **Envoyer un courrier électronique de révision**: ce processus envoie le courrier électronique de révision à l’initiateur et aux réviseurs.

- **Planifier la tâche pour fermer la révision**: ce processus permet de s’assurer que le processus de révision se termine lorsque le délai est écoulé.


Lorsque vous créez un processus de révision personnalisé, la première tâche consiste à définir les métadonnées requises par le processus de création de révision. Pour ce faire, vous pouvez créer un script ECMA. Vous trouverez ci-dessous un exemple de script ECMA qui affecte les métadonnées :

```javascript
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
```

Vous pouvez créer ce script dans la variable `/etc/workflows/scripts` noeud . Le tableau suivant décrit les propriétés affectées par ce script ECMA :

| Propriété | Type | Description |
|--------|----|-----------|
| `initiator` | Chaîne | ID utilisateur de l’utilisateur qui lance la tâche de révision. |
| `operation` | Chaîne | Une valeur statique définie comme `AEM_REVIEW`. |
| `orgTopics` | Chaîne | Chemin d’accès des rubriques partagées en vue de la révision. Spécifiez plusieurs rubriques séparées par une virgule. |
| `payloadJson` | Objet JSON | Spécifiez les valeurs suivantes : -   `base`: chemin d’accès du dossier parent contenant la rubrique envoyée pour révision. <br> -   `asset`: chemin d’accès de la rubrique envoyée pour révision. <br> -   `referrer`: laissez le champ vide. |
| `deadline` | Chaîne | Définition de l’heure `yyyy-MM-dd'T'HH:mm:ss.SSSXXX` format. |
| `title` | Chaîne | Saisissez un titre pour la tâche de révision. |
| `description` | Chaîne | Saisissez une description pour la tâche de révision. |
| `assignee` | Chaîne | Identifiant utilisateur des utilisateurs auxquels vous souhaitez envoyer la rubrique\(s\) à des fins de révision. |
| `status` | Entier | Valeur statique définie sur 1. |
| `startTime` | Long | Utilisez la variable `System.currentTimeMillis()` pour obtenir l’heure actuelle du système. |

Une fois que vous avez créé le script, appelez-le avant d’appeler le processus Créer une révision dans votre workflow. Ensuite, en fonction de vos besoins, vous pouvez appeler les autres processus de workflow de révision.

### Supprimer le workflow de révision de la configuration de purge

Pour améliorer les performances du moteur de workflow, vous pouvez régulièrement purger les instances de workflow terminées du référentiel AEM. Si vous utilisez les configurations d’AEM par défaut, toutes les instances de workflow terminées sont nettoyées après une période spécifique. Cela entraîne également la purge de tous les workflows de révision du référentiel AEM.

Vous pouvez empêcher la purge automatique des workflows de révision en supprimant le modèle de workflow de révision \(information\) de la configuration de purge automatique. Vous devez utiliser la variable **Configuration de la purge du workflow Adobe Granite** pour supprimer les modèles de workflow de révision de la liste de purge automatique.

Dans le **Configuration de la purge du workflow Adobe Granite**, veillez à répertorier au moins un workflow que vous pouvez purger en toute sécurité. Par exemple, vous pouvez utiliser l’un des workflows suivants créés par AEM Guides :

- /etc/workflow/models/publishditamap/jcr:content/model
- /etc/workflow/models/post-dita-project-creating-tasks/ jcr:content/model

Ajouter un workflow dans la **Configuration de la purge du workflow Adobe Granite** s’assure qu’AEM purge uniquement les workflows répertoriés dans la configuration. Cela empêche AEM de purger les informations du workflow de révision.

Pour plus d’informations sur la configuration de la variable **Configuration de la purge du workflow Adobe Granite**, voir *Administration des instances de workflow* dans la documentation AEM.

### Personnalisation des modèles de courrier électronique

Un certain nombre de processus AEM Guides utilisent des notifications par e-mail. Par exemple, si vous lancez une tâche de révision, un email de notification est envoyé aux réviseurs. Toutefois, pour vous assurer que l’email de notification est envoyé, vous devez activer cette fonctionnalité dans AEM. Pour activer la notification électronique dans AEM, reportez-vous à l’article [Envoi d’un email](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html?lang=fr#sending-email) dans la documentation AEM.

Les Guides d’AEM contiennent un ensemble de modèles de courrier électronique que vous pouvez personnaliser. Effectuez les étapes suivantes pour personnaliser ces modèles :

1. Utilisez le gestionnaire de modules pour télécharger `/libs/fmdita/mail` fichier .

   >[!NOTE]
   >
   > Ne pas mettre à disposition des personnalisations dans les fichiers de configuration par défaut dans le ``libs`` noeud . Vous devez créer une superposition de la variable ``libs`` dans le noeud ``apps`` et mettez à jour les fichiers requis dans le ``apps`` uniquement.

1. Le dossier de courrier contient les modèles personnalisables suivants :

   | Nom de fichier du modèle | Description |
   |-----------------|-----------|
   | closereview.html | Ce modèle de courrier électronique est utilisé lorsqu’une tâche de révision est fermée. |
   | createreview.html | Ce modèle de courrier électronique est utilisé lors de la création d’une tâche de révision. |
   | reviewapproval.css | Ce fichier CSS contient le style des modèles de courrier électronique. |


## Personnaliser le workflow de génération après la sortie {#id17A6GI004Y4}

AEM Guides vous offre la possibilité de spécifier un workflow de génération de post-sortie. Vous pouvez effectuer certaines tâches de post-traitement sur la sortie générée à l’aide des AEM Guides. Par exemple, vous pouvez appliquer certaines balises CQ à la sortie Site AEM générée ou définir certaines propriétés sur la sortie PDF, ou envoyer un courrier électronique à un ensemble d’utilisateurs une fois la sortie générée.

Vous pouvez créer un modèle de workflow à utiliser comme workflow de génération après sortie. Lorsqu’un workflow de génération de sortie est déclenché, le workflow de génération de sortie partage des informations contextuelles par le biais de la carte des métadonnées de workflow, que vous pouvez utiliser pour effectuer le traitement sur la sortie générée. Le tableau suivant décrit les informations contextuelles partagées en tant que métadonnées :

| Propriété | Type | Description |
|--------|----|-----------|
| ``outputName`` | Chaîne | Nom du paramètre prédéfini de sortie utilisé pour générer la sortie. |
| `generatedPath` | Chaîne | Chemin d’accès dans la gestion des actifs numériques où est stockée la sortie générée. |
| `outputType` | com.adobe.fmdita.output.OutputType | Type du paramètre prédéfini de sortie. |
| `outputTitle` | Chaîne | Titre du paramètre prédéfini de sortie. |
| `outputHistoryPath` | Chaîne | Chemin du référentiel du noeud history. |
| `isSuccess` | Booléen | Indicateur décrivant l’état final du processus de génération de sortie - succès ou échec. |
| `logPath` | Chaîne | Chemin d’accès dans DAM où les journaux de génération de sortie sont enregistrés. |
| `generatedTime` | Long | Heure à laquelle le processus de génération de sortie a été déclenché. |
| `initiator` | Chaîne | ID utilisateur de l’utilisateur qui a déclenché le workflow de génération de sortie. |

Pour utiliser les métadonnées de génération de sortie, vous pouvez créer un script ECMA ou un lot OSGi. Vous trouverez ci-dessous un exemple du script ECMA qui utilise les métadonnées :

>[!NOTE]
>
> Vous pouvez créer ce script dans la variable ``/etc/workflows/scripts`` noeud .

```javascript
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

Une fois que vous avez créé le script, appelez le script personnalisé dans votre workflow. Ensuite, en fonction de vos besoins, vous pouvez appeler les autres processus du workflow. Une fois que vous avez conçu votre workflow personnalisé, appelez la fonction *Finalisation de la génération de publication* comme dernière étape de votre processus de workflow. La variable *Finalisation de la génération de publication* l’étape permet de s’assurer que l’état de la tâche de génération de sortie est mis à jour vers *Terminé* une fois le processus de génération de sortie terminé. Après avoir créé un workflow personnalisé de génération de sortie, vous pouvez le configurer avec l’un de vos paramètres prédéfinis de génération de sortie. Sélectionnez le workflow requis dans la *Exécuter le processus de génération de publication* du paramètre prédéfini requis. Lorsque vous exécutez une tâche de génération de sortie à l’aide du paramètre prédéfini de sortie configuré, l’état de la tâche \(dans l’onglet Sortie\) passe à *Post-traitement*.
