---
title: Génération automatique des identifiants d’élément
description: Découvrez comment générer automatiquement des identifiants d’élément
exl-id: a651db7f-228e-4de5-b569-3f1b4f86c418
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 1%

---

# Génération automatique des identifiants d’élément {#id20CIL40016I}

AEM Guides génère un ID de document pour tout nouveau document que vous créez. Par exemple, lorsque vous créez un mappage DITA, un identifiant comme `map.ditamap_random_digits` est affectée à l’identifiant de la carte. Vous pouvez également définir des éléments sur lesquels un ID est automatiquement généré et affecté.

AEM Guides fournit des paramètres de configuration simples dans lesquels vous devez définir les éléments sur lesquels un ID est généré automatiquement et un modèle pour l’ID. Par défaut, certains éléments comme `section`, `table`, `ul`, `ol`, sont configurés pour la génération automatique de l’identifiant. Vous pouvez ajouter d’autres éléments à cette liste de sorte qu’à chaque fois que ces éléments sont insérés dans un document, AEM Guides génère et attribue un identifiant en fonction du modèle donné.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer les identifiants d’élément générés automatiquement :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.classes` | Spécifiez une liste d’éléments séparés par des virgules. <br> **Valeur par défaut**: `"topic, section, table, simpletable, fig, image, ul, ol"` |

Pour configurer un modèle d’identifiant généré automatiquement, créez un fichier de configuration avec les propriétés suivantes :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.pattern` | La valeur par défaut de ce champ est définie sur `${elementName}_${id}`. La variable `${elementName}` est remplacée par le nom de l’élément . La variable `${id}` génère un nombre séquentiel pour l’élément. Par exemple, si vous attribuez à l’élément de paragraphe des identifiants générés automatiquement, le premier paragraphe de la rubrique ou du document reçoit un identifiant comme p\_1, le paragraphe suivant reçoit p\_2, etc. Cependant, dans un autre document, le processus de génération des identifiants redémarre. Cela signifie que dans un autre document, des identifiants comme p\_1 et p\_2 peuvent être affectés aux éléments de paragraphe. **Valeur par défaut**: ``${elementName}_${id}`` |

**Rubrique parente :**[ Personnalisation de l’éditeur web](conf-web-editor.md)
