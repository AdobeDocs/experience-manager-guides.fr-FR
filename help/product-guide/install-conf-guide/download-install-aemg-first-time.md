---
title: Télécharger et installer AEM Guides pour la première fois
description: Découvrez comment télécharger et installer AEM Guides pour la première fois
feature: Introduction, Installation
role: Admin
level: Experienced
source-git-commit: 453da51a42984b912547570f2e1de70806b41171
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 0%

---

# Télécharger et installer AEM Guides pour la première fois {#id213BCL00KEV}

Pour télécharger et installer AEM Guides pour la première fois, procédez comme suit :

>[!IMPORTANT]
>
> Si vous souhaitez utiliser Livefyre avec AEM Guides, assurez-vous d’installer les versions de Livefyre antérieures à la version 3.0 avant d’installer AEM Guides. Si vous utilisez Livefyre version 3.0 ou ultérieure, il n’existe aucune restriction de ce type.

1. Téléchargez AEM Guides à partir du [portail de distribution logicielle Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).

   >[!NOTE]
   >
   >Avant d’installer Experience Manager Guides, assurez-vous que votre système répond aux [ exigences techniques ](../install-conf-guide/aemg-technical-requirements.md).

1. Connectez-vous à votre instance AEM et accédez au gestionnaire de packages CRX. L’URL par défaut pour accéder au gestionnaire de packages est :

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

   Le gestionnaire de packages gère les packages sur votre installation AEM locale. Pour plus d’informations sur l’utilisation du gestionnaire de packages, consultez [ Utilisation des packages ](https://helpx.adobe.com/fr/experience-manager/6-5/sites/administering/using/package-manager.html) dans la documentation d’AEM.

   ![](assets/package-manager.png){width="650" align="left"}

1. Pour télécharger le package AEM Guides, cliquez sur **Télécharger le package**.

1. Dans la boîte de dialogue Charger le package , accédez au fichier AEM Guides téléchargé à l’étape 1 et cliquez sur **OK**.

   Le package est chargé sur votre instance AEM.

1. Pour installer le package, cliquez sur **Installer**.

   ![](assets/install-package.png){width="650" align="left"}

1. Dans la boîte de dialogue Installer le package , cliquez sur **Installer**.

1. Pour commencer à utiliser AEM Guides, cliquez sur le bouton Accueil ![](assets/home-button.png) dans le coin supérieur gauche du gestionnaire de packages CRX.


>[!NOTE]
>
> Effectuez la procédure d’installation sur toutes les instances des serveurs AEM de votre configuration.
