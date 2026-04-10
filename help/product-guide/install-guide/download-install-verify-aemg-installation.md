---
title: Vérification de l’installation d’AEM Guides
description: Découvrez comment vérifier l’installation d’AEM Guides
exl-id: 8e0afe18-5675-4c7e-b216-6de1a752bd01
feature: Installation
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '165'
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
