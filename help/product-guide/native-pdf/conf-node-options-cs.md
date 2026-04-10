---
title: Native PDF | Configuration du processus de nœud pour la publication native de PDF
description: Découvrez comment configurer le processus de nœud pour la publication native de PDF.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 453da51a42984b912547570f2e1de70806b41171
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 1%

---

# Configuration du processus de nœud pour la publication native de PDF pour Cloud Service

La publication native de PDF lance un processus NodeJs distinct pour convertir les fichiers générés dans le processus de publication en PDF final. Vous devrez peut-être ajuster les configurations de ce processus Node exécutant la publication Native PDF pour prendre en charge différents scénarios. Par exemple, pour exécuter des charges de travail plus volumineuses, vous devez augmenter la taille maximale du tas disponible pour le processus NodeJs généré.

Suivez les instructions données dans [Remplacements de configuration](../install-conf-guide/download-install-config-override.md) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails (de propriété) suivants :

| PID | Clé de la propriété | Valeur de la propriété |
|---|---|---|
| `com.adobe.fmdita.config.ConfigManager` | `native.pdf.node.opts` | Valeur de chaîne pour définir toute `NODE_OPTIONS` standard.<BR> Valeur par défaut : « » |
