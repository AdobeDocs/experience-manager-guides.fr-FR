---
title: Configuration du nombre de LimitReads pour une requête
description: Découvrez comment configurer le nombre de LimitReads pour une requête
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 1%

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

**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur web](customize-overview.md)
