---
title: Recommandations pour l’optimisation des performances de Cloud Service
description: Découvrez les recommandations relatives à l’optimisation des performances
feature: Performance Optimization
role: Admin
level: Experienced
exl-id: 6c9684d4-180f-4ccb-bfd6-6c82a8a7b720
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: baa3aa24-d162-4a57-b73a-d27341145083
    internal-label: Performance optimization
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 5%
---
# Recommandations pour l’optimisation des performances de Cloud Service {#id213BD0JG0XA}

Pour l’optimisation des performances, tenez compte des points suivants :

- Pour optimiser l’expérience de contenu et d’indexation, consultez [Optimiser la recherche et l’indexation de contenu](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=fr) dans la documentation d’AEM.

- Correctif de Xerces Jar lors de l’utilisation de DITA-OT personnalisés pour la publication. Il s’agit d’une configuration obligatoire, selon votre cas d’utilisation. Cette modification est requise uniquement si vous utilisez le DITA-OT personnalisé pour publier la sortie.

  *Configuration requise* : remplacez le fichier Xerces Jar dans votre package DITA-OT personnalisé par celui livré prêt à l’emploi. Le fichier `xercesImpl-2.11.0.jar` prêt à l’emploi par défaut est disponible dans le fichier `/libs/fmdita/dita\_resources/DITA-OT.zip` . Veillez à renommer le fichier `xercesImpl-2.11.0.jar` pour qu’il corresponde à l’ancien fichier Xerces Jar à remplacer. Cette opération peut être effectuée au moment de l’exécution.

  Cette modification réduit le temps de publication et l&#39;utilisation de la mémoire lors de la publication de plans DITA comportant un grand nombre de rubriques.
