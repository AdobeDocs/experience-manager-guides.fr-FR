---
title: Publication d’une rubrique sur un fragment d’expérience
description: Publiez une rubrique ou les éléments d’une rubrique dans un fragment d’expérience dans AEM Guides.  Découvrez comment afficher les fragments d’expérience présents pour une rubrique et les republier.
feature: Publishing
role: User
source-git-commit: 7c7e3dcddf733793a5d6db50205ba60d24702451
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 1%

---


# Publication de fragments d’expérience

Les fragments d’expérience sont des éléments de contenu modulaire dans Adobe Experience Manager. Ces blocs de contenu sont basés sur des modèles et encapsulent le contenu et sa mise en page. Ces éléments de contenu réutilisables permettent aux créateurs de contenu d’assembler et de diffuser des expériences cohérentes et évolutives sur plusieurs canaux pris en charge par Experience Manager. Cette fonctionnalité vous permet de créer facilement des expériences marketing cohérentes, telles que des newsletters, des bannières de promotion et des témoignages client.

Les guides du Experience Manager vous permettent de publier une rubrique ou ses éléments dans un fragment d’expérience. Vous pouvez créer un mappage JSON entre une rubrique et ses éléments dans un fragment d’expérience. Ensuite, utilisez le mappage pour publier une rubrique ou ses éléments sur un fragment d’expérience. Vous pouvez ensuite utiliser des fragments d’expérience dans n’importe quel site de Experience Manager ou extraire les détails via des API prises en charge par les fragments d’expérience.




Pour générer un fragment d’expérience, procédez comme suit :


1. Créez un dossier dans les fragments d’expérience. Utilisez ce dossier pour enregistrer les fragments d’expérience que vous créez en fonction des modèles de fragments d’expérience. Par exemple : *sales-experience-fragments*.
1. Sélectionnez le dossier, puis le **Propriétés** de la partie supérieure.
1. Modifiez les propriétés du dossier (par exemple, *sales-experience-fragments*).


   * **Titre**: affichez ou modifiez le titre du dossier.

   * **Modèles autorisés**: contient la liste des modèles qui peuvent être ajoutés en tant que pages enfants du fragment d’expérience. Pour ajouter le modèle autorisé, spécifiez l’expression régulière permettant de récupérer les modèles requis dans le **Modèles autorisés** champ .
Par exemple :
     `/libs/cq/experience-fragments/components/experiencefragment/template`

     Si vous ne définissez pas de modèle autorisé pour un dossier, les modèles sont sélectionnés par défaut dans le dossier parent ou dans le dossier templates.
   * **Orderable**: permet de modifier l’ordre des ressources dans un dossier.
     ![ajout des détails de configuration du cloud dans les propriétés du dossier](images/experience-fragment-folder-properties.png){width="650" align="left"}
     *Ajoutez la configuration de cloud dans les propriétés du dossier pour la connecter aux modèles de fragment.*
1. Pour générer un fragment d’expérience, sélectionnez **Nouvelle sortie** ![nouvelle icône de sortie](./images/Add_icon.svg) de la **Sorties** dans la section **Propriétés du fichier** d’une rubrique.
1. Sélectionnez **Fragment d’expérience**.\
   ![onglet options des propriétés du fichier](./images/file-properties-outputs.png){width="300" align="left"}

   *Ajout d’un fragment d’expérience à partir des propriétés de fichier d’une rubrique*.

   >[!NOTE]
   >
   > Vous pouvez également publier un fragment d’expérience à partir du **Repository View**. Sélectionnez la rubrique que vous souhaitez publier en tant que fragment d’expérience. Ensuite, à partir du **Options** menu, sélectionnez **Publier sous** > **Fragment d’expérience**.

