---
title: Native PDF | Configuration des indicateurs JVM pour la publication native de PDF
description: Configuration des indicateurs JVM pour la publication native PDF
feature: Output Generation
role: Admin
level: Experienced
exl-id: d5432913-4b5a-48e7-9467-7f6c6e0adbe4
source-git-commit: ccaf2ead1a9a24ab822298c6b9ef6866a1c32e8c
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 1%

---

# Configuration des indicateurs JVM pour la publication native PDF pour On-Premise

La publication native de PDF lance un processus JVM distinct pour générer un PDF. Vous devrez peut-être ajuster les configurations de cette JVM pour prendre en charge différents scénarios. Par exemple, pour exécuter des charges de travail plus importantes, vous devez augmenter la taille maximale du tas disponible pour le processus JVM généré.

Pour configurer les indicateurs JVM de publication PDF native AEM Guides, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et sélectionnez le lot *com.adobe.fmdita.config.ConfigManager*.

1. Mettez à jour la propriété **Options de ligne de commande Java pour le pdf natif** (*native.pdf.java.opts*) pour transmettre des indicateurs JVM standard.



1. Cliquez sur **Enregistrer**.
