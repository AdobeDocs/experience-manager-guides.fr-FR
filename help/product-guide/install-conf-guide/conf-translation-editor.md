---
title: Configuration de la fonctionnalité de traduction dans l’éditeur
description: Découvrez comment configurer la fonctionnalité de traduction dans l’éditeur
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 22d7e1c7-2059-43fb-b7aa-3ae4a6072678
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
source-wordcount: '150'
ht-degree: 0%
---
# Configuration de la fonctionnalité de traduction dans l’éditeur pour Cloud Service

L’éditeur fournit une puissante fonctionnalité de traduction permettant de traduire votre contenu dans plusieurs langues.

Vous pouvez utiliser l’onglet **Gérer** dans l’éditeur pour traduire votre contenu. Cet onglet est disponible par défaut.

Pour masquer l’onglet **Gérer** dans l’éditeur, procédez comme suit :

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

**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur](customize-overview.md)
