---
title: Gestionnaire d’événements de processus de conversion
description: En savoir plus sur le gestionnaire d’événements de processus de conversion
exl-id: 8033935d-2113-4e39-ab74-b7431b89f948
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# Gestionnaire d’événements de processus de conversion {#id175UB30E05Z}

AEM Guides expose l’événement com/adobe/fmdita/conversion/complete utilisé pour effectuer toutes les opérations de post-traitement une fois le processus de conversion terminé. Cet événement est déclenché lorsqu’un document non DITA est migré au format de fichier DITA. Par exemple, si vous exécutez un processus de conversion Word vers DITA ou InDesign vers un processus de conversion DITA, cet événement est appelé une fois le processus de conversion terminé.

Vous devez créer un gestionnaire d’événements AEM pour lire les propriétés disponibles dans cet événement et effectuer un traitement ultérieur.

Les détails de l’événement sont expliqués ci-dessous :

**Nom de l’événement**:

```HTTP
com/adobe/fmdita/conversion/complete 
```

**Paramètres**:\
|Nom|Type|Description| |—|—|—| |`status`|String|L’état de retour de l’opération effectuée. Les options possibles sont : - SUCCESS : le processus de conversion s’est terminé avec succès. <br> - TERMINÉ AVEC DES ERREURS : le processus de conversion s’est terminé, mais avec certaines erreurs. <br>- FAILED : le processus de conversion a échoué en raison d’une erreur fatale.| |`filePath`|Chaîne|Chemin absolu du fichier source \(à convertir\) dans le référentiel AEM.| |`outputPath`|Chaîne|Chemin absolu de l’emplacement de destination où les fichiers DITA convertis seront enregistrés.| |`logPath`|Chaîne|Chemin absolu du noeud où sera enregistré le journal de conversion.|
