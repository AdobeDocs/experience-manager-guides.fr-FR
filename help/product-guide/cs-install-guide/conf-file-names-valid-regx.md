---
title: Configuration de Regx pour les caractères de nom de fichier valides
description: Découvrez comment configurer la regx pour les caractères de nom de fichier valides
exl-id: 05e9ca3c-28ff-4f82-8061-3d20307890ff
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# Configuration de Regx pour les caractères de nom de fichier valides {#id214BD0550E8}

Depuis la version AEM Guides 3.8, en tant qu’administrateur, vous pouvez définir une liste de caractères spéciaux valides autorisés dans les noms de fichiers. Dans les versions antérieures, les utilisateurs étaient autorisés à définir des noms de fichier contenant des caractères spéciaux tels que `@`, `$`, `>`, etc. Ces caractères spéciaux entraînaient des problèmes lors de l’ouverture de rubriques à partir du tableau de bord de la carte DITA ou du clic sur le lien de la rubrique dans la table des matières, ce qui entraînait souvent l’ouverture de la page en raison de caractères spéciaux dans l’URL.

En utilisant la configuration qui vous permet de définir une regx pour les caractères de nom de fichier valides, vous avez un contrôle total sur la manière dont les fichiers sont nommés en interne dans le système. Vous pouvez définir une liste de caractères spéciaux autorisés dans les noms de fichier. Par défaut, la configuration de nom de fichier valide contient &quot;`a-z A-Z 0-9 - _`&quot;. Lors de la création d’un fichier, vous pouvez avoir n’importe quel caractère spécial dans le titre du fichier, mais en interne, il sera remplacé par &quot;`-`&quot; dans le nom du fichier. Par exemple, le titre du fichier peut être &quot;Introduction 1&quot; ou &quot;Introduction@1&quot;, le nom de fichier correspondant généré pour ces deux cas serait &quot;Introduction-1&quot;.

Lorsque vous définissez une liste de caractères valides, n’oubliez pas que ces caractères &quot;`*/:[\]|#%{}?&<>"/+`&quot; seront toujours remplacés par un &quot;`-`&quot;.

Si vous ne configurez pas la liste des caractères spéciaux valides, le processus de création de fichier peut vous donner des résultats inattendus. Pour éviter de telles erreurs, il est vivement recommandé d’effectuer cette modification de configuration.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer l’expression régulière pour les caractères de nom de fichier valides :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `valid.characters` | La valeur est un modèle regex. Elle doit contenir trois caractères de base et la liste doit commencer par un trait d’union \(-\).<br> **Valeur par défaut** : \[-a-zA-Z0-9\_\] |

>[!NOTE]
>
> Tout comme la liste des caractères de nom de fichier valides, vous pouvez également spécifier une liste de caractères de nom de fichier valides pour AEM sortie Site. Pour plus d’informations, voir [Configuration de noms de fichier valides pour AEM sortie du site](conf-file-names-valid-regx-aem-site-output.md#).

**Rubrique parente :**&#x200B;[ Configurer les noms de fichier](conf-file-names.md)
