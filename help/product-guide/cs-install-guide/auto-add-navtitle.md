---
title: Inclure l’attribut @navtitle par défaut
description: Découvrez comment inclure l’attribut @navtitle par défaut
exl-id: 38711c0c-efa8-461a-92e1-ecfcdcdd36d3
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Inclure l’attribut @navtitle par défaut {#id2115BC0J0XA}

Vous pouvez ajouter différents types de fichiers de référence dans un mappage, par exemple rubrique, référence, tâche, mappages \(sub\), etc. La plupart de ces fichiers prennent en charge l’attribut `@navtitle`. Cependant, peu d’auteurs l’utilisent de manière cohérente. Si vous souhaitez appliquer l’utilisation de l’attribut `@navtitle` dans tous les fichiers référencés d’une carte, vous pouvez le faire avec une configuration simple.

Une fois activé, chaque fichier de référence que vous ajoutez dans une carte est automatiquement ajouté à ses propriétés par l’attribut `@navtitle`. `@navtitle` obtiendra également la valeur de l’élément `title` du contenu référencé.

Pour inclure l’attribut `@navtitle` par défaut dans les propriétés des fichiers de référence, procédez comme suit :

1. Pour télécharger le fichier de configuration de l’interface utilisateur, connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et sélectionnez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils et cliquez sur le bouton **Profils de dossier**.
1. Cliquez sur la mosaïque **Profil global** .
1. Sélectionnez l’onglet **Configuration de l’éditeur XML** et cliquez sur l’icône **Modifier** en haut
1. Cliquez sur l’icône **Télécharger** pour télécharger le fichier ui\_config.json sur votre système local.
1. Vous pouvez effectuer cette modification au niveau global ou à un profil au niveau du dossier. Selon l’emplacement où vous souhaitez apporter cette modification, vous devez télécharger le fichier ui\_config.json correspondant. Pour plus d’informations sur le téléchargement du fichier ui\_config.json, voir [Configuration et personnalisation de l’éditeur Web XML](conf-folder-level.md#id2065G300O5Z).

1. Recherchez la définition `ditaAttributes`.

   La définition par défaut de `ditaAttributes` est :

   ```
   "ditaAttributes": {
                           "attributes": [],
                           "constraint": false,
                           "required": {}
                           },
   ```

1. Modifiez le paramètre `required` en tant que :

   ```
   "required": {"navtitle": true}
   ```

1. Enregistrez le fichier.

1. Téléchargez le fichier dans le profil correspondant \(Global ou Dossier\).


Avec cette configuration, chaque fichier de référence que vous ajoutez à un mappage contient l’attribut `@navtitle` par défaut.

**Rubrique parente :**&#x200B;[ Personnaliser l’éditeur web](conf-web-editor.md)
