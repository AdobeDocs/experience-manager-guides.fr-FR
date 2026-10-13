---
title: Configuration de la réplication DITA Assets pour les services On-Premise
description: Découvrez comment configurer la réplication des ressources distantes pour les services On-Premise
feature: Output Generation
role: Admin
level: Experienced
exl-id: 49fd9dfe-e1a5-4388-abbd-ec5d45669b45
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 2%
---
# Configuration de la réplication des ressources DITA

Pour configurer la fonction de traitement des ressources, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et sélectionnez le lot *com.adobe.fmdita.config.ConfigManager*.

1. Configurez les `Replicate DITA assets` de paramètres en fonction de vos besoins. Par défaut, le paramètre est activé.


   ![](assets/dita-assets-replication.png){width="350"}


1. Sélectionnez **Enregistrer**.
