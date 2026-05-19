---
title: Configurer des noms de fichiers valides pour la sortie du site AEM
description: Découvrez comment Configurer des noms de fichiers valides pour la sortie du site AEM
exl-id: 05215bec-653b-4563-83c6-a1bb16200469
feature: Filename Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/hhc9Q8A-Eq3e8PAHHDXf1jXf8qVb-p4sU3Cum53ra9M
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 145
ht-degree: 1%

---

# Configurer des noms de fichiers valides pour la sortie du site AEM {#id214GK0X0KXA}

Tout comme la liste des caractères de nom de fichier valides autorisés pour les rubriques DITA, vous pouvez également configurer une liste de caractères de nom de fichier valides pour la sortie du site AEM. Voici quelques caractères connus qui ne sont pas autorisés dans une URL : ``'<>`@$``. Ces caractères sont configurés pour être automatiquement convertis en trait de soulignement « `_` » lorsqu’ils sont trouvés lors de la génération de noms de fichiers de sortie du site AEM.

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(property\) suivants pour définir des caractères valides dans la sortie du site AEM :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Ajoutez les caractères que vous souhaitez remplacer par un trait de soulignement dans les noms de fichier de sortie du site AEM. <br> **Valeur par défaut** : ``'<\>\`@$`` |

**Rubrique parente :**&#x200B;[&#x200B; Configurer les noms de fichier](conf-file-names.md)
