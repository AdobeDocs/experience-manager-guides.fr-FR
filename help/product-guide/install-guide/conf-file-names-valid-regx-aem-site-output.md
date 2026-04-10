---
title: Configurer des noms de fichiers valides pour la sortie du site AEM
description: Découvrez comment Configurer des noms de fichiers valides pour la sortie du site AEM
exl-id: 1e69d6f8-7baf-4189-bbbd-34cd0fec6634
feature: Filename Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 0%

---

# Configurer des noms de fichiers valides pour la sortie du site AEM {#id214GK0X0KXA}

Tout comme la liste des caractères de nom de fichier valides autorisés pour les rubriques DITA, vous pouvez également configurer une liste de caractères de nom de fichier valides pour la sortie du site AEM. Voici quelques caractères connus qui ne sont pas autorisés dans une URL : ```'<>`@$```. Ces caractères sont configurés pour être automatiquement convertis en trait de soulignement « _ » lorsqu’ils sont trouvés lors de la génération de noms de fichiers de sortie du site AEM. La configuration qui vous permet de définir des caractères valides dans la sortie du site AEM est présente dans le lot `com.adobe.fmdita.common.SanitizeNodeNameImpl`. **Définissez le jeu de caractères interdits pour la publication sur AEM Sites** pour inclure les caractères que vous souhaitez remplacer par un trait de soulignement dans les noms de fichier de sortie du site AEM.

**Rubrique parente :**[ Configurer les noms de fichier](conf-file-names.md)
