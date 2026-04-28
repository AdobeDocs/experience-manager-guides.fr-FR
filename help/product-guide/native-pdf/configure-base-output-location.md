---
title: Configurer l’emplacement de sortie de base pour la publication de sortie pour les services On-Premise
description: Configurer l’emplacement de sortie de base pour la publication de sortie pour les services On-Premise
feature: Output Generation
role: Admin
level: Experienced
exl-id: ae1d805a-7b79-4b76-8be2-a19c5552530c
source-git-commit: ccaf2ead1a9a24ab822298c6b9ef6866a1c32e8c
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 1%

---

# Configuration de l’emplacement de sortie de base pour la publication de la sortie pour les services On-Premise

Pour configurer l’emplacement de sortie de base, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et sélectionnez le lot *com.adobe.fmdita.config.ConfigManager*.

1. Mettez à jour la propriété **Emplacement de sortie de base** pour spécifier le chemin par défaut dans le référentiel AEM où le PDF sera enregistré après publication. De plus, si un chemin non valide est saisi, il revient automatiquement au chemin par défaut : /content/dam/fmdita-output.

1. Cliquez sur **Enregistrer**.
