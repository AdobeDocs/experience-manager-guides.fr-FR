---
title: Génération automatique des identifiants d’élément
description: Découvrez comment générer automatiquement des identifiants d’élément
exl-id: 8d09ab89-4be5-49f1-9831-9f01c92dc472
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Génération automatique des identifiants d’élément {#id20CIL40016I}

AEM Guides génère un ID de document pour tout nouveau document que vous créez. Par exemple, lorsque vous créez un mappage DITA, un ID du type `map.ditamap_random_digits` est affecté à l’ID du mappage. Vous pouvez également définir des éléments sur lesquels un ID est automatiquement généré et affecté.

AEM Guides fournit des paramètres de configuration simples dans lesquels vous devez définir les éléments sur lesquels un ID est généré automatiquement et un modèle pour l’ID. Par défaut, certains éléments tels que `section`, `table`, `ul`, `ol` sont configurés pour la génération automatique de l’ID. Vous pouvez ajouter d’autres éléments à cette liste de sorte qu’à chaque fois que ces éléments sont insérés dans un document, AEM Guides génère et attribue un identifiant en fonction du modèle donné.

Effectuez les étapes suivantes pour configurer les éléments avec un identifiant généré automatiquement :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Dans les paramètres *XmlEditorConfig* , spécifiez un ou plusieurs éléments dans le champ **Auto Generate IDs for Element Tags** .

   >[!NOTE]
   >
   > Les balises d’élément sont les noms d’élément DITA tels que `body`, `title`, `codeblock`, etc. Pour spécifier plusieurs éléments, séparez les noms des éléments par une virgule.

1. Dans le champ **Modèle pour la génération des ID** , spécifiez un modèle pour générer un ID.

   La valeur par défaut de ce champ est définie sur `${elementName}_${id}`. La valeur `${elementName}` est remplacée par le nom de l’élément . La variable `${id}` génère un numéro séquentiel pour l’élément . Par exemple, si vous attribuez à l’élément de paragraphe des identifiants générés automatiquement, le premier paragraphe de la rubrique ou du document reçoit un identifiant comme p\_1, le paragraphe suivant reçoit p\_2, etc. Cependant, dans un autre document, le processus de génération des identifiants redémarre. Cela signifie que dans un autre document, des identifiants comme p\_1 et p\_2 peuvent être affectés aux éléments de paragraphe.

   Si votre document contient déjà des identifiants dans le modèle spécifié, le processus de génération automatique n’affecte pas ces identifiants aux nouveaux éléments.

1. Cliquez sur **Enregistrer**.


**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur web](conf-web-editor.md)
