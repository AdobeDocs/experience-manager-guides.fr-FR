---
title: PDF natif | Configuration des indicateurs JVM pour la publication native de PDF
description: Configuration des indicateurs JVM pour la publication native de PDF
exl-id: d5432913-4b5a-48e7-9467-7f6c6e0adbe4
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 1%

---

# Configuration des indicateurs JVM pour la publication native de PDF

La publication d’un PDF natif lance un processus JVM distinct pour générer un PDF. Vous devrez peut-être ajuster les configurations de cette JVM pour prendre en charge différents scénarios. Par exemple, pour exécuter des charges de travail plus volumineuses, vous devez augmenter la taille maximale du tas disponible pour le processus JVM engendré.

Effectuez les étapes suivantes pour configurer les indicateurs JVM de publication d’AEM Guides Native PDF :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et sélectionnez le lot *com.adobe.fmdita.config.ConfigManager*.

1. Mettez à jour la propriété **Java Command line options for native pdf** (*native.pdf.java.opts*) pour transmettre des indicateurs JVM standard.



1. Cliquez sur **Enregistrer**.
