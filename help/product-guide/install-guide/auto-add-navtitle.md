---
title: Inclure l’attribut @navtitle par défaut
description: Découvrez comment inclure l’attribut @navtitle par défaut
exl-id: 3def20dc-dd24-4526-ae36-45708249d34a
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/bwVOZrkVrn6QPq7BoUttFvnFAzdLIL6--JGCoHYkA0o
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 222
ht-degree: 1%

---

# Inclure l’attribut @navtitle par défaut {#id2115BC0J0XA}

Vous pouvez ajouter différents types de fichiers de référence dans un mappage, par exemple des mappages de rubrique, de référence, de tâche, \(sub\), etc. La plupart de ces fichiers prennent en charge l’attribut `@navtitle`. Cependant, peu d’auteurs l’utilisent de manière cohérente. Si vous souhaitez appliquer l’utilisation de l’attribut `@navtitle` dans tous les fichiers référencés d’un mappage, vous pouvez le faire avec une configuration simple.

Une fois activé, chaque fichier de référence que vous ajoutez dans un mappage ajoute automatiquement l’attribut `@navtitle` à ses propriétés. L’`@navtitle` obtient également la valeur de l’élément `title` du contenu référencé.

Pour inclure `@navtitle` attribut par défaut dans les propriétés des fichiers de référence, procédez comme suit :

1. Téléchargez le fichier ui\_config.json .

   Vous pouvez effectuer cette modification au niveau global ou au niveau d’un profil de dossier. Selon l’emplacement où vous souhaitez effectuer cette modification, vous devez télécharger le fichier ui\_config.json correspondant. Pour plus d’informations sur le téléchargement du fichier ui\_config.json, consultez [Configuration et personnalisation de l’éditeur web XML](conf-folder-level.md#id2065G300O5Z).

1. Recherchez la définition du `ditaAttributes`.

   La définition par défaut de `ditaAttributes` est la suivante :

   ```json
   "ditaAttributes": {
   "attributes": [],
   "constraint": false,
   "required": {}
   },
   ```

1. Modifiez le paramètre `required` en tant que :

   ```json
   "required": {"navtitle": true}
   ```

1. Enregistrez le fichier.

1. Chargez le fichier dans le profil correspondant \(Global ou Dossier\).


Avec cette configuration, chaque fichier de référence que vous ajoutez à une carte contient l’attribut `@navtitle` par défaut.
