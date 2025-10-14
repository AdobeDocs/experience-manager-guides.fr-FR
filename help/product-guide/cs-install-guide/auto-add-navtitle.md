---
title: Inclure l’attribut @navtitle par défaut
description: Découvrez comment inclure l’attribut @navtitle par défaut
exl-id: 38711c0c-efa8-461a-92e1-ecfcdcdd36d3
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: a3c7973868549c72e868c05a3fc6ca8bdce9bce3
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 0%

---

# Inclure l’attribut @navtitle par défaut {#id2115BC0J0XA}

Vous pouvez ajouter différents types de fichiers de référence dans un mappage, par exemple des mappages de rubrique, de référence, de tâche, \(sub\), etc. La plupart de ces fichiers prennent en charge l’attribut `@navtitle`. Cependant, peu d’auteurs l’utilisent de manière cohérente. Si vous souhaitez appliquer l’utilisation de l’attribut `@navtitle` dans tous les fichiers référencés d’un mappage, vous pouvez le faire avec une configuration simple.

Une fois activé, chaque fichier de référence que vous ajoutez dans un mappage ajoute automatiquement l’attribut `@navtitle` à ses propriétés. L’`@navtitle` obtient également la valeur de l’élément `title` du contenu référencé.

Pour inclure `@navtitle` attribut par défaut dans les propriétés des fichiers de référence, procédez comme suit :

1. Pour télécharger le fichier de configuration de l’interface utilisateur, connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils, puis cliquez sur le **Profils de dossier**.
1. Cliquez sur la mosaïque **Profil global**.
1. Sélectionnez l’onglet **Configuration de l’éditeur XML** et cliquez sur l’icône **Modifier** en haut
1. Cliquez sur l’icône **Télécharger** pour télécharger le fichier ui\_config.json sur votre système local.
1. Vous pouvez effectuer cette modification au niveau global ou au niveau d’un profil de dossier. Selon l’emplacement où vous souhaitez effectuer cette modification, vous devez télécharger le fichier ui\_config.json correspondant. Pour plus d’informations sur le téléchargement du fichier ui\_config.json, consultez [Configuration et personnalisation de l’éditeur web XML](conf-folder-level.md#id2065G300O5Z).

1. Recherchez la définition du `ditaAttributes`.

   La définition par défaut de `ditaAttributes` est la suivante :

   ```
   "ditaAttributes": {
                           "attributes": [],
                           "constraint": false,
                           "required": {}
                           },
   ```

1. Modifiez le paramètre `required` comme illustré ci-dessous :

   ```
   "required": {"navtitle": true}
   ```

   Lorsque la valeur est définie sur `true`, le bouton **Actualiser l’attribut de titre de navigation** est activé pour s’afficher dans la barre d’outils de l’éditeur. Lorsqu’il est défini sur `false` ou laissé vide, le bouton reste masqué dans l’éditeur.
1. Enregistrez le fichier.

1. Chargez le fichier dans le profil correspondant \(Global ou Dossier\).


Avec cette configuration, chaque fichier de référence que vous ajoutez à une carte contient l’attribut `@navtitle` par défaut.



**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur web](conf-web-editor.md)
