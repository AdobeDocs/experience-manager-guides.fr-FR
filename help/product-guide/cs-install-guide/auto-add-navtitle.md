---
title: Inclure l’attribut @navtitle par défaut
description: Découvrez comment inclure l’attribut @navtitle par défaut
exl-id: 38711c0c-efa8-461a-92e1-ecfcdcdd36d3
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Inclure l’attribut @navtitle par défaut {#id2115BC0J0XA}

Vous pouvez ajouter différents types de fichiers de référence dans un mappage, par exemple rubrique, référence, tâche, mappages \(sub\), etc. La plupart de ces fichiers prennent en charge la variable `@navtitle` attribut. Cependant, peu d’auteurs l’utilisent de manière cohérente. Si vous souhaitez appliquer l’utilisation de la variable `@navtitle` dans tous les fichiers référencés d’une carte, puis vous pouvez le faire avec une configuration simple.

Une fois activé, chaque fichier de référence que vous ajoutez dans une carte reçoit automatiquement la variable `@navtitle` ajouté à ses propriétés. La variable `@navtitle` obtient également la valeur de la variable `title` élément du contenu référencé.

À inclure `@navtitle` par défaut dans les propriétés des fichiers de référence, procédez comme suit :

1. Pour télécharger le fichier de configuration de l’interface utilisateur, connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et choisissez **Outils**.
1. Sélectionner **Guides** dans la liste des outils, puis cliquez sur l’icône **Profils de dossier**.
1. Cliquez sur le bouton **Profil global** mosaïque.
1. Sélectionnez la variable **Configuration de l’éditeur XML** et cliquez sur **Modifier** icône en haut
1. Cliquez sur le bouton **Télécharger** pour télécharger le fichier ui\_config.json sur votre système local.
1. Vous pouvez effectuer cette modification au niveau global ou à un profil au niveau du dossier. Selon l’emplacement où vous souhaitez apporter cette modification, vous devez télécharger le fichier ui\_config.json correspondant. Pour plus d’informations sur le téléchargement du fichier ui\_config.json, voir [Configuration et personnalisation de l’éditeur Web XML](conf-folder-level.md#id2065G300O5Z).

1. Recherchez le `ditaAttributes` définition.

   La définition par défaut de `ditaAttributes` est :

   ```
   "ditaAttributes": {
                           "attributes": [],
                           "constraint": false,
                           "required": {}
                           },
   ```

1. Modifiez la variable `required` parameter as :

   ```
   "required": {"navtitle": true}
   ```

1. Enregistrez le fichier.

1. Téléchargez le fichier dans le profil correspondant \(Global ou Dossier\).


Avec cette configuration, chaque fichier de référence que vous ajoutez à un mappage contient le `@navtitle` par défaut.

**Rubrique parente :**[ Personnalisation de l’éditeur web](conf-web-editor.md)
