---
title: Configurer la valeur par défaut de la vue Balises
description: Découvrez comment Configurer la valeur par défaut de la vue Balises
exl-id: 52214459-74b8-47ec-982b-6176145348a8
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Configurer la valeur par défaut de la vue Balises {#id223GN0M0NDC}

AEM Guides vous permet de configurer l’état par défaut de la vue Balises dans l’éditeur web, ce qui vous permet de garder la vue Balises activée ou désactivée par défaut pour la session d’un nouvel utilisateur. Effectuez les étapes suivantes pour configurer la valeur par défaut de la vue Balises :

1. Téléchargez le fichier de configuration de l’interface utilisateur en vous connectant à Adobe Experience Manager en tant qu’administrateur.
1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils, puis cliquez sur le **Profils de dossier**.
1. Cliquez sur la mosaïque **Profil global**.
1. Sélectionnez l’onglet **Configuration de l’éditeur XML** et cliquez sur l’icône **Modifier** en haut.
1. Dans la section **Configuration de l’interface utilisateur de l’éditeur XML**, cliquez sur l’icône **Télécharger** pour télécharger le fichier `ui_config.json` sur votre système local.
1. Dans le fichier `ui_config.json`, modifiez l’état d’affichage des balises par défaut en modifiant la section defaultValues comme illustré ci-dessous :

   ```json
   "defaultValues":
                   {
                   "tagsView": true
                   }
   ```

1. Enregistrez le fichier et chargez-le.

>[!NOTE]
>
> La préférence de l’utilisateur dans l’éditeur web pour activer/désactiver la vue Balises est prioritaire par rapport à cette valeur par défaut. Ainsi, si un utilisateur ou une utilisatrice active la vue Balises à partir de l’éditeur web, elle reste activée même entre les sessions.

**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
