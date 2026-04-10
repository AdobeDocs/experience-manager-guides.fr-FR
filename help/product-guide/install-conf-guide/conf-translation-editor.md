---
title: Configuration de la fonctionnalité de traduction dans l’éditeur web
description: Découvrez comment configurer la fonctionnalité de traduction dans l’éditeur web
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 0%

---

# Configuration de la fonctionnalité de traduction dans l’éditeur web pour Cloud Service

L’éditeur web offre une puissante fonctionnalité de traduction pour traduire votre contenu dans plusieurs langues.

Vous pouvez utiliser l’onglet **Gérer** dans l’éditeur web pour traduire votre contenu. Cet onglet est disponible par défaut.

Pour masquer l’onglet **Gérer** dans l’éditeur web, procédez comme suit :

1. Connectez-vous à **** en tant qu&#39;administrateur.
1. Cliquez sur le lien **** en haut et choisissez **Outils**.
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

**Rubrique parente :**[ Personnaliser l’éditeur web](customize-overview.md)
