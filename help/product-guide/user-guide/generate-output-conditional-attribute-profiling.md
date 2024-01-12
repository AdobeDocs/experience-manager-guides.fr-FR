---
title: profilage conditionnel des attributs
description: Découvrez comment créer des attributs conditionnels dans AEM Guides. Utilisez des attributs conditionnels dans le dossier et les profils globaux pour conditionner votre contenu.
exl-id: 5ec7666e-df6b-4b0d-b6c2-cdc395fcccc5
feature: Publishing
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# profilage conditionnel des attributs {#id1843I0HN0Y4}

Au niveau de l’entreprise, il est extrêmement important de s’assurer que vous disposez d’un système de balisage standard. Les balises ou les attributs conditionnels peuvent être associés à des ressources numériques dans le référentiel, ce qui permet de publier la sortie en fonction des conditions sélectionnées. Par exemple, vous pouvez créer un attribut conditionnel pour le contenu Windows et Mac. Vous ajoutez ensuite ces attributs au contenu approprié dans vos rubriques. Au moment de la publication du contenu, vous pouvez choisir de publier du contenu sous Windows ou Mac uniquement.

AEM Guides vous permet de créer et d’associer facilement des attributs conditionnels à l’aide des attributs DITA appropriés. Vous pouvez définir des attributs conditionnels au niveau global ou au niveau du dossier. Les conditions définies globalement sont visibles pour tous les projets et les conditions spécifiques aux dossiers ne sont visibles que dans les projets créés dans le dossier spécifié. Les auteurs de contenu peuvent utiliser ces attributs conditionnels pour conditionner le contenu de leurs rubriques ou mappages DITA qu’ils créent ou utilisent. Ces conditions peuvent ensuite être utilisées par l’éditeur pour créer des paramètres prédéfinis conditionnels. À l’aide des paramètres prédéfinis conditionnels, l’éditeur peut choisir la condition à inclure et à exclure de la sortie publiée.

>[!NOTE]
>
> Vous pouvez créer ou modifier les attributs conditionnels dans un profil de dossier auquel vous avez accès. Si votre administrateur système ne vous a pas donné accès à un profil de dossier, vous ne pouvez pas créer ni modifier les attributs conditionnels dans le profil de dossier.

Pour définir des attributs conditionnels, procédez comme suit :

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et choisissez **Outils**.

1. Sélectionner **Guides** dans la liste des outils.

1. Cliquez sur le bouton **Profils de dossier** et sélectionnez un profil de dossier.

   >[!NOTE]
   >
   > Vous ne pouvez pas modifier le profil global.

1. Cliquez sur le bouton **Attributs conditionnels** et cliquez sur **Modifier**.

   Le tableau Attributs conditionnels s’affiche.

1. Cliquez sur **Ajouter**.

1. Saisissez le **Nom**, **Valeur**, et a **Libellé** pour l’attribut .

   Vous pouvez enregistrer un profil avec uniquement le nom de l’attribut. Cependant, un attribut ne peut être utilisé que s’il a une valeur qui lui est spécifiée. Si vous spécifiez à la fois la valeur et le libellé d’un attribut, l’éditeur Web n’affichera que la valeur de l’attribut. Le libellé s’affiche pour l’administrateur de publication au moment de la création d’un paramètre prédéfini conditionnel.

   La capture d’écran suivante montre la définition de la variable `platform` avec la valeur de `unix` et un libellé de `Red Hat Linux`.

   ![](images/add-profile.png){width="800" align="left"}

1. Si vous souhaitez ajouter d’autres valeurs pour le même attribut, cliquez sur le bouton **+** et saisissez une valeur et un libellé supplémentaires.

1. Pour ajouter d’autres attributs, cliquez sur **Ajouter**.

1. Cliquez sur **Enregistrer** pour enregistrer les modifications.


La variable `platform` est stocké dans le système. Lorsqu’un auteur décide d’utiliser la variable `platform` dans une rubrique DITA dans un dossier, les valeurs s’affichent dans l’onglet Propriétés de l’éditeur web.

![](images/properties-tab.png){width="350" align="left"}

**Rubrique parente :**[ Génération de sortie](generate-output.md)
