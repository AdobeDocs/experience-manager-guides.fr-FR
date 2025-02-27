---
title: Publication d’une rubrique dans un fragment de contenu
description: Publier une rubrique ou les éléments d’une rubrique dans un fragment de contenu dans AEM Guides.  Découvrez comment afficher les fragments de contenu présents pour une rubrique et les republier.
feature: Publishing
role: User
hide: true
exl-id: f8a8dfd3-19de-49ff-b4d4-265b3ac09488
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '1031'
ht-degree: 0%

---

# Publier des fragments de contenu

Les fragments de contenu sont des éléments de contenu distincts dans Adobe Experience Manager. Il s’agit de contenu structuré basé sur un modèle de contenu. Les fragments de contenu sont du contenu pur sans informations de conception ou de disposition. Ils peuvent être créés et gérés indépendamment des canaux pris en charge par Adobe Experience Manager. Les fragments de contenu sont modulaires, où le contenu est divisé en composants plus petits.

Experience Manager Guides vous permet de publier une rubrique ou ses éléments dans un fragment de contenu.

>[!NOTE]
>
>Vous ne pouvez choisir que les éléments d&#39;une rubrique pour lesquels un attribut id est défini.


Pour créer un fragment de contenu, procédez comme suit :

1. Créez un [modèle de fragment de contenu](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=fr) dans Adobe Experience Manager Assets.
1. Créez un dossier dans lequel vous souhaitez enregistrer les fragments de contenu que vous créez en fonction du modèle de fragment de contenu. Par exemple, « stock-content-fragments ».
1. Modifiez les propriétés du dossier (par exemple, « stock-content-fragments ») et ajoutez le chemin du dossier, qui contient le modèle de fragment de contenu dans la configuration cloud.
Par exemple, ajoutez `/conf/we-retail` dans la configuration cloud. Cette configuration connecte tous les modèles de fragment de contenu au dossier.\
   ![ajoutez les détails de la configuration cloud dans les propriétés du dossier](images/fragment-folder-cloud-configuration.png){width="650" align="left"}
   *Ajoutez la configuration cloud dans les propriétés du dossier pour la connecter aux modèles de fragment.*

1. Pour générer un fragment de contenu, sélectionnez **Nouvelle sortie** ![nouvelle icône de sortie](./images/Add_icon.svg) dans la section **Sorties** de la **Propriétés du fichier** d’une rubrique.
1. Sélectionnez **Fragment de contenu**.\
   ![onglet options des propriétés du fichier](./images/file-properties-outputs-tab.png) {width="300" align="left"}

   *Ajoutez un nouveau fragment de contenu à partir des propriétés de fichier d’une rubrique*.

1. Dans la boîte de dialogue **Générer le fragment de contenu**, renseignez les informations suivantes sous les onglets **Général** et **Mappage**.

   Onglet **Général**
   ![Ajoutez le modèle de fragment et les détails de mappage dans la boîte de dialogue Publier en tant que fragment de contenu](images/generate-content-fragment.png)
   *Ajoutez le chemin, le nom, le titre et le filtrage des conditions pour publier une rubrique ou ses éléments en tant que fragment de contenu.*


   * **Chemin d’accès** : recherchez et sélectionnez le chemin d’accès du dossier dans lequel vous souhaitez publier le fragment de contenu. Si vous sélectionnez un fragment de contenu existant, il remplace le contenu des champs mappés.
   * **Titre** : saisissez le titre du fragment de contenu. Par défaut, le titre est renseigné avec le titre de la rubrique. Vous pouvez le modifier. Ce titre est utilisé pour générer le nom du fragment de contenu.
   * **Nom** : saisissez le nom du fragment de contenu. Par défaut, le nom est renseigné avec le titre du topic et les espaces sont remplacés par « _ ». Par exemple, *sample_content_fragment*. Vous pouvez le modifier.  Ce nom est utilisé pour générer l’URL du fragment de contenu.

   * Vous pouvez sélectionner différentes conditions pour créer des variantes de fragment de contenu. Sélectionnez l’une des options suivantes :
     >[!NOTE]
     > 
     > Les conditions ne sont activées que si les attributs de condition sont définis dans la rubrique.

      * **Aucune** : sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur la sortie publiée.
      * **Utilisation de DITAVAL** : sélectionnez le fichier DITAVAL pour inclure ou exclure un contenu spécifique de la sortie générée. Vous pouvez sélectionner le fichier DITAVAL à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin d’accès au fichier.
      * **Utilisation d&#39;attributs** : vous pouvez définir des attributs de condition dans vos rubriques DITA. Sélectionnez ensuite l’attribut de condition pour publier le contenu approprié.






   Onglet **Mappage**

   ![Ajoutez le modèle de fragment et les détails de mappage dans la boîte de dialogue Publier en tant que fragment de contenu](images/content-fragment-mapping.png)

   *Sélectionnez le modèle de fragment de contenu et ajoutez les détails du mappage pour publier une rubrique ou ses éléments en tant que fragment de contenu.*

   * **Modèle** : sélectionnez le modèle de fragment de contenu que vous souhaitez utiliser pour créer votre fragment de contenu. Les modèles sont sélectionnés dans le dossier que vous avez configuré sur le serveur Experience Manager Guides.
   * **Mappage** : vous pouvez afficher les éléments de rubrique auxquels un attribut id est appliqué. Faites glisser les éléments de la rubrique vers les champs présents dans le modèle de fragment de contenu.
