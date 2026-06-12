---
title: Configurer la génération PDF sur une seule rubrique
description: Découvrez comment Configurer la génération PDF à rubrique unique.
exl-id: 5b66fd3b-6450-49ce-b06e-d2d5bab37990
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/DinL1ZwovhmP61iQOQkW6XR-ALahlONxOU4e5UXpSGY
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9baid: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 271
ht-degree: 0%

---

# Configurer la génération PDF sur une seule rubrique {#id22ADC70M0XA}

Avec AEM Guides, vous pouvez générer la PDF de rubriques individuelles ou un fichier de mappage entier. Vous pouvez publier vos rubriques au format PDF à l’aide de PDF natif ou de la méthode DITA-OT. Utilisez la méthode PDF native pour générer une sortie PDF riche en fonctionnalités basée sur les normes des médias paginés W3C, CSS3 et CSS. Vous pouvez utiliser la méthode DITA-OT pour générer une sortie PDF pour un mappage à partir du tableau de bord de mappage.

>[!NOTE]
>
> Le PDF natif est la méthode par défaut pour générer un PDF dans la version actuelle d’AEM Guides.

Pour activer l’ancienne génération PDF via le DITA-OT à partir du mode d’aperçu de rubrique, procédez comme suit :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur et téléchargez le fichier de configuration de l’interface utilisateur.

1. Pour ce faire, cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils, puis cliquez sur le **Profils de dossier**.
1. Cliquez sur la mosaïque **Profil global**.
1. Sélectionnez l’onglet **Configuration de l’éditeur XML** et cliquez sur l’icône **Modifier** en haut
1. Cliquez sur l’icône **Télécharger** pour télécharger le fichier ui\_config.json sur votre système local. Vous pouvez ensuite apporter des modifications au fichier , puis le charger.
1. Dans le fichier `ui_config.json`, recherchez la configuration suivante :

   ```
   {
                           "component": "button",
                           "variant": "action",
                           "quiet": true,
                           "icon": "filePDF",
                           "title": "Download as PDF",
                           "on-click": "EDITOR_SAVE_AS_PDF"
                           }
   ```

   et remplacez-le par .

   ```
   {
                           "component": "button",
                           "icon": "filePDF",
                           "variant": "action",
                           "quiet": true, "title": "Export as PDF",
                           "on-click": "DOWNLOAD_TOPIC_PDF",
                           "show" : ["@isPreviewMode", "@isXmlMode"]
                           }
   ```

1. Enregistrez le fichier et chargez-le.

Après avoir effectué les étapes données ci-dessus, si vous choisissez le même profil de dossier dans les Préférences utilisateur dans l’éditeur web, vous verrez l’option de génération PDF dans le mode d’aperçu d’une rubrique.

**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
