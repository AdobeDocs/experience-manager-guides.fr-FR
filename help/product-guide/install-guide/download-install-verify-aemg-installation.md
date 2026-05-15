---
title: Vérification de l’installation d’AEM Guides
description: Découvrez comment vérifier l’installation d’AEM Guides
exl-id: 8e0afe18-5675-4c7e-b216-6de1a752bd01
feature: Installation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/sniTYknUIyJH0D1moIL3olj3AeBT08kLH52Gba27sqs
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 0%

---

# Vérification de l’installation d’AEM Guides {#id213BD030FBE}

Une fois que vous avez installé AEM Guides, vous devez vérifier si l’installation a réussi ou non. Pour vérifier le processus d’installation, procédez comme suit :

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
> Vous pouvez prendre en compte un certain nombre de recommandations d’optimisation des performances pour améliorer les performances de votre système. Pour plus d’informations, consultez [Recommandations pour l’optimisation des performances](download-install-recommend-perf-optimiz.md#).

**Rubrique parente :**[ Télécharger et installer](download-install.md)
