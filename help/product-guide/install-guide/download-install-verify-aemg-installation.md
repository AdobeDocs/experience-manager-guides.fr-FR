---
title: Vérification de l’installation AEM Guides
description: Découvrez comment vérifier l’installation des AEM Guides
exl-id: 8e0afe18-5675-4c7e-b216-6de1a752bd01
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---

# Vérification de l’installation AEM Guides {#id213BD030FBE}

Une fois que vous avez installé AEM Guides, vous devez vérifier si l’installation a réussi ou non. Effectuez les étapes suivantes pour vérifier le processus d’installation :

1. Connectez-vous à votre instance AEM et accédez à la page AEM Web Console Bundles. L’URL par défaut pour accéder à la page des lots est la suivante :

   ```http
   http://<server name>:<port>/system/console/bundles
   ```

   Une liste de lots s’affiche.

1. Filtrez la liste des lots en saisissant fmdita dans la zone de texte de filtrage, puis appuyez sur **Entrée**.

   La liste des lots est filtrée pour afficher les lots installés par AEM Guides. Si l’installation a réussi, tous les lots installés auront une **État** de **Actif**.

   Si l’un des lots n’a pas de **Actif** , puis vérifiez les journaux d’AEM pour résoudre le problème d’installation.


>[!IMPORTANT]
>
> Il existe un certain nombre de recommandations d’optimisation des performances que vous pouvez prendre en compte pour améliorer les performances de votre système. Voir [Recommendations pour l’optimisation des performances](download-install-recommend-perf-optimiz.md#) pour plus d’informations.

**Rubrique parente :**[ Télécharger et installer](download-install.md)
