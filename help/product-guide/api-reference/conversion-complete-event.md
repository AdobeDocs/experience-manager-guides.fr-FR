---
title: Gestionnaire d'événements de processus de conversion
description: En savoir plus sur le gestionnaire d’événements du processus de conversion
exl-id: 8033935d-2113-4e39-ab74-b7431b89f948
feature: Conversion Process Event Handler
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/VhlUaVSMTZpfyh5MiJI0WHFpc46s41xjLbuLMUnKH58
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 191
ht-degree: 3%

---

# Gestionnaire d&#39;événements de processus de conversion {#id175UB30E05Z}

AEM Guides expose l’événement com/adobe/fmdita/conversion/complete utilisé pour effectuer toute opération de post-traitement à la fin d’un processus de conversion de document. Cet événement est déclenché chaque fois qu&#39;un document non DITA est migré au format de fichier DITA. Par exemple, si vous exécutez un processus de conversion Word vers DITA ou InDesign vers DITA, cet événement est appelé une fois le processus de conversion terminé.

Vous devez créer un gestionnaire d’événements AEM pour lire les propriétés disponibles dans cet événement et effectuer un traitement ultérieur.

Les détails des événements sont expliqués ci-dessous :

**Nom de l’événement** :

```HTTP
com/adobe/fmdita/conversion/complete 
```

**Paramètres** :

| Nom | Type | Description |
|----|----|-----------|
| `status` | Chaîne | Statut de retour de l’opération effectuée. Les options possibles sont les suivantes : - SUCCÈS : le processus de conversion s’est terminé avec succès. <br> - TERMINÉ AVEC DES ERREURS : le processus de conversion s’est terminé, mais avec des erreurs. <br>- ÉCHEC : le processus de conversion a échoué en raison d’une erreur fatale. |
| `filePath` | Chaîne | Chemin d’accès absolu au fichier source \(à convertir\) dans le référentiel AEM. |
| `outputPath` | Chaîne | Chemin d&#39;accès absolu à l&#39;emplacement de destination où les fichiers DITA convertis seront enregistrés. |
| `logPath` | Chaîne | Chemin d’accès absolu au nœud où sera enregistré le journal de conversion. |
