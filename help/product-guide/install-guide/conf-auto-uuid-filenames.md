---
title: Configuration des noms de fichier automatique en fonction de l’UUID
description: Découvrez comment configurer des noms de fichier automatique en fonction de l’UUID
exl-id: 2a599228-6d46-494f-a57a-96c3f30e073a
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# Configuration des noms de fichier automatique en fonction de l’UUID {#id205QG070D5Z}

Par défaut, lorsqu’un fichier de rubrique ou de mappage est créé, les auteurs disposent d’une option pour spécifier également le nom du fichier. Les auteurs sont libres d’attribuer les noms de fichier en fonction de leurs besoins. Cela peut toutefois entraîner des incohérences et un large éventail de noms de fichiers est visible dans un système de documentation volumineux. En tant qu’administrateur, vous pouvez empêcher vos auteurs d’affecter des noms de fichier aux fichiers qu’ils créent dans votre système. Pour chaque nouveau fichier de rubrique ou de mappage, vous pouvez choisir d’attribuer automatiquement des noms de fichier UID.

Effectuez les étapes suivantes pour attribuer automatiquement le nom de fichier basé sur l’UUID à tous les nouveaux fichiers créés dans le système :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot *com.adobe.fmdita.xmleditor.config.XmlEditorConfig*.

1. Sélectionnez l’option **Utiliser des noms de fichiers système basés sur UUID** .

1. Cliquez sur **Enregistrer**.


>[!NOTE]
>
> Par défaut, cette option est désactivée. Lorsque cette option est activée, les auteurs ne voient pas l’option permettant de spécifier le nom de fichier lors de la création d’un fichier de rubrique ou de mappage. Un nouveau fichier de rubrique ou de mappage peut être créé à partir de l’interface utilisateur d’Assets et de l’éditeur web.

**Rubrique parente :**[ Configurer les noms de fichier](conf-file-names.md)
