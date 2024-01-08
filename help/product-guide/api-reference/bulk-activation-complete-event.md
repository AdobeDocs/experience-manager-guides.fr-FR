---
title: Gestionnaire d’événements complete d’activation en bloc
description: En savoir plus sur le gestionnaire d’événement complet d’activation en bloc
source-git-commit: 8f1bb12a92ab9a63aef1765e51159644242683a0
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 2%

---

# Gestionnaire d’événements complete d’activation en bloc

Exposition de guides du Experience Manager `com/adobe/fmdita/replication/complete` qui est utilisé pour effectuer toute opération après la fin d’un processus d’activation en bloc. Cet événement est déclenché chaque fois qu’un processus d’activation en bloc est terminé. Par exemple, si vous exécutez l’activation en bloc d’un paramètre prédéfini de site AEM d’une carte, cet événement est appelé une fois le processus d’activation terminé.

Vous devez créer un gestionnaire d’événements AEM pour lire les propriétés disponibles dans cet événement et effectuer un traitement ultérieur.

Les détails de l’événement sont expliqués ci-dessous :

**Nom de l’événement**:

```
com/adobe/fmdita/replication/complete 
```

**Paramètres**: |Nom|Type|Description| |—|—|—| |`path`|String|Le chemin d’accès du fichier qui a déclenché cet événement. <br> Par exemple, `/content/output/sites/ditamap1-ditamap`. <br> Il s’agit d’une liste de chemins sérialisés en tant que tableau JSON.| |`messageType`|Chaîne|Type d’un message. <br>Option possible : `REPLICATION`| |`action`|String|Il s’agit de l’action effectuée. <br>Option possible : `BulkReplicate`| |`user`|String|L’utilisateur qui a démarré l’opération.| |`result`|Chaîne|Résultat de l’activation en bloc. Il s’agit d’un objet JSON sérialisé : <br>`{"success":boolean,"code":integer,"message":"" }`| |`agentId`|String|L’agentId utilisé dans la réplication. Par exemple, `"publish"`.| |`importMode`|Chaîne|Mode d’importation utilisé dans Activation. Les options possibles sont les suivantes : <br>`REPLACE, MERGE, UPDATE`.


**Écouteur d’événements d’exemple**:

```XML
@Component(service = EventHandler.class,
        immediate = true,
        property = {
                EventConstants.EVENT_TOPIC + "=" + "com/adobe/fmdita/replication/complete",
        })
 
public class SampleEventHandler implements EventHandler {
 
    protected final Logger log = LoggerFactory.getLogger(this.getClass());
 
    @Override
    public void handleEvent(final Event event) {
        Map<String, String> properties = new HashMap<>();
        properties.put("paths", (String) event.getProperty("paths"));
        properties.put("messageType", (String) event.getProperty("messageType"));
        properties.put("action", (String) event.getProperty("action"));
        properties.put("result", (String) event.getProperty("result"));
        properties.put("user", (String) event.getProperty("user"));
        properties.put("agentId", (String) event.getProperty("agentId"));
        properties.put("importMode", (String) event.getProperty("importMode"));
 
        String eventTopic = event.getTopic();
        log.debug("eventTopic {}", eventTopic);
        for(Map.Entry entry:properties.entrySet()) {
            log.debug(entry.getKey() + " : " + entry.getValue());
        }
 
    }
}
```
