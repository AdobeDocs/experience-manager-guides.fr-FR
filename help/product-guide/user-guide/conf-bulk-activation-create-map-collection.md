---
title: Création d’une collection de cartes d’activation en bloc
description: Découvrez comment créer une collection de cartes d’activation en bloc dans AEM guides.
exl-id: ea0bd465-a2d9-488f-83e9-62b336233eb1
feature: Publishing, Bulk Activation
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 0%

---

# Création d’une collection de cartes d’activation en bloc {#id214GG0E90EV}

Pour créer une collection de mappages d’activation en bloc, procédez comme suit :

1. Sélectionner **Guides** dans la liste des outils.

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et choisissez **Outils**.

1. Cliquez sur le bouton **Tableau de bord de publication en bloc** mosaïque.

   Pour la première fois, une page de collections vierge s’affiche. Si vous avez déjà créé des collections d’activation en bloc, elles s’affichent sur cette page.

1. Cliquez sur **Créer**.

1. Saisissez le titre de votre collection de cartes d’activation en bloc, puis cliquez sur **Créer**.

   Un message de réussite s’affiche lors de la création de la collection de mappages d’activation en bloc.

1. Cliquez sur **Ouvrir** sur le message Succès .

1. Cliquez sur **Modifier** puis cliquez sur **Ajouter des mappages**.

1. Recherchez et ajoutez les mappages DITA à ajouter à la collection de mappages d’activation en bloc.

   Par défaut, tous les paramètres prédéfinis et paramètres régionaux associés à la carte sont ajoutés automatiquement.

1. Sélectionnez la sortie souhaitée en activant ou en désactivant le bouton coulissant.

   Vous pouvez choisir plusieurs paramètres prédéfinis de sortie pour toutes les langues disponibles.

1. Cliquez sur **Terminé**.

   Les fichiers de mappage DITA sont ajoutés à votre collecte de mappage d’activation en bloc.

   ![](images/bulk-activation-collection-created.png){width="800" align="left"}


L’onglet Cartes et paramètres prédéfinis présente des informations dans les colonnes suivantes :

- **Carte**: affiche le titre du fichier de mappage DITA.
- **Chemin de mappage**: affiche le chemin d’accès complet au fichier de mappage DITA.

- **UUID**: affiche l’identifiant unique associé au fichier.

- **Langue**: affiche le code de langue du mappage DITA.
- **Prédéfinie**: affiche le titre du paramètre prédéfini de sortie configuré dans le fichier de mappage. Il affiche également l’icône en fonction du type de paramètre prédéfini de sortie.

  >[!NOTE]
  >
  > Le petit ![](images/global-preset-icon.svg) indique un paramètre prédéfini au niveau du profil de dossier.
- **Modifié**: indique si le mappage DITA est mis à jour après la dernière publication. En fonction de ces informations, vous pouvez décider si vous souhaitez activer ou non la sortie pour ce mappage DITA.
- **Généré**: affiche la date et l’heure de la dernière sortie générée.
- **Publié**: affiche la date et l’heure de la dernière sortie publiée (ou activée). Si vous sélectionnez le lien, la variable **Résultats de l’activation** s’affiche, qui contient les journaux avec des informations sur le chemin racine où le contenu est activé.


Les options de filtrage disponibles dans le panneau de gauche sont les suivantes :

- **Modifié**: vous pouvez sélectionner Oui ou Non. Si vous sélectionnez oui, seules les cartes DITA modifiées s’affichent. Une carte modifiée est une carte générée depuis sa dernière publication.
- **Prédéfinie**: sélectionnez un paramètre prédéfini pour lequel vous souhaitez filtrer les fichiers map. Par exemple, si vous choisissez *AEM site* prédéfini, alors seules les cartes qui comportent la variable *AEM site* paramètre prédéfini de sortie configuré dessus.
- **Langue**: vous pouvez sélectionner l’un des codes de langue disponibles et afficher uniquement la langue sélectionnée dans l’onglet Cartes et paramètres prédéfinis .

- **Filtre :** Le dernier rail affiche les filtres suivants :
- **Cartes et paramètres prédéfinis** tableau : le tableau Cartes et paramètres prédéfinis présente les colonnes suivantes :

**Rubrique parente :**[ Activation en masse de contenu publié](conf-bulk-activation.md)
