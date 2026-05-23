---
title: Ajout de styles personnalisés à l’éditeur web de Guides
description: Découvrez comment ajouter des styles personnalisés pour modifier l’aspect de l’éditeur web de Guides.
exl-id: 03143fb2-d05d-4103-b172-8b91880b7f9e
feature: Web Editor
role: User, Admin
TQID: https://experienceleague.adobe.com/uQc8TTz7dHxbN6-zbin-esQevLoJR-IMR1hchrwEs8M
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 300
ht-degree: 0%

---

# Ajout de styles personnalisés à l’éditeur web de Guides

Dans cet article, nous allons découvrir comment ajouter des styles personnalisés pour modifier l’aspect par défaut de l’éditeur web.

Pour ce faire, les étapes sont les suivantes :
- Ajout de styles personnalisés via la configuration de l’éditeur XML de profil de dossier
- Sélection du profil de dossier correspondant dans l’éditeur web et test des modifications


## Implémentation en prenant un exemple

Comprenons ceci avec un exemple où nous voulons afficher la description courte et le titre sous la forme d’un bloc distinct avec certains aspects de style dans l’éditeur.

![Aperçu de l’éditeur web avec des styles personnalisés](../../../assets/authoring/webeditor-customstyles-preview.png)


## Mise en œuvre de ceci


### Ajout du CSS personnalisé au profil de dossier

Utilisez les profils de dossier pour vérifier le fichier *css_layout.css* sous l’onglet « Configuration de l’éditeur XML » et ajoutez le fichier CSS avec des styles personnalisés

[Utilisez ce lien pour en savoir plus sur le profil de dossier et la configuration de la disposition du modèle CSS](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=fr#customize-the-css-template-layout)

Utilisez les éléments suivants pour configurer le style ci-dessus dans votre éditeur web :
- Utilisez [css_layout.css](../../../assets/authoring/webeditor-customstyles-css_layout.css) et chargez-le dans le profil de dossier de votre choix
- Installez le package joint [webeditor-styles-resources.zip](../../../assets/authoring/webeditor-styles-resources.zip) à l’aide du gestionnaire de packages AEM pour installer les ressources utilisées dans le fichier CSS ci-dessus

```
This will install the resources at path "/content/dam/resources" which will include sub-folders "fonts" and "images"
```


### Tests

- Ouvrir l’éditeur web
- Dans les préférences utilisateur , choisissez le profil de dossier dans lequel vous avez ajouté les styles personnalisés. Si vous l’avez ajouté au profil global, vous l’utilisez probablement déjà.
- Ouvrez une rubrique pour constater que la zone de modification doit comporter une interface utilisateur personnalisée

```
Please note this is compatible to AEM Guides version 4.2 and AEM Guides cloud version 2303 (March)
```


## Références

Vous pouvez également être intéressé par la session d’experts sur les configurations et la personnalisation de l’éditeur web, abordée dans la section [Session d’experts sur l’éditeur web](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/expert-session/webbased-authoring-jan2023.html?lang=fr)
