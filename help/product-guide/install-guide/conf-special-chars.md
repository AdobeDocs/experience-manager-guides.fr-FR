---
title: Configuration des caractères spéciaux autorisés
description: Découvrez comment configurer des caractères spéciaux autorisés
exl-id: 3dd7752e-0836-480a-b1e1-6fa2099d404f
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Configuration des caractères spéciaux autorisés {#id20CIL600035}

L’éditeur web vous permet d’insérer des caractères spéciaux prêts à l’emploi. Cependant, vous pouvez personnaliser la liste des caractères spéciaux que vos auteurs peuvent insérer dans leurs documents. Si vous personnalisez la liste des caractères spéciaux, elle remplace le jeu par défaut de caractères spéciaux. Seuls les caractères spéciaux que vous ajoutez dans votre configuration sont mis à la disposition des auteurs.

Effectuez les étapes suivantes pour remplacer la liste par défaut des caractères spéciaux :

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite.

1. create `symbols.json` à l’emplacement suivant :

   ```json
   /apps/fmdita/xmleditor/
   ```

1. Ajoutez la définition de caractère spécial dans le `symbols.json` en tant que :

   ```json
   {"symbols": [{"label": "Arrows",
      "items": [
      {   "name": "←",   "title": "Left Arrow"   } 
      ,   
      {   "name": "↑",   "title": "Up Arrow"      } 
      ]   
      }   ]   }
   ```


La structure de la variable `symbols.json` est expliqué ci-dessous :

- `"label": "Arrows"`: permet de spécifier la catégorie des caractères spéciaux. Dans le fragment de code, une catégorie portant le nom `"Arrows"` est définie.
- `"items"`: définit la collection de caractères spéciaux dans la catégorie.
- `"name": "←", "title": "Left Arrow"`: il s’agit de la définition du caractère spécial. Elle commence par la fonction `"name"` qui ne doit pas être modifiée. Le nom est suivi du caractère spécial. La variable `"title"` est le nom ou le titre du caractère spécial qui apparaît comme info-bulle pour ce caractère spécial.

  Vous pouvez définir plusieurs définitions de caractères spéciaux dans une catégorie.


**Rubrique parente :**[ Personnalisation de l’éditeur web](conf-web-editor.md)
