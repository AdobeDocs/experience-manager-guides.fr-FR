---
title: Gestionnaire d'événements de post-traitement
description: En savoir plus sur le gestionnaire d’événements de post-traitement
exl-id: 3b105ff5-02d4-40e3-a713-206a7fcf18b2
feature: Post-Processing Event Handler
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/ixD-jFpXxkdmPbOWtCDxPgjtxu-FfJkzGCdUHNeA1CY
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 427
ht-degree: 4%

---

# Gestionnaire d&#39;événements de post-traitement {#id175UB30E05Z}

## UUID et Cloud Service

Adobe Experience Manager Guides expose `com/adobe/guides/postprocess/complete` événement utilisé pour effectuer toute opération de post-traitement. Cet événement est déclenché chaque fois qu&#39;une opération est effectuée sur un fichier DITA. Les opérations suivantes sur un fichier DITA déclenchent cet événement :

- Chargement
- Créer
- Modification

>[!NOTE]
>
> L’événement de post-traitement est déclenché en activant l’indicateur de `fire.processing.events` qui est un paramètre de configuration dans le `fmdita config manager` . Lorsque la valeur est définie sur true, elle déclenche des événements (com/adobe/guides/postprocess/complete) pour effectuer le suivi de l’achèvement du post-traitement. Par défaut, elle est définie sur false (désactivée).

Vous devez créer un gestionnaire d’événements Adobe Experience Manager pour lire les propriétés disponibles dans cet événement et effectuer un traitement ultérieur.

Les détails des événements sont expliqués ci-dessous :

**Nom de l’événement** :

```
com/adobe/guides/postprocess/complete 
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `path` | Chaîne | Chemin d’accès au fichier qui a déclenché cet événement. En règle générale, il s’agit du fichier sur lequel une opération a été effectuée. |
| `eventType` | Chaîne | Type d’événement, c’est-à-dire CRÉER ou MODIFIER. |
| `status` | Chaîne | Statut de retour de l’opération effectuée. Les options possibles sont les suivantes : <br>- SUCCÈS : L’opération de post-traitement s’est terminée avec succès. <br>- ÉCHEC : l’opération de post-traitement a échoué en raison d’une erreur. |
| `errorMsg` | Chaîne | Message d’erreur en cas d’échec de l’opération de post-traitement. |
| `uuid` | Chaîne | UUID du fichier qui a déclenché cet événement. En règle générale, il s’agit du fichier sur lequel une opération a été effectuée. |

**Exemple d’écouteur d’événement**


```
@Component(service = EventHandler.class,
        immediate = true,
        property = {
                EventConstants.EVENT_TOPIC + "=" + "com/adobe/guides/postprocess/complete",
        })
public class PostProcessCompleteEventHandler implements EventHandler {

    protected final Logger log = LoggerFactory.getLogger(this.getClass());

    @Override
    public void handleEvent(final Event event) {
        Set<String> propertyNames = new HashSet<>(Arrays.asList(event.getPropertyNames()));
        Map<String, String> properties = new HashMap<>();
        properties.put("path", (String) event.getProperty("path"));
        properties.put("eventType", (String) event.getProperty("eventType"));
        properties.put("status", (String) event.getProperty("status"));
        if(propertyNames.contains("errorMsg")) {
            properties.put("errorMsg", (String) event.getProperty("errorMsg"));
        }
        if (propertyNames.contains("uuid")) {
            properties.put("uuid", (String) event.getProperty("uuid"));
        }
        String eventTopic = event.getTopic();
        log.debug("eventTopic {}", eventTopic);
        for(Map.Entry entry:properties.entrySet()) {
            log.debug(entry.getKey() + " : " + entry.getValue());
        }
    }
}
```

## Non UUID


Adobe Experience Manager Guides expose l’événement com/adobe/fmdita/postprocess/complete utilisé pour effectuer toute opération de post-traitement. Cet événement est déclenché chaque fois qu&#39;une opération est effectuée sur un fichier DITA. Les opérations suivantes sur un fichier DITA déclenchent cet événement :

>[!NOTE]
>
> Cet événement n’est pas déclenché pour l’opération de suppression dans AEM 6.1.

- Chargement
- Création
- Modification
- Suppression

Vous devez créer un gestionnaire d’événements Adobe Experience Manager pour lire les propriétés disponibles dans cet événement et effectuer un traitement ultérieur.

Les détails des événements sont expliqués ci-dessous :

**Nom de l’événement** :

```
com/adobe/fmdita/postprocess/complete 
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `path` | Chaîne | Chemin d’accès au fichier qui a déclenché cet événement. En règle générale, il s’agit du fichier sur lequel une opération a été effectuée. |
| `status` | Chaîne | Statut de retour de l’opération effectuée. Les options possibles sont les suivantes : <br>- SUCCÈS : L’opération de post-traitement s’est terminée avec succès. <br>- TERMINÉ AVEC DES ERREURS : l’opération de post-traitement s’est terminée, mais avec des erreurs. <br>- ÉCHEC : l’opération de post-traitement a échoué en raison d’une erreur. |
| `message` | Chaîne | Si l’état est TERMINÉ AVEC DES ERREURS ou EN ÉCHEC, ce paramètre contient les détails sur l’erreur ou la raison de l’échec. |
| `operation` | Chaîne | Opération de post-traitement effectuée sur le fichier. Les options possibles sont les suivantes : <br>- Ajout <br>- Mise à jour <br>- Suppression |
