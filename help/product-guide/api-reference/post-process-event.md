---
title: Gestionnaire d’événements de post-traitement
description: En savoir plus sur le gestionnaire d’événements de post-traitement
exl-id: 3b105ff5-02d4-40e3-a713-206a7fcf18b2
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: 83966cc9187b13dd3b5956821e0aa038b41db28e
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 5%

---

# Gestionnaire d’événements de post-traitement {#id175UB30E05Z}

AEM Guides expose l’événement com/adobe/fmdita/postprocess/complete utilisé pour effectuer toutes les opérations de post-traitement. Cet événement est déclenché chaque fois qu’une opération est effectuée sur un fichier DITA. Les opérations suivantes sur un fichier DITA déclenchent cet événement :

>[!NOTE]
>
> Cet événement n’est pas déclenché pour l’opération de suppression dans AEM 6.1.

- Chargement
- Création
- Modification
- Suppression

Vous devez créer un gestionnaire d’événements AEM pour lire les propriétés disponibles dans cet événement et effectuer un traitement ultérieur.

Les détails de l’événement sont expliqués ci-dessous :

**Nom de l’événement** :

```
com/adobe/fmdita/postprocess/complete 
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `path` | Chaîne | Chemin d’accès du fichier qui a déclenché cet événement. En règle générale, il s’agit du fichier sur lequel une opération a été effectuée. |
| `status` | Chaîne | État de retour de l’opération effectuée. Les options possibles sont : - <br>- SUCCESS : l’opération de post-traitement s’est terminée avec succès. <br> - TERMINÉ AVEC DES ERREURS : l’opération de post-traitement s’est terminée, mais avec certaines erreurs. <br> - ÉCHEC : l’opération de post-traitement a échoué en raison d’une erreur fatale. |
| `message` | Chaîne | Si l’état est TERMINÉ AVEC DES ERREURS ou ÉCHEC, ce paramètre contient les détails sur l’erreur ou la raison de l’échec. |
| `operation` | Chaîne | L’opération de post-traitement effectuée sur le fichier. Les options possibles sont :<br>- Ajout <br>- Mise à jour <br>- Suppression |
