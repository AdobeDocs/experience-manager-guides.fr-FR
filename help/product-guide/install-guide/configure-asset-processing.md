---
title: Configuration du traitement des ressources pour les services On-Premise
description: Configuration du traitement des ressources pour les services On-Premise
feature: Output Generation
role: Admin
level: Experienced
exl-id: 9d771bba-aa90-4726-a75f-1cb7b804a192
TQID: https://experienceleague.adobe.com/GDyCE4ziLqhXXJTgFuv-uVf-2W86-OSNeMCMWYT35wg
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 68
ht-degree: 2%

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
