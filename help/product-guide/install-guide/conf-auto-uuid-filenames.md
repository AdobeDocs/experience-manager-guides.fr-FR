---
title: Configurer des noms de fichier automatiques en fonction de l’UUID
description: Découvrez comment configurer des noms de fichier automatiques en fonction de l’UUID
exl-id: 2a599228-6d46-494f-a57a-96c3f30e073a
feature: Filename Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# Configurer des noms de fichier automatiques en fonction de l’UUID {#id205QG070D5Z}

Par défaut, lorsqu’un fichier de rubrique ou de mappage est créé, les auteurs ont également la possibilité de spécifier le nom du fichier. Les auteurs sont libres d’attribuer les noms de fichier en fonction de leurs besoins. Toutefois, cela peut entraîner des incohérences et un large éventail de noms de fichiers est visible dans un vaste système de documentation. En tant qu’administrateur, vous pouvez empêcher vos auteurs d’attribuer des noms de fichiers aux fichiers qu’ils créent dans votre système. Pour chaque nouvelle rubrique ou fichier de mappage, vous pouvez choisir d&#39;attribuer automatiquement des noms de fichiers basés sur UUID.

Pour attribuer automatiquement le nom de fichier basé sur l’UUID à tous les nouveaux fichiers créés dans le système, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot *com.adobe.fmdita.xmleditor.config.XmlEditorConfig* et cliquez dessus.

1. Sélectionnez l’option **Utiliser des noms de fichier système basés sur UUID**.

1. Cliquez sur **Enregistrer**.


>[!NOTE]
>
> Par défaut, cette option est désactivée. Lorsque cette option est activée, les auteurs ne voient pas l’option permettant de spécifier le nom du fichier lors de la création d’une rubrique ou d’un fichier de mappage. Vous pouvez créer une nouvelle rubrique ou un fichier de mappage à partir de l’interface utilisateur d’Assets et de l’éditeur web.

**Rubrique parente :**&#x200B;[&#x200B; Configurer les noms de fichier](conf-file-names.md)
