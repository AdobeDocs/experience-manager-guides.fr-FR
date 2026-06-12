---
title: Configurer la valeur par défaut de la vue Balises
description: Découvrez comment Configurer la valeur par défaut de la vue Balises
exl-id: 52214459-74b8-47ec-982b-6176145348a8
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/5Dh86YzZVL8vKnHpDPLNijpDxISnpbgkcfCIbUNxZTo
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
source-wordcount: 214
ht-degree: 0%

---

# Configurer la valeur par défaut de la vue Balises {#id223GN0M0NDC}

AEM Guides vous permet de configurer l’état par défaut de la vue Balises dans l’éditeur web, ce qui vous permet de garder la vue Balises activée ou désactivée par défaut pour la session d’un nouvel utilisateur.Pour configurer la valeur par défaut de la vue Balises, procédez comme suit :

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

**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur web](conf-web-editor.md)
