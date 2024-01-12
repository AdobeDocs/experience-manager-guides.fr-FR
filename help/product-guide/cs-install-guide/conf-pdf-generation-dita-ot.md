---
title: Configuration de la génération d’un PDF de rubrique unique
description: Découvrez comment configurer la génération d’un PDF de rubrique unique
exl-id: 5b66fd3b-6450-49ce-b06e-d2d5bab37990
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Configuration de la génération d’un PDF de rubrique unique {#id22ADC70M0XA}

Avec les AEM Guides, vous pouvez générer le PDF de rubriques individuelles ou d’un fichier de mappage entier. Vous pouvez publier vos rubriques dans un format PDF à l’aide d’un PDF natif ou d’une méthode DITA-OT. Utilisez la méthode de PDF native pour générer une sortie de PDF riche en fonctionnalités basée sur les normes W3C CSS3 et CSS paged Media. Vous pouvez utiliser la méthode DITA-OT pour générer une sortie de PDF pour une carte à partir du tableau de bord de la carte.

>[!NOTE]
>
> Le PDF natif est la méthode par défaut pour générer un PDF dans la version actuelle des AEM Guides.

Pour activer l’ancienne génération de PDF via DITA-OT à partir du mode d’aperçu de rubrique, procédez comme suit :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur et téléchargez le fichier de configuration de l’interface utilisateur.

1. Pour ce faire, cliquez sur le lien Adobe Experience Manager en haut de l’écran et choisissez **Outils**.
1. Sélectionner **Guides** dans la liste des outils, puis cliquez sur l’icône **Profils de dossier**.
1. Cliquez sur le bouton **Profil global** mosaïque.
1. Sélectionnez la variable **Configuration de l’éditeur XML** et cliquez sur **Modifier** icône en haut
1. Cliquez sur le bouton **Télécharger** pour télécharger le fichier ui\_config.json sur votre système local. Vous pouvez ensuite apporter des modifications au fichier, puis charger le même fichier.
1. Dans le `ui_config.json` recherchez la configuration suivante :

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

   et remplacez-le par

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

1. Enregistrez le fichier et téléchargez-le.

Après avoir effectué les étapes ci-dessus, si vous choisissez le même profil de dossier dans Préférences utilisateur dans l’éditeur web, l’option de génération de PDF s’affiche en mode d’aperçu d’une rubrique.

**Rubrique parente :**[ Personnalisation de l’éditeur web](conf-web-editor.md)
