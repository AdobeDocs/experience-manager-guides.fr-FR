---
title: Configurer une nouvelle ligne de base pour On-premise
description: Découvrez comment activer ou désactiver la nouvelle ligne de base pour On-premise
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
source-git-commit: 4abf673f636ffd20d087c99b5112d8504929a6ee
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 1%
---
# Configurer une nouvelle ligne de base pour On-Premise

>[!IMPORTANT]
>
> Déployez les configurations système par le biais du code au lieu de les appliquer manuellement dans l’environnement d’exécution.

Les étapes suivantes expliquent comment activer la nouvelle ligne de base dans votre environnement On-Premise.

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et sélectionnez le lot **com.adobe.fmdita.config.ConfigManager**.

1. Activez le paramètre **Activer une ligne de base plus rapide (v2)**. Vous pouvez également effectuer une recherche avec le nom de paramètre exact `enable.baseline.v2`.

1. Sélectionnez **Enregistrer**.

>[!NOTE]
>
>Après avoir activé cette fonctionnalité, vous devez migrer les lignes de base existantes vers la nouvelle ligne de base. Pour obtenir des instructions détaillées et une vidéo de présentation, consultez [Nouvelle ligne de base dans Experience Manager Guides](../user-guide/web-editor-baseline-v2.md).

