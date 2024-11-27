---
title: Publish d’une rubrique sur un fragment de contenu
description: Publish d’une rubrique ou des éléments d’une rubrique dans un fragment de contenu dans AEM Guides.  Découvrez comment afficher les fragments de contenu présents pour une rubrique et les republier.
feature: Publishing
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '1031'
ht-degree: 0%

---

# Publier des fragments de contenu

Les fragments de contenu sont des éléments de contenu distincts dans Adobe Experience Manager. Il s’agit de contenu structuré basé sur un modèle de contenu. Les fragments de contenu sont du contenu pur sans informations de conception ou de mise en page. Ils peuvent être créés et gérés indépendamment des canaux pris en charge par Adobe Experience Manager. Les fragments de contenu sont modulaires, où le contenu est ventilé en composants plus petits.

Experience Manager Guides vous permet de publier une rubrique ou ses éléments dans un fragment de contenu.

>[!NOTE]
>
>Vous pouvez choisir uniquement les éléments d’une rubrique dont l’attribut id est défini.


Pour créer un fragment de contenu, procédez comme suit :

1. Créez un [modèle de fragment de contenu](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=fr) dans Adobe Experience Manager Assets.
1. Créez un dossier dans lequel vous souhaitez enregistrer les fragments de contenu que vous créez en fonction du modèle Fragment de contenu . Par exemple, &quot;stock-content-fragments&quot;.
1. Modifiez les propriétés du dossier (par exemple, &quot;stock-content-fragments&quot;) et ajoutez le chemin du dossier, qui contient le modèle Fragment de contenu dans la configuration cloud.
Par exemple, ajoutez `/conf/we-retail` dans la configuration cloud. Cette configuration connecte tous les modèles de fragment de contenu au dossier .\
   ![ Ajoutez des détails de configuration de cloud dans les propriétés de dossier](images/fragment-folder-cloud-configuration.png){width="650" align="left"}
   *Ajoutez la configuration cloud dans les propriétés du dossier pour la connecter aux modèles de fragment.*

1. Pour générer un fragment de contenu, sélectionnez **Nouvelle sortie** ![nouvelle icône de sortie](./images/Add_icon.svg) dans la section **Sorties** de la rubrique **Propriétés du fichier**.
1. Sélectionnez **Fragment de contenu**.\
   ![ Onglet Options des propriétés de fichier ](./images/file-properties-outputs-tab.png) {width="300" align="left"}

   *Ajoutez un nouveau fragment de contenu à partir des propriétés de fichier d’une rubrique*.

1. Dans la boîte de dialogue **Générer un fragment de contenu**, renseignez les détails suivants sous les onglets **Général** et **Mapping** .

   Onglet **Général**
   ![Ajoutez le modèle de fragment et les détails de mappage dans la boîte de dialogue Publish en tant que fragment de contenu](images/generate-content-fragment.png)
   *Ajoutez le chemin, le nom, le titre et le filtrage de condition pour publier une rubrique ou ses éléments en tant que fragment de contenu.*


   * **Chemin** : recherchez et sélectionnez le chemin d’accès du dossier dans lequel vous souhaitez publier le fragment de contenu. Si vous sélectionnez un fragment de contenu existant, il remplace le contenu des champs mappés.
   * **Titre** : saisissez le titre du fragment de contenu. Par défaut, le titre est renseigné avec le titre de la rubrique. Vous pouvez le modifier. Ce titre est utilisé pour générer le nom du fragment de contenu.
   * **Nom** : saisissez le nom du fragment de contenu. Par défaut, le nom est renseigné avec le titre de la rubrique et les espaces sont remplacés par &quot;_&quot;. Par exemple, *sample_content_fragment*. Vous pouvez le modifier.  Ce nom est utilisé pour générer l’URL du fragment de contenu.

   * Vous pouvez sélectionner différentes conditions pour créer des variantes de fragments de contenu. Sélectionnez l’une des options suivantes :
     >[!NOTE]
     > 
     > Les conditions ne sont activées que si les attributs de condition sont définis dans la rubrique.

      * **Aucun** : sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur la sortie publiée.
      * **Utilisation de DITAVAL** : sélectionnez le fichier DITAVAL pour inclure ou exclure du contenu spécifique dans la sortie générée. Vous pouvez sélectionner le fichier DITAVAL à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin du fichier.
      * **Utilisation d’attributs** : vous pouvez définir des attributs de condition dans vos rubriques DITA. Sélectionnez ensuite l’attribut de condition pour publier le contenu correspondant.






   Onglet **Mapping**

   ![Ajoutez le modèle de fragment et les détails de mappage dans la boîte de dialogue Publish en tant que fragment de contenu](images/content-fragment-mapping.png)

   *Sélectionnez le modèle de fragment de contenu et ajoutez les détails du mappage pour publier une rubrique ou ses éléments en tant que fragment de contenu.*

   * **Modèle** : sélectionnez le modèle de fragment de contenu que vous souhaitez utiliser pour créer votre fragment de contenu. Les modèles sont sélectionnés dans le dossier que vous avez configuré sur le serveur Experience Manager Guides.
   * **Mapping** : vous pouvez afficher les éléments de rubrique auxquels un attribut id est appliqué. Faites glisser les éléments de la rubrique vers les champs présents dans le modèle de fragment de contenu.
