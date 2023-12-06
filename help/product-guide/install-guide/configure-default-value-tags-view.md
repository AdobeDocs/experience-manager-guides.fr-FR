---
title: Configuration de la valeur par défaut pour la vue Balises
description: Découvrez comment configurer la valeur par défaut de la vue Balises
exl-id: 52214459-74b8-47ec-982b-6176145348a8
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Configuration de la valeur par défaut pour la vue Balises {#id223GN0M0NDC}

AEM Guides vous permet de configurer l’état par défaut de la vue Balises dans l’éditeur web, ce qui vous permet de conserver la vue Balises activée ou désactivée par défaut pour la session d’un nouvel utilisateur. Pour configurer la valeur par défaut de la vue Balises, procédez comme suit :

1. Téléchargez le fichier de configuration de l’interface utilisateur en vous connectant à Adobe Experience Manager en tant qu’administrateur.
1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et choisissez **Outils**.
1. Sélectionner **Guides** dans la liste des outils, puis cliquez sur l’icône **Profils de dossier**.
1. Cliquez sur le bouton **Profil global** mosaïque.
1. Sélectionnez la variable **Configuration de l’éditeur XML** et cliquez sur l’onglet **Modifier** en haut.
1. Dans le **Configuration de l’interface utilisateur de l’éditeur XML** , cliquez sur le bouton **Télécharger** pour télécharger l’icône `ui_config.json` sur votre système local.
1. Dans le `ui_config.json` modifiez l’état d’affichage des balises par défaut en modifiant la section defaultValues comme illustré ci-dessous :

   ```json
   "defaultValues":
                   {
                   "tagsView": true
                   }
   ```

1. Enregistrez le fichier et téléchargez-le.

>[!NOTE]
>
> La préférence de l’utilisateur dans l’éditeur web pour activer/désactiver la vue Balises est prioritaire sur cette valeur par défaut. Ainsi, si un utilisateur active la vue Balises à partir de l’éditeur web, elle reste activée même au cours des sessions.

**Rubrique parente :**[ Personnalisation de l’éditeur web](conf-web-editor.md)
