---
title: Créer une collection de mappages d’activation en bloc
description: Découvrez comment créer une collection de mappages d’activation en bloc dans les guides AEM.
exl-id: ea0bd465-a2d9-488f-83e9-62b336233eb1
feature: Publishing, Bulk Activation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---

# Créer une collection de mappages d’activation en bloc {#id214GG0E90EV}

Pour créer une collection de mappages d’activation en bloc, procédez comme suit :

1. Sélectionnez le logo Adobe Experience Manager en haut et choisissez **Outils**.

1. Dans le panneau **Outils**, sélectionnez **Guides**.

1. Sélectionnez la mosaïque **Tableau de bord de publication en bloc**.

   Le tableau de bord de publication en bloc s’affiche. Vous pouvez également accéder à ce tableau de bord à partir du panneau de gauche de la page d’accueil d’Adobe Experience Manager Guides [&#128279;](intro-home-page.md).

   Pour la première fois, une page de collections vierge s’affiche. Si vous avez créé précédemment des collections d’activation en bloc, elles s’affichent sur cette page.


1. Sélectionnez **Créer**.

1. Saisissez un titre pour votre collection de mappages d’activation en bloc et sélectionnez **Créer**.

   Un message de réussite s’affiche lors de la création de la collection de mappages d’activation en bloc.

1. Sélectionnez **Ouvrir** dans le message de réussite.

1. Sélectionnez **Modifier** puis sélectionnez **Ajouter des mappages**.

1. Recherchez et ajoutez les mappages DITA à ajouter à la collection de mappages d&#39;activation en bloc.

   Par défaut, tous les paramètres prédéfinis et les paramètres régionaux associés à la carte sont ajoutés automatiquement.

1. Sélectionnez la sortie souhaitée en activant ou en désactivant le bouton coulissant.

   Vous pouvez choisir plusieurs paramètres prédéfinis de sortie dans les paramètres régionaux disponibles.

1. Sélectionnez **Terminé**.

Les fichiers de mappage DITA sont ajoutés à votre collection de mappages d&#39;activation en bloc.

![ a créé une collection d’activation en bloc](images/bulk-activation-collection-created.png){align="left"}

## Onglet Mappages et paramètres prédéfinis

L’onglet **Mappages et paramètres prédéfinis** affiche des informations dans les colonnes suivantes :

- **Map** : affiche le titre du fichier de plan DITA.
- **Chemin de mappage** : affiche le chemin d&#39;accès complet du fichier de mappage DITA.

- **UUID** : affiche l&#39;identifiant unique associé au fichier.

- **Langue** : affiche le code de langue du plan DITA.
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
  ![ l’onglet historique d’audit de la collecte d’activation en bloc créé](images/bulk-collection-audit-history.png){align="left"}

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

**Rubrique parente : &#x200B;** [Activation en bloc du contenu publié](conf-bulk-activation.md)
