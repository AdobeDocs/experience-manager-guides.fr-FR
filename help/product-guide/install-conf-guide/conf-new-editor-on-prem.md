---
title: Configurer un nouvel éditeur
description: Découvrez comment activer ou désactiver le nouvel éditeur
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 2%

---

# Configuration d’un nouvel éditeur pour On-Premise

>[!IMPORTANT]
>
> Déployez les configurations système par le biais du code au lieu de les appliquer manuellement dans l’environnement d’exécution.

Les étapes suivantes expliquent comment activer le nouvel éditeur dans votre environnement On-Premise.

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et sélectionnez le lot **com.adobe.fmdita.config.ConfigManager**.

1. Activez le paramètre **Activer l’éditeur 2.0** (`enable.markup.editor`).

1. Sélectionnez **Enregistrer**.

