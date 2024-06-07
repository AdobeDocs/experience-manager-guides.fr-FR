---
title: Publication d’une rubrique sur un fragment de contenu
description: Publiez une rubrique ou les éléments d’une rubrique sur un fragment de contenu dans AEM Guides.  Découvrez comment afficher les fragments de contenu présents pour une rubrique et les republier.
exl-id: b1769e48-d721-4e93-b10f-04b385272be7
feature: Publishing
role: User
source-git-commit: 7c7e3dcddf733793a5d6db50205ba60d24702451
workflow-type: tm+mt
source-wordcount: '925'
ht-degree: 1%

---

# Publier des fragments de contenu

Les fragments de contenu sont des éléments de contenu distincts dans Adobe Experience Manager. Il s’agit de contenu structuré basé sur un modèle de contenu. Les fragments de contenu sont du contenu pur sans informations de conception ou de mise en page. Ils peuvent être créés et gérés indépendamment des canaux pris en charge par Adobe Experience Manager. Les fragments de contenu sont modulaires, où le contenu est ventilé en composants plus petits.

Les guides Adobe Experience Manager vous permettent de publier une rubrique ou les éléments d’une rubrique sur un fragment de contenu. Vous pouvez créer un mappage basé sur JSON entre une rubrique et un modèle de fragment de contenu. Utilisez ce mappage pour publier une rubrique ou les éléments d’une rubrique sur un fragment de contenu. Vous pouvez ensuite utiliser des fragments de contenu sur n’importe quel site Adobe Experience Manager ou extraire les détails via des API prises en charge par les fragments de contenu.


Pour créer un fragment de contenu, procédez comme suit :

1. Créez un [Modèle de fragment de contenu](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=fr) dans Adobe Experience Manager Assets.
1. Créez un dossier dans lequel vous souhaitez enregistrer les fragments de contenu que vous créez en fonction du modèle Fragment de contenu . Par exemple, &quot;stock-content-fragments&quot;.
1. Modifiez les propriétés du dossier (par exemple, &quot;stock-content-fragments&quot;) et ajoutez le chemin du dossier, qui contient le modèle Fragment de contenu dans la configuration cloud.
Par exemple, ajoutez `/conf/we-retail` dans la configuration cloud. Cette configuration connecte tous les modèles de fragment de contenu au dossier .\
   ![ajout des détails de configuration du cloud dans les propriétés du dossier](images/fragment-folder-cloud-configuration.png){width="650" align="left"}
   *Ajoutez la configuration de cloud dans les propriétés du dossier pour la connecter aux modèles de fragment.*

1. Pour générer un fragment de contenu, sélectionnez **Nouvelle sortie** ![nouvelle icône de sortie](./images/Add_icon.svg) de la **Sorties** dans la section **Propriétés du fichier** d’une rubrique.
1. Sélectionner **Fragment de contenu**.\
   ![onglet options des propriétés du fichier](./images/file-properties-outputs-tab.png){width="300" align="left"}

   *Ajout d’un fragment de contenu à partir des propriétés de fichier d’une rubrique*.

