---
title: Configuration des noms de fichier automatique en fonction de l’UUID
description: Découvrez comment configurer des noms de fichier automatique en fonction de l’UUID
exl-id: 2a599228-6d46-494f-a57a-96c3f30e073a
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
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

1. Recherchez et cliquez sur le bouton *com.adobe.fmdita.xmleditor.config.XmlEditorConfig* du lot.

1. Sélectionnez la variable **Utilisation de noms de fichier système UUID** .

1. Cliquez sur **Enregistrer**.


>[!NOTE]
>
> Par défaut, cette option est désactivée. Lorsque cette option est activée, les auteurs ne voient pas l’option permettant de spécifier le nom de fichier lors de la création d’un fichier de rubrique ou de mappage. Un nouveau fichier de rubrique ou de mappage peut être créé à partir de l’interface utilisateur d’Assets et de l’éditeur web.

**Rubrique parente :**[ Configuration des noms de fichier](conf-file-names.md)
