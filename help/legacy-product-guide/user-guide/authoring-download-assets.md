---
title: Téléchargement de fichiers
description: Découvrez comment télécharger des fichiers à partir de la console de mappage DITA dans AEM Guides et exporter un fichier de mappage DITA dans AEM référentiel.
feature: Content Management
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 0%

---

# Téléchargement de fichiers {#id216MC0H0BE8}

Vous pouvez télécharger des ressources, y compris des fichiers DITA et non DITA. Il existe plusieurs façons de télécharger des ressources. Certaines méthodes sont natives d’AEM et d’autres sont prises en charge par AEM Guides. Pour plus d’informations sur le téléchargement des ressources d’AEM natives, voir [Téléchargement de ressources à partir de Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/download-assets-from-aem.html) dans AEM documentation. La section suivante explique le mécanisme de téléchargement de fichiers via la console de mappage DITA dans AEM Guides.

## Exportation d’un fichier de mappage DITA

Une fois que vous disposez du fichier de mappage DITA dans le référentiel AEM, vous pouvez télécharger le fichier de mappage avec ses dépendances. Vous avez ainsi la possibilité de partager le fichier de mappage complet pour la modification hors ligne, la validation, la révision ou simplement la création d’une sauvegarde.

Effectuez les étapes suivantes pour télécharger un fichier de mappage DITA avec ses fichiers dépendants :

1. Dans l’interface utilisateur d’Assets, accédez au mappage DITA que vous souhaitez télécharger.

1. Cliquez sur le mappage DITA pour l’ouvrir dans la console de mappage DITA.

1. Sélectionnez l’onglet **Rubriques** pour afficher la liste des rubriques disponibles dans le mappage DITA.

1. Dans la barre d’outils principale, cliquez sur **Télécharger la carte**.

   La boîte de dialogue Télécharger la carte s’affiche.

   ![](images/download-map.png){width="300" align="left"}

1. Cliquez sur **Télécharger**. Dans la boîte de dialogue Télécharger la carte , vous pouvez choisir les options suivantes :

   - **Utiliser la ligne de base** : sélectionnez cette option pour obtenir une liste des lignes de base créées pour le mappage DITA. Si vous souhaitez télécharger le fichier de mappage et son contenu en fonction d’une ligne de base spécifique, sélectionnez la ligne de base dans la liste déroulante. Pour plus d’informations sur l’utilisation des lignes de base, voir [Utilisation de la ligne de base](generate-output-use-baseline-for-publishing.md#).
   - **Aplatir la hiérarchie de fichiers** : sélectionnez cette option pour enregistrer toutes les rubriques et tous les fichiers multimédias référencés dans un seul dossier.
   >[!NOTE]
   >
   > Vous pouvez également télécharger le fichier map sans sélectionner d’option. Dans ce cas, la dernière version conservée des rubriques et des fichiers multimédia référencés est téléchargée.

1. Après avoir cliqué sur le bouton **Télécharger**, la demande de téléchargement de carte est mise en file d’attente. Vous recevrez la notification suivante une fois que la carte sera prête à être téléchargée.

   ![](images/download-map-prompt.png){width="550" align="left"}

   - Cliquez sur **Télécharger** pour télécharger le fichier de carte au format .zip.

   - Cliquez sur **Télécharger ultérieurement** pour télécharger le fichier de carte ultérieurement. Le lien de téléchargement est accessible à partir de la boîte de réception des notifications AEM. Cliquez sur la notification de mappage générée dans la boîte de réception pour télécharger le mappage au format .zip.

   >[!NOTE]
   >
   > Par défaut, les mappages téléchargés restent pendant cinq jours dans la boîte de réception des notifications AEM.

![](images/download-map-inbox.png){width="300" align="left"}

Une fois la carte téléchargée, vous pouvez la sélectionner et utiliser l’icône Ouvrir dans la partie supérieure pour ouvrir le rapport sélectionné.

**Rubrique parente :**[ Gérer le contenu](authoring.md)
