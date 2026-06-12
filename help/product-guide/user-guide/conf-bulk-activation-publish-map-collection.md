---
title: Activer la sortie
description: Activez la sortie des plans DITA dans AEM Guides. Découvrez comment activer votre contenu sur l’instance de publication.
exl-id: 4da644b9-8c5f-4976-a212-960085b693b8
feature: Publishing, Bulk Activation
role: User
TQID: https://experienceleague.adobe.com/ujkifru-aKa2oYvrE8EKUEE3Sai8NqQ9lx9BA2ZUw9U
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2: id: c38bc65b-dea9-4a6e-9de3-3daf1d2b388b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 469
ht-degree: 1%

---

# Activer la sortie {#id214GGF00V5U}

Une fois que vous avez créé une collection de mappages pour l’activation en bloc, l’étape suivante consiste à activer votre contenu sur l’instance de publication. Pour activer votre contenu, procédez comme suit :

1. Sélectionnez le logo Adobe Experience Manager en haut et choisissez **Outils**.

1. Dans le panneau **Outils**, sélectionnez **Guides**.

1. Sélectionnez la mosaïque **Tableau de bord de publication en bloc**.

   Le tableau de bord de publication en bloc s’affiche avec une liste de collections de mappages d’activation en bloc. Vous pouvez également accéder à ce tableau de bord à partir du panneau de gauche de la page d’accueil d’Adobe Experience Manager Guides [](intro-home-page.md).

1. Sélectionnez la collection que vous souhaitez publier, puis sélectionnez **Ouvrir**.

   ![](images/bulk-activation-collection-open.png)

1. \(*Facultatif*\) Appliquez les filtres requis à partir du rail de gauche pour filtrer la carte en fonction de leur \(statut\), de leur paramètre prédéfini de sortie ou de leur langue modifié.

   >[!NOTE]
   >
   >Générez la sortie du mappage à l’aide du paramètre prédéfini de sortie avant de l’activer dans la collection de mappages.


Affichez les différentes manières d’activer votre collection en fonction de votre configuration.

<details>
<summary> Services cloud </summary>

![bulk-collection-publish sur cloud service](images/bulk-activation-collection-quick-publish-CS.png){width="650"}

Vous pouvez activer la sortie sur les instances **Aperçu** ou **Publication**.

**Prévisualisation**

* Pour activer la sortie des mappages sélectionnés, sélectionnez la sortie de mappage prégénérée et sélectionnez **Publier sur** > **Aperçu**.
* Pour activer la sortie de tous les plans DITA avec leurs paramètres prédéfinis configurés, cochez la case en regard de la colonne **Plan**, puis sélectionnez **Publier vers** > **Publier**.


**Publier**

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
  ![bulk-collection-publish](images/bulk-activation-collection-quick-publish.png){width="650"}

  >[!NOTE]
  > 
  >La case à cocher correspondant à une sortie de mappage n’est activée que si vous avez généré la sortie pour un mappage.


Un message de réussite s’affiche lorsque la sortie du mappage est mise en file d’attente pour publication.

Une fois que la sortie est activée pour les fichiers de mappage sélectionnés, l’onglet Historique d’audit est mis à jour et la dernière sortie activée s’affiche en haut. La colonne **Publié** est mise à jour avec la date et l’heure de publication.

**Rubrique parente : **[Activation en bloc du contenu publié](conf-bulk-activation.md)
