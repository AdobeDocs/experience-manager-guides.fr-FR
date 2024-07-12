---
title: Configurer le titre des icônes d’archivage et d’extraction
description: Découvrez comment configurer le titre des icônes d’archivage et d’extraction
exl-id: a8888a17-e819-4fa2-bb6f-cafe1002803a
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---

# Configuration du titre des icônes d’archivage et d’extraction

AEM Guides vous permet de configurer le titre des icônes d’archivage et d’extraction dans l’éditeur web. Effectuez les étapes suivantes pour configurer le titre des icônes d’archivage et d’extraction :

1. Téléchargez le fichier de configuration de l’interface utilisateur en vous connectant à Adobe Experience Manager en tant qu’administrateur.
1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et sélectionnez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils et cliquez sur le bouton **Profils de dossier**.
1. Cliquez sur la mosaïque **Profil global** .
1. Sélectionnez l’onglet **Configuration de l’éditeur XML** et cliquez sur l’icône **Modifier** en haut.
1. Dans la section **Configuration de l’interface utilisateur de l’éditeur XML**, cliquez sur l’icône **Télécharger** pour télécharger le fichier `ui_config.json` sur votre système local.
1. Dans le fichier `ui_config.json`, modifiez le titre dans la section &quot;topbar&quot;. Vous pouvez modifier les valeurs suivantes :

   ```json
   //Change title to "Check out" instead of "Lock"
           "title": "Check out"
   
   //Change title to "Check in" instead of "@checkOutBy
            "title": "Check in"
   ```

1. Enregistrez le fichier et téléchargez-le.
