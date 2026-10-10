---
title: Installation de Adobe Experience Manager
description: Découvrez comment installer Adobe Experience Manager
feature: Introduction, Installation
role: Admin
level: Experienced
exl-id: d72b007c-9f0a-41be-bca2-2d6b54c30de1
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
source-wordcount: '213'
ht-degree: 5%
---
# Installation de Adobe Experience Manager {#id213BCI020E8}

AEM Guides est un plug-in qui s’installe sur Adobe Experience Manager. L’installation d’AEM nécessite une compréhension de certains concepts de base d’AEM et des scénarios de déploiement recommandés. Les liens suivants vous aideront à prendre en main l’installation d’AEM :

- [Concepts de base d’AEM](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/deploy.html#BasicConcepts)

- [Déploiements AEM recommandés](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/recommended-deploys.html)

>[!IMPORTANT]
>
> Si vous utilisez Java 11 avec AEM 6.5.x, il se peut que vous rencontriez un problème : *JDK 11 entraîne des`NoClassDefFoundError`*. Pour résoudre ce problème, reportez-vous à l’article [JDK 11 provoque l’erreur NoClassDefFoundError \| AEM 6.5](https://helpx.adobe.com/experience-manager/kb/jdk-11-causes-noclassdeffounderror---aem-6-5.html).

Une fois que vous avez identifié la stratégie de déploiement qui fonctionne le mieux pour votre organisation, effectuez le processus d’installation comme décrit dans la section *[Prise en main](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/deploy.html?lang=frl#GettingStarted)* de la documentation AEM.

Si vous prévoyez de mettre à niveau votre instance AEM, vous devez suivre la séquence donnée :

1. Désinstallez AEM Guides.
1. Mettez à niveau votre instance AEM.
1. Réinstallez AEM Guides.

>[!IMPORTANT]
>
> Vous pouvez prendre en compte un certain nombre de recommandations d’optimisation des performances pour améliorer les performances de votre système. Pour plus d’informations, consultez [Recommandations pour l’optimisation des performances](./perf-optimization-on-prem.md).
