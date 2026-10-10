---
title: Déploiement et configuration du Dispatcher
description: Découvrez le déploiement et la configuration du Dispatcher dans Experience Manager Guides as a Cloud Service
feature: Introduction, Installation
role: Admin
level: Experienced
exl-id: 657a42be-36e7-4657-83d5-e866f8e55f09
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: c5fd2af0-6cbb-4746-ab0d-40ecb093af12
    internal-label: Introduction
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 6%
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

Dispatcher est l’outil de mise en cache et/ou d’équilibrage de charge d’Adobe Experience Manager. Pour plus d&#39;informations, consultez la section [Dispatcher en mode cloud](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/content-delivery/disp-overview.html?lang=en).

1. Pour migrer la configuration de Dispatcher d’AMS vers Cloud Service, voir [Migration de la configuration de Dispatcher d’AMS vers AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/content-delivery/ams-aem.html?lang=en).
1. Pour plus d’informations sur la configuration du Dispatcher, voir [Configuration de Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=fr).

>[!NOTE]
>
> AEM as a Cloud Service ne prend pas en charge le dispatcher pour l’instance de création.
