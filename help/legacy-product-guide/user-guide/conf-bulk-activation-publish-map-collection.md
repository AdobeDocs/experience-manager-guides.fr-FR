---
title: Activer la sortie
description: Activez la sortie des plans DITA dans AEM Guides. Découvrez comment activer votre contenu sur l’instance de publication.
feature: Publishing, Bulk Activation
role: User
hide: true
exl-id: de1fd057-60c6-4b1a-9e55-f32969eb0079
source-git-commit: 4801f0d327b4bd0641aa195d39ec2c4be2a2ce74
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 2%

---

# Activer la sortie {#id214GGF00V5U}

Une fois que vous avez créé une collection de mappages pour l’activation en bloc, l’étape suivante consiste à activer votre contenu sur l’instance de publication. Pour activer votre contenu, procédez comme suit :

1. Sélectionnez **Guides** dans la liste des outils.

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.

1. Cliquez sur la mosaïque **Tableau de bord de publication en bloc**.

   Une liste des collections de mappages d’activation en bloc s’affiche.

1. Sélectionnez la collection à publier, puis cliquez sur **Ouvrir**.

   ![](images/bulk-activation-collection-open.png){width="800" align="left"}

1. \(*Facultatif*\) Appliquez les filtres requis à partir du rail de gauche pour filtrer la carte en fonction de leur \(statut\), de leur paramètre prédéfini de sortie ou de leur langue modifié.

   >[!NOTE]
   >
   >Générez la sortie du mappage à l’aide du paramètre prédéfini de sortie avant de l’activer dans la collection de mappages.


Affichez les différentes manières d’activer votre collection en fonction de votre configuration.

<details>
<summary> Services cloud </summary>

![bulk-collection-publish sur cloud service](images/bulk-activation-collection-quick-publish-CS.png){width="650" align="left"}

Vous pouvez activer la sortie sur les instances **Aperçu** ou **Publication**.

**Aperçu**

* Pour activer la sortie des mappages sélectionnés, sélectionnez la sortie de mappage prégénérée et sélectionnez **Publier sur** > **Aperçu**.
* Pour activer la sortie de tous les plans DITA avec leurs paramètres prédéfinis configurés, cochez la case en regard de la colonne **Plan**, puis sélectionnez **Publier vers** > **Publier**.


**Publication**

* Pour activer la sortie des mappages sélectionnés, sélectionnez la sortie de mappage prégénérée et sélectionnez **Publier vers** > **Publier**.

* Pour activer la sortie de tous les mappages DITA avec leurs paramètres prédéfinis configurés, cochez la case en regard de Mappage (colonne), puis sélectionnez **Publier vers** > **Publier**.


>[!NOTE]
> 
> La case à cocher correspondant à une sortie de mappage n’est activée que si vous avez généré la sortie pour un mappage.

Un message de réussite s’affiche lorsque la sortie du mappage est mise en file d’attente pour publication.

Une fois que la sortie est activée pour les fichiers de mappage sélectionnés, l’onglet Historique d’audit est mis à jour et la dernière sortie activée s’affiche en haut. La colonne **Publié** est mise à jour avec la date et l’heure de publication.

</details>

<details>    
<summary>  Logiciel On-Premise </summary>


Utilisez l’une des méthodes suivantes :

* Pour activer la sortie des mappages sélectionnés, sélectionnez la sortie de mappage prégénérée et sélectionnez **Publication rapide**.
* Pour activer la sortie de tous les mappages DITA avec leurs paramètres prédéfinis configurés, cochez la case en regard de Mappage (colonne), puis sélectionnez **Publication rapide**.
  ![bulk-collection-publish](images/bulk-activation-collection-quick-publish.png){width="650" align="left"}

  >[!NOTE]
  > 
  >La case à cocher correspondant à une sortie de mappage n’est activée que si vous avez généré la sortie pour un mappage.


Un message de réussite s’affiche lorsque la sortie du mappage est mise en file d’attente pour publication.

Une fois que la sortie est activée pour les fichiers de mappage sélectionnés, l’onglet Historique d’audit est mis à jour et la dernière sortie activée s’affiche en haut. La colonne **Publié** est mise à jour avec la date et l’heure de publication.

**Rubrique parente : **[Activation en bloc du contenu publié](conf-bulk-activation.md)
