---
title: Configuration des filtres d’état du document
description: Découvrez comment configurer les filtres d’état du document
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 4942b914ff278ebcf09d00da32d6f9c7cc4d7ff9
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
       « repositoryFilters » : [
       {
       « title »: « Document state »,
       « property »: « jcr:content/metadata/docstate »,
       « children » : [
       {
       « title »: « Draft »,
       « value »: « Draft »
       } 
       {
       « title »: « Edit »,
       « value »: « Modifier »
       } 
       {
       « title »: « In-Review »,
       « value »: « In-Review »
       } 
       {
       « title »: « Approved »,
       « value » : « Approuvé »
       } 
       {
       « title »: « Reviewed »,
       « value »: « Reviewed »
       } 
       {
       « title »: « Done »,
       « value »: « Terminé »
       }
       ]
       }
       ]
       « 
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

**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
