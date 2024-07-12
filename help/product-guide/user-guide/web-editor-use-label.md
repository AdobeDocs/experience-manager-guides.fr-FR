---
title: Utilisation des libellés
description: Découvrez l’utilisation des libellés pour différentes versions d’un fichier dans AEM Guides. Découvrez comment ajouter ou supprimer une étiquette à une version d’une rubrique.
exl-id: d116906d-b469-4a97-b0af-4fadbe15222b
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---

# Utilisation des libellés {#id164JBG0M0T1}

AEM Guides vous permet d’ajouter des étiquettes à différentes versions d’un fichier. Vous pouvez utiliser ces libellés pour spécifier la version que vous souhaitez inclure dans une ligne de base pour la publication. Pour plus d’informations sur l’utilisation des libellés pour créer une ligne de base, voir [Utilisation de la ligne de base](generate-output-use-baseline-for-publishing.md#).

Par exemple, si vous souhaitez utiliser *version 1.0* d’une rubrique dans *release 1.0* et *version 1.1* de la même rubrique dans *release 2.0*, vous pouvez ajouter l’étiquette *release 1.0* sur les *version 1.0* et *release{2.0} Libellé 13} sur la* version 1.1 *.*

Une fois que vous avez ajouté les libellés, vous pouvez créer une ligne de base et spécifier la version de la rubrique à inclure pour la publication à l’aide de cette ligne de base. Pour voir quelle version doit être incluse ou exclues dans une ligne de base, vous pouvez utiliser l’option Historique des versions .

## Ajouter un libellé

Pour ajouter un libellé à votre rubrique, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, sélectionnez une rubrique.
1. Cliquez sur l’icône du sélecteur de rail de gauche et sélectionnez **Historique de version**.
1. Dans l’historique des versions, cliquez sur une version dans laquelle vous souhaitez ajouter un libellé.

1. Saisissez le libellé de la version sélectionnée et appuyez sur Entrée. Par exemple, *2.6 Release*.

   >[!NOTE]
   >
   > Vous ne pouvez pas ajouter le même libellé aux différentes versions d’une rubrique. Vous pouvez toutefois ajouter plusieurs libellés à la même version d’une rubrique.

   Les libellés s’affichent dans l’historique des versions de la rubrique sélectionnée. La capture d’écran suivante affiche les libellés *x.x Release* et *Guide de l’utilisateur* ajoutés à la version mise en surbrillance de la rubrique.

   ![](images/labels.png){width="300" align="left"}

>[!NOTE]
>
> Une ligne de base vous permet d’ajouter un libellé à plusieurs rubriques. Pour plus d’informations sur l’ajout de libellés à l’aide de la ligne de base, voir [Ajout d’étiquettes à une ligne de base](generate-output-use-baseline-for-publishing.md#id184KD0T305Z).

## Suppression d’une étiquette

Pour supprimer un libellé, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, sélectionnez une rubrique à laquelle un libellé est ajouté.
1. Cliquez sur l’icône du sélecteur de rail de gauche et sélectionnez **Historique de version**.

   Dans l’historique des versions, vous verrez toutes les versions d’une rubrique et les libellés qui y sont associés. L’image suivante présente un exemple de différentes versions d’une rubrique auxquelles sont ajoutés des libellés pour une version.

   ![](images/labels.png){width="300" align="left"}

1. Cliquez sur le bouton de suppression \(**X**\) pour supprimer l’étiquette.

   ![](images/delete-labels.png){width="300" align="left"}


**Rubrique parente :**[ Utilisation de l’éditeur web](web-editor.md)
