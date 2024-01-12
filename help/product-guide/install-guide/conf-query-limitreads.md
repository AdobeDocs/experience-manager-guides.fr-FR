---
title: Configuration du nombre de LimitReads pour une requête
description: Découvrez comment configurer le nombre de limites de lecture pour une requête
exl-id: f6010cc3-5fec-4ec7-adf7-5ad3c9bd8879
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 2%

---

# Configuration du nombre de LimitReads pour une requête {#id231RC0HL0ID}

Pour augmenter le nombre de noeuds qu’une requête peut lire à la fois, procédez comme suit :

1. Ouvrez la page JMX de la console web Adobe Experience Manager.

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/jmx
   ```

1. Recherchez et cliquez sur **QueryEngineSettings**.

1. Modifiez la valeur d’attribut pour la variable **LimitReads** attribut.

1. Cliquez sur **Enregistrer**.


Lorsque vous augmentez cette valeur d’attribut, vous pouvez générer le rapport pour les mappages DITA plus volumineux.

**Rubrique parente :**[ Personnalisation de l’éditeur web](conf-web-editor.md)
