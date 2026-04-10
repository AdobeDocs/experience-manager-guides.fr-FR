---
title: Configuration des caractères spéciaux autorisés
description: Découvrez comment configurer les caractères spéciaux autorisés
exl-id: 3dd7752e-0836-480a-b1e1-6fa2099d404f
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Configuration des caractères spéciaux autorisés {#id20CIL600035}

L’éditeur web vous permet d’insérer des caractères spéciaux prêts à l’emploi. Cependant, vous pouvez personnaliser la liste des caractères spéciaux que vos auteurs peuvent insérer dans leurs documents. Si vous personnalisez la liste des caractères spéciaux, elle remplace l’ensemble par défaut des caractères spéciaux. Seuls les caractères spéciaux que vous ajoutez dans votre configuration sont mis à la disposition des auteurs.

Procédez comme suit pour remplacer la liste par défaut des caractères spéciaux :

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite .

1. créez `symbols.json` fichier à l’emplacement suivant :

   ```json
   /apps/fmdita/xmleditor/
   ```

1. Ajoutez la définition des caractères spéciaux dans le fichier `symbols.json` en tant que :

   ```json
   {"symbols": [{"label": "Arrows",
      "items": [
      {   "name": "←",   "title": "Left Arrow"   } 
      ,   
      {   "name": "↑",   "title": "Up Arrow"      } 
      ]   
      }   ]   }
   ```


La structure du fichier `symbols.json` est expliquée ci-dessous :

- `"label": "Arrows"` : permet de spécifier la catégorie des caractères spéciaux. Dans le fragment de code, une catégorie portant le nom `"Arrows"` est définie.
- `"items"` : définit la collection de caractères spéciaux dans la catégorie.
- `"name": "←", "title": "Left Arrow"` : il s’agit de la définition du caractère spécial. Il commence par le libellé `"name"`, qui ne doit pas être modifié. Le nom est suivi du caractère spécial. Le `"title"` est le nom ou le titre du caractère spécial qui s’affiche en tant qu’info-bulle pour ce caractère spécial.

  Vous pouvez définir plusieurs définitions de caractères spéciaux au sein d’une catégorie.


**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