Le côté droit est renseigné avec le contenu du fragment de contenu publié dans le cas d’un fragment de contenu existant. Ils peuvent être remplacés par le contenu de la rubrique, si nécessaire. Vous pouvez également sélectionner **Annuler** pour annuler les modifications de mappage.


     >[!NOTE]
     >
     > Si vous utilisez des versions 4.4 ou antérieures, sélectionnez un mappage dans la liste déroulante. Il sélectionne les mappages à partir du fichier *contentFragmentMapping.json*.  Votre administrateur peut ajouter les mappages dans le fichier *contentFragmentMapping.json*. Découvrez comment [créer un mappage entre une rubrique et un fragment de contenu](../cs-install-guide/conf-content-fragment-mapping-cs.md) dans le Guide d’installation et de configuration.

1. Cliquez sur **Générer** pour publier le fragment de contenu.

1. Vous pouvez afficher les fragments de contenu pour une rubrique sous la section **Sorties** dans les **propriétés du fichier**.

   ![Affichage des fragments de contenu pour une rubrique](images/outputs-options-menu.png){width="300" align="left"}

   *Affichez les fragments de contenu présents pour une rubrique et republiez-les.*


Une fois que vous avez publié les fragments de contenu, vous pouvez également les utiliser dans n’importe quel site Adobe Experience Manager.




## Menu Options d’un fragment de contenu

Vous pouvez également effectuer les actions suivantes pour un fragment de contenu à partir du menu **Options** :

* **Générer** : republiez le fragment de contenu pour le mettre à jour avec le contenu le plus récent de la rubrique DITA. Lorsque vous régénérez la sortie, vous pouvez modifier le chemin, le nom, le titre, le modèle et le mappage du fragment de contenu. Vous pouvez également sélectionner différentes conditions lors de la régénération de la sortie.

* **Dupliquer** : dupliquez un fragment de contenu. Vous pouvez modifier le chemin, le nom, le titre, le modèle et le mappage. Vous pouvez également sélectionner différentes conditions lorsque vous dupliquez un fragment de contenu pour créer une variante de fragment de contenu.

* **Supprimer** : supprimez un fragment de contenu de la liste des sorties. Une invite de confirmation s’affiche. Une fois que vous avez confirmé, le fragment de contenu est supprimé de la liste **Sorties**.

  >[!NOTE]
  >
  > Aucune partie du contenu n’est supprimée du fragment de contenu par cette action.

* **Afficher** : affichez l’éditeur de fragment de contenu. Vous pouvez également apporter des modifications et les enregistrer.

## Amélioration de la migration du contenu non UUID vers UUID

Le nouveau script de migration de contenu UID a été considérablement optimisé, ce qui rend la migration de contenu d’un UUID à un UUID 30 fois plus rapide que le script précédent. Il comprend des fonctionnalités telles que la reprise à partir des points de contrôle, des informations en direct, une estimation du temps d’achèvement et des rapports détaillés, ce qui garantit un processus de migration harmonieux. En particulier, le processus de migration conserve les métadonnées des ressources sans aucune modification. Le script a été testé et vérifié sur un grand jeu de données de 3 millions de ressources, confirmant son efficacité et sa fiabilité pour les migrations à grande échelle.

En savoir plus sur la [migration de contenu non UUID vers UUID](../install-guide/migrate-non-uuid-uuid.md).