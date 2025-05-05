---
title: Configuration d’une invite pour l’enregistrement en tant que nouvelle version à la fermeture
description: Découvrez comment configurer une invite pour enregistrer en tant que nouvelle version à la fermeture
exl-id: 1b8c3eaa-a654-4563-9541-18a59b7d306c
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Configuration d’une invite pour l’enregistrement en tant que nouvelle version à la fermeture {#id222HBI00XXA}

Lorsque l’utilisateur tente de fermer un fichier ouvert dans l’éditeur Web à l’aide du bouton **Fermer** de l’onglet du fichier ou de l’option **Fermer** du menu Options, une boîte de dialogue s’affiche si le fichier contient des données non enregistrées ou une version non enregistrée. L’utilisateur est invité à enregistrer le fichier en tant que nouvelle version si la version n’est pas enregistrée.

La case à cocher **Enregistrer comme nouvelle version** n’est pas activée par défaut et vous devez l’activer à partir de configMgr. Effectuez les étapes suivantes pour activer l’option par défaut dans l’éditeur web :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Sélectionnez l&#39;option **Demander une nouvelle version à l&#39;ouverture** .

1. Cliquez sur **Enregistrer**.


Lorsque cette option est sélectionnée, la case à cocher **Enregistrer comme nouvelle version** est sélectionnée par défaut dans la boîte de dialogue.

Pour plus d’informations, reportez-vous à la section *Fermeture de fichier et scénarios d’enregistrement* du guide Utilisation de l’as a Cloud Service Adobe Experience Manager Guides.

**Rubrique parente :**&#x200B;[ Personnaliser l’éditeur web](conf-web-editor.md)
