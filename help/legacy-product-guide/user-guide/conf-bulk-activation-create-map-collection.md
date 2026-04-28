---
title: Créer une collection de mappages d’activation en bloc
description: Learn how to create a bulk activation map collection in AEM guides.
feature: Publishing, Bulk Activation
role: User
hide: true
exl-id: a242efde-2b29-4d2b-8a50-fd4ae7e8f239
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 0%

---

# Créer une collection de mappages d’activation en bloc {#id214GG0E90EV}

To create a bulk activation map collection, perform the following steps:

1. Sélectionnez **Guides** dans la liste des outils.

1. Select the Adobe Experience Manager link at the top and choose **Tools**.

1. Select the **Bulk Publish Dashboard** tile.

   For the first time, a blank collections page is displayed. If you had created bulk activation collections earlier, then they are shown on this page.

1. Cliquez sur **Créer**.

1. Enter a title for your bulk activation map collection and click **Create**.

   A success message is displayed on creation of the bulk activation map collection.

1. Click **Open** on the success message.

1. Select **Edit** and then select **Add Maps**.

1. Locate and add the DITA maps that you want to add to the bulk activation map collection.

   By default, all the presets and locales associated with the map are added automatically.

1. Select the desired output by turning the sliding button on or off.

   You can choose multiple output presets across available locales.

1. Cliquez sur **Terminé**.

The DITA map files are added to your bulk activation map collection.

![ created bulk activation collection](images/bulk-activation-collection-created.png){width="800" align="left"}

## Maps and Presets tab

The **Maps and Presets** tab presents information in the following columns:

- **Map**: Shows the title of the DITA map file.
- **Map Path**: Shows the complete path of the DITA map file.

- **UUID**: Shows the unique identifier associated with the file.

- **Language**: Shows the language code of the DITA map.
- **Paramètre prédéfini** : affiche le titre du paramètre prédéfini de sortie configuré sur le fichier map. Elle affiche également l’icône en fonction du type de paramètre prédéfini de sortie.

  >[!NOTE]
  >
  > La petite icône ![](images/global-preset-icon.svg) indique un paramètre prédéfini de niveau de profil de dossier.

- **Modifié** : indique si le plan DITA est mis à jour après la dernière publication. En fonction de ces informations, vous pouvez décider d&#39;activer ou non la sortie de ce plan DITA.
- **Généré** : affiche la date et l’heure de la dernière sortie générée.
- **Publié** : affiche la date et l’heure de la dernière sortie publiée (ou activée). Si vous sélectionnez le lien, la page **Résultats de l’activation** s’affiche. Elle contient les journaux avec des informations sur le chemin racine où le contenu est activé.

## Onglet Historique d’audit

L’onglet **Historique des contrôles** présente des informations sur les sorties de mappage activées dans les colonnes suivantes :
- **Map** : affiche le titre du fichier de plan DITA.
- **Chemin de mappage** : affiche le chemin d&#39;accès complet du fichier de mappage DITA.
- **UUID** : affiche l&#39;identifiant unique associé au fichier.
- **Langue** : affiche le code de langue du plan DITA.
- **Paramètre prédéfini** : affiche le titre du paramètre prédéfini de sortie configuré sur le fichier map. Elle affiche également l’icône en fonction du type de paramètre prédéfini de sortie.
- **Statut** : affiche le statut de l’activation comme étant « réussi » ou « non réussi ».
- **Destination** : si vous générez la sortie sur Experience Manager Guides as a Cloud Service, vous pouvez afficher la destination de la sortie en tant que Publication ou Aperçu.

  >[!NOTE]
  >
  > La petite icône ![](images/global-preset-icon.svg) indique un paramètre prédéfini de niveau de profil de dossier.

- **Modifié** : indique si le plan DITA a été mis à jour après la dernière publication. En fonction de ces informations, vous pouvez décider d&#39;activer ou non la sortie de ce plan DITA.
- **Publié** : affiche la date et l’heure de la dernière sortie publiée (ou activée). Si vous sélectionnez le lien, la page Résultats de l’activation s’affiche, qui contient les journaux avec des informations sur le chemin racine où le contenu est activé.
  ![ l’onglet historique d’audit de la collecte d’activation en bloc créé](images/bulk-collection-audit-history.png){width="800" align="left"}

  *Affichez les informations sur les sorties de mappage activées dans l’onglet **Historique d’audit**.*


  >[!NOTE]
  >
  > Les sorties de l’onglet **Historique des contrôles** sont triées en fonction de la colonne **Publié**.



## Panneau de gauche

Les options de filtrage disponibles dans le panneau de gauche sont les suivantes :

- **Modifié** : vous pouvez sélectionner Oui ou Non. Si vous sélectionnez Oui, seuls les plans DITA modifiés s&#39;affichent. Un mappage modifié est un mappage qui a été généré depuis sa dernière publication.
- **Paramètre prédéfini** : sélectionnez un paramètre prédéfini pour lequel vous souhaitez filtrer les fichiers de mappage. Cette colonne affiche le titre du paramètre prédéfini de sortie configuré sur le fichier map. Par exemple, si vous choisissez le paramètre prédéfini *Site AEM*, seuls les mappages sur lesquels le paramètre prédéfini de sortie *Site AEM* est configuré s’affichent.
- **Langue** : vous pouvez sélectionner l’un des codes de langue disponibles et afficher uniquement la langue sélectionnée dans l’onglet Cartes et paramètres prédéfinis.

Les filtres sont mis à jour lorsque vous passez de l’onglet **Mappages et paramètres prédéfinis** à l’onglet **Historique des contrôles** et vice versa.

**Rubrique parente : **[Activation en bloc du contenu publié](conf-bulk-activation.md)
