---
title: Comment ajouter  [!DNL Experience Manager Guides] à votre environnement  [!DNL Experience Manager as a Cloud Service]
description: Découvrez comment ajouter  [!DNL AEM Guides] à votre  [!DNL AEM as a Cloud Service] environnement
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
feature: Installation
role: Leader
source-git-commit: 1b25f1df67fa2442ab79830dc2ac5a6eabd0394c
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# [!DNL Adobe Experience Manager Guides] Déploiement as a Cloud Service

Découvrez comment ajouter [!DNL Experience Manager Guides] à votre environnement [!DNL Experience Manager as a Cloud Service].


>[!NOTE]
>
> À compter de la version 2024.2.0, Experience Manager Guides n’est disponible qu’en tant que module complémentaire automatisé as a Cloud Service Experience Manager. Si vous utilisez des déploiements manuels pour Experience Manager Guides, supprimez la ligne `<module>dox.installer</module> from file dox/pom.xml` de votre base de code git de gestion du cloud avant d’activer Experience Manager Guides pour votre programme.

1. Connectez-vous à [!UICONTROL Cloud Manager].

1. Modifiez le programme pour lequel vous souhaitez configurer [!DNL Experience Manager Guides].

1. Passez à l’onglet **[!UICONTROL Solutions et modules complémentaires]** .

1. Dans la table **[!UICONTROL Solutions and Add-ons]**, cliquez sur **[!UICONTROL Assets]**.

1. Sélectionnez **[!UICONTROL Guides]** et sélectionnez **[!UICONTROL Enregistrer]**.

Vous avez correctement configuré votre programme pour la mise en service automatique de la solution Experience Manager Guides.

![Configuration de la solution Experience Manager Guides](assets/addon-configuration.png)

>[!NOTE]
>
>Pour installer [!DNL Experience Manager Guides] sur un environnement sous le programme intégré, vous devez exécuter le pipeline associé à l’environnement. Aucune configuration supplémentaire n’est requise dans votre base de code Git CM pour l’installation de [!DNL Experience Manager Guides].
