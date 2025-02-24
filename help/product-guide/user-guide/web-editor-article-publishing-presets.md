---
title: Création de paramètres prédéfinis de sortie à partir de l’éditeur web
description: Créez des paramètres prédéfinis de sortie à partir de l’éditeur web. Découvrez comment modifier, renommer, dupliquer et supprimer un paramètre prédéfini de sortie dans AEM Guides.
exl-id: cd38b039-ef91-45c9-a226-433e57b09873
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: 5011481c25b4888a3e72b0e2238b10d8e2fbc191
workflow-type: tm+mt
source-wordcount: '367'
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


   ![Nouveau ](images/knowledge-base-preset-dialog-box.png){width="800" align="left"}

Une fois le paramètre prédéfini créé, vous pouvez générer la sortie pour des articles spécifiques de la base de connaissances. Pour ce faire, accédez à l’onglet **Articles** et sélectionnez les rubriques pour lesquelles vous souhaitez générer la sortie.
1. Sélectionnez **Générer la sortie** en haut pour générer la sortie.

   ![](images/add-preset-articles-tab_cs.png){width="800" align="left"}

1. Dans l’invite **Confirmer les fichiers à publier**, sélectionnez les fichiers à publier et confirmez en sélectionnant **Publier**.

   ![Nouveau ](images/knowledge-base-confirm-files-for-publishing.png){width="800" align="left"}

Vous verrez l’état du processus de génération de sortie. La colonne **Rubriques** répertorie les rubriques pour lesquelles une sortie est générée tandis que la colonne **Statut** affiche le statut de publication de chaque rubrique.


![](images/add-preset-output-generated_cs.png){width="800" align="left"}

Pour afficher la sortie, fermez la boîte de dialogue Sortie générée et sélectionnez **Afficher la sortie** sur la page du paramètre prédéfini.


>[!NOTE]
>
> Vous pouvez également Renommer, Dupliquer ou Supprimer un paramètre prédéfini de sortie existant à partir du menu Options.



**Rubrique parente :**[ Publication basée sur des articles à partir de l’éditeur](web-editor-article-publishing.md)
