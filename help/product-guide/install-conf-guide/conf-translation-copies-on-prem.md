---
title: Configurer l’initialisation de la copie de destination dans le workflow de traduction pour On-Premise
description: Découvrez comment activer ou désactiver l’initialisation de la copie de destination dans le workflow de traduction pour On-Premise
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 1%

---

# Configurer l’initialisation de la copie de destination dans le workflow de traduction pour On-Premise

Les étapes suivantes expliquent comment activer l’initialisation de la copie de destination dans le workflow de traduction pour votre environnement On-Premise.

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et sélectionnez le lot **com.adobe.fmdita.config.ConfigManager**.

1. Activez ou désactivez le paramètre **Initialiser la copie de langue de destination avec le contenu source** ( translation.workflow.propagate.source.content) en fonction de vos besoins. Ce paramètre s’applique uniquement lorsque le workflow de traduction hérité est désactivé.

1. Sélectionnez **Enregistrer**.
