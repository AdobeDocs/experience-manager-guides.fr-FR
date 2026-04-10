---
title: Configuration du traitement des ressources pour les services On-Premise
description: Configuration du traitement des ressources pour les services On-Premise
feature: Output Generation
role: Admin
level: Experienced
exl-id: 9d771bba-aa90-4726-a75f-1cb7b804a192
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '66'
ht-degree: 3%

---

# Configuration de la fonctionnalité de traitement des ressources

Pour configurer la fonction de traitement des ressources, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et sélectionnez le lot *com.adobe.fmdita.config.ConfigManager*.

1. Configurez les `Enable Guides asset processing scheduled job` de paramètres en fonction de vos besoins. Par défaut, le paramètre est activé.

1. Sélectionnez **Enregistrer**.
