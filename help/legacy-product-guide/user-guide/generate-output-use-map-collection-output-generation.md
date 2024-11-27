---
title: Utilisation de la collecte des cartes pour la génération de la sortie
description: Découvrez comment créer et supprimer une collection de mappages et ajouter ou supprimer un mappage DITA. Configurez, générez et annulez une tâche de génération de sortie à partir d’une collection de mappages dans AEM Guides.
feature: Publishing
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 0%

---

# Utilisation de la collecte des cartes pour la génération de la sortie {#id1723F20G0HS}

Dans n’importe quelle organisation, un produit peut comporter plusieurs types de documentation. En tant que spécialiste de la publication, vous souhaitez contrôler la sortie que vous souhaitez générer pour quel document. Il doit également exister un moyen de publier par lots plusieurs documents en un seul clic.

AEM Guides vous permet d’organiser votre contenu pour la publication à l’aide d’un tableau de bord appelé Collection de cartes. Une collection de cartes vous permet d’assembler tous les types de documents différents en une seule unité. Vous pouvez choisir le type de sortie à générer pour chaque document de votre collection de cartes. De plus, vous pouvez également générer une sortie et voir la progression de la génération de la sortie depuis le tableau de bord de publication.

Collection de cartes vous offre la possibilité de voir si une modification est apportée à une carte à partir de la dernière sortie publiée. Vous pouvez afficher les détails dans l’onglet Cartes et paramètres prédéfinis de votre collection de cartes, puis republier la sortie si nécessaire. Pour plus d’informations, voir Ajout d’une carte à une collection de cartes.

## Création d’une collection de mappages et ajout de mappages DITA

Pour créer une collection de mappages et ajouter des mappages DITA à la collection, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, cliquez sur **Mapper les collections**.

   Si le lien Mapper les collections n’est pas disponible, sélectionnez l’option **Navigation** dans le rail de gauche, puis cliquez sur **Mapper les collections**.

   ![](images/access-map-collection-left-rail.png){width="350" align="left"}

1. Saisissez un titre pour votre collection de mappages.
1. Cliquez sur **Créer**.

   Un message de réussite s’affiche lors de la création de la collection de mappages.

1. Cliquez sur **Fermer** dans le message Succès.

   Le fichier de mappage nouvellement créé s’affiche sur la page Collections de mappages .

1. Cliquez sur la zone grise dans la mosaïque de la collection que vous souhaitez modifier.
1. Cliquez sur **Modifier**, puis sur **Ajouter des cartes**.
1. Recherchez et ajoutez les mappages DITA à ajouter à la collection de mappages.

   Par défaut, tous les paramètres prédéfinis et paramètres régionaux associés à la carte sont ajoutés automatiquement.

1. Sélectionnez la sortie souhaitée en activant ou en désactivant le bouton coulissant.
1. Cliquez sur **Terminé**.

   Les fichiers de mappage DITA sont ajoutés à votre collection de cartes.

   ![tableau de bord de la collection de cartes](./images/map-collection-dashboard.png){width="800" align="left"}

Les options de filtrage et les détails de mappage suivants sont affichés sur la page de collection :

- **Filtre :** Le rail de la dernière heure affiche les filtres suivants :
   - **Modifié** : vous pouvez sélectionner Oui ou Non. Si vous sélectionnez l’option Oui, seules les cartes DITA modifiées s’affichent dans le tableau Cartes et paramètres prédéfinis .
   - **Paramètre prédéfini** : sélectionnez un paramètre prédéfini pour lequel vous souhaitez filtrer les fichiers de mappage. Par exemple, si vous choisissez le paramètre prédéfini *AEM Site*, seules les cartes dont le paramètre prédéfini de sortie *AEM Site* est configuré s’affichent.
   - **Langue** : vous pouvez sélectionner n’importe quel code de langue disponible et afficher uniquement la langue sélectionnée dans le tableau Cartes et paramètres prédéfinis .
- Table **Cartes et paramètres prédéfinis** : le tableau Cartes et paramètres prédéfinis présente des informations dans les colonnes suivantes :
   - **Map** : affiche le titre du fichier de mappage DITA.
   - **Nom de fichier** : affiche le nom de fichier du mappage DITA.
   - **Langue** : affiche la langue du mappage DITA.
   - **Paramètre prédéfini** : affiche le type de paramètre prédéfini de sortie configuré dans le fichier de mappage.
   - **Baseline** : affiche la ligne de base utilisée par le paramètre prédéfini de sortie.  Si aucune ligne de base n’est utilisée, un trait d’union &quot;-&quot; s’affiche.
   - **Modifié** : indique si le mappage DITA est mis à jour après la dernière publication. En fonction de ces informations, vous pouvez décider si vous souhaitez republier la sortie pour ce mappage DITA ou non.
   - **Dernière génération** : affiche la date et l’heure de la dernière sortie générée.

## Configuration et génération de la sortie à l’aide d’une collection de cartes

Pour configurer et générer la sortie à l’aide d’une collection de cartes, procédez comme suit :

1. Ouvrez la collection de cartes. Vous pouvez afficher les différents paramètres prédéfinis de sortie tels que le site AEM, le PDF (y compris le PDF natif), l’HTML 5, l’EPUB et les paramètres prédéfinis personnalisés. Vous pouvez également afficher les paramètres prédéfinis de profil global et de dossier créés par votre administrateur.

   L’icône ![](images/global-preset-icon.svg) indique un paramètre prédéfini de niveau profil de dossier.
