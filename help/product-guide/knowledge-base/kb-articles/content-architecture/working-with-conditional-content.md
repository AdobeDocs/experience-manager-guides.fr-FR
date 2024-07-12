---
title: Utilisation de contenu conditionnel
description: Découvrez comment créer des conditions, puis configurer la génération de contenu conditionnel dans [!DNL AEM Guides]
role: User
exl-id: a86007e3-48d1-458b-84a7-b683e113e5b2
feature: Publishing
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 5%

---

# Utilisation de contenu conditionnel

**Cas d’utilisation**


* Les auteurs peuvent définir des conditions sur un élément de contenu afin qu’ils puissent contrôler s’il est affiché dans la sortie.

* Lors de la publication, les auteurs peuvent choisir d’afficher ou de masquer différentes conditions.

* Par exemple, les auteurs peuvent ajouter des attributs comme version 1.0 et version 2.0 dans le contenu, et utiliser des conditions pour inclure la version 1.0 pour la version 1.0 et exclure la version 2.0.

**Étape 1**

Définissez les conditions relatives à la documentation dans les [!UICONTROL profils de dossier] :
Reportez-vous à la section **Configuration d’attributs conditionnels pour les profils globaux ou au niveau du dossier** dans la [page 69 du Guide d’installation et de configuration](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

![Configuration de conditions dans les profils de dossier](assets/conditions-in-profiles.png)

**Étape 2**

Sélectionnez le **[!UICONTROL profil de dossier]** défini à l’étape 1 dans **Préférences utilisateur** dans l’éditeur XML :
Reportez-vous à la section **Préférences utilisateur** dans la [page 41 du Guide de l’utilisateur](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)


**Étape 3**

Utilisez les conditions pour conditionner les sections de contenu :
Reportez-vous à la section **Conditions** de la [page 90 du Guide de l’utilisateur](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)

![Conditions d’utilisation dans l’éditeur web](assets/conditions-in-web-editor.png)

**Étape 4**

Définissez des paramètres prédéfinis de condition au niveau du mappage pour choisir les conditions à activer dans la sortie :
Reportez-vous à la section **Utiliser des paramètres prédéfinis de condition** dans la [page 249 du Guide de l’utilisateur](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)
