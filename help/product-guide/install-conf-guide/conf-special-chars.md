---
title: Configuration des caractères spéciaux autorisés
description: Découvrez comment configurer les caractères spéciaux autorisés
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---

# Configuration des caractères spéciaux autorisés {#id20CIL600035}

L’éditeur web vous permet d’insérer des caractères spéciaux prêts à l’emploi. Cependant, vous pouvez personnaliser la liste des caractères spéciaux que vos auteurs peuvent insérer dans leurs documents. Si vous personnalisez la liste des caractères spéciaux, elle remplace l’ensemble par défaut des caractères spéciaux. Seuls les caractères spéciaux que vous ajoutez dans votre configuration sont mis à la disposition des auteurs.

Les onglets suivants fournissent des instructions pour remplacer la liste par défaut des caractères spéciaux en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB ]

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

>[!TAB  On-Premise ]

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

>[!ENDTABS]

**Rubrique parente :**[ Personnaliser l’éditeur web](customize-overview.md)