1. \(Facultatif\) Effectuez l’une des opérations suivantes selon vos besoins :
   - Appliquez des filtres à partir du rail de gauche pour filtrer les mappages, le paramètre prédéfini de sortie ou la langue modifiés.
   - Si nécessaire, cliquez sur **Modifier** et modifiez la sortie souhaitée en activant ou en désactivant le bouton coulissant.



     >[!NOTE]
     >  
     > Par défaut, tout nouveau paramètre prédéfini est désactivé.

1. Vous pouvez activer les paramètres prédéfinis pour un mappage DITA de la manière suivante :

   - Activez n’importe quel paramètre prédéfini.
   - Activez **Tous les paramètres prédéfinis** pour un mappage DITA afin de sélectionner tous les paramètres prédéfinis en une seule fois. Cette option est désactivée par défaut.
   - Activez **Paramètres prédéfinis de profil de dossier** pour un mappage DITA afin de sélectionner tous les paramètres prédéfinis de profil de dossier pour celui-ci. Cette option est désactivée par défaut.
     ![Modification d’une collection de cartes sur les services cloud](images/edit-map-collection-cs.png){width="800" align="left"}



1. Utilisez l’une des méthodes suivantes :

   - Pour générer la sortie des mappages sélectionnés, sélectionnez les fichiers de mappage et cliquez sur **Générer la sélection**.
   - Pour générer la sortie de toutes les cartes DITA avec leurs paramètres prédéfinis configurés, cliquez sur **Générer tout**.

   >[!IMPORTANT]
   >
   > Si un processus de génération de sortie pour un paramètre prédéfini ou un mappage DITA se trouve dans la file d’attente ou en cours, vous ne pouvez pas lancer une autre tâche de génération de sortie pour le même paramètre prédéfini ou le même mappage.

## Configuration des propriétés de métadonnées

Dans la collection de mappages, vous pouvez configurer les propriétés de métadonnées en bloc pour les mappages DITA. Sélectionnez **Configurer les métadonnées** pour ouvrir la page **Métadonnées de ressource**. Sur la page **Métadonnées de ressource**, toutes les cartes présentes dans la collection sont répertoriées sur la gauche.

![configurer les métadonnées](images/map-collection-asset-metadata.png){width="800" align="left"}

Pour configurer les propriétés de métadonnées, procédez comme suit :

1. Vous pouvez choisir les cartes pour lesquelles vous souhaitez mettre à jour les métadonnées. Par défaut, tous les mappages DITA présents sont sélectionnés.

1. Une fois que vous avez sélectionné les mappages DITA, vous pouvez afficher des propriétés telles que les métadonnées, la planification (de)l’activation, les références, l’état du document, etc.

1. Mettez à jour les propriétés des métadonnées.

1. Cliquez sur **Enregistrer et fermer** dans la partie supérieure pour enregistrer les mises à jour.
1. (Facultatif) Lorsque vous mettez à jour les balises, vous pouvez également sélectionner Ajouter dans la liste déroulante **Enregistrer et fermer** pour ajouter les nouvelles balises à la liste existante.
1. Cliquez sur **Submit** dans la liste déroulante **Save &amp; Close** (Enregistrer et fermer).
Les propriétés de métadonnées sont mises à jour pour les mappages DITA que vous sélectionnez en bloc dans la collection de mappages.

>[!NOTE]
> 
>Dans la liste déroulante **État du document**, vous ne pouvez sélectionner que les états du document autorisés en commun pour tous les mappages DITA sélectionnés. Pour en savoir plus, consultez [**Document State**](./web-editor-document-states.md).

Les propriétés de métadonnées sont synchronisées avec les propriétés du fichier. Une fois que vous les avez mis à jour, vous pouvez les afficher à partir du panneau **Propriétés du fichier** dans l’éditeur web.



## Suppression d’une collection de cartes ou d’un mappage DITA de la collection de cartes

- Pour supprimer une collection de cartes, sélectionnez une collection dans la page Collection de cartes, puis cliquez sur **Supprimer**.
- Pour supprimer un mappage DITA d’une collection de mappages, ouvrez la collection de mappages en mode d’édition, sélectionnez le fichier de mappage DITA, puis cliquez sur **Supprimer de la collection**.

Cela supprime également tous les paramètres prédéfinis ou les paramètres régionaux associés au mappage DITA de la collection de cartes.


## Annulation d’une tâche de génération de sortie à partir d’une collection de cartes

Tout comme pour annuler une tâche de génération de sortie à partir de la [console de mappage DITA](generate-output-for-a-dita-map.md#id2061H100T5Z) ou du [tableau de bord Publish](generate-output-publish-dashboard.md#), vous pouvez annuler une tâche de génération de sortie à partir d’une collection de cartes. Accédez à l’onglet Sorties d’une collection de cartes, accédez à la tâche de publication que vous souhaitez annuler, puis cliquez sur l’icône **Annuler cette tâche** pour annuler la tâche de publication.

![](images/cancel-publish-task-map-collection.png){width="800" align="left"}

**Rubrique parente :**[ Génération de sortie](generate-output.md)
