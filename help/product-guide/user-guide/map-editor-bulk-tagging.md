---
title: Balisage en masse de contenu DITA
description: Utilisez le balisage massif du contenu dans AEM Guides pour améliorer la visibilité du contenu DITA. Découvrez comment appliquer, supprimer, afficher ou masquer des balises en bloc sur une ou plusieurs rubriques.
exl-id: 4c6639a3-333b-44ad-9aec-735a327c3320
feature: Metadata Management
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 0%

---

# Balisage en masse de contenu DITA {#id179SG0TN05Z}

Les balises vous permettent de regrouper ou de classer le contenu dans votre référentiel de contenu, ainsi que dans la sortie publiée. Si vous avez appliqué des balises à votre contenu, vous pouvez facilement trouver des rubriques connexes dans un mappage DITA qui peut vous aider à créer du contenu. Avec la sortie publiée, les utilisateurs finaux pourront localiser plus rapidement le contenu approprié avec les balises appropriées en place.

AEM Guides vous permet de baliser le contenu DITA en quelques clics. Vous pouvez utiliser la fonction de balisage en masse pour appliquer plusieurs balises sur plusieurs rubriques, un mappage DITA ou sur un sous-mappage. Vous pouvez également appliquer des balises sur une rubrique individuelle. Le balisage est la fonctionnalité native d’AEM. Vous trouverez plus d’informations sur la création et la gestion des balises dans la section [Administration des balises](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=en) de la documentation d’AEM.

Par défaut, AEM Guides n’accorde l’accès en lecture à aucun utilisateur du dossier où sont stockées toutes les balises du référentiel AEM. Pour utiliser des balises définies dans le référentiel AEM, vous devez demander à votre administrateur système d’accorder l’accès au dossier dans lequel les balises sont stockées.

## Application de balises en bloc

Utilisez la fonction de balisage en masse pour appliquer plusieurs balises à la fois. Effectuez les étapes suivantes pour appliquer des balises à vos rubriques dans un mappage DITA :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de mappage DITA et cliquez dessus.

   La console de mappage DITA apparaît et affiche la liste des paramètres prédéfinis de sortie disponibles pour générer la sortie.

1. Cliquez sur **Rubriques**.

   Une liste des rubriques disponibles dans le mappage DITA s’affiche. Les UUID des rubriques sont affichés sous le titre de la rubrique.

1. Sélectionnez les rubriques ou sous-plans sur lesquels vous souhaitez appliquer des balises.

   ![](images/apply-tags-uuid.png){width="650" align="left"}


   >[!NOTE]
   >
   > La capture d’écran ci-dessus montre une sous-carte sélectionnée et développée. Lors de la sélection de la sous-carte, toutes les rubriques sous la sous-carte sont également sélectionnées.

1. Cliquez sur **Appliquer les balises**.

   La boîte de dialogue Sélectionner des balises s’affiche.

1. Sélectionnez une ou plusieurs balises à appliquer sur les rubriques sélectionnées.

1. Confirmez votre sélection.

   Les balises sélectionnées sont appliquées aux rubriques et affichées en regard du titre de la rubrique.

   >[!NOTE]
   >
   > Après avoir ajouté des balises à vos rubriques, si vous déplacez ou supprimez une rubrique, les balises de ces rubriques sont également supprimées. Cependant, cette rubrique reste dans la carte jusqu’à ce que vous la supprimiez.


## Application de balises à une rubrique individuelle

Effectuez les étapes suivantes pour appliquer des balises à une rubrique individuelle :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de rubrique sur lequel vous souhaitez appliquer des balises et sélectionnez-le.

1. Dans la barre d’outils, cliquez sur **Propriétés**.

   La page des propriétés de la rubrique s’affiche.

1. Dans l’onglet De base, cliquez sur l’icône Parcourir en regard du champ **Balises** .

1. Sélectionnez une ou plusieurs balises à appliquer à la rubrique sélectionnée.

1. Confirmez votre sélection.

1. Cliquez sur **Appliquer les balises**.

   Les balises sélectionnées sont appliquées à la rubrique et affichées dans le champ Balises .

1. Cliquez sur **Enregistrer et fermer**.


## Supprimer des balises

En fonction des besoins de votre entreprise, vous pouvez modifier les informations de balisage pour n’importe quelle rubrique DITA. Vous pouvez facilement supprimer toutes les balises à la fois ou supprimer uniquement les balises qui ne sont pas valides sur la rubrique.

Pour supprimer toutes les balises d’une ou de plusieurs rubriques, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de mappage DITA et cliquez dessus.

   La console de mappage DITA apparaît et affiche la liste des paramètres prédéfinis de sortie disponibles pour générer la sortie.

1. Cliquez sur **Rubriques**.

   Une liste des rubriques disponibles dans le mappage DITA s’affiche.

1. Sélectionnez les rubriques à partir desquelles vous souhaitez supprimer des balises.

1. Cliquez sur **Supprimer les balises**.

   >[!NOTE]
   >
   > Si l’icône Supprimer les balises n’est pas visible, assurez-vous que vous n’avez pas activé la fonction Masquer les balises .

1. Dans la boîte de dialogue Confirmer la suppression, cliquez sur **OK** pour supprimer des balises des rubriques sélectionnées.


## Afficher ou masquer des balises

Si une longue liste de balises est appliquée à vos rubriques, il peut s’avérer un peu fastidieux de naviguer. Vous pouvez facilement masquer les balises dans à partir de la vue de la console de mappage DITA en cliquant sur l’icône Masquer les balises . De même, lorsque les balises ne sont pas visibles, cliquez sur Afficher les balises pour afficher toutes les balises.

**Rubrique parente :**[ Gérer les métadonnées](manage-metadata.md)
