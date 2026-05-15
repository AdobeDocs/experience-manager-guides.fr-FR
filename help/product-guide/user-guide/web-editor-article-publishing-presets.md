---
title: Création de paramètres prédéfinis de sortie à partir de l’éditeur web
description: Créez des paramètres prédéfinis de sortie à partir de l’éditeur web. Découvrez comment modifier, renommer, dupliquer et supprimer un paramètre prédéfini de sortie dans AEM Guides.
exl-id: cd38b039-ef91-45c9-a226-433e57b09873
feature: Authoring, Features of Web Editor, Publishing
role: User
TQID: https://experienceleague.adobe.com/e5BEPmlmFDY2ipC8nNQPjrgGx3cV6AaD4PmZYw4hAYI
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0efid: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 368
ht-degree: 0%

---

# Création de paramètres prédéfinis de sortie pour la base de connaissances à partir de l’éditeur {#id218CL400JW3}

Pour créer des paramètres prédéfinis de sortie pour votre plan DITA, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de mappage à modifier.

1. Pour obtenir un verrouillage exclusif sur le fichier de mappage, sélectionnez le fichier de mappage et sélectionnez **Extraire**.

1. Sélectionnez l’option **Modifier les rubriques** dans le menu d’actions du fichier de mappage.

   Le fichier de mappage est ouvert pour modification dans l’éditeur.

   >[!NOTE]
   >
   > Vous pouvez ajouter ou supprimer n’importe quelle rubrique de la carte à l’aide de l’éditeur de cartes avancé. Pour plus d’informations, consultez la section [Utilisation de l’éditeur de carte avancé](map-editor-advanced-map-editor.md#).

1. Sélectionnez l’icône **Ouvrir dans la console de mappage**. La carte s’ouvre dans la console de carte.

1. Accédez à l&#39;onglet **Paramètres prédéfinis de sortie** et sélectionnez l&#39;icône + pour créer un paramètre prédéfini de sortie pour votre plan DITA.

1. Sélectionnez **Base de connaissances** dans la liste déroulante **Type**, saisissez un nom, puis sélectionnez **Adobe Experience Manager** dans la boîte de dialogue **Nouveau paramètre prédéfini de sortie**.
1. Sélectionnez l’option **Ajouter au profil du dossier actuel** pour créer un paramètre prédéfini de sortie pour le profil du dossier actuel. ![icône de profil de dossier](images/global-preset-icon.svg) l’icône indique un paramètre prédéfini de niveau de profil de dossier.

   En savoir plus sur la [Gestion des paramètres prédéfinis de sortie de profil global et de dossier](./web-editor-manage-output-presets.md).

1. Sélectionnez **Ajouter**.

   Le paramètre prédéfini de la base de connaissances est créé.


   ![Nouveau ](images/knowledge-base-preset-dialog-box.png)

Une fois le paramètre prédéfini créé, vous pouvez générer la sortie pour des articles spécifiques de la base de connaissances. Pour ce faire, accédez à l’onglet **Articles** et sélectionnez les rubriques pour lesquelles vous souhaitez générer la sortie.
1. Sélectionnez **Générer la sortie** en haut pour générer la sortie.

   ![](images/add-preset-articles-tab_cs.png)

1. Dans l’invite **Confirmer les fichiers à publier**, sélectionnez les fichiers à publier et confirmez en sélectionnant **Publier**.

   ![Nouveau ](images/knowledge-base-confirm-files-for-publishing.png)

Vous verrez l’état du processus de génération de sortie. La colonne **Rubriques** répertorie les rubriques pour lesquelles une sortie est générée tandis que la colonne **Statut** affiche le statut de publication de chaque rubrique.


![](images/add-preset-output-generated_cs.png)

Pour afficher la sortie, fermez la boîte de dialogue Sortie générée et sélectionnez **Afficher la sortie** sur la page du paramètre prédéfini.


>[!NOTE]
>
> Vous pouvez également Renommer, Dupliquer ou Supprimer un paramètre prédéfini de sortie existant à partir du menu Options.



**Rubrique parente :**[ Publication basée sur des articles à partir de l’éditeur](web-editor-article-publishing.md)
