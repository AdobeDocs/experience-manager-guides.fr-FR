---
title: Configuration de la fonctionnalité de traduction dans l’éditeur web
description: Découvrez comment configurer la fonctionnalité de traduction dans l’éditeur web
exl-id: e25473c3-9a84-4658-87c9-6fd72bcaa2b6
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---

# Configuration de la fonctionnalité de traduction dans l’éditeur web {#id21BONI0J0YR}

L’éditeur web offre une puissante fonctionnalité de traduction pour traduire votre contenu dans plusieurs langues.

Vous pouvez utiliser l’onglet **Gérer** dans l’éditeur web pour traduire votre contenu. Cet onglet est disponible par défaut.

Pour masquer l’onglet **Gérer** dans l’éditeur web, procédez comme suit :

1. Connectez-vous à **&#x200B;**&#x200B;en tant qu&#39;administrateur.
1. Cliquez sur le lien **&#x200B;**&#x200B;en haut et choisissez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils, puis cliquez sur le **Profils de dossier**.
1. Cliquez sur la mosaïque **Profil global**.
1. Cliquez sur **Configuration de l’éditeur XML**.
1. Cliquez sur l’icône **Modifier** dans la partie supérieure.
1. Téléchargez le fichier `ui\_config.json`.Supprimez le fragment de code suivant du fichier téléchargé :

   ```json
   {
       "component":"tab",
       "id":"workflow",
       "title":"Manage",
       "on-click":"APP_MODE_CHANGE",
       "items":
       [
           {
               "component":"label",
               "label":"Manage"
           }
       ]
   },
   ```

1. Chargez le fichier ui\_config.json mis à jour.

Notez que le filtre **Gérer** n’est plus disponible.

**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur web](conf-web-editor.md)
