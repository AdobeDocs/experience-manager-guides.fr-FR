---
title: Configuration de noms de fichier valides pour AEM sortie Site
description: Découvrez comment configurer des noms de fichier valides pour AEM sortie Site
exl-id: 05215bec-653b-4563-83c6-a1bb16200469
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 1%

---

# Configuration de noms de fichier valides pour AEM sortie Site {#id214GK0X0KXA}

Tout comme la liste des caractères de nom de fichier valides autorisés pour les rubriques DITA, vous pouvez configurer une liste de caractères de nom de fichier valides pour AEM sortie Site. Voici quelques-uns des caractères connus qui ne sont pas autorisés dans une URL : ``'<>`@$``. Ces caractères sont configurés pour être automatiquement convertis en traits de soulignement &quot;`_`&quot; lorsqu’elles sont trouvées lors de la génération AEM noms de fichiers de sortie du site.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour définir des caractères valides dans AEM sortie Site :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Ajoutez les caractères que vous souhaitez remplacer par un trait de soulignement dans les noms de fichiers de sortie Site AEM. <br> **Valeur par défaut**: ``'<\>\`@$`` |

**Rubrique parente :**[ Configuration des noms de fichier](conf-file-names.md)
