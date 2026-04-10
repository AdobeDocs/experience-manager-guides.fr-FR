---
title: Recommandations pour l’optimisation des performances de Cloud Service
description: Découvrez les recommandations relatives à l’optimisation des performances
feature: Performance Optimization
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 0%

---

# Recommandations pour l’optimisation des performances de Cloud Service {#id213BD0JG0XA}

Pour l’optimisation des performances, tenez compte des points suivants :

- Pour optimiser l’expérience de contenu et d’indexation, consultez [Optimiser la recherche et l’indexation de contenu](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=fr) dans la documentation d’AEM.

- Correctif de Xerces Jar lors de l’utilisation de DITA-OT personnalisés pour la publication. Il s’agit d’une configuration obligatoire, selon votre cas d’utilisation. Cette modification est requise uniquement si vous utilisez le DITA-OT personnalisé pour publier la sortie.

  *Configuration requise* : remplacez le fichier Xerces Jar dans votre package DITA-OT personnalisé par celui livré prêt à l’emploi. Le fichier `xercesImpl-2.11.0.jar` prêt à l’emploi par défaut est disponible dans le fichier `/libs/fmdita/dita\_resources/DITA-OT.zip` . Veillez à renommer le fichier `xercesImpl-2.11.0.jar` pour qu’il corresponde à l’ancien fichier Xerces Jar à remplacer. Cette opération peut être effectuée au moment de l’exécution.

  Cette modification réduit le temps de publication et l&#39;utilisation de la mémoire lors de la publication de plans DITA comportant un grand nombre de rubriques.

