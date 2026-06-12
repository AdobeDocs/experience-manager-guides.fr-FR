---
title: Configuration des caractères spéciaux autorisés
description: Découvrez comment configurer les caractères spéciaux autorisés
exl-id: 7ff4305f-71bb-4155-b8e5-911cea6f0ad9
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/4E8kj37-4mj6StL4NBMzoebW6XgyfNV5e5emGg3EX8c
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 208
ht-degree: 0%

---

# Configuration des caractères spéciaux autorisés {#id20CIL600035}

L’éditeur web vous permet d’insérer des caractères spéciaux prêts à l’emploi. Cependant, vous pouvez personnaliser la liste des caractères spéciaux que vos auteurs peuvent insérer dans leurs documents. Si vous personnalisez la liste des caractères spéciaux, elle remplace l’ensemble par défaut des caractères spéciaux. Seuls les caractères spéciaux que vous ajoutez dans votre configuration sont mis à la disposition des auteurs.

Procédez comme suit pour remplacer la liste par défaut des caractères spéciaux :

1. Créez `symbols.json` fichier à l’emplacement suivant dans votre référentiel Git Cloud Manager :

   ```
   /apps/fmdita/xmleditor/
   ```

1. Ajoutez la définition des caractères spéciaux dans le fichier `symbols.json` en tant que :

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

- `"label": "Arrows"` : permet de spécifier la catégorie des caractères spéciaux. Dans le fragment de code, une catégorie portant le nom `"Arrows"` est définie.
- `"items"` : définit la collection de caractères spéciaux dans la catégorie.
- `"name": "←", "title": "Left Arrow"` : il s’agit de la définition du caractère spécial. Il commence par le libellé `"name"`, qui ne doit pas être modifié. Le nom est suivi du caractère spécial. Le `"title"` est le nom ou le titre du caractère spécial qui s’affiche en tant qu’info-bulle pour ce caractère spécial.

  Vous pouvez définir plusieurs définitions de caractères spéciaux au sein d’une catégorie.


**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur web](conf-web-editor.md)
