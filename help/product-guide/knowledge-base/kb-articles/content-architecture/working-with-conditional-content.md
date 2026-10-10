---
title: Utilisation de contenu conditionnel
description: Découvrez comment créer des conditions, puis configurer la génération de contenu conditionnel dans [!DNL AEM Guides]
role: User
exl-id: a86007e3-48d1-458b-84a7-b683e113e5b2
feature: Publishing
TQID: 'https://experienceleague.adobe.com/3Gz6-sJn7dvzJSlnKgRoRqpFTqtj5fiVlAjOv0lbD1o'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
    internal-label: Profiles
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 3%
---
# Utilisation de contenu conditionnel

**Cas d’utilisation**

* Les auteurs peuvent définir des conditions sur un élément de contenu afin de pouvoir contrôler s’il s’affiche dans la sortie.

* Les auteurs peuvent choisir, lors de la publication, d’afficher ou de masquer différentes conditions.

* Par exemple, les auteurs peuvent ajouter des attributs en tant que version 1.0 et version 2.0 dans le contenu et utiliser des conditions pour inclure la version 1.0 pour la version 1.0 et exclure la version 2.0.

**Étape 1**

Définissez les conditions relatives à la documentation dans [!UICONTROL Profils de dossier] :
Reportez-vous à la section **Configurer des attributs conditionnels pour les profils globaux ou au niveau du dossier** à la [Page 69 du Guide d’installation et de configuration](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

![Configurer des conditions dans des profils de dossier](assets/conditions-in-profiles.png)

**Étape 2**

Sélectionnez le **[!UICONTROL Profil de dossier]** défini à l’étape 1 dans **Préférences utilisateur** dans l’éditeur XML :
Reportez-vous à la section **Préférences utilisateur** à la [Page 41 du Guide de l’utilisateur](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)


**Étape 3**

Utilisez les conditions pour conditionner les sections de contenu :
Reportez-vous à la section **Conditions** à la [page 90 du guide de l’utilisateur](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)

![Utilisation de conditions dans l’éditeur](assets/conditions-in-web-editor.png)

**Étape 4**

Définissez des paramètres prédéfinis de condition au niveau du mappage pour choisir les conditions à activer dans la sortie :
Reportez-vous à la section **Utilisation de paramètres prédéfinis de condition** à la [Page 249 du guide de l’utilisateur](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)
