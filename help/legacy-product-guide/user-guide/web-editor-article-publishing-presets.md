---
title: Création de paramètres prédéfinis de sortie à partir de l’éditeur web
description: Créez des paramètres prédéfinis de sortie à partir de l’éditeur web. Découvrez comment modifier, renommer, dupliquer et supprimer un paramètre prédéfini de sortie dans AEM Guides.
feature: Authoring, Features of Web Editor, Publishing
role: User
hide: true
exl-id: ce8e3614-907b-4172-a8f0-e81e4dc096df
TQID: https://experienceleague.adobe.com/nCmtXuQXfOVVHbmGrRT6rVzEa6NlR-o9TGmwhqczWPs
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0efid: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 370
ht-degree: 0%

---

# Création de paramètres prédéfinis de sortie à partir de l’éditeur web {#id218CL400JW3}

Pour créer des paramètres prédéfinis de sortie pour votre plan DITA, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de mappage à modifier.

1. Pour obtenir un verrou exclusif sur le fichier de mappage, sélectionnez le fichier de mappage et cliquez sur **Extraire**.

1. Sélectionnez l’option **Modifier les rubriques** dans le menu d’actions du fichier de mappage.

   Le fichier de mappage est ouvert pour modification dans l’éditeur web.

   >[!NOTE]
   >
   > Vous pouvez ajouter ou supprimer n’importe quelle rubrique de la carte à l’aide de l’éditeur de cartes avancé. Pour plus d’informations, voir [ Utilisation de l’éditeur de cartes avancé ](map-editor-advanced-map-editor.md#).

1. Dans l&#39;onglet **Sortie**, sélectionnez l&#39;icône + pour créer un paramètre prédéfini de sortie pour votre plan DITA.

   ![](images/output-tab-preset_cs.png){width="350"}

1. Saisissez le nom du paramètre prédéfini dans la boîte de dialogue Ajouter un paramètre prédéfini , puis cliquez sur **Ajouter**.

1. Saisissez les informations de configuration suivantes.

   1. Sélectionnez les options requises dans l’onglet **Général**. Vous pouvez choisir de créer un paramètre prédéfini de sortie avec ou sans conditions. Vous pouvez également utiliser un fichier DITVAL. AEM Guides vous permet également de sélectionner une ligne de base pour publier une version spécifique de votre plan DITA.
   1. Saisissez les détails du site AEM dans l’onglet **AEM**. **Site** affiche la liste des AEM Sites disponibles dans votre référentiel AEM. **Catégorie**, **Modèle de section** et **Modèle d’article** sont les composants structurels utilisés pour organiser l’aspect de votre sortie. Ils sont prédéfinis dans le modèle de site AEM.

      >[!NOTE]
      >
      > Actualisez chaque liste déroulante pour obtenir la classification supplémentaire dans la liste déroulante suivante.

   1. Dans l’onglet **Articles**, sélectionnez les rubriques pour lesquelles vous souhaitez générer la sortie.
1. Sélectionnez l’icône **Générer le paramètre prédéfini** en haut pour générer la sortie.

   ![](images/add-preset-articles-tab_cs.png){width="800"}

1. Vous verrez le statut du processus de génération de sortie. La colonne **Rubriques** répertorie les rubriques pour lesquelles une sortie est générée tandis que la colonne **Statut** affiche le statut de publication de chaque rubrique.

   Pour afficher la sortie, placez le pointeur de la souris sur la rubrique et cliquez sur Afficher la sortie.

   ![](images/add-preset-output-generated_cs.png){width="800"}


>[!NOTE]
>
> Vous pouvez également Modifier, Renommer, Dupliquer ou Supprimer un paramètre prédéfini de sortie existant à partir du menu Options.

![](images/edit-preset_cs.png){width="550"}

**Rubrique parente :**[ Publication basée sur des articles dans l’éditeur web](web-editor-article-publishing.md)