1. Dans le **Générer un fragment de contenu** , renseignez les informations suivantes :
   ![Ajoutez le modèle de fragment et les détails de mappage dans la boîte de dialogue Publier en tant que fragment de contenu .](images/content-fragment-publish.png){width="500" align="left"}
   *Ajoutez les détails du chemin, du modèle et du mappage pour publier une rubrique ou ses éléments en tant que fragment de contenu. Vous pouvez remplacer un fragment de contenu existant.*

   >[!NOTE]
   >
   >Vous pouvez également publier un fragment de contenu à partir du **Repository View**. Sélectionnez la rubrique que vous souhaitez publier en tant que fragment de contenu. Ensuite, à partir du **Options** menu, sélectionnez **Publier sous** > **Fragment de contenu**.

   * **Chemin**: recherchez et sélectionnez le chemin du dossier dans lequel vous souhaitez publier le fragment de contenu. Si vous sélectionnez un fragment de contenu existant, il remplace le contenu des champs mappés.
   * **Titre**: saisissez le titre du fragment de contenu. Par défaut, le titre est renseigné avec le titre de la rubrique. Vous pouvez le modifier. Ce titre est utilisé pour générer le nom du fragment de contenu.
   * **Nom**: saisissez le nom du fragment de contenu. Par défaut, le nom est renseigné avec le titre de la rubrique et les espaces sont remplacés par &quot;_&quot;. Par exemple : *sample_content_fragment*. Vous pouvez le modifier.  Ce nom est utilisé pour générer l’URL du fragment de contenu.
   * **Modèle**: sélectionnez le modèle de fragment de contenu que vous souhaitez utiliser pour créer le fragment de contenu. Les modèles sont sélectionnés dans le dossier que vous avez configuré dans les services cloud.
   * **Mappage**: sélectionnez un mappage dans la liste déroulante. Il sélectionne les mappages de la variable *contentFragmentMapping.json* fichier .



     Votre administrateur peut ajouter les mappages dans la variable *contentFragmentMapping.json* fichier . En savoir plus sur la manière de procéder [créer un mappage entre une rubrique et un fragment de contenu ;](../cs-install-guide/conf-content-fragment-mapping-cs.md) dans le Guide d&#39;installation et de configuration.

   * Vous pouvez également sélectionner différentes conditions pour publier le contenu.  Sélectionnez l’une des options suivantes :


      * **Aucun**: sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur la sortie publiée.
      * **Utilisation de DITAVAL**: sélectionnez le fichier DITAVAL à générer en sortie, qui comprend un contenu spécifique. Vous pouvez sélectionner le fichier DITAVAL à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin du fichier.
      * **Utilisation des attributs**: vous pouvez définir des attributs de condition dans vos rubriques DITA. Sélectionnez ensuite l’attribut de condition pour publier le contenu correspondant.
     >[!NOTE]
     > 
     >Les conditions ne sont activées que si les attributs de condition sont définis dans la rubrique.



   * Sélectionner **Remplacer le contenu existant** si votre fragment de contenu existe déjà et que vous souhaitez le remplacer. Experience Manager Guides affiche une erreur si vous ne cochez pas la case et que votre fragment de contenu existe déjà.
1. Cliquez sur **Générer** pour publier le fragment de contenu.

1. Vous pouvez afficher les fragments de contenu d’une rubrique sous le **Sorties** dans la section **Propriétés du fichier**.

   ![Affichage des fragments de contenu pour une rubrique](images/outputs-options-menu.png){width="300" align="left"}

   *Afficher les fragments de contenu présents pour une rubrique et les republier.*


Une fois que vous avez publié les fragments de contenu, vous pouvez également les utiliser dans n’importe quel site Adobe Experience Manager.




## Menu Options d’un fragment de contenu

Vous pouvez également effectuer les actions suivantes pour un fragment de contenu à partir du **Options** menu :

* **Générer**: republiez le fragment de contenu pour le mettre à jour avec le contenu le plus récent de la rubrique DITA. Lorsque vous régénérez la sortie, vous ne pouvez pas modifier le chemin, le nom, le titre, le modèle et le mappage du fragment de contenu. Vous pouvez toutefois sélectionner différentes conditions lors de la régénération de la sortie.

* **Dupliquer**: dupliquez un fragment de contenu. Vous pouvez modifier le chemin, le nom, le titre, le modèle et le mappage. Vous pouvez également sélectionner différentes conditions lorsque vous dupliquez un fragment de contenu.

* **Supprimer**: supprimez un fragment de contenu de la liste des sorties. Une invite de confirmation s’affiche. Une fois que vous avez confirmé, le fragment de contenu est supprimé du **Sorties** liste.

  >[!NOTE]
  >
  > Aucune partie du contenu n’est supprimée du fragment de contenu par cette action.

* **Affichage**: affichez l’éditeur de fragment de contenu. Vous pouvez également apporter des modifications et les enregistrer.


