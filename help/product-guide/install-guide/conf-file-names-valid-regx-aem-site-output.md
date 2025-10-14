---
title: Configuration de noms de fichier valides pour AEM sortie Site
description: Découvrez comment configurer des noms de fichier valides pour AEM sortie Site
exl-id: 1e69d6f8-7baf-4189-bbbd-34cd0fec6634
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 0%

---

# Configuration de noms de fichier valides pour AEM sortie Site {#id214GK0X0KXA}

Tout comme la liste des caractères de nom de fichier valides autorisés pour les rubriques DITA, vous pouvez configurer une liste de caractères de nom de fichier valides pour AEM sortie Site. Certains des caractères connus non autorisés dans une URL sont : ```'<>`@$```. Ces caractères sont configurés pour être automatiquement convertis en traits de soulignement &quot;_&quot; lorsqu’ils sont détectés lors de la génération AEM noms de fichiers de sortie de site. La configuration qui vous permet de définir des caractères valides dans AEM sortie du site est présente dans le lot `com.adobe.fmdita.common.SanitizeNodeNameImpl`. **Définissez le paramètre Jeu de caractères non autorisé pour la publication sur AEM Sites** afin d’inclure les caractères que vous souhaitez remplacer par un trait de soulignement dans les noms de fichiers de sortie du site AEM.

**Rubrique parente :**&#x200B;[&#x200B; Configurer les noms de fichier](conf-file-names.md)
