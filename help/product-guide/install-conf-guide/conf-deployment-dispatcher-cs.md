---
title: Déploiement et configuration du Dispatcher
description: Découvrez le déploiement et la configuration du Dispatcher dans Experience Manager Guides as a Cloud Service
feature: Introduction, Installation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 4%

---

# Déploiement et configuration du Dispatcher

Cet article fournit des informations sur le déploiement de Experience Manager Guides as a Cloud Service et la configuration du Dispatcher.

## Déploiement de Experience Manager Guides as a Cloud Service

Vous pouvez commencer par déployer Experience Manager Guides via le Cloud Manager. Pour déployer le module, suivez les instructions mentionnées dans [Déploiement d’AEM Guides as a Cloud Service](../release-info/deploy-xml-on-aemaacs.md).

>[!NOTE]
>
> À compter de la version 2024.2.0, Experience Manager Guides n’est disponible que sous la forme d’un module complémentaire automatisé pour Experience Manager as a Cloud Service. Si vous utilisez la version de décembre 2023 ou une version antérieure, vous pouvez télécharger l’Adobe Experience Manager Guides à partir du référentiel GitHub et l’installer. Si vous utilisez des déploiements manuels pour Experience Manager Guides, supprimez la ligne `<module>dox.installer</module> from file dox/pom.xml` dans la base de code Git de Cloud Manager avant d’activer Experience Manager Guides pour votre programme.

Pour déployer le module Experience Manager Guides, procédez comme suit :

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


## Configuration du Dispatcher

Dispatcher est l’outil de mise en cache et/ou d’équilibrage de charge d’Adobe Experience Manager. Pour plus d&#39;informations, consultez la section [Dispatcher en mode cloud](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/content-delivery/disp-overview.html?lang=fr).

1. Pour migrer la configuration de Dispatcher d’AMS vers Cloud Service, voir [Migration de la configuration de Dispatcher d’AMS vers AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/content-delivery/ams-aem.html?lang=fr).
1. Pour plus d’informations sur la configuration du Dispatcher, voir [Configuration de Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=fr).

>[!NOTE]
>
> AEM as a Cloud Service ne prend pas en charge le dispatcher pour l’instance de création.
