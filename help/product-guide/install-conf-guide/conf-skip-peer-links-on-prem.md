---
title: Configurer l’omission de liens d’homologue pour la ligne de base V1 dans On-Premise
description: Découvrez comment activer ou désactiver l’omission des liens d’homologue pour la ligne de base V1 dans On-Premise
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 1%

---

# Configuration de l&#39;omission des liens d&#39;homologue pour l&#39;ancienne ligne de base dans On-Premise

Les étapes suivantes expliquent comment activer l&#39;omission des liens d&#39;homologue pour l&#39;ancienne ligne de base dans votre environnement On-Premise.

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et sélectionnez le lot **com.adobe.fmdita.config.ConfigManager**.

1. Activez le paramètre **Ignorer les liens d’homologue pour la ligne de base V1** (guides.baseline.v1.skip.peer.links). Par défaut, ce paramètre est désactivé.

1. Sélectionnez **Enregistrer**.
