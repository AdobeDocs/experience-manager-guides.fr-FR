---
title: Configuration de noms de fichier valides pour AEM sortie Site
description: Découvrez comment configurer des noms de fichier valides pour AEM sortie Site
exl-id: 05215bec-653b-4563-83c6-a1bb16200469
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 1%

---

# Configuration de noms de fichier valides pour AEM sortie Site {#id214GK0X0KXA}

Tout comme la liste des caractères de nom de fichier valides autorisés pour les rubriques DITA, vous pouvez configurer une liste de caractères de nom de fichier valides pour AEM sortie Site. Certains des caractères connus non autorisés dans une URL sont : ``'<>`@$``. Ces caractères sont configurés pour être automatiquement convertis en caractère de soulignement &quot;`_`&quot; lorsqu’ils sont détectés lors de la génération AEM noms de fichiers de sortie de site.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour définir des caractères valides dans AEM sortie Site :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Ajoutez les caractères que vous souhaitez remplacer par un trait de soulignement dans les noms de fichiers de sortie Site AEM. <br> **Valeur par défaut** : ``'<\>\`@$`` |

**Rubrique parente :**&#x200B;[ Configurer les noms de fichier](conf-file-names.md)
