---
title: Native PDF | Configuration du processus de nœud pour la publication native de PDF
description: Découvrez comment configurer le processus de nœud pour la publication native de PDF.
feature: Output Generation
role: Admin
level: Experienced
exl-id: 5321c785-8259-4ee2-9ada-ee70fb99b4fd
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 1%
---
# Configuration du processus de nœud pour la publication native de PDF pour Cloud Service

La publication native de PDF lance un processus NodeJs distinct pour convertir les fichiers générés dans le processus de publication en PDF final. Vous devrez peut-être ajuster les configurations de ce processus Node exécutant la publication Native PDF pour prendre en charge différents scénarios. Par exemple, pour exécuter des charges de travail plus volumineuses, vous devez augmenter la taille maximale du tas disponible pour le processus NodeJs généré.

Suivez les instructions fournies dans [Remplacements de la configuration](../install-conf-guide/download-install-config-override.md) pour créer le fichier de configuration.Dans le fichier de configuration, fournissez les détails (propriété) suivants :

| PID | Clé de la propriété | Valeur de la propriété |
|---|---|---|
| `com.adobe.fmdita.config.ConfigManager` | `native.pdf.node.opts` | Valeur de chaîne pour définir une `NODE_OPTIONS` standard.<BR> Valeur par défaut : « » |
