---
title: Gestionnaire d’événements d’activation en bloc terminée
description: En savoir plus sur le gestionnaire d’événements d’activation en bloc
feature: Bulk Activation Event Handler
role: Developer
level: Experienced
exl-id: 08b153d7-3d13-4804-9e3e-38790dbea1f3
TQID: https://experienceleague.adobe.com/M8Q8A8auCkKjmoilHsUfU2ztNSCxOWstwPC1bMLmvD0
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 185
ht-degree: 6%

---

# Gestionnaire d’événements d’activation en bloc terminée

Experience Manager Guides expose `com/adobe/fmdita/replication/complete` événement utilisé pour effectuer toute opération après l’achèvement d’un processus d’activation en bloc. Cet événement est déclenché chaque fois qu’un processus d’activation en bloc est terminé. Par exemple, si vous exécutez l’activation en bloc d’un paramètre prédéfini de site AEM d’une carte, cet événement est appelé une fois le processus d’activation terminé.

Vous devez créer un gestionnaire d’événements AEM pour lire les propriétés disponibles dans cet événement et effectuer un traitement ultérieur.

Les détails des événements sont expliqués ci-dessous :

**Nom de l’événement** :

```
com/adobe/fmdita/replication/complete 
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `path` | Chaîne | Chemin d’accès au fichier qui a déclenché cet événement. <br> Par exemple, `/content/output/sites/ditamap1-ditamap`. <br> Il s’agit d’une liste de chemins sérialisés sous la forme d’un tableau JSON. |
| `messageType` | Chaîne | Type d’un message. <br>Option possible : `REPLICATION` |
| `action` | Chaîne | Il s’agit de l’action effectuée. <br>Option possible : `BulkReplicate` |
| `user` | Chaîne | L’utilisateur ou l’utilisatrice qui a démarré l’opération. |
| `result` | Chaîne | Résultat de l’activation en bloc. C’est un objet JSON sérialisé : <br>`{"success":boolean,"code":integer,"message":"" }` |
| `agentId` | Chaîne | AgentId utilisé dans la réplication. Par exemple, `"publish"`. |
| `importMode` | Chaîne | Mode d&#39;import utilisé dans Activation. Les options possibles sont : <br>`REPLACE, MERGE, UPDATE`. |


**Exemple d’écouteur d’événement** :

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
