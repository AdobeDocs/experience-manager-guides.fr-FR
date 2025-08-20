---
title: Configurer l’emplacement de sortie de base pour la publication de sortie pour les services On-Premise
description: Configurer l’emplacement de sortie de base pour la publication de sortie pour les services On-Premise
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: ab6f1f09de2ef758d7f05ba0a49194ac9f387dea
workflow-type: tm+mt
source-wordcount: '108'
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


