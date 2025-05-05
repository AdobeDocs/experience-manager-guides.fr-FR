---
title: Création de profils d’attributs conditionnels
description: Découvrez comment créer des attributs conditionnels dans AEM Guides. Utilisez des attributs conditionnels dans le dossier et des profils globaux pour conditionner votre contenu.
exl-id: 5ec7666e-df6b-4b0d-b6c2-cdc395fcccc5
feature: Publishing
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---

# Création de profils d’attributs conditionnels {#id1843I0HN0Y4}

Au niveau de l’entreprise, il est extrêmement important de s’assurer que vous disposez d’un système de balisage standard. Les balises ou les attributs conditionnels peuvent être associés aux ressources numériques dans le référentiel, ce qui permet de publier la sortie en fonction des conditions sélectionnées. Par exemple, vous pouvez créer un attribut conditionnel pour le contenu Windows et Mac. Vous ajoutez ensuite ces attributs au contenu approprié dans vos rubriques. Au moment de publier du contenu, vous pouvez choisir de publier du contenu Windows ou Mac uniquement.

Adobe Experience Manager Guides vous permet de créer et d&#39;associer facilement des attributs conditionnels à l&#39;aide des attributs DITA appropriés. Vous pouvez définir des attributs conditionnels au niveau global ou au niveau du dossier. Les conditions définies globalement sont visibles dans tous les projets et les conditions spécifiques aux dossiers ne sont visibles que dans les projets créés dans le dossier spécifié. Les auteurs de contenu peuvent utiliser ces attributs conditionnels pour conditionner le contenu de leurs rubriques ou mappages DITA qu&#39;ils créent ou utilisent. Ces conditions peuvent ensuite être utilisées par l’éditeur pour créer des paramètres prédéfinis conditionnels. À l’aide des paramètres prédéfinis conditionnels, l’éditeur peut décider quelle condition inclure et exclure de la sortie publiée.

>[!NOTE]
>
> Vous pouvez créer ou modifier les attributs conditionnels dans un profil de dossier auquel vous avez accès. Si votre administrateur système ne vous a pas donné accès à un profil de dossier, vous ne pouvez pas créer ni modifier les attributs conditionnels dans le profil de dossier.

Pour définir des attributs conditionnels, procédez comme suit :

1. Sélectionnez le logo Adobe Experience Manager en haut et choisissez **Outils**.

1. Dans le panneau Outils, sélectionnez **Guides**.

1. Sélectionnez la mosaïque **Profils de dossier** et sélectionnez un profil de dossier.

   >[!NOTE]
   >
   > Vous ne pouvez pas modifier le profil global.

1. Sélectionnez l’onglet **Attributs conditionnels** puis sélectionnez **Modifier**.

   Le tableau Attributs conditionnels s’affiche.

1. Sélectionnez **Ajouter**.

1. Saisissez les **Nom**, **Valeur** et un **Libellé** pour l’attribut.

   Vous pouvez enregistrer un profil avec uniquement le nom d’attribut. Cependant, un attribut ne peut être utilisé que lorsqu’une valeur lui est spécifiée. Si vous spécifiez à la fois - valeur et libellé pour un attribut, l’éditeur web affiche toujours uniquement la valeur de l’attribut. Le libellé est présenté à l’administrateur de publication au moment de la création d’un paramètre prédéfini conditionnel.

   La capture d’écran suivante montre la définition de l’attribut `platform` avec la valeur `unix` et un libellé `Red Hat Linux`.

   ![](images/add-profile-new.png){align="left"}

1. Si vous souhaitez ajouter d’autres valeurs pour le même attribut, sélectionnez l’icône **+** et saisissez une valeur et un libellé supplémentaires.

1. Si vous souhaitez ajouter d’autres attributs, sélectionnez **Ajouter**.

1. Sélectionnez **Enregistrer** pour enregistrer les modifications.


L’attribut `platform` est stocké dans le système. Chaque fois qu’un auteur décide d’utiliser l’attribut `platform` dans une rubrique DITA d’un dossier, il peut afficher les valeurs dans l’onglet Propriétés de l’éditeur.

![](images/properties-tab.png){width="350" align="left"}

**Rubrique parente :**&#x200B;[ Génération de sortie](generate-output.md)
