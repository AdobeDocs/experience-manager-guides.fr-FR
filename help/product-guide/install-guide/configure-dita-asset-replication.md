---
title: Configuration de la réplication DITA Assets pour les services On-Premise
description: Découvrez comment configurer la réplication des ressources distantes pour les services On-Premise
feature: Output Generation
role: Admin
level: Experienced
exl-id: 49fd9dfe-e1a5-4388-abbd-ec5d45669b45
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '71'
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


   ![](assets/dita-assets-replication.png){width="350" align="left"}


1. Sélectionnez **Enregistrer**.
