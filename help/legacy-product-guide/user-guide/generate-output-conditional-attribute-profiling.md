---
title: Création de profils d’attributs conditionnels
description: Découvrez comment créer des attributs conditionnels dans AEM Guides. Utilisez des attributs conditionnels dans le dossier et des profils globaux pour conditionner votre contenu.
feature: Publishing
role: User
hide: true
exl-id: f8397acf-acd3-4e68-adce-9adbbef55337
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# Création de profils d’attributs conditionnels {#id1843I0HN0Y4}

Au niveau de l’entreprise, il est extrêmement important de s’assurer que vous disposez d’un système de balisage standard. Les balises ou les attributs conditionnels peuvent être associés aux ressources numériques dans le référentiel, ce qui permet de publier la sortie en fonction des conditions sélectionnées. Par exemple, vous pouvez créer un attribut conditionnel pour le contenu Windows et Mac. Vous ajoutez ensuite ces attributs au contenu approprié dans vos rubriques. Au moment de publier du contenu, vous pouvez choisir de publier du contenu Windows ou Mac uniquement.

AEM Guides vous permet de créer et d&#39;associer facilement des attributs conditionnels à l&#39;aide des attributs DITA appropriés. Vous pouvez définir des attributs conditionnels au niveau global ou au niveau du dossier. Les conditions définies globalement sont visibles dans tous les projets et les conditions spécifiques aux dossiers ne sont visibles que dans les projets créés dans le dossier spécifié. Les auteurs de contenu peuvent utiliser ces attributs conditionnels pour conditionner le contenu de leurs rubriques ou mappages DITA qu&#39;ils créent ou utilisent. Ces conditions peuvent ensuite être utilisées par l’éditeur pour créer des paramètres prédéfinis conditionnels. À l’aide des paramètres prédéfinis conditionnels, l’éditeur peut décider quelle condition inclure et exclure de la sortie publiée.

>[!NOTE]
>
> Vous pouvez créer ou modifier les attributs conditionnels dans un profil de dossier auquel vous avez accès. Si votre administrateur système ne vous a pas donné accès à un profil de dossier, vous ne pouvez pas créer ni modifier les attributs conditionnels dans le profil de dossier.

Pour définir des attributs conditionnels, procédez comme suit :

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils.

1. Cliquez sur la mosaïque **Profils de dossier** et sélectionnez un profil de dossier.

   >[!NOTE]
   >
   > Vous ne pouvez pas modifier le profil global.

1. Cliquez sur l’onglet **Attributs conditionnels**, puis sur **Modifier**.

   Le tableau Attributs conditionnels s’affiche.

1. Cliquez sur **Ajouter**.

1. Saisissez les **Nom**, **Valeur** et un **Libellé** pour l’attribut.

   You can save a profile with only the attribute name. However, an attribute can only be used when it has a value specified to it. If you specify both - value and label for an attribute, the Web Editor would still show only the value of the attribute. The label is shown to the publishing administrator at the time of creating conditional preset.

   The following screenshot shows the definition for the `platform` attribute with value of `unix` and a label of `Red Hat Linux`.

   ![](images/add-profile.png){width="800" align="left"}

1. If you want to add more values for the same attribute, click the **+** icon and enter additional value and label.

1. If you want to add more attributes, click **Add**.

1. Cliquez sur **Enregistrer** pour enregistrer les modifications.


The `platform` attribute is stored in the system. Whenever an author decides to use the `platform` attribute in a DITA topic in a folder, they will see the values in the Properties tab in the Web Editor.

![](images/properties-tab.png){width="350" align="left"}

**Rubrique parente :**&#x200B;[&#x200B; Génération de sortie](generate-output.md)
