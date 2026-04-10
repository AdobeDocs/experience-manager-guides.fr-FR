---
title: Vérification de l’installation d’AEM Guides
description: Découvrez comment vérifier l’installation d’AEM Guides
feature: Installation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Vérification de l’installation d’AEM Guides {#id213BD030FBE}

Une fois que vous avez installé AEM Guides, vous devez vérifier si l’installation a réussi ou non.

Les onglets suivants fournissent des instructions pour vérifier l’installation d’AEM Guides en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB Tab]

Effectuez les étapes suivantes pour vérifier l’installation :

1. Accédez au Developer Console de votre Cloud Service.

   Pour plus d’informations sur l’accès à Developer Console, voir Accès à [Developer Console](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=fr) dans la documentation d’AEM.

1. Accédez à la liste des lots OSGi dans AEM.

   Pour plus d’informations sur l’accès aux lots, voir [Lots](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=en#bundles) dans la documentation AEM.

1. Recherchez fmdita dans la liste des lots et vérifiez son statut.

   Le statut doit afficher *Actif* pour les lots déployés avec succès. Si l’un des lots n’a pas le statut Actif , vérifiez les journaux AEM pour résoudre le problème d’installation.

>[!TAB  On-Premise ]

Effectuez les étapes suivantes pour vérifier l’installation :

1. Connectez-vous à votre instance AEM et accédez à la page Bundles de la console web AEM . L’URL par défaut pour accéder à la page des lots est :

   ```http
   http://<server name>:<port>/system/console/bundles
   ```

   Une liste de lots s’affiche.

1. Filtrez la liste des lots en entrant fmdita dans la zone de texte de filtrage et appuyez sur **Entrée**.

   La liste des lots est filtrée afin d’afficher les lots installés par AEM Guides. Si l’installation a réussi, tous les lots installés auront un **Statut** de **Actif**.

   Si l’un des lots n’a pas le statut **Actif**, vérifiez les journaux AEM pour résoudre le problème d’installation.


>[!IMPORTANT]
>
> Vous pouvez prendre en compte un certain nombre de recommandations d’optimisation des performances pour améliorer les performances de votre système. Pour plus d’informations, consultez [Recommandations pour l’optimisation des performances](perf-optimization-on-prem.md#).

>[!ENDTABS]


