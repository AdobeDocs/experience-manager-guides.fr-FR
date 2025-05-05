---
title: Configuration des caractères spéciaux autorisés
description: Découvrez comment configurer des caractères spéciaux autorisés
exl-id: 7ff4305f-71bb-4155-b8e5-911cea6f0ad9
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# Configuration des caractères spéciaux autorisés {#id20CIL600035}

L’éditeur web vous permet d’insérer des caractères spéciaux prêts à l’emploi. Cependant, vous pouvez personnaliser la liste des caractères spéciaux que vos auteurs peuvent insérer dans leurs documents. Si vous personnalisez la liste des caractères spéciaux, elle remplace le jeu par défaut de caractères spéciaux. Seuls les caractères spéciaux que vous ajoutez dans votre configuration sont mis à la disposition des auteurs.

Effectuez les étapes suivantes pour remplacer la liste par défaut des caractères spéciaux :

1. Créez un fichier `symbols.json` à l’emplacement suivant dans votre référentiel Git Cloud Manager :

   ```
   /apps/fmdita/xmleditor/
   ```

1. Ajoutez la définition de caractère spécial dans le fichier `symbols.json` en tant que :

   ```
   {"symbols": [{"label": "Arrows",
      "items": [
      {   "name": "←",   "title": "Left Arrow"   } 
      ,   
      {   "name": "↑",   "title": "Up Arrow"      } 
      ]   
      }   ]   }
   ```


La structure du fichier `symbols.json` est expliquée ci-dessous :

- `"label": "Arrows"` : indique la catégorie des caractères spéciaux. Dans l’extrait de code, une catégorie portant le nom `"Arrows"` est définie.
- `"items"` : définit la collection de caractères spéciaux dans la catégorie.
- `"name": "←", "title": "Left Arrow"` : il s’agit de la définition du caractère spécial. Il commence par le libellé `"name"`, qui ne doit pas être modifié. Le nom est suivi du caractère spécial. `"title"` est le nom ou le titre du caractère spécial qui apparaît comme info-bulle pour ce caractère spécial.

  Vous pouvez définir plusieurs définitions de caractères spéciaux dans une catégorie.


**Rubrique parente :**&#x200B;[ Personnaliser l’éditeur web](conf-web-editor.md)
