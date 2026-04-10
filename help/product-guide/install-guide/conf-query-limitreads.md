---
title: Configuration du nombre de LimitReads pour une requête
description: Découvrez comment configurer le nombre de LimitReads pour une requête
exl-id: f6010cc3-5fec-4ec7-adf7-5ad3c9bd8879
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 2%

---

# Configuration du nombre de LimitReads pour une requête {#id231RC0HL0ID}

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

**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur web](conf-web-editor.md)
