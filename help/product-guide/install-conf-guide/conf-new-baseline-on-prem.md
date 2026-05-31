---
title: Configurer une nouvelle ligne de base pour On-premise
description: Découvrez comment activer ou désactiver la nouvelle ligne de base pour On-premise
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '125'
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
>Après avoir activé cette fonctionnalité, vous devez migrer les lignes de base existantes vers la nouvelle ligne de base. Pour obtenir des instructions détaillées et une vidéo de présentation, consultez [Nouvelle ligne de base (Beta) dans Experience Manager Guides](../user-guide/web-editor-baseline-v2.md).

