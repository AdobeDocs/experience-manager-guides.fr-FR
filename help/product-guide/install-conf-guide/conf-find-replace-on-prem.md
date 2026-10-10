---
title: Configuration de la recherche et du remplacement (vue Source) pour On-Premise
description: Découvrez comment configurer Rechercher et remplacer (vue Source) pour On-Premise
feature: Configuration
role: Admin
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 2%
---
# Configuration de la recherche et du remplacement (vue Source) pour On-Premise

Les étapes suivantes expliquent comment activer l&#39;option Rechercher et remplacer (vue Source) dans votre environnement On-Premise.

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et sélectionnez le lot **com.adobe.fmdita.config.ConfigManager**.

1. Activez le paramètre **Activer la recherche et le remplacement de balises** (enable.markup.findreplace).

1. Sélectionnez **Enregistrer**.