Le contenu du fragment de contenu publié s’il existe un fragment de contenu existant se trouve sur le côté droit. Elles peuvent être remplacées par le contenu de la rubrique, si nécessaire. Vous pouvez également sélectionner **Annuler** pour annuler les modifications du mappage.


     >[!NOTE]
     >
     > Si vous utilisez la version 4.4 ou antérieure, sélectionnez un mappage dans la liste déroulante. Il sélectionne les mappages dans le fichier *contentFragmentMapping.json*.  Votre administrateur peut ajouter les mappages dans le fichier *contentFragmentMapping.json*. Découvrez comment [créer un mappage entre une rubrique et un fragment de contenu](/help/product-guide/cs-install-guide/conf-content-fragment-mapping-cs.md) dans le Guide d’installation et de configuration.

1. Cliquez sur **Générer** pour publier le fragment de contenu.

1. Vous pouvez afficher les fragments de contenu d’une rubrique dans la section **Sorties** de la **Propriétés du fichier**.

   ![Affichage des fragments de contenu d’une rubrique](images/outputs-options-menu.png){width="300" align="left"}

   *Afficher les fragments de contenu présents pour une rubrique et les republier.*


Une fois les fragments de contenu publiés, vous pouvez également les utiliser dans n’importe quel site Adobe Experience Manager.




## Menu Options d’un fragment de contenu

Vous pouvez également effectuer les actions suivantes pour un fragment de contenu à partir du menu **Options** :

* **Générer** : republiez le fragment de contenu pour le mettre à jour avec le contenu le plus récent de la rubrique DITA. Lorsque vous régénérez la sortie, vous pouvez modifier le chemin, le nom, le titre, le modèle et le mappage du fragment de contenu. Vous pouvez également sélectionner différentes conditions lors de la régénération de la sortie.

* **Dupliquer** : dupliquez un fragment de contenu. Vous pouvez modifier le chemin, le nom, le titre, le modèle et le mappage. Vous pouvez également sélectionner différentes conditions lorsque vous dupliquez un fragment de contenu pour créer une variante de fragment de contenu.

* **Supprimer** : permet de supprimer un fragment de contenu de la liste des sorties. Une invite de confirmation s’affiche. Une fois que vous avez confirmé, le fragment de contenu est supprimé de la liste **Sorties**.

  >[!NOTE]
  >
  > Aucun contenu n’est supprimé du fragment de contenu par cette action.

* **Affichage** : affichez l’éditeur de fragment de contenu. Vous pouvez également apporter des modifications et les enregistrer.

## Amélioration de la migration de contenu non-UUID vers UUID

Le nouveau script de migration de contenu UUID a été considérablement optimisé, ce qui rend la migration de contenu de Non-UUID vers UUID 30 fois plus rapide que le script précédent. Il comprend des fonctionnalités telles que la reprise à partir des points de contrôle, des informations en direct, un délai d’achèvement estimé et des rapports détaillés, afin d’assurer un processus de migration harmonieux. Le processus de migration préserve notamment les métadonnées des ressources sans modification. Le script a été testé et vérifié sur un jeu de données volumineux de 3 millions de ressources, confirmant son efficacité et sa fiabilité pour les migrations à grande échelle.

En savoir plus sur [Migration de contenu non-UUID vers UUID](/help/product-guide/install-guide/migrate-non-uuid-uuid.md).
