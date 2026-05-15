---
title: Native PDF | Configuration des indicateurs JVM pour la publication native de PDF
description: Configuration des indicateurs JVM pour la publication native PDF
feature: Output Generation
role: Admin
level: Experienced
exl-id: d5432913-4b5a-48e7-9467-7f6c6e0adbe4
TQID: https://experienceleague.adobe.com/UvDTutOu-rfQ7tNTMZ6f1dNYJ90dwSGCtTJvWWFm638
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: d6596f3f-92a7-43ec-b444-237db6adad05id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 128
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
