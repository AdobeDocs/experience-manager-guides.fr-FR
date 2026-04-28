---
title: Activer la sortie
description: Activate output of DITA maps in AEM Guides. Learn how to activate your content on the publishing instance.
feature: Publishing, Bulk Activation
role: User
hide: true
exl-id: de1fd057-60c6-4b1a-9e55-f32969eb0079
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 2%

---

# Activer la sortie {#id214GGF00V5U}

Once you have created a map collection for bulk activation, the next step is to activate your content on the publishing instance. To activate your content, perform the following steps:

1. Sélectionnez **Guides** dans la liste des outils.

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.

1. Cliquez sur la mosaïque **Tableau de bord de publication en bloc**.

   A list of bulk activation map collections is displayed.

1. Select the collection that you want to publish and click **Open**.

   ![](images/bulk-activation-collection-open.png){width="800" align="left"}

1. \(*Optional*\) Apply the required filters from the left rail to filter map on the basis of their modified \(status\), output preset, or language.

   >[!NOTE]
   >
   >Generate the output for the map using the output preset before activating them in the map collection.


View the different ways to activate your collection based on your setup.

<details>
<summary> Services cloud </summary>

![bulk-collection-publish on cloud service](images/bulk-activation-collection-quick-publish-CS.png){width="650" align="left"}

You can activate the output to the **Preview** or **Publish** instances.

**Prévisualisation**

* To activate the output of selected maps, select the pregenerated map output and select **Publish to** > **Preview**.
* To activate the output of all DITA maps with their configured presets, select the checkbox next to the **Map** column, and then select **Publish to** > **Publish**.


**Publier**

* To activate the output of selected maps, select the pregenerated map output and select **Publish to** > **Publish**.

* To activate the output of all DITA maps with their configured presets, select the checkbox next to the Map (column), and then select **Publish to** > **Publish**.


>[!NOTE]
> 
> The checkbox for a map output is enabled only if you have generated the output for a map.

A success message is displayed when the map output is queued for publishing.

Once the output is activated for the selected map files, the audit history tab is updated, and the latest activated output appears on top. The **Published** column is updated with the publishing date and time.

</details>

<details>    
<summary>  Logiciel On-Premise </summary>


Utilisez l’une des méthodes suivantes :

* To activate the output of selected maps, select the pregenerated map output and select **Quick Publish**.
* To activate the output of all DITA maps with their configured presets, select the checkbox next to the Map (column), and then select **Quick Publish.**
  ![bulk-collection-publish](images/bulk-activation-collection-quick-publish.png){width="650" align="left"}

  >[!NOTE]
  > 
  >The checkbox for a map output is enabled only if you have generated the output for a map.


A success message is displayed when the map output is queued for publishing.

Once the output is activated for the selected map files, the audit history tab is updated, and the latest activated output appears on top. The **Published** column is updated with the publishing date and time.

**Rubrique parente : &#x200B;** [Activation en bloc du contenu publié](conf-bulk-activation.md)
