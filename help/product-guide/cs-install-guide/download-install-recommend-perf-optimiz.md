---
title: Recommandations pour l’optimisation des performances
description: Découvrez les recommandations relatives à l’optimisation des performances
exl-id: 92ac1f81-2f51-44b0-82c3-56b39e8f3027
feature: Performance Optimization
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---

# Recommandations pour l’optimisation des performances {#id213BD0JG0XA}

Pour l’optimisation des performances, tenez compte des points suivants :

- Pour optimiser l’expérience de contenu et d’indexation, consultez [Optimiser la recherche et l’indexation de contenu](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=fr) dans la documentation d’AEM.

- Correctif de Xerces Jar lors de l’utilisation de DITA-OT personnalisés pour la publication. Il s’agit d’une configuration obligatoire, selon votre cas d’utilisation. Cette modification est requise uniquement si vous utilisez le DITA-OT personnalisé pour publier la sortie.

  *Configuration requise* : remplacez le fichier Xerces Jar dans votre package DITA-OT personnalisé par celui livré prêt à l’emploi. Le fichier xercesImpl-2.11.0.jar par défaut prêt à l’emploi est disponible dans le fichier /libs/fmdita/dita\_resources/DITA-OT.zip . Veillez à renommer le fichier xercesImpl-2.11.0.jar pour qu’il corresponde à l’ancien fichier Xerces Jar à remplacer. Cette opération peut être effectuée au moment de l’exécution.

  Cette modification réduit le temps de publication et l&#39;utilisation de la mémoire lors de la publication de plans DITA comportant un grand nombre de rubriques.


**Rubrique parente :**[ Télécharger et installer](download-install.md)
