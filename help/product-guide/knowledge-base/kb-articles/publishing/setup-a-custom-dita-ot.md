---
title: Configuration de DITA-OT personnalisé dans [!DNL AEM Guides]
description: Découvrez comment configurer DITA-OT personnalisé dans [!DNL Adobe Experience Manager Guides]
role: Admin
exl-id: f479c2cf-5b8b-4517-be97-81303468007a
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---

# Configuration de DITA-OT personnalisé dans [!DNL AEM Guides] pour les AEM

Les étapes d’ajout d’un DITA-OT personnalisé sont présentées dans la section . _Utilisation des modules externes DITA-OT personnalisés_ de _Guide d&#39;installation et de configuration_.

À un niveau élevé, les étapes sont les suivantes :

+ Obtention du DITA-OT de base
   + Si vous souhaitez obtenir une copie de DITA-OT prêt à l’emploi à partir de [!DNL AEM Guides], le télécharger à partir du chemin d’accès `/etc/fmdita/dita_resources/DITA-OT.zip`
   + Si vous souhaitez obtenir une autre version, vous pouvez télécharger à partir de [référentiel dita-ot](https://www.dita-ot.org/download)
+ Apportez des modifications à DITA-OT comme [ajout d’un nouveau module externe](https://www.dita-ot.org/dev/topics/plugins-installing.html)ou personnaliser les modules externes existants (voir l’exemple dans la section des liens connexes ci-dessous)
+ Télécharger `DITA-OT.zip` reçu à `/apps/<project-folder>/dita_resources` (la création d’un dossier de projet personnalisé est une approche recommandée)
+ Ajouter un profil DITA via **[!UICONTROL Outils]** > **[!UICONTROL Guides]** > **[!UICONTROL Profils DITA]** (utilisez le chemin DITA-OT où le DITA-OT personnalisé est téléchargé, reportez-vous à la capture d’écran ci-dessous)
  ![Profils DITA](assets/dita-profile.png)

>[!MORELIKETHIS]
>
>+ [Personnalisation des exemples de modules externes DITA-OT](https://www.dita-ot.org/dev/topics/pdf-customization.html)
