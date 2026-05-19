---
title: Configuration de la fonctionnalité de traduction dans l’éditeur web
description: Découvrez comment configurer la fonctionnalité de traduction dans l’éditeur web
exl-id: e25473c3-9a84-4658-87c9-6fd72bcaa2b6
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/7-SFQ0FXQ6bGo3pjAOK-18sEsU4-zriruioG2nMx2o0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 154
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
