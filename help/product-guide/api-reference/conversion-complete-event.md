---
title: Gestionnaire d’événements de processus de conversion
description: En savoir plus sur le gestionnaire d’événements de processus de conversion
exl-id: 8033935d-2113-4e39-ab74-b7431b89f948
feature: Conversion Process Event Handler
role: Developer
level: Experienced
source-git-commit: 83966cc9187b13dd3b5956821e0aa038b41db28e
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 3%

---

# Gestionnaire d’événements de processus de conversion {#id175UB30E05Z}

AEM Guides expose l’événement com/adobe/fmdita/conversion/complete utilisé pour effectuer toutes les opérations de post-traitement après la fin d’un processus de conversion de document. Cet événement est déclenché lorsqu’un document non DITA est migré au format de fichier DITA. Par exemple, si vous exécutez un processus de conversion Word vers DITA ou InDesign vers un processus de conversion DITA, cet événement est appelé une fois le processus de conversion terminé.

Vous devez créer un gestionnaire d’événements AEM pour lire les propriétés disponibles dans cet événement et effectuer un traitement ultérieur.

Les détails de l’événement sont expliqués ci-dessous :

**Nom de l’événement** :

```HTTP
com/adobe/fmdita/conversion/complete 
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `status` | Chaîne | État de retour de l’opération effectuée. Les options possibles sont : -   SUCCÈS : le processus de conversion s’est terminé avec succès. <br> -   TERMINÉ AVEC DES ERREURS : le processus de conversion s’est terminé, mais avec certaines erreurs. <br>-   ÉCHEC : le processus de conversion a échoué en raison d’une erreur fatale. |
| `filePath` | Chaîne | Chemin d’accès absolu au fichier source \(à convertir\) dans le référentiel AEM. |
| `outputPath` | Chaîne | Chemin absolu de l’emplacement de destination où les fichiers DITA convertis seront enregistrés. |
| `logPath` | Chaîne | Chemin d’accès absolu au noeud où le journal de conversion sera enregistré. |
