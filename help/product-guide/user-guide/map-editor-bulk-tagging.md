---
title: Balisage en bloc du contenu DITA
description: Utilisez le balisage en masse du contenu dans AEM Guides pour améliorer la visibilité du contenu DITA. Découvrez comment appliquer, supprimer, afficher ou masquer des balises en bloc sur une ou plusieurs rubriques.
exl-id: 4c6639a3-333b-44ad-9aec-735a327c3320
feature: Metadata Management
role: User
source-git-commit: 9898f98d897da4da9ca76a89efd262239606ac2e
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 1%

---

# Balisage en bloc du contenu DITA {#id179SG0TN05Z}

Les balises vous permettent de regrouper ou de classer le contenu dans votre référentiel de contenu ainsi que dans la sortie publiée. Si vous avez appliqué des balises à votre contenu, vous pouvez facilement trouver des rubriques connexes dans un plan DITA afin de créer du contenu. Grâce à la sortie publiée, les utilisateurs finaux pourront localiser plus rapidement le contenu approprié avec les balises appropriées en place.

Adobe Experience Manager Guides vous permet de baliser le contenu DITA en quelques étapes. Vous pouvez utiliser la fonction de balisage en bloc pour appliquer plusieurs balises à plusieurs rubriques, à un plan DITA ou à un sous-plan. Vous pouvez également appliquer des balises à une rubrique spécifique. Le balisage est la fonctionnalité native de Adobe Experience Manager. Vous trouverez plus d’informations sur la création et la gestion des balises dans la section [Administration des balises](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=fr) de la documentation de Adobe Experience Manager.

Par défaut, Experience Manager Guides n’accorde pas l’accès en lecture à un utilisateur sur le dossier dans lequel toutes les balises du référentiel Adobe Experience Manager sont stockées. Pour utiliser les balises définies dans le référentiel Adobe Experience Manager, vous devez demander à votre administrateur système d’accorder l’accès au dossier dans lequel les balises sont stockées.

## Application de balises en bloc

Utilisez la fonction de balisage en bloc pour appliquer plusieurs balises à la fois. Pour appliquer des balises à vos rubriques dans un plan DITA, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, recherchez et sélectionnez le fichier de plan DITA.

   La console de mappage DITA s&#39;affiche, affichant la liste des paramètres prédéfinis de sortie disponibles pour générer la sortie.

1. Sélectionnez **Rubriques**.

   Une liste des rubriques disponibles dans le plan DITA s&#39;affiche. Les UUID des rubriques sont affichés sous le titre de la rubrique.

1. Sélectionnez les rubriques ou sous-cartes sur lesquelles vous souhaitez appliquer des balises.

   ![](images/apply-tags-uuid.png){width="650" align="left"}


   >[!NOTE]
   >
   > La capture d’écran ci-dessus montre une sous-carte sélectionnée et développée. Lors de la sélection de la sous-carte, tous les sujets sous la sous-carte sont également sélectionnés.

1. Sélectionnez **Appliquer les balises**.

   La boîte de dialogue Sélectionner les balises s’affiche.

1. Sélectionnez une ou plusieurs balises à appliquer aux rubriques sélectionnées.

1. Confirmez votre sélection.

   Les balises sélectionnées sont appliquées aux rubriques et affichées en regard du titre de la rubrique.

   >[!NOTE]
   >
   > Après avoir ajouté des balises à vos rubriques, si vous déplacez ou supprimez une rubrique, les balises de ces rubriques sont également supprimées. Cependant, cette rubrique reste dans la carte jusqu’à ce que vous la supprimiez.


## Application de balises sur une rubrique individuelle

Effectuez les étapes suivantes pour appliquer des balises à une rubrique individuelle :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de rubrique sur lequel vous souhaitez appliquer des balises, puis sélectionnez-le.

1. Dans la barre d’outils, sélectionnez **Propriétés**.

   La page des propriétés de la rubrique s&#39;affiche.

1. Dans l’onglet De base , sélectionnez l’icône Parcourir en regard du champ **Balises**.

1. Sélectionnez une ou plusieurs balises à appliquer à la rubrique sélectionnée.

1. Confirmez votre sélection.

1. Sélectionnez **Appliquer les balises**.

   Les balises sélectionnées sont appliquées à la rubrique et affichées dans le champ Balises .

1. Sélectionnez **Enregistrer et fermer**.


## Supprimer les balises

En fonction des besoins de votre entreprise, vous pouvez modifier les informations de balisage pour n&#39;importe quelle rubrique DITA. Vous pouvez facilement supprimer toutes les balises en même temps ou supprimer uniquement les balises qui ne sont pas valides sur la rubrique.

Pour supprimer toutes les balises d’une ou de plusieurs rubriques, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de plan DITA et sélectionnez-le.

   La console de mappage DITA s&#39;affiche, affichant la liste des paramètres prédéfinis de sortie disponibles pour générer la sortie.

1. Sélectionnez **Rubriques**.

   Une liste des rubriques disponibles dans le plan DITA s&#39;affiche.

1. Sélectionnez les rubriques à partir desquelles vous souhaitez supprimer des balises.

1. Sélectionnez **Supprimer les balises**.

   >[!NOTE]
   >
   > Si l’icône Supprimer les balises n’est pas visible, assurez-vous que vous n’avez pas activé la fonction Masquer les balises.

1. Dans la boîte de dialogue Confirmer la suppression, sélectionnez **OK** pour supprimer les balises des rubriques sélectionnées.


## Afficher ou masquer les balises

Si une longue liste de balises est appliquée à vos rubriques, la navigation peut s’avérer un peu fastidieuse. Vous pouvez facilement masquer les balises dans dans la vue de la console Plan DITA en sélectionnant l&#39;icône Masquer les balises . De même, lorsque les balises ne sont pas visibles, si vous sélectionnez Afficher les balises , toutes les balises sont affichées.

**Rubrique parente :**&#x200B;[ Gérer les métadonnées](manage-metadata.md)
