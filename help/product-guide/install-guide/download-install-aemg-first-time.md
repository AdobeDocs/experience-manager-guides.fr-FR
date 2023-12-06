---
title: Télécharger et installer AEM Guides pour la première fois
description: Découvrez comment télécharger et installer AEM Guides pour la première fois
exl-id: 830a4381-303c-419c-b87f-9563352a7eeb
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# Télécharger et installer AEM Guides pour la première fois {#id213BCL00KEV}

Pour télécharger et installer AEM Guides pour la première fois sur un ordinateur, procédez comme suit :

>[!IMPORTANT]
>
> Si vous souhaitez utiliser Livefyre avec AEM Guides, veillez à installer les versions Livefyre antérieures à la version 3.0 avant d’installer AEM Guides. Si vous utilisez la version 3.0 ou ultérieure de Livefyre, cette restriction n’existe pas.

1. Téléchargez AEM Guides à partir du portail de distribution de logiciels Adobe.

1. Connectez-vous à votre instance AEM et accédez au gestionnaire de modules CRX. L’URL par défaut pour accéder au gestionnaire de packages est la suivante :

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

   Le gestionnaire de modules gère les modules de votre installation AEM locale. Pour plus d’informations sur l’utilisation du gestionnaire de modules, voir [Utilisation de modules](https://helpx.adobe.com/fr/experience-manager/6-5/sites/administering/using/package-manager.html) dans la documentation AEM.

   ![](assets/package-manager.png){width="650" align="left"}

1. Pour charger le module AEM Guides, cliquez sur **Télécharger le module**.

1. Dans la boîte de dialogue Télécharger le package, accédez au fichier AEM Guides que vous avez téléchargé à l’étape 1, puis cliquez sur **OK**.

   Le package est téléchargé sur votre instance AEM.

1. Pour installer le package, cliquez sur **Installer**.

   ![](assets/install-package.png){width="650" align="left"}

1. Dans la boîte de dialogue Installer le package, cliquez sur **Installer**.

1. Pour commencer à utiliser les AEM Guides, cliquez sur le bouton Accueil . ![](assets/home-button.png) dans le coin supérieur gauche du gestionnaire de modules CRX.


>[!NOTE]
>
> Exécutez la procédure d’installation sur toutes les instances des serveurs AEM de votre configuration.

**Rubrique parente :**[ Télécharger et installer](download-install.md)
