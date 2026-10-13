---
title: Configuration des filtres d’état du document
description: Découvrez comment configurer les filtres d’état du document
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 682c915b-bc42-4d2e-84a0-9e88734e278e
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
source-wordcount: '251'
ht-degree: 0%
---
# Configuration des filtres d’état du document

Adobe Experience Manager Guides permet de rechercher un fichier en fonction de son état actuel dans le document. Vous pouvez utiliser la recherche par filtre pour rechercher des fichiers dans l’interface du référentiel afin de parcourir les fichiers.

Effectuez les étapes suivantes pour configurer les filtres d’état du document :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur.
1. Sélectionnez le lien Adobe Experience Manager en haut et choisissez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils, puis sélectionnez **Profils de dossier**.
1. Ouvrez la mosaïque **Profil global**. Vous pouvez également sélectionner une mosaïque de profil de dossier spécifique si vous souhaitez que ces modifications s’appliquent uniquement à ce dossier et non à l’ensemble des dossiers.
1. Accédez à **Configuration de l’éditeur XML**.
1. Sélectionnez l’icône **Modifier** en haut.
1. Sélectionnez l’icône **Télécharger** pour télécharger le fichier `ui\_config.json` sur votre système local.
Dans le fichier `ui\_config.json` téléchargé, reportez-vous à la section suivante :

       « 
     « repositoryFilters » : &lbrack;
     &lbrace;
     « title »: « Document state »,
     « property »: « jcr:content/metadata/docstate »,
« children »: &lbrack;    &lbrace;
« title »: « Draft »,    « value »: « Draft »
&rbrace;,    &lbrace;
« title »: « Edit »,    « value »: « Edit »
&rbrace;,    &lbrace;
« title »: « In-Review »,    « value »: « In-Review »
     &rbrace;,
&lbrace;    « title »: « Approved »,
     « value »: « Approved »
&rbrace;,    &lbrace;
« title »: « Reviewed »,    « value »: « Reviewed »
&rbrace;,    &lbrace;
« title »: « Done »,    « value »: « Done »
«     &rbrace;
&rbrack;    &rbrace;
&rbrack;    « 
      
      
      
      
      
      
      
      
      
      
      
      
      
   Ce fragment de code représente les filtres d’état de document par défaut disponibles dans Experience Manager Guides.

1. Vous pouvez personnaliser les valeurs de filtre en fonction du workflow de votre organisation. Par exemple, pour ajouter un état de document personnalisé **En attente**, insérez l’entrée suivante sous `children` :

   ```
   {
       "title": "Pending",
       "value": "Pending"
   }
   ```

1. Une fois la mise à jour effectuée, enregistrez le fichier et chargez-le.

Les filtres configurés s’affichent dans le panneau **Filtres** dans le référentiel de la page d’accueil.

**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur web](conf-web-editor.md)
