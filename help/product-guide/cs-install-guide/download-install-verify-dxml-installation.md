---
title: Vérification de l’installation d’AEM Guides
description: Découvrez comment vérifier l’installation d’AEM Guides
exl-id: 4e566c57-a522-4605-bc70-47155f20b429
feature: Installation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/WDiYcOCdCuaJCrGYCupOS0TEk5TV-1q6Zi5z-S7KWLA
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 162
ht-degree: 10%

---

# Vérification de l’installation d’AEM Guides {#id213BD030FBE}

Une fois que vous avez installé AEM Guides, vous devez vérifier si l’installation a réussi ou non. Effectuez les étapes suivantes pour vérifier l’installation :

1. Accédez au Developer Console de votre Cloud Service.

   Pour plus d’informations sur l’accès à Developer Console, voir Accès à [Developer Console](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=fr) dans la documentation d’AEM.

1. Accédez à la liste des lots OSGi dans AEM.

   Pour plus d’informations sur l’accès aux lots, voir [Lots](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=en#bundles) dans la documentation AEM.

1. Recherchez fmdita dans la liste des lots et vérifiez son statut.

   Le statut doit afficher *Actif* pour les lots déployés avec succès. Si l’un des lots n’a pas le statut Actif , vérifiez les journaux AEM pour résoudre le problème d’installation.


**Rubrique parente :**[ Télécharger et installer](download-install.md)
