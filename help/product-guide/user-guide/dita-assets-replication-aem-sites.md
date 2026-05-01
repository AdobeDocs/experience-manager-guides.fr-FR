---
title: Gestion de la réplication des ressources sources DITA
description: Découvrez comment effectuer une réplication des ressources sources DITA
feature: Publishing
role: User
exl-id: 71aec782-2cc1-4fd5-b35b-97a603c3dd48
source-git-commit: 12ba7129255257970ddd7a0989149be664ce9803
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%

---

# Gestion de la réplication des ressources sources DITA

Lorsque la sortie générée à partir du contenu DITA est publiée à l&#39;aide de l&#39;option **Publication rapide** ou **Gérer la publication** dans certains environnements de publication, AEM tente également de publier les ressources sources DITA associées, telles que les plans DITA et, dans certains cas, les rubriques DITA. Cela se produit, car AEM traite les ressources DITA comme des dépendances des pages Sites générées.

![](images/quick-publish-site-instance.png){width="350"}

Pour empêcher la réplication involontaire du contenu DITA vers l&#39;environnement de publication et éviter des problèmes de performances, les administrateurs doivent gérer explicitement la réplication des ressources DITA via le gestionnaire de configuration. Cette configuration permet aux administrateurs de contrôler la réplication des types de ressources DITA pris en charge, y compris les plans DITA, les rubriques DITA, les fichiers XML et les fichiers Markdown (.md).

Pour configurer la fonction de réplication des ressources DITA, consultez [Configuration de la réplication des ressources DITA pour Cloud Service](../cs-install-guide/configure-dita-assets-replication.md) ou [Configuration de la réplication des ressources DITA pour On-Premise](../install-guide/configure-dita-asset-replication.md) selon la configuration que vous utilisez
