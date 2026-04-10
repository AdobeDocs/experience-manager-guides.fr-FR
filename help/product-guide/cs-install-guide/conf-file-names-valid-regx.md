---
title: Configurer Regx pour les caractères de nom de fichier valides
description: Découvrez comment configurer la regx pour les caractères de nom de fichier valides
exl-id: 05e9ca3c-28ff-4f82-8061-3d20307890ff
feature: Filename Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# Configurer Regx pour les caractères de nom de fichier valides {#id214BD0550E8}

À partir de la version 3.8 d’AEM Guides, en tant qu’administrateur, vous pouvez définir une liste de caractères spéciaux valides autorisés dans les noms de fichier. Dans les versions antérieures, les utilisateurs étaient autorisés à définir des noms de fichier contenant des caractères spéciaux tels que `@`, `$`, `>`, etc. Ces caractères spéciaux entraînaient des problèmes lors de l&#39;ouverture de rubriques à partir du tableau de bord de plan DITA ou du clic sur le lien de la rubrique dans la table des matières, ce qui empêchait souvent l&#39;ouverture de la page en raison de caractères spéciaux dans l&#39;URL.

En utilisant la configuration qui vous permet de définir une regx pour les caractères de nom de fichier valides, vous avez un contrôle total sur la manière dont les fichiers sont nommés en interne dans le système. Vous pouvez définir une liste de caractères spéciaux autorisés dans les noms de fichier. Par défaut, la configuration du nom de fichier valide contient « `a-z A-Z 0-9 - _` ». Lors de la création d’un fichier, vous pouvez avoir n’importe quel caractère spécial dans le titre du fichier, mais en interne, il sera remplacé par « `-` » dans le nom du fichier. Par exemple, si le titre du fichier est « Introduction 1 » ou « Introduction@1 », le nom de fichier correspondant généré pour ces deux cas est « Introduction-1 ».

Lorsque vous définissez une liste de caractères valides, n&#39;oubliez pas que ces caractères « `*/:[\]|#%{}?&<>"/+` » seront toujours remplacés par un « `-` ».

Si vous ne configurez pas la liste de caractères spéciaux valide, le processus de création de fichier peut vous donner des résultats inattendus. Pour éviter de telles erreurs, il est vivement recommandé de modifier cette configuration.

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(property\) suivants pour configurer une expression régulière pour les caractères de nom de fichier valides :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `valid.characters` | La valeur est un modèle RegEx. Il doit comporter trois caractères de base et la liste doit commencer par un trait d’union \(-\).<br> **Valeur par défaut** : \[-a-zA-Z0-9\_\] |

>[!NOTE]
>
> Tout comme la liste des caractères de nom de fichier valides, vous pouvez également spécifier une liste de caractères de nom de fichier valide pour la sortie du site AEM. Pour plus d’informations, voir [Configurer des noms de fichier valides pour la sortie de site AEM](conf-file-names-valid-regx-aem-site-output.md#).

**Rubrique parente :**&#x200B;[&#x200B; Configurer les noms de fichier](conf-file-names.md)
