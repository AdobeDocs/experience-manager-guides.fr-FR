---
title: Création d’une collection de cartes d’activation en bloc
description: Découvrez comment créer une collection de cartes d’activation en bloc dans AEM guides.
feature: Publishing, Bulk Activation
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 0%

---

# Création d’une collection de cartes d’activation en bloc {#id214GG0E90EV}

Pour créer une collection de mappages d’activation en bloc, procédez comme suit :

1. Sélectionnez **Guides** dans la liste des outils.

1. Sélectionnez le lien Adobe Experience Manager en haut et choisissez **Outils**.

1. Sélectionnez la mosaïque **Tableau de bord Publish en bloc** .

   Pour la première fois, une page de collections vierge s’affiche. Si vous avez déjà créé des collections d’activation en bloc, elles s’affichent sur cette page.

1. Cliquez sur **Créer**.

1. Saisissez un titre pour votre collection de cartes d’activation en bloc et cliquez sur **Créer**.

   Un message de réussite s’affiche lors de la création de la collection de cartes d’activation en bloc.

1. Cliquez sur **Ouvrir** dans le message de succès.

1. Sélectionnez **Edit** (Modifier), puis **Add Maps** (Ajouter des cartes).

1. Recherchez et ajoutez les mappages DITA à ajouter à la collection de mappages d’activation en bloc.

   Par défaut, tous les paramètres prédéfinis et les paramètres régionaux associés à la carte sont ajoutés automatiquement.

1. Sélectionnez la sortie souhaitée en activant ou en désactivant le bouton coulissant.

   Vous pouvez choisir plusieurs paramètres prédéfinis de sortie pour toutes les langues disponibles.

1. Cliquez sur **Terminé**.

Les fichiers de mappage DITA sont ajoutés à votre collecte de mappage d’activation en bloc.

![ collection d’activation en bloc créée](images/bulk-activation-collection-created.png){width="800" align="left"}

## Onglet Mappages et paramètres prédéfinis

L’onglet **Cartes et paramètres prédéfinis** présente des informations dans les colonnes suivantes :

- **Map** : affiche le titre du fichier de mappage DITA.
- **Chemin d’accès aux cartes** : affiche le chemin d’accès complet du fichier de mappage DITA.

- **UID** : affiche l’identifiant unique associé au fichier.

- **Langue** : affiche le code de langue du mappage DITA.
- **Paramètre prédéfini** : affiche le titre du paramètre prédéfini de sortie configuré dans le fichier de mappage. Il affiche également l’icône en fonction du type de paramètre prédéfini de sortie.

  >[!NOTE]
  >
  > La petite icône ![](images/global-preset-icon.svg) indique un paramètre prédéfini de niveau profil de dossier.

- **Modifié** : indique si le mappage DITA est mis à jour après la dernière publication. En fonction de ces informations, vous pouvez décider si vous souhaitez activer ou non la sortie pour ce mappage DITA.
- **Généré** : affiche la date et l’heure de la dernière sortie générée.
- **Publié** : affiche la date et l’heure de la dernière sortie publiée (ou activée). Si vous sélectionnez le lien, la page **Résultats de l’activation** s’affiche, qui contient les journaux avec des informations sur le chemin racine où le contenu est activé.

## Onglet Historique des audits

L’onglet **Historique d’audit** présente des informations sur les sorties de mappage activées dans les colonnes suivantes :
- **Map** : affiche le titre du fichier de mappage DITA.
- **Chemin d’accès aux cartes** : affiche le chemin d’accès complet du fichier de mappage DITA.
- **UID** : affiche l’identifiant unique associé au fichier.
- **Langue** : affiche le code de langue du mappage DITA.
- **Paramètre prédéfini** : affiche le titre du paramètre prédéfini de sortie configuré dans le fichier de mappage. Il affiche également l’icône en fonction du type de paramètre prédéfini de sortie.
- **État** : indique que l’état de l’activation a réussi ou a échoué.
- **Destination** : si vous générez la sortie as a Cloud Service Experience Manager Guides, vous pouvez afficher la destination de la sortie sous la forme Publish ou Preview.

  >[!NOTE]
  >
  > La petite icône ![](images/global-preset-icon.svg) indique un paramètre prédéfini de niveau profil de dossier.

- **Modifié** : indique si le mappage DITA a été mis à jour après la dernière publication. En fonction de ces informations, vous pouvez décider d’activer ou non la sortie pour ce mappage DITA.
- **Publié** : affiche la date et l’heure de la dernière sortie publiée (ou activée). Si vous sélectionnez le lien, la page Résultats de l’activation s’affiche. Elle contient les journaux avec des informations sur le chemin racine où le contenu est activé.
  ![ onglet historique d’audit de collection d’activation en bloc créé](images/bulk-collection-audit-history.png){width="800" align="left"}

  *Affichez les informations sur les sorties de mappage activées dans l’onglet **Historique d’audit**.*


  >[!NOTE]
  >
  > Les sorties de l’onglet **Historique d’audit** sont triées en fonction de la colonne **Publié**.



## Panneau gauche

Les options de filtrage disponibles dans le panneau de gauche sont les suivantes :

- **Modifié** : vous pouvez sélectionner Oui ou Non. Si vous sélectionnez oui, seules les cartes DITA modifiées s’affichent. Une carte modifiée est une carte générée depuis sa dernière publication.
- **Paramètre prédéfini** : sélectionnez un paramètre prédéfini pour lequel vous souhaitez filtrer les fichiers de mappage. Cette colonne affiche le titre du paramètre prédéfini de sortie configuré dans le fichier de mappage. Par exemple, si vous choisissez le paramètre prédéfini *AEM Site*, seules les cartes dont le paramètre prédéfini de sortie *AEM Site* est configuré s’affichent.
- **Langue** : vous pouvez sélectionner n’importe quel code de langue disponible et afficher uniquement la langue sélectionnée dans l’onglet Cartes et paramètres prédéfinis .

Les filtres sont mis à jour lorsque vous passez de l’onglet **Cartes et paramètres prédéfinis** à l’onglet **Historique d’audit** et vice versa.

**Rubrique parente : **[Activation en masse du contenu publié](conf-bulk-activation.md)
