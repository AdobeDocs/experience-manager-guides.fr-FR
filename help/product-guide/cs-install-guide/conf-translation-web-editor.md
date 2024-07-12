---
title: Configuration de la fonction de traduction dans l’éditeur web
description: Découvrez comment configurer la fonction de traduction dans l’éditeur web
exl-id: e25473c3-9a84-4658-87c9-6fd72bcaa2b6
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---

# Configuration de la fonction de traduction dans l’éditeur web {#id21BONI0J0YR}

L’éditeur web fournit une puissante fonction de traduction pour traduire votre contenu dans plusieurs langues.

Vous pouvez utiliser l’onglet **Gérer** de l’éditeur Web pour traduire votre contenu. Cet onglet est disponible par défaut.

Pour masquer l’onglet **Gérer** dans l’éditeur web, procédez comme suit :

1. Connectez-vous à **Adobe Experience Manager** en tant qu’administrateur.
1. Cliquez sur le lien **Adobe Experience Manager** dans la partie supérieure et sélectionnez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils et cliquez sur le bouton **Profils de dossier**.
1. Cliquez sur la mosaïque **Profil global** .
1. Cliquez sur **Configuration de l’éditeur XML**.
1. Cliquez sur l’icône **Modifier** en haut de l’écran.
1. Téléchargez le fichier `ui\_config.json`. Supprimez le fragment de code suivant du fichier téléchargé :

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

1. Téléchargez le fichier ui\_config.json mis à jour.

Notez que le filtre **Gérer** n’est plus disponible.

**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
