---
title: Configurez le DITA-OT personnalisé dans  [!DNL AEM Guides]
description: Découvrez comment configurer le DITA-OT personnalisé dans  [!DNL Adobe Experience Manager Guides]
role: Admin
exl-id: f479c2cf-5b8b-4517-be97-81303468007a
feature: DITA-OT Configuration
TQID: https://experienceleague.adobe.com/EaU6rkZL-RBkkYDhKxHNkizIVSqNzEDd-TtFlJAmREw
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 0%

---

# Configuration de DITA-OT personnalisés dans [!DNL AEM Guides] pour AEM

Les étapes d&#39;ajout d&#39;un DITA-OT personnalisé sont documentées dans la section _Utiliser des plug-ins DITA-OT personnalisés_ du _Guide d&#39;installation et de configuration_.

À un niveau élevé, les étapes sont les suivantes :

+ Obtenir le DITA-OT de base
   + Si vous souhaitez obtenir une copie du fichier DITA-OT prêt à l&#39;emploi à partir de [!DNL AEM Guides], téléchargez-la à partir du chemin `/etc/fmdita/dita_resources/DITA-OT.zip`
   + Si vous souhaitez obtenir une autre version, vous pouvez la télécharger à partir du référentiel [dita-ot](https://www.dita-ot.org/download)
+ Apportez des modifications à DITA-OT comme l&#39;[ajout d&#39;un nouveau plug-in](https://www.dita-ot.org/dev/topics/plugins-installing.html) ou la personnalisation de plug-ins existants (consultez l&#39;exemple de la section Liens connexes ci-dessous).
+ Charger les `DITA-OT.zip` reçus dans `/apps/<project-folder>/dita_resources` (la création d’un dossier de projet personnalisé est une approche recommandée)
+ Ajouter un profil DITA via **[!UICONTROL Outils]** > **[!UICONTROL Guides]** > **[!UICONTROL Profils DITA]** (utilisez le chemin DITA-OT où le DITA-OT personnalisé est chargé, reportez-vous à la capture d&#39;écran ci-dessous)
  ![&#x200B; Profils DITA &#x200B;](assets/dita-profile.png)

>[!MORELIKETHIS]
>
>+ [Personnalisation d’exemples de plug-in DITA-OT](https://www.dita-ot.org/dev/topics/pdf-customization.html)
