---
title: Recommandations pour l’optimisation des performances
description: Découvrez les recommandations relatives à l’optimisation des performances
exl-id: 92ac1f81-2f51-44b0-82c3-56b39e8f3027
feature: Performance Optimization
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/vh0hogZNMjKrCL12WdKVuwF2qXdzy64KxIhhB-K4esA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: b1210526-416b-4ef6-bcc0-1692e99f30e9
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
subfeature_v2:
  - id: baa3aa24-d162-4a57-b73a-d27341145083
  - id: c8841798-1a28-4264-a46a-984860f8e6f6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 162
ht-degree: 5%

---

# Recommandations pour l’optimisation des performances {#id213BD0JG0XA}

Pour l’optimisation des performances, tenez compte des points suivants :

- Pour optimiser l’expérience de contenu et d’indexation, consultez [Optimiser la recherche et l’indexation de contenu](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=fr) dans la documentation d’AEM.

- Correctif de Xerces Jar lors de l’utilisation de DITA-OT personnalisés pour la publication. Il s’agit d’une configuration obligatoire, selon votre cas d’utilisation. Cette modification est requise uniquement si vous utilisez le DITA-OT personnalisé pour publier la sortie.

  *Configuration requise* : remplacez le fichier Xerces Jar dans votre package DITA-OT personnalisé par celui livré prêt à l’emploi. Le fichier xercesImpl-2.11.0.jar par défaut prêt à l’emploi est disponible dans le fichier /libs/fmdita/dita\_resources/DITA-OT.zip . Veillez à renommer le fichier xercesImpl-2.11.0.jar pour qu’il corresponde à l’ancien fichier Xerces Jar à remplacer. Cette opération peut être effectuée au moment de l’exécution.

  Cette modification réduit le temps de publication et l&#39;utilisation de la mémoire lors de la publication de plans DITA comportant un grand nombre de rubriques.


**Rubrique parente :**&#x200B;[&#x200B; Télécharger et installer](download-install.md)
