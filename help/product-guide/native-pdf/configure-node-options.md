---
title: Native PDF | Configuration du processus de nœud pour la publication native de PDF
description: Découvrez comment configurer le processus de nœud pour la publication native de PDF.
feature: Output Generation
role: Admin
level: Experienced
exl-id: f470939b-a5cb-4d28-92d1-7a0a52c4c637
TQID: https://experienceleague.adobe.com/7i-6SjvI5FuSNsWPy9sX96UsXld9fJjAjHNKDKzo824
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 122
ht-degree: 1%

---

# Configuration du processus de nœud pour la publication native de PDF pour Cloud Service

La publication native de PDF lance un processus NodeJs distinct pour convertir les fichiers générés dans le processus de publication en PDF final. Vous devrez peut-être ajuster les configurations de ce processus Node exécutant la publication Native PDF pour prendre en charge différents scénarios. Par exemple, pour exécuter des charges de travail plus volumineuses, vous devez augmenter la taille maximale du tas disponible pour le processus NodeJs généré.

Suivez les instructions fournies dans [Remplacements de la configuration](../install-conf-guide/download-install-config-override.md) pour créer le fichier de configuration.Dans le fichier de configuration, fournissez les détails (propriété) suivants :

| PID | Clé de la propriété | Valeur de la propriété |
|---|---|---|
| `com.adobe.fmdita.config.ConfigManager` | `native.pdf.node.opts` | Valeur de chaîne pour définir une `NODE_OPTIONS` standard.<BR> Valeur par défaut : « » |
