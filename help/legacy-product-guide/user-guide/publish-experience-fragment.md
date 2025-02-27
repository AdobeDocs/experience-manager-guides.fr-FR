---
title: Publication d’une rubrique dans un fragment d’expérience
description: Publier une rubrique ou les éléments d’une rubrique dans un fragment d’expérience dans AEM Guides.  Découvrez comment afficher les fragments d’expérience présents pour une rubrique et les republier.
feature: Publishing
role: User
hide: true
exl-id: c3c6c063-441c-413b-a63e-0acbd126ca6d
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 1%

---

# Publier des fragments d’expérience

Les fragments d’expérience sont des éléments de contenu modulaire dans Adobe Experience Manager. Ces blocs de contenu sont basés sur des modèles et encapsulent à la fois le contenu et sa mise en page. Ces éléments de contenu réutilisables permettent aux créateurs et aux créatrices de contenu d’assembler et de diffuser des expériences cohérentes et évolutives sur plusieurs canaux pris en charge par Experience Manager. Cette fonctionnalité vous permet de créer facilement et efficacement des expériences marketing cohérentes, telles que des newsletters, des bannières de promotion et des témoignages de clients.

Experience Manager Guides vous permet de publier une rubrique ou ses éléments dans un fragment d’expérience. Vous pouvez créer un mappage JSON entre une rubrique et ses éléments dans un fragment d’expérience. Utilisez ensuite le mappage pour publier une rubrique ou ses éléments dans un fragment d’expérience. Vous pouvez ensuite utiliser les fragments d’expérience dans n’importe quel site Experience Manager ou extraire les détails par le biais d’API prises en charge par les fragments d’expérience.




Pour générer un fragment d’expérience, procédez comme suit :


1. Créez un dossier dans les fragments d’expérience. Utilisez ce dossier pour enregistrer les fragments d’expérience que vous créez en fonction des modèles de fragment d’expérience. Par exemple, *sales-experience-fragments*.
1. Sélectionnez le dossier, puis sélectionnez l’icône **Propriétés** dans la partie supérieure.
1. Modifiez les propriétés du dossier (par exemple, *sales-experience-fragments*).


   * **Titre** : affichez ou modifiez le titre du dossier.

   * **Modèles autorisés** : contient la liste des modèles qui peuvent être ajoutés en tant que pages enfants du fragment d’expérience. Pour ajouter le modèle autorisé, spécifiez l’expression régulière permettant de récupérer les modèles requis dans le champ **Modèles autorisés**.
Par exemple :
     `/libs/cq/experience-fragments/components/experiencefragment/template`

     Si vous ne définissez pas de modèle autorisé pour un dossier, les modèles sont sélectionnés à partir du dossier parent ou du dossier de modèles par défaut.
   * **Classable** : permet de modifier l’ordre des ressources dans un dossier.
     ![ajoutez les détails de la configuration cloud dans les propriétés du dossier](images/experience-fragment-folder-properties.png){width="650" align="left"}
     *Ajoutez la configuration cloud dans les propriétés du dossier pour la connecter aux modèles de fragment.*
1. Pour générer un fragment d’expérience, sélectionnez **Nouvelle sortie** ![nouvelle icône de sortie](./images/Add_icon.svg) dans la section **Sorties** de la **Propriétés du fichier** d’une rubrique.
1. Sélectionnez **Fragment d’expérience**.\
   ![onglet options des propriétés du fichier](./images/file-properties-outputs.png){width="300" align="left"}

   *Ajoutez un nouveau fragment d’expérience à partir des propriétés de fichier d’une rubrique*.

   >[!NOTE]
   >
   > Vous pouvez également publier un fragment d’expérience à partir de la vue **Repository**. Sélectionnez la rubrique à publier en tant que fragment d’expérience. Ensuite, dans le menu **Options**, sélectionnez **Publier sous** > **Fragment d’expérience**.