1. Dans le **Générer un fragment d’expérience** , renseignez les informations suivantes :
   ![Ajoutez le modèle de fragment et les détails de mappage dans la boîte de dialogue Publier en tant que fragment d’expérience .](images/experience-fragment-generate.png){width="500" align="left"}

   *Ajoutez les détails du chemin, du modèle et du mappage pour publier une rubrique ou ses éléments en tant que fragment d’expérience. Vous pouvez remplacer un fragment d’expérience existant.*

   * **Chemin**: recherchez et sélectionnez le chemin d’accès au dossier dans lequel vous souhaitez publier le fragment d’expérience. Vous pouvez également sélectionner un fragment d’expérience existant et le republier.
   * **Titre**: saisissez le titre du fragment d’expérience. Par défaut, le titre est renseigné avec le titre de la rubrique. Vous pouvez le modifier. Ce titre est utilisé pour générer le nom du fragment d’expérience.
   * **Nom**: saisissez le nom du fragment d’expérience. Par défaut, le nom est renseigné avec le titre de la rubrique et les espaces sont remplacés par &quot;_&quot;. Par exemple : *sample_experience_fragment*. Vous pouvez le modifier. Ce nom est utilisé pour générer l’URL du fragment d’expérience.
   * **Modèle**: sélectionnez le modèle de fragment d’expérience que vous souhaitez utiliser pour créer le fragment d’expérience. Les modèles sont sélectionnés dans le dossier que vous avez configuré dans les propriétés.
   * **Mappage**: il sélectionne le mappage à partir de la variable *experienceFragmentMapping.json* et l’affiche.



     Votre administrateur peut ajouter les mappages dans la variable *experienceFragmentMapping.json* fichier .  En savoir plus sur la manière de procéder [créer un mappage entre une rubrique et un fragment d’expérience ;](../cs-install-guide/conf-experience-fragment-mapping-cs.md) dans le Guide d&#39;installation et de configuration.

   * Vous pouvez également sélectionner différentes conditions pour publier le contenu.  Sélectionnez l’une des options suivantes :


      * **Aucun**: sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur la sortie publiée.
      * **Utilisation de DITAVAL**: sélectionnez le fichier DITAVAL pour générer du contenu personnalisé. Vous pouvez sélectionner le fichier DITAVAL à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin du fichier.
      * **Utilisation des attributs**: vous pouvez définir des attributs de condition dans vos rubriques DITA. Sélectionnez ensuite l’attribut de condition pour publier le contenu correspondant.

     >[!NOTE]
     > 
     >Les conditions ne sont activées que si les attributs de condition sont définis dans la rubrique.


   * Sélectionnez la variable **Remplacer le contenu existant** si votre fragment d’expérience existe déjà et que vous souhaitez le remplacer. Experience Manager Guides affiche une erreur si vous ne cochez pas la case et que votre fragment d’expérience existe déjà.
1. Cliquez sur **Générer** pour publier le fragment d’expérience.
1. Vous pouvez afficher les fragments d’expérience pour une rubrique sous la rubrique **Sorties** dans la section **Propriétés du fichier**. Les fragments d’expérience s’affichent en fonction de la date et de l’heure de publication, la date la plus récente étant la première.

   ![Affichage des fragments d’expérience pour une rubrique](images/experience-fragment-outputs.png){width=300 align=&quot;left&quot;}

   *Afficher les fragments d’expérience présents pour une rubrique et les republier.*




Une fois que vous avez publié les fragments d’expérience, vous pouvez également les utiliser sur n’importe quel site Adobe Experience Manager.


## Menu Options d’un fragment d’expérience

Vous pouvez également effectuer les actions suivantes pour un fragment d’expérience à partir du **Options** menu :

* **Générer**: republiez le fragment d’expérience pour le mettre à jour avec le contenu le plus récent de la rubrique DITA. Lorsque vous régénérez la sortie, vous ne pouvez pas modifier le chemin, le nom, le titre et le modèle du fragment d’expérience. Vous pouvez toutefois sélectionner différentes conditions lors de la régénération de la sortie.

* **Dupliquer**: dupliquez un fragment d’expérience. Vous pouvez modifier le chemin, le nom, le titre et le modèle. Vous pouvez également sélectionner différentes conditions lorsque vous dupliquez un fragment d’expérience.

* **Supprimer**: supprimez un fragment d’expérience de la liste des sorties. Une invite de confirmation s’affiche. Une fois que vous avez confirmé, le fragment d’expérience est supprimé du **Sorties** liste. Toutefois, le fragment d’expérience n’est pas supprimé du dossier.

* **Affichage**: affichez l’éditeur de fragments d’expérience. Vous pouvez également apporter des modifications et les enregistrer.


