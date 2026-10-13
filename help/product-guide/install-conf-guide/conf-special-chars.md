---
title: Configuration des caractères spéciaux autorisés
description: Découvrez comment configurer les caractères spéciaux autorisés
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: e3747a18-b6a1-46fd-a4d1-28a9c087e924
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%
---
# Configuration des caractères spéciaux autorisés {#id20CIL600035}

L’éditeur vous permet d’insérer des caractères spéciaux prêts à l’emploi. Cependant, vous pouvez personnaliser la liste des caractères spéciaux que vos auteurs peuvent insérer dans leurs documents. Si vous personnalisez la liste des caractères spéciaux, elle remplace l’ensemble par défaut des caractères spéciaux. Seuls les caractères spéciaux que vous ajoutez dans votre configuration sont mis à la disposition des auteurs.

Les onglets suivants fournissent des instructions pour remplacer la liste par défaut des caractères spéciaux en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB Tab]

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

**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur](customize-overview.md)
