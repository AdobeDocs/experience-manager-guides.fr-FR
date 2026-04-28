---
title: Launch the Web Editor
description: Learn how to launch the web editor from the AEM Navigation Page, AEM Assets UI, and DITA map Console in AEM Guides.
feature: Authoring, Web Editor
role: User
hide: true
exl-id: 374042e4-0f1c-44cf-926c-c9fefa4b1de0
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 0%

---

# Launch the Web Editor {#id2056B0140HS}

You can launch the Web Editor from the following locations:

- [AEM Navigation page](#id2056BG00RZJ)
- [AEM Assets UI](#id2056BG0307U)
- [DITA map console](#id2056BG090BF)

The following sections cover the details of how you can access and launch the Web Editor from various locations.

## AEM Navigation page {#id2056BG00RZJ}

When you log into AEM, you are shown the Navigation page:

![](images/web-editor-from-navigation-page.png){width="800" align="left"}

Clicking the **Guides** link takes you directly to the Web Editor.

![](images/web-editor-launch-page.png){width="800" align="left"}

As you have launched the Web Editor without selecting any file, a blank Web Editor screen is shown. You can open a file for editing from AEM repository or your Favorites collection.

- Click the **Guides** icon (![](images/aem-guides-icon.png) ), to go back to the AEM Navigation page.

- The **Close** button  takes you to a destination based on your setup:



  <details>

  <summary> Services cloud </summary>

  If you are using Cloud Services, click the **Close** button  to go back to the AEM Navigation page.
  </details>

  <details>

  <summary> On-premise Software</summary>

  If you&#39;re using AEM Guides On-premise Software (4.2.1 and later), click the **Close** button on the right to go back to your current file path in the Assets UI.

  </details>

## AEM Assets UI {#id2056BG0307U}

Another location from where you can launch the Web Editor is from the AEM Assets UI. You can select one or more topics and open them directly in the Web Editor. To open a topic in the Web Editor, follow these steps:

1. In the Assets UI, navigate to the topic that you want to edit.

   >[!NOTE]
   >
   > You can also see the UUID of the topic.

   .

   ![](images/assets_ui_with_uuid_cs.png){width="800" align="left"}

   >[!IMPORTANT]
   >
   > Ensure that you have the read and write permissions on the folder that contains the topic you want to edit.

1. Pour obtenir un verrou exclusif sur la rubrique, sélectionnez la rubrique et cliquez sur **Extraire**.

   >[!IMPORTANT]
   >
   > Si votre administrateur a configuré l’option **Désactiver la modification sans extraction**, vous devez extraire le fichier avant de le modifier. Si vous n&#39;extrayez pas le fichier, vous ne pourrez pas voir l&#39;option d&#39;édition.

1. Fermez le mode de sélection des ressources et cliquez sur la rubrique à modifier.

   L’aperçu de la rubrique s’affiche.

   Vous pouvez ouvrir l’éditeur web en mode Liste , Carte et Aperçu .

   >[!IMPORTANT]
   >
   > Si vous souhaitez ouvrir plusieurs rubriques pour les modifier, sélectionnez les rubriques de votre choix dans l’interface utilisateur d’Assets et cliquez sur Modifier. Assurez-vous que le blocage des fenêtres contextuelles n’est pas activé dans votre navigateur, sinon seule la première rubrique de la liste sélectionnée est ouverte pour modification.

   ![](images/edit-from-preview_cs.png){width="800" align="left"}

   Si vous ne souhaitez pas prévisualiser une rubrique et que vous souhaitez l’ouvrir directement dans l’éditeur web, cliquez sur l’icône Modifier dans le menu d’action rapide en mode Carte :

   ![](images/edit-topic-from-quick-action_cs.png){width="800" align="left"}

1. Cliquez sur **Modifier** pour ouvrir la rubrique dans l’éditeur web.

   ![](images/edit-mode.png){width="800" align="left"}


## Console de mappage DITA {#id2056BG090BF}

Pour ouvrir l&#39;éditeur Web à partir de la console de plan DITA, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de plan DITA contenant la rubrique à modifier, puis cliquez dessus.

   La console de plan DITA s&#39;affiche.

1. Cliquez sur **Rubriques**.

   Une liste de rubriques dans le fichier de mappage s’affiche. L&#39;UUID des rubriques s&#39;affiche sous le titre de la rubrique.

1. Sélectionnez le fichier de rubrique à modifier.

1. Cliquez sur **Modifier rubrique**.

   ![](images/edit-topics-map-console_cs.png){width="800" align="left"}

1. La rubrique est ouverte dans l&#39;éditeur Web.

   >[!IMPORTANT]
   >
   > Si votre administrateur a configuré l’option **Désactiver la modification sans extraction**, vous devez extraire le fichier avant de le modifier. Si vous ne récupérez pas le fichier, le document s’ouvre dans l’éditeur en mode lecture seule.


**Rubrique parente :**[ Utiliser l’éditeur web](web-editor.md)
