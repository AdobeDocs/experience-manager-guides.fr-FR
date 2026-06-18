---
title: Configuration de la fonctionnalité de traduction dans l’éditeur
description: Découvrez comment configurer la fonctionnalité de traduction dans l’éditeur
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 22d7e1c7-2059-43fb-b7aa-3ae4a6072678
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 0%

---

# Configuration de la fonctionnalité de traduction dans l’éditeur pour Cloud Service

L’éditeur fournit une puissante fonctionnalité de traduction permettant de traduire votre contenu dans plusieurs langues.

Vous pouvez utiliser l’onglet **Gérer** dans l’éditeur pour traduire votre contenu. Cet onglet est disponible par défaut.

Pour masquer l’onglet **Gérer** dans l’éditeur, procédez comme suit :

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

**Rubrique parente :**[ Personnaliser l’éditeur](customize-overview.md)
