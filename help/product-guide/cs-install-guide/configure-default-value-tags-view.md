---
title: Configuration de la valeur par défaut pour la vue Balises
description: Découvrez comment configurer la valeur par défaut de la vue Balises
exl-id: 3ab75101-4c23-4e45-bfcf-76c1f5b92c96
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# Configuration de la valeur par défaut pour la vue Balises {#id223GN0M0NDC}

AEM Guides vous permet de configurer l’état par défaut de la vue Balises dans l’éditeur web, ce qui vous permet de conserver ou de désactiver l’affichage des balises par défaut pour la session d’un nouvel utilisateur. Pour configurer la valeur par défaut de la vue Balises, procédez comme suit :

1. Téléchargez le fichier de configuration de l’interface utilisateur en vous connectant à Adobe Experience Manager en tant qu’administrateur.
1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et sélectionnez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils et cliquez sur le bouton **Profils de dossier**.
1. Cliquez sur la mosaïque **Profil global** .
1. Sélectionnez l’onglet **Configuration de l’éditeur XML** et cliquez sur l’icône **Modifier** en haut.
1. Dans la section **Configuration de l’interface utilisateur de l’éditeur XML**, cliquez sur l’icône **Télécharger** pour télécharger le fichier `ui_config.json` sur votre système local.
1. Dans le fichier `ui_config.json`, modifiez l’état d’affichage des balises par défaut en modifiant la section defaultValues comme illustré ci-dessous :

```
"defaultValues":
                {
                "tagsView": true
                }
```

1.) Enregistrez le fichier et téléchargez-le.

>[!NOTE]
>
> La préférence de l’utilisateur dans l’éditeur web pour activer/désactiver la vue Balises est prioritaire sur cette valeur par défaut. Ainsi, si un utilisateur active la vue Balises à partir de l’éditeur web, elle reste activée même au cours des sessions.

**Rubrique parente :**&#x200B;[ Personnaliser l’éditeur web](conf-web-editor.md)
