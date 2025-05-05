---
title: Lancement de l’éditeur web
description: Découvrez comment lancer l’éditeur web à partir de la page de navigation d’AEM, de l’interface utilisateur d’AEM Assets et de la console de mappage DITA dans AEM Guides.
feature: Authoring, Web Editor
role: User
hide: true
exl-id: 374042e4-0f1c-44cf-926c-c9fefa4b1de0
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 0%

---

# Lancement de l’éditeur web {#id2056B0140HS}

Vous pouvez lancer l’éditeur web à partir des emplacements suivants :

- [Page de navigation d’AEM](#id2056BG00RZJ)
- [Interface utilisateur d’AEM Assets](#id2056BG0307U)
- [Console de mappage DITA](#id2056BG090BF)

Les sections suivantes décrivent en détail comment accéder à l’éditeur web et le lancer à partir de différents emplacements.

## Page de navigation d’AEM {#id2056BG00RZJ}

Lorsque vous vous connectez à AEM, la page Navigation s’affiche :

![](images/web-editor-from-navigation-page.png){width="800" align="left"}

Cliquez sur le lien **Guides** pour accéder directement à l’éditeur web.

![](images/web-editor-launch-page.png){width="800" align="left"}

Lorsque vous lancez l’éditeur web sans sélectionner de fichier, un écran d’éditeur web vierge s’affiche. Vous pouvez ouvrir un fichier pour le modifier à partir du référentiel AEM ou de votre collection Favoris.

- Cliquez sur l’icône **Guides** (![](images/aem-guides-icon.png) ) pour revenir à la page de navigation d’AEM.

- Le bouton **Fermer** vous dirige vers une destination en fonction de votre configuration :



  <details>

  <summary> Services cloud </summary>

  Si vous utilisez Cloud Services, cliquez sur le bouton **Fermer** pour revenir à la page de navigation d’AEM.
  </details>

  <details>

  <summary> Logiciel On-Premise</summary>

  Si vous utilisez le logiciel On-premise AEM Guides (4.2.1 et versions ultérieures), cliquez sur le bouton **Fermer** à droite pour revenir au chemin d’accès actuel au fichier dans l’interface utilisateur d’Assets.

  </details>

## Interface utilisateur d’AEM Assets {#id2056BG0307U}

L’interface utilisateur d’AEM Assets est un autre emplacement à partir duquel vous pouvez lancer l’éditeur web. Vous pouvez sélectionner une ou plusieurs rubriques et les ouvrir directement dans l&#39;éditeur Web. Pour ouvrir une rubrique dans l&#39;éditeur Web, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez à la rubrique à modifier.

   >[!NOTE]
   >
   > Vous pouvez également voir l’UUID de la rubrique.

   .

   ![](images/assets_ui_with_uuid_cs.png){width="800" align="left"}

   >[!IMPORTANT]
   >
   > Assurez-vous de disposer des autorisations de lecture et d’écriture sur le dossier contenant la rubrique à modifier.

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


**Rubrique parente :**&#x200B;[ Utiliser l’éditeur web](web-editor.md)
