---
title: Configurer des noms de fichiers valides pour la sortie du site AEM
description: Découvrez comment Configurer des noms de fichiers valides pour la sortie du site AEM
exl-id: 1e69d6f8-7baf-4189-bbbd-34cd0fec6634
feature: Filename Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/vGe4--XJ9VL5q74J7hVFCmD0vrBRnUkBAdZDCFcUxeU
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 179e9016b12edb14c09ce9352a318e06a4fc628a
workflow-type: tm+mt
source-wordcount: 139
ht-degree: 0%

---

# Configurer des noms de fichiers valides pour la sortie du site AEM {#id214GK0X0KXA}

Tout comme la liste des caractères de nom de fichier valides autorisés pour les rubriques DITA, vous pouvez également configurer une liste de caractères de nom de fichier valides pour la sortie du site AEM. Voici quelques caractères connus qui ne sont pas autorisés dans une URL : `<>``@$`. Ces caractères sont configurés pour être automatiquement convertis en trait de soulignement « _ » lorsqu’ils sont trouvés lors de la génération de noms de fichiers de sortie du site AEM. La configuration qui vous permet de définir des caractères valides dans la sortie du site AEM est présente dans le lot `com.adobe.fmdita.common.SanitizeNodeNameImpl`. **Définissez le jeu de caractères interdits pour la publication sur AEM Sites** pour inclure les caractères que vous souhaitez remplacer par un trait de soulignement dans les noms de fichier de sortie du site AEM.

**Rubrique parente :**[ Configurer les noms de fichier](conf-file-names.md)
