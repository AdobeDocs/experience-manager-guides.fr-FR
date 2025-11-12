---
title: Configuration du traitement des ressources pour les services On-Premise
description: Configuration du traitement des ressources pour les services On-Premise
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: e1b332b100cc8e3937557e4617d66352c1a0dc3c
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
