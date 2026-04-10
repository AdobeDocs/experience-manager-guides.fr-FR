---
title: Générer automatiquement des identifiants d’élément
description: Découvrez comment générer automatiquement des identifiants d’élément.
exl-id: 8d09ab89-4be5-49f1-9831-9f01c92dc472
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Générer automatiquement des identifiants d’élément {#id20CIL40016I}

AEM Guides génère un identifiant de document pour tout nouveau document que vous créez. Par exemple, lorsque vous créez un plan DITA, un identifiant comme `map.ditamap_random_digits` est attribué à l&#39;identifiant du plan. Vous pouvez également définir des éléments sur lesquels un identifiant est automatiquement généré et attribué.

AEM Guides fournit des paramètres de configuration simples dans lesquels vous devez définir les éléments sur lesquels un identifiant est généré automatiquement et un motif pour l’identifiant. Par défaut, certains éléments tels que `section`, `table`, `ul` et `ol` sont configurés pour la génération automatique d’identifiants. Vous pouvez ajouter d’autres éléments à cette liste. Ainsi, chaque fois que ces éléments sont insérés dans un document, AEM Guides génère et attribue un identifiant en fonction du modèle donné

Pour configurer les éléments avec un identifiant généré automatiquement, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** et cliquez dessus.

1. Dans les paramètres *XmlEditorConfig*, spécifiez un ou plusieurs éléments dans le champ **Générer automatiquement des identifiants pour les balises d’élément**.

   >[!NOTE]
   >
   > Les balises d&#39;élément sont les noms d&#39;élément DITA tels que `body`, `title`, `codeblock`, etc. Pour spécifier plusieurs éléments, séparez les noms des éléments par une virgule.

1. Dans le champ **Motif pour la génération des identifiants** spécifiez un motif pour générer un identifiant.

   La valeur par défaut de ce champ est définie sur `${elementName}_${id}`. La valeur `${elementName}` est remplacée par le nom de l’élément. La variable `${id}` génère un numéro séquentiel pour l’élément. Par exemple, si vous attribuez à l’élément de paragraphe des identifiants générés automatiquement, le premier paragraphe de la rubrique ou du document obtient un identifiant du type p\_1, le paragraphe suivant obtient p\_2, etc. Cependant, dans un autre document, le processus de génération des identifiants redémarre. Cela signifie que dans un autre document, des identifiants tels que p\_1 et p\_2 peuvent être affectés aux éléments de paragraphe.

   Si votre document contient déjà des identifiants selon le modèle spécifié, le processus de génération automatique n’affecte pas ces identifiants aux nouveaux éléments.

1. Cliquez sur **Enregistrer**.


**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
