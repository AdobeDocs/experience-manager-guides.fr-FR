---
title: Inclure l’attribut @navtitle par défaut
description: Découvrez comment inclure l’attribut @navtitle par défaut
exl-id: 3def20dc-dd24-4526-ae36-45708249d34a
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 1%

---

# Inclure l’attribut @navtitle par défaut {#id2115BC0J0XA}

Vous pouvez ajouter différents types de fichiers de référence dans un mappage, par exemple rubrique, référence, tâche, mappages \(sub\), etc. La plupart de ces fichiers prennent en charge la variable `@navtitle` attribut. Cependant, peu d’auteurs l’utilisent de manière cohérente. Si vous souhaitez appliquer l’utilisation de la variable `@navtitle` dans tous les fichiers référencés d’une carte, puis vous pouvez le faire avec une configuration simple.

Une fois activé, chaque fichier de référence que vous ajoutez dans une carte reçoit automatiquement la variable `@navtitle` ajouté à ses propriétés. La variable `@navtitle` obtient également la valeur de la variable `title` élément du contenu référencé.

À inclure `@navtitle` par défaut dans les propriétés des fichiers de référence, procédez comme suit :

1. Téléchargez le fichier ui\_config.json.

   Vous pouvez effectuer cette modification au niveau global ou à un profil au niveau du dossier. Selon l’emplacement où vous souhaitez apporter cette modification, vous devez télécharger le fichier ui\_config.json correspondant. Pour plus d’informations sur le téléchargement du fichier ui\_config.json, voir [Configuration et personnalisation de l’éditeur Web XML](conf-folder-level.md#id2065G300O5Z).

1. Recherchez le `ditaAttributes` définition.

   La définition par défaut de `ditaAttributes` est :

   ```json
   "ditaAttributes": {
   "attributes": [],
   "constraint": false,
   "required": {}
   },
   ```

1. Modifiez la variable `required` parameter as :

   ```json
   "required": {"navtitle": true}
   ```

1. Enregistrez le fichier.

1. Téléchargez le fichier dans le profil correspondant \(Global ou Dossier\).


Avec cette configuration, chaque fichier de référence que vous ajoutez à un mappage contient le `@navtitle` par défaut.
