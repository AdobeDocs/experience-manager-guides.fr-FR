---
title: Vérification de l’installation d’AEM Guides
description: Découvrez comment vérifier l’installation d’AEM Guides
exl-id: 4e566c57-a522-4605-bc70-47155f20b429
feature: Installation
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

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
