---
title: Configurer le titre des icônes Archiver et Extraire
description: Découvrez comment configurer le titre des icônes Archiver et Extraire
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 3032b49e-73d1-44d0-88b4-7e6e9444cac6
source-git-commit: 82c93529b8535532cf50f6428c41a1881b24859e
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 0%

---

# Configurez le titre des icônes Archiver et Extraire pour On-Premise

AEM Guides vous permet de configurer le titre des icônes Archiver et Extraire dans l’éditeur web. Pour configurer le titre des icônes Archiver et Extraire, procédez comme suit :

1. Téléchargez le fichier de configuration de l’interface utilisateur en vous connectant à Adobe Experience Manager en tant qu’administrateur.
1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils, puis cliquez sur le **Profils de dossier**.
1. Cliquez sur la mosaïque **Profil global**.
1. Sélectionnez l’onglet **Configuration de l’éditeur XML** et cliquez sur l’icône **Modifier** en haut.
1. Dans la section **Configuration de l’interface utilisateur de l’éditeur XML**, cliquez sur l’icône **Télécharger** pour télécharger le fichier `ui_config.json` sur votre système local.
1. Dans le fichier `ui_config.json`, modifiez le titre dans la section « barre supérieure ». Vous pouvez modifier les valeurs suivantes :

   ```json
   //Change title to "Check out" instead of "Lock"
           "title": "Check out"
   
   //Change title to "Check in" instead of "@checkOutBy
            "title": "Check in"
   ```

1. Enregistrez le fichier et chargez-le.
