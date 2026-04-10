---
title: Configurer la valeur par défaut de la vue Balises
description: Découvrez comment Configurer la valeur par défaut de la vue Balises
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
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

   ```
   "defaultValues":
               {
               "tagsView": true
               }
   ```

1. Enregistrez le fichier et chargez-le.

>[!NOTE]
>
> La préférence de l’utilisateur dans l’éditeur web pour activer/désactiver la vue Balises est prioritaire par rapport à cette valeur par défaut. Ainsi, si un utilisateur ou une utilisatrice active la vue Balises à partir de l’éditeur web, elle reste activée même entre les sessions.

**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur web](customize-overview.md)
