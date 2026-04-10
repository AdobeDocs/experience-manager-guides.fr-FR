---
title: Installation de Adobe Experience Manager
description: Découvrez comment installer Adobe Experience Manager
feature: Introduction, Installation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---

# Installation de Adobe Experience Manager {#id213BCI020E8}

AEM Guides est un plug-in qui s’installe sur Adobe Experience Manager. L’installation d’AEM nécessite une compréhension de certains concepts de base d’AEM et des scénarios de déploiement recommandés. Les liens suivants vous aideront à prendre en main l’installation d’AEM :

- [ Concepts de base d’AEM ](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/deploy.html#BasicConcepts)

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
