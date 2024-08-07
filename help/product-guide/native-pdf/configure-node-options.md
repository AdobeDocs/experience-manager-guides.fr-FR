---
title: PDF natif | Configuration du processus Node pour la publication native de PDF
description: Découvrez comment configurer le processus Node pour la publication native de PDF
exl-id: f470939b-a5cb-4d28-92d1-7a0a52c4c637
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 1%

---

# Configuration du processus de création de noeuds pour la publication avec PDF natif

La publication d’un PDF natif lance un processus NodeJs distinct pour convertir les fichiers générés dans le processus de publication en PDF final. Vous devrez peut-être ajuster les configurations de ce processus Node exécutant la publication de PDF natif pour prendre en charge différents scénarios. Par exemple, pour exécuter des charges de travail plus volumineuses, vous devez augmenter la taille maximale du tas disponible pour le processus NodeJs généré.

Suivez les instructions de la section [Remplacements de configuration](../cs-install-guide/download-install-additional-config-override.md) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails (de propriété) suivants :

| PID | Clé de propriété | Valeur de la propriété |
|---|---|---|
| `com.adobe.fmdita.config.ConfigManager` | `native.pdf.node.opts` | Valeur de chaîne pour définir toute valeur `NODE_OPTIONS` standard.<BR> Valeur par défaut : &quot;&quot; |
