---
title: Publish d’une rubrique sur une page AEM Sites
description: Publish d’une rubrique ou des éléments d’une rubrique dans une sortie Adobe Experience Manager Sites.  Découvrez comment afficher la page Experience Manager Sites présente pour une rubrique et la republier.
feature: Publishing
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 0%

---

# Pages Publish Adobe Experience Manager Sites


La page Experience Manager Sites fait référence au contenu publié sur le site web de Adobe Experience Manager. Experience Manager Guides vous permet de publier une rubrique autonome sur une page Sites.

Cette fonctionnalité vous permet de publier une rubrique et ses éléments sans créer de mappage DITA ni de paramètres prédéfinis de sortie. Vous pouvez facilement mettre à jour la rubrique, republier la page Sites et la réutiliser sur différentes pages web. Grâce à cette fonctionnalité, vous pouvez facilement publier des articles autonomes ou du contenu marketing.





Pour générer une page Sites, procédez comme suit :




1. Sélectionnez **Nouvelle sortie** ![nouvelle icône de sortie](./images/Add_icon.svg) dans la section **Sorties** de la rubrique **Propriétés du fichier**.
1. Sélectionnez **Page Sites**.


1. Dans la boîte de dialogue **Générer la page de sites**, renseignez les détails suivants :
   ![Ajoutez les détails du chemin et du modèle dans la page Générer les sites](images/aem-sites-page-generate.png){width="500" align="left"}

   *Ajoutez les détails du chemin, du titre, du nom et du modèle pour publier une rubrique ou ses éléments en tant que page Sites. *

   * **Chemin** : recherchez et sélectionnez le chemin du dossier dans lequel vous souhaitez publier la page Sites.
   * **Titre** : saisissez le titre de la page Sites. Par défaut, le titre est renseigné avec le titre de la rubrique. Vous pouvez le modifier. Ce titre est utilisé pour générer le nom de la page Sites.
   * **Nom** : saisissez le nom de la page Sites. Par défaut, le nom est renseigné avec le titre de la rubrique et les caractères non autorisés tels que les espaces et les caractères spéciaux sont remplacés par &#39;_&#39;. Par exemple, *sample_sites_page*. Vous pouvez le modifier. Ce nom est utilisé pour générer l’URL de la page Sites.
   * **Modèle de page** : sélectionnez le modèle de page Sites pour créer votre page Sites. Vous pouvez afficher les modèles dans le dossier sur le chemin d’accès sélectionné. Votre administrateur peut également charger des modèles personnalisés.


   * Vous pouvez également sélectionner différentes conditions pour publier le contenu.  Sélectionnez l’une des options suivantes :


      * **Aucun** : sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur la sortie publiée.
      * **Utilisation de DITAVAL** : sélectionnez le fichier DITAVAL pour générer du contenu personnalisé. Vous pouvez sélectionner le fichier DITAVAL à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin du fichier.
      * **Utilisation d’attributs** : vous pouvez définir des attributs de condition dans vos rubriques DITA. Sélectionnez ensuite l’attribut de condition pour publier le contenu correspondant.

     >[!NOTE]
     > 
     >Les conditions ne sont activées que si les attributs de condition sont définis dans la rubrique.



1. Cliquez sur **Générer** pour publier la page Sites.
1. Vous pouvez afficher la page Sites pour une rubrique sous la section **Sorties** dans les **propriétés du fichier**. Les pages Sites s’affichent en fonction de la date et de l’heure de publication, la dernière page étant la première.

   ![Afficher la page Sites pour une rubrique](images/aem-sites-outputs.png){width=300 align=&quot;left&quot;}

   *Affichez la page Sites présente pour une rubrique et republiez-la.*




Une fois la page Sites publiée, vous pouvez également l’utiliser sur n’importe quel site Adobe Experience Manager.


## Menu Options d’un Experience Manager Sites

Vous pouvez également effectuer les actions suivantes pour un Experience Manager Sites à partir du menu **Options** :

* **Générer** : republiez la page Sites pour la mettre à jour avec le contenu le plus récent de la rubrique DITA. Lorsque vous régénérez la sortie sans modifier le chemin, le nom, le titre, le modèle et les conditions, la page Sites est simplement mise à jour avec le contenu le plus récent.

* **Dupliquer** : dupliquez une page Sites. Vous pouvez modifier le chemin, le nom, le titre et le modèle. Vous pouvez également sélectionner différentes conditions lorsque vous dupliquez une page Sites.

* **Supprimer** : supprimez une page Sites de la liste de sorties. Une invite de confirmation s’affiche. Une fois que vous avez confirmé, la page Sites est supprimée de la liste **Sorties**. Mais la page Sites n’est pas supprimée de manière permanente.

* **Afficher** : affichez l’éditeur de page Sites. Vous pouvez également apporter des modifications et les enregistrer.
