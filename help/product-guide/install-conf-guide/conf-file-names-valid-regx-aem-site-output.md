---
title: Configurer des noms de fichiers valides pour la sortie du site AEM
description: Découvrez comment Configurer des noms de fichiers valides pour la sortie du site AEM
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# Configurer des noms de fichiers valides pour la sortie du site AEM {#id214GK0X0KXA}

Tout comme la liste des caractères de nom de fichier valides autorisés pour les rubriques DITA, vous pouvez également configurer une liste de caractères de nom de fichier valides pour la sortie du site AEM. Voici quelques caractères connus qui ne sont pas autorisés dans une URL : ``'<>`@$``. Ces caractères sont configurés pour être automatiquement convertis en trait de soulignement « `_` » lorsqu’ils sont trouvés lors de la génération de noms de fichiers de sortie du site AEM.

Les onglets suivants fournissent des instructions pour configurer des noms de fichiers valides pour la sortie de site AEM en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB ]

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(property\) suivants pour définir des caractères valides dans la sortie du site AEM :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Ajoutez les caractères que vous souhaitez remplacer par un trait de soulignement dans les noms de fichier de sortie du site AEM. <br> **Valeur par défaut** : ``'<\>\`@$`` |

>[!TAB  On-Premise ]

La configuration qui vous permet de définir des caractères valides dans la sortie du site AEM est présente dans le lot `com.adobe.fmdita.common.SanitizeNodeNameImpl`. **Définissez le jeu de caractères interdits pour la publication sur AEM Sites** pour inclure les caractères que vous souhaitez remplacer par un trait de soulignement dans les noms de fichier de sortie du site AEM.

>[!ENDTABS]
