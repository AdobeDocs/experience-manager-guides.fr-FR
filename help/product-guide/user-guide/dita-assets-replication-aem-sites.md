---
title: Gestion de la réplication des ressources sources DITA
description: Découvrez comment effectuer une réplication des ressources sources DITA
feature: Publishing
role: User
exl-id: 71aec782-2cc1-4fd5-b35b-97a603c3dd48
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%
---
# Gestion de la réplication des ressources sources DITA

Lorsque la sortie générée à partir du contenu DITA est publiée à l&#39;aide de l&#39;option **Publication rapide** ou **Gérer la publication** dans certains environnements de publication, AEM tente également de publier les ressources sources DITA associées, telles que les plans DITA et, dans certains cas, les rubriques DITA. Cela se produit, car AEM traite les ressources DITA comme des dépendances des pages Sites générées.

![](images/quick-publish-site-instance.png){width="350"}

Pour empêcher la réplication involontaire du contenu DITA vers l&#39;environnement de publication et éviter des problèmes de performances, les administrateurs doivent gérer explicitement la réplication des ressources DITA via le gestionnaire de configuration. Cette configuration permet aux administrateurs de contrôler la réplication des types de ressources DITA pris en charge, y compris les plans DITA, les rubriques DITA, les fichiers XML et les fichiers Markdown (.md).

Pour configurer la fonction de réplication des ressources DITA, consultez [Configuration de la réplication des ressources DITA pour Cloud Service](../cs-install-guide/configure-dita-assets-replication.md) ou [Configuration de la réplication des ressources DITA pour On-Premise](../install-guide/configure-dita-asset-replication.md) selon la configuration que vous utilisez
