---
title: Use DITAVAL editor
description: Understand how to create and edit DITAVAL files using the DIVATAL Editor in AEM Guides. Know how the DITAVAL editor supports DITAVAL files in author and source views.
feature: Authoring, DITAVAL Editor
role: User
hide: true
exl-id: 8eee347d-840e-4eaf-9441-c7c53a7c3aa0
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 0%

---

# Éditeur DITAVAL {#ditaval-editor}

DITAVAL files are used to generate conditional output. In a single topic, you can add conditions using element attributes to conditionalize content. Then, you create a DITAVAL file wherein you specify the conditions that should be picked up to generate content, and which condition should be left out from the final output.

AEM Guides allows you to easily create and edit DITAVAL files using the DITAVAL editor. The DITAVAL editor retrieves the attributes \(or tags\) defined in your system, and you can use them to create or edit DITAVAL files. For more details about creating and managing tags in AEM, see [Administering Tags](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=en) section in AEM documentation.

## Create DITAVAL file

Perform the following steps to create a DITAVAL file:

1. In the Assets UI, navigate to the location where you want to create the DITAVAL file.

1. Click **Create** \> **DITA Topic**.

1. On the Blueprint page, select DITAVAL file template and click **Next**.

1. On the Properties page, specify the **Title** and **Name** for the DITAVAL file.

   >[!NOTE]
   >
   > The name is automatically suggested based on the Title of your file. If you want to manually specify the file name, then ensure that the Name does not contain any spaces, apostrophe, or braces and ends with .ditaval.

1. Cliquez sur **Créer**. Le message Rubrique créée s’affiche.

   You can choose to open the DITAVAL file for editing in the DITAVAL editor, or the save the topic file in the AEM repository.


## Edit DITAVAL file

Perform the following steps to edit a DITAVAL file:

1. In the Assets UI, navigate to the DITAVAL file that you want to edit.

1. Pour obtenir un verrou exclusif sur le fichier, sélectionnez le fichier et cliquez sur **Extraire**.

1. Sélectionnez le fichier et cliquez sur **Modifier** pour ouvrir le fichier dans l&#39;éditeur DITAVAL d&#39;AEM Guides.

   L&#39;éditeur DITAVAL permet d&#39;effectuer les tâches suivantes :

   A : Activer/désactiver le panneau de gauche
Activez/désactivez la vue du panneau de gauche. Si vous avez ouvert le fichier DITAVAL via un plan DITA, le plan et le référentiel sont affichés dans ce panneau. Pour plus d&#39;informations sur l&#39;ouverture d&#39;un fichier via un plan DITA, voir [Modifier les rubriques via un plan DITA](map-editor-advanced-map-editor.md#id17ACJ0F0FHS).

   B : enregistrer
Enregistre les modifications effectuées dans le fichier. Toutes vos modifications sont enregistrées dans la version actuelle de votre fichier.

   C : Ajouter une propriété
Ajoutez une seule propriété dans votre fichier DITAVAL.

   ![](images/ditaval-editor-props.png)

   La première liste déroulante répertorie les attributs DITA autorisés que vous pouvez utiliser dans le fichier DITAVAL. Cinq attributs sont pris en charge : `audience`, `platform`, `product`, `props` et `otherprops`.

   La deuxième liste déroulante affiche les valeurs configurées pour l’attribut sélectionné. Ensuite, la liste déroulante suivante affiche les actions que vous pouvez configurer sur l’attribut sélectionné. Les valeurs autorisées dans le menu déroulant de l’action sont les suivantes : `include`, `exclude`, `passthrough` et `flag`. Pour plus d&#39;informations sur ces valeurs, voir la définition de l&#39;élément [prop](http://docs.oasis-open.org/dita/dita/v1.3/errata01/os/complete/part3-all-inclusive/langRef/ditaval/ditaval-prop.html#ditaval-prop) dans la documentation OASIS DITA

   D : Ajouter toutes les propriétés
Si vous souhaitez ajouter d’un seul clic toutes les propriétés ou tous les attributs conditionnels définis dans votre système, utilisez la fonction Ajouter toutes les propriétés .

   >[!NOTE]
   >
   > Si toutes les propriétés conditionnelles définies existent déjà dans le fichier DITAVAL, vous ne pouvez pas ajouter d’autres propriétés. Un message d’erreur s’affiche dans ce scénario.

   ![](images/ditaval-all-props.png)

1. Une fois la modification du fichier DITAVAL terminée, cliquez sur **Enregistrer**.

   >[!NOTE]
   >
   > Si vous fermez le fichier sans enregistrer, les modifications seront perdues. Si vous ne souhaitez pas valider les modifications dans le référentiel AEM, cliquez sur **Fermer**, puis sur **Fermer sans enregistrer** dans la boîte de dialogue **Modifications non enregistrées**.


## Vues de l’éditeur DITAVAL

L’éditeur DITAVAL d’AEM Guides prend en charge l’affichage des fichiers DITAVAL dans deux modes ou vues différents :

**Auteur** :   Voici une vue standard Ce que vous voyez est ce que vous obtenez \(WYSISYG\) de l’éditeur DITAVAL. Vous pouvez ajouter ou supprimer des propriétés à l’aide de l’interface utilisateur simple, qui présente les propriétés, ses valeurs et les actions dans une liste déroulante. Dans la vue Auteur, vous avez la possibilité d’insérer une propriété individuelle et d’insérer toutes les propriétés en un seul clic.

Vous pouvez également trouver la version du fichier DITAVAL sur lequel vous travaillez actuellement en plaçant le pointeur de la souris sur le nom du fichier.

**Source**:   La vue Source affiche le code XML sous-jacent qui constitue le fichier DITAVAL. Outre les modifications de texte standard effectuées dans cet affichage, un auteur peut également ajouter ou modifier des propriétés à l’aide du catalogue dynamique.

Pour appeler le catalogue dynamique, placez le curseur à la fin de toute définition de propriété et saisissez « &lt; ». L’éditeur affiche une liste de tous les éléments XML valides que vous pouvez insérer à cet emplacement.

![](images/ditaval-source-view.png)