1. Dans la boîte de dialogue **Générer un fragment d’expérience**, renseignez les informations suivantes :
   ![Ajoutez le modèle de fragment et les détails de mappage dans la boîte de dialogue Publier en tant que fragment d’expérience](images/experience-fragment-generate.png){width="500" align="left"}

   *Ajoutez le chemin d’accès, le modèle et les détails de mappage pour publier une rubrique ou ses éléments en tant que fragment d’expérience. Vous pouvez remplacer un fragment d’expérience existant.*

   * **Chemin d’accès** : recherchez et sélectionnez le chemin d’accès du dossier dans lequel vous souhaitez publier le fragment d’expérience. Vous pouvez également sélectionner un fragment d’expérience existant et le republier.
   * **Titre** : saisissez le titre du fragment d’expérience. Par défaut, le titre est renseigné avec le titre de la rubrique. Vous pouvez le modifier. Ce titre est utilisé pour générer le nom du fragment d’expérience.
   * **Nom** : saisissez le nom du fragment d’expérience. Par défaut, le nom est renseigné avec le titre du topic et les espaces sont remplacés par « _ ». Par exemple, *sample_experience_fragment*. Vous pouvez le modifier. Ce nom est utilisé pour générer l’URL du fragment d’expérience.
   * **Modèle** : sélectionnez le modèle de fragment d’expérience à utiliser pour créer votre fragment d’expérience. Les modèles sont sélectionnés dans le dossier que vous avez configuré dans les propriétés.
   * **Mapping** : il sélectionne le mapping du fichier *experienceFragmentMapping.json* et l’affiche.



     Votre administrateur peut ajouter les mappages dans le fichier *experienceFragmentMapping.json*.  Découvrez comment [créer un mappage entre une rubrique et un fragment d’expérience](/help/product-guide/cs-install-guide/conf-experience-fragment-mapping-cs.md) dans le Guide d’installation et de configuration.

   * Vous pouvez également sélectionner différentes conditions pour publier le contenu.  Sélectionnez l’une des options suivantes :


      * **Aucune** : sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur la sortie publiée.
      * **A partir de DITAVAL** : sélectionnez le fichier DITAVAL afin de générer un contenu personnalisé. Vous pouvez sélectionner le fichier DITAVAL à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin d’accès au fichier.
      * **Utilisation d&#39;attributs** : vous pouvez définir des attributs de condition dans vos rubriques DITA. Sélectionnez ensuite l’attribut de condition pour publier le contenu approprié.

     >[!NOTE]
     > 
     >Les conditions ne sont activées que si les attributs de condition sont définis dans la rubrique.


   * Cochez la case **Remplacer le contenu existant** si votre fragment d’expérience existe déjà et que vous souhaitez le remplacer. Experience Manager Guides affiche une erreur si vous ne cochez pas la case et que votre fragment d’expérience existe déjà.
1. Cliquez sur **Générer** pour publier le fragment d’expérience.
1. Vous pouvez afficher les fragments d’expérience d’une rubrique dans la section **Sorties** de la **Propriétés du fichier**. Les fragments d’expérience s’affichent en fonction de la date et de l’heure de leur publication, la plus récente étant la première.

   ![Affichage des fragments d’expérience d’une rubrique](images/experience-fragment-outputs.png){width=300 align=« left »}

   *Afficher les fragments d’expérience présents pour une rubrique et les republier.*




Une fois les fragments d’expérience publiés, vous pouvez également les utiliser sur n’importe quel site Adobe Experience Manager.


## Menu Options d’un fragment d’expérience

Vous pouvez également effectuer les actions suivantes pour un fragment d’expérience à partir du menu **Options** :

* **Générer** : republiez le fragment d’expérience pour le mettre à jour avec le contenu le plus récent de la rubrique DITA. Lorsque vous régénérez la sortie, vous ne pouvez pas modifier le chemin, le nom, le titre et le modèle du fragment d’expérience. Cependant, vous pouvez sélectionner différentes conditions lors de la régénération de la sortie.

* **Dupliquer** : dupliquez un fragment d’expérience. Vous pouvez modifier le chemin d’accès, le nom, le titre et le modèle. Vous pouvez également sélectionner différentes conditions lorsque vous dupliquez un fragment d’expérience.

* **Supprimer** : permet de supprimer un fragment d’expérience de la liste des sorties. Une invite de confirmation s’affiche. Une fois que vous avez confirmé, le fragment d’expérience est supprimé de la liste **Sorties**. Mais le fragment d’expérience n’est pas supprimé du dossier.

* **Affichage** : affichez l’éditeur de fragment d’expérience. Vous pouvez également apporter des modifications et les enregistrer.
