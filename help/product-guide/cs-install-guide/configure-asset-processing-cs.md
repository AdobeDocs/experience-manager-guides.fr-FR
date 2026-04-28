---
title: Configuration du traitement des ressources pour Cloud Service
description: Découvrez comment configurer le traitement des ressources pour Cloud Service
feature: Output Generation
role: Admin
level: Experienced
exl-id: 219a096f-4087-489f-9b3b-104864817198
source-git-commit: ccaf2ead1a9a24ab822298c6b9ef6866a1c32e8c
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 3%

---

# Configuration de la fonctionnalité de traitement des ressources

Pour configurer la fonction de traitement des ressources, procédez comme suit :

1. Suivez les instructions fournies dans [Remplacements de la configuration](../cs-install-guide/download-install-additional-config-override.md) pour créer le fichier de configuration.

1. Dans le fichier de configuration, fournissez les détails (propriété) suivants :

   | PID | Clé de la propriété | Valeur de la propriété |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `enable.asset.processing.scheduler` | **Valeur par défaut :** « true » |
