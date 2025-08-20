---
title: PDF natif | Configuration de l’emplacement de sortie de base pour la publication de PDF pour les services cloud
description: Configuration de l’emplacement de sortie de base pour la publication de PDF pour les services cloud
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: ab6f1f09de2ef758d7f05ba0a49194ac9f387dea
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 2%

---

# Configuration de l’emplacement de sortie de base pour la publication de sortie pour les services cloud

Pour configurer l’emplacement de sortie de base, procédez comme suit :

1. Suivez les instructions fournies dans [Remplacements de la configuration](../cs-install-guide/download-install-additional-config-override.md) pour créer le fichier de configuration.

1. Dans le fichier de configuration, fournissez les détails (propriété) suivants pour configurer l’emplacement de sortie de base :

   | PID | Clé de la propriété | Valeur de la propriété |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `base.output.path` | **Valeur par défaut :** « /content/dam/fmdita-output » |
