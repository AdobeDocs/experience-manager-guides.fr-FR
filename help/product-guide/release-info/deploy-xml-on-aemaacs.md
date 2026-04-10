---
title: 'Comment ajouter  [!DNL Experience Manager Guides]  à votre  [!DNL Experience Manager as a Cloud Service] '
description: Découvrez comment ajouter  [!DNL AEM Guides]  à votre  [!DNL AEM as a Cloud Service] .
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
feature: Installation
role: Leader
hidefromtoc: true
source-git-commit: 55edd53d1dda7a68352e53b2e59eafd15b677fdd
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# [!DNL Adobe Experience Manager Guides] le déploiement d’as a Cloud Service

Découvrez comment ajouter des [!DNL Experience Manager Guides] à votre environnement [!DNL Experience Manager as a Cloud Service].


>[!NOTE]
>
> À compter de la version 2024.2.0, Experience Manager Guides n’est disponible que sous la forme d’un module complémentaire automatisé pour Experience Manager as a Cloud Service. Si vous utilisez des déploiements manuels pour Experience Manager Guides, supprimez la ligne `<module>dox.installer</module> from file dox/pom.xml` dans la base de code Git de Cloud Manager avant d’activer Experience Manager Guides pour votre programme.

1. Connexion à .

1. Modifiez le programme pour lequel vous souhaitez configurer des [!DNL Experience Manager Guides].

1. Passez à l’onglet **[!UICONTROL Solutions et modules complémentaires]**.

1. Dans le tableau **[!UICONTROL Solutions et modules complémentaires]**, cliquez sur **[!UICONTROL Assets]**.

1. Sélectionnez **[!UICONTROL Guides]** puis sélectionnez **[!UICONTROL Enregistrer]**.

Vous avez correctement configuré votre programme pour l’approvisionnement automatique de la solution Experience Manager Guides.

![Configuration de la solution Experience Manager Guides](assets/addon-configuration.png)

>[!NOTE]
>
>Pour installer [!DNL Experience Manager Guides] dans un environnement sous le programme intégré, vous devez exécuter le pipeline associé à l’environnement. Aucune configuration supplémentaire n’est requise dans la base de code Git de CM pour installer [!DNL Experience Manager Guides].
