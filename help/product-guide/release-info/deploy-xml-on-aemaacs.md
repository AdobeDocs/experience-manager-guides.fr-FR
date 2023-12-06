---
title: Comment ajouter [!DNL AEM Guides] à votre [!DNL AEM as a Cloud Service] environnement
description: Découvrez comment ajouter [!DNL AEM Guides] à votre [!DNL AEM as a Cloud Service] environnement
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---

# [!DNL AEM Guides] déploiement as a Cloud Service

Découvrez comment ajouter [!DNL Guides] à votre [!DNL AEM as a Cloud Service] environnement.

## Déploiement manuel via le pipeline Git de Cloud Manager

Si vous avez acheté [!DNL AEM Guides] as a Cloud Service avant le 29 mars 2022, suivez les instructions de déploiement suivantes :

* Si vous recommencez, vous pouvez remplacer le code généré automatiquement par [!UICONTROL Cloud Manager] avec le code du référentiel ci-dessous qui comporte déjà un module externe XML intégré : https://github.com/Adobe-TCS/XML-documentation-for-AEMaaCS

* Si des personnalisations sont déjà archivées dans [!UICONTROL Cloud Manager] git repo, vous pouvez consulter le référentiel ci-dessous pour obtenir des instructions sur la manière d’ajouter un module externe XML à votre code existant : https://github.com/Adobe-TCS/DoX-Installer-for-AEMaaCS

## Déploiement Via Cloud Manager

Si vous êtes un client qui a acheté [!DNL AEM Guides] as a Cloud Service le 03/29/2022 ou après, suivez ces instructions pour ajouter [!DNL Guides] à votre [!DNL AEM as a Cloud Service] environnement :

1. Connexion à [!UICONTROL Cloud Manager].

1. Éditez le programme pour lequel vous souhaitez configurer [!DNL AEM Guides].

1. Basculer vers **[!UICONTROL Solutions et modules complémentaires]** .

1. Dans le **[!UICONTROL Solutions et modules complémentaires]** tableau, cliquez sur **[!UICONTROL Ressources]**.

1. Sélectionner **[!UICONTROL Guides]** et sélectionnez **[!UICONTROL Enregistrer]**.

Vous avez correctement configuré votre programme pour la configuration automatique de la solution AEM Guides.

![Configuration de la solution AEM Guides](assets/addon-configuration.png)

>[!NOTE]
>
>Pour installer [!DNL AEM Guides] dans n’importe quel environnement du programme intégré, vous devez exécuter le pipeline associé à l’environnement. Aucune configuration supplémentaire n’est requise dans votre base de code Git CM pour l’installation. [!DNL AEM Guides].
