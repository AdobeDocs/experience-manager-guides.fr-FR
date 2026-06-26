---
title: Configuration du nombre de LimitReads pour une requête
description: Découvrez comment configurer le nombre de LimitReads pour une requête
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 53748636-f3d1-4b3b-a772-2730b78741cb
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 2%

---

# Configurer le nombre de LimitReads pour une requête On-Premise

Pour augmenter le nombre de nœuds qu’une requête peut lire à la fois, procédez comme suit :

1. Ouvrez la page JMX de la console web Adobe Experience Manager.

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/jmx
   ```

1. Recherchez et cliquez sur **QueryEngineSettings**.

1. Modifiez la valeur de l’attribut **LimitReads**.

1. Cliquez sur **Enregistrer**.


Lorsque vous augmentez la valeur de cet attribut, vous générez plus facilement le rapport pour les plans DITA plus volumineux.

**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur](customize-overview.md)
