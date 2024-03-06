---
title: Comment ajouter [!DNL Experience Manager Guides] à votre [!DNL Experience Manager as a Cloud Service] environnement
description: Découvrez comment ajouter [!DNL AEM Guides] à votre [!DNL AEM as a Cloud Service] environnement
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
feature: Installation
role: Leader
source-git-commit: 1b25f1df67fa2442ab79830dc2ac5a6eabd0394c
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# [!DNL Adobe Experience Manager Guides] déploiement as a Cloud Service

Découvrez comment ajouter [!DNL Experience Manager Guides] à votre [!DNL Experience Manager as a Cloud Service] environnement.


>[!NOTE]
>
> À compter de la version 2024.2.0, les Guides du Experience Manager ne seront disponibles qu’en tant que module complémentaire automatisé pour Experience Manager as a Cloud Service. Si vous utilisez des déploiements manuels pour les guides Experience Manager, supprimez la ligne. `<module>dox.installer</module> from file dox/pom.xml` dans votre cloud, gérez le code git avant d’activer les guides du Experience Manager pour votre programme.

1. Connexion à [!UICONTROL Cloud Manager].

1. Éditez le programme pour lequel vous souhaitez configurer [!DNL Experience Manager Guides].

1. Basculer vers **[!UICONTROL Solutions et modules complémentaires]** .

1. Dans le **[!UICONTROL Solutions et modules complémentaires]** tableau, cliquez sur **[!UICONTROL Ressources]**.

1. Sélectionner **[!UICONTROL Guides]** et sélectionnez **[!UICONTROL Enregistrer]**.

Vous avez correctement configuré votre programme pour la mise en service automatique de la solution de guides du Experience Manager.

![Configuration de la solution de guides du Experience Manager](assets/addon-configuration.png)

>[!NOTE]
>
>Pour installer [!DNL Experience Manager Guides] dans n’importe quel environnement du programme intégré, vous devez exécuter le pipeline associé à l’environnement. Aucune configuration supplémentaire n’est requise dans votre base de code Git CM pour l’installation. [!DNL Experience Manager Guides].
