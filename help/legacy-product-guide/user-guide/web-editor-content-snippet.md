---
title: Insertion d’un fragment de contenu à partir de votre source de données
description: Utilisez les données de votre source de données dans AEM Guides. Découvrez comment insérer un fragment de contenu de votre source de données. Créez une rubrique à l’aide du générateur de rubriques.
feature: Authoring, Features of Web Editor
role: User
source-git-commit: 324b9b1364c14117740a924e825395f7c9d5c424
workflow-type: tm+mt
source-wordcount: '2389'
ht-degree: 0%

---

# Utiliser les données de votre source de données

Une **source de données** est un système dans lequel vous stockez et gérez les données pour votre organisation. Il s’agit de vos systèmes d’enregistrement tels que JIRA, SQL Datases, PIM ou PLM. AEM Guides fournit la fonctionnalité permettant de se connecter à votre source de données et d’utiliser les données qu’elle contient.

Vous pouvez également vous connecter aux fichiers de données JSON à l’aide d’un connecteur de fichier. Téléchargez le fichier JSON sur votre ordinateur ou parcourez-le à partir des ressources Adobe Experience Manager. Créez ensuite des fragments de contenu ou des rubriques à l’aide des générateurs.

## Panneau Sources de données

Sélectionnez **Sources de données** ![ source de données](images/data-source-icon.svg) dans le panneau de gauche pour afficher les sources de données connectées. Le panneau Sources de données s’ouvre et affiche toutes les sources de données connectées.

Selon votre configuration, votre administrateur peut configurer un connecteur de source de données :

<details>
<summary> Services cloud </summary>


- Si vous utilisez la version d’octobre 2023 ou une version ultérieure, apprenez à [configurer un connecteur de source de données à partir de l’interface utilisateur](/help/product-guide/cs-install-guide/conf-data-source-connector-tools.md) dans le Guide d’installation et de configuration de Cloud Service.

- Si vous utilisez la version de juillet 2023 ou de septembre 2023, apprenez à [configurer un connecteur de source de données](/help/product-guide/cs-install-guide/conf-data-source-connector.md) dans le Guide d’installation et de configuration de Cloud Service.

</details>

<details>    
<summary>  Logiciel On-Premise </summary>

- Si vous utilisez la version 4.3.1 ou ultérieure, apprenez à [configurer un connecteur de source de données à partir de l’interface utilisateur](/help/product-guide/cs-install-guide/conf-data-source-connector-tools.md) dans le Guide d’installation et de configuration On-premise.

- Si vous utilisez la version 4.3, apprenez à [configurer un connecteur de source de données](/help/product-guide/cs-install-guide/conf-data-source-connector.md) dans le Guide d’installation et de configuration On-premise.
</details>


>[!NOTE]
>
> Vous verrez les sources de données pour lesquelles votre administrateur a configuré le connecteur.


## Afficher le mode Liste ou Mosaïque

Vous pouvez basculer entre le mode Liste et le mode Mosaïque pour afficher les différentes sources de données sous la forme d’une liste ou de mosaïques.

Sélectionnez une source de données pour afficher les générateurs de fragments de contenu et les générateurs de rubrique disponibles pour la source de données sélectionnée.

### Mode Liste ![](images/data-sources-list-view-icon.svg)

![](images/data-sources-list-view.png){width="300" align="left"}

*Liste des sources de données connectées.*

### Mosaïque   ![](images/data-sources-tile-view-icon.svg)

![](images/data-sources-tile-view.png){width="300" align="left"}

*Affichez les sources de données connectées sous forme de mosaïques.*

Vous pouvez utiliser les données des sources de données de deux manières :
- Insertion d’un fragment de contenu
- Création d’une rubrique



## Insertion d’un fragment de contenu à partir de votre source de données

AEM Guides fournit la fonctionnalité permettant de se connecter à votre source de données. Vous pouvez récupérer vos données, les insérer dans vos rubriques et les modifier. Vous pouvez facilement créer un fragment de contenu à l’aide du générateur de fragments de contenu et le réutiliser dans vos rubriques.

Effectuez les étapes suivantes pour créer un fragment de contenu à l’aide du générateur de fragments de contenu et l’insérer dans votre rubrique :

1. Sélectionnez **Sources de données** ![](images/data-source-icon.svg)   dans le panneau de gauche pour afficher les sources de données connectées.

1. Sélectionnez une source de données pour afficher les générateurs de fragments de contenu disponibles pour la source de données sélectionnée.

   ![](images/code-snippet-generator.png){width="300" align="left"}

   *Le panneau Sources de données répertorie les générateurs de fragments de contenu disponibles.*

1. Sélectionnez **Ajouter** pour ajouter un nouveau générateur de fragments de contenu. Le panneau **Ajouter le générateur de fragments de contenu** s’ouvre.

1. Saisissez la requête dans la zone de texte **Requête de données** .  Sélectionnez **Copier l’exemple de requête** pour copier rapidement une requête de données. Au lieu de créer manuellement la requête, vous pouvez copier et coller l’exemple de requête dans la zone de texte **Requête de données** . Ensuite, modifiez simplement la requête en fonction de vos besoins de données.

   >[!NOTE]
   >
   >Experience Manager fournit différents exemples de requêtes pour toutes les ressources des différentes sources de données. Ils correspondent à la source de données à partir de laquelle vous récupérez les données.

1. Si vous utilisez un connecteur de fichier, vous pouvez charger le fichier JSON à partir de votre ordinateur ou parcourir un fichier JSON à partir de ressources Adobe Experience Manager.

   >[!NOTE]
   >
   > Si vous utilisez un connecteur de fichier, vous verrez les options permettant de charger ou de parcourir des fichiers au lieu d’une requête de données.

1. Sélectionnez le modèle qui mappe avec votre source de données dans la liste déroulante **Modèle de mappage de données** .
Les modèles d’usine de la source de données sélectionnée s’affichent dans la liste déroulante. Par exemple, vous pouvez afficher le modèle &quot;sql-table&quot; pour la source de données nommée &quot;PostgreSQL&quot;.

   >[!NOTE]
   >  
   > Si votre administrateur a configuré des modèles personnalisés, ils s’affichent également dans la liste déroulante (en fonction des configurations de chemin d’accès au modèle effectuées par votre administrateur).
   >   
   >Vous pouvez également utiliser les outils Velocity dans les modèles. Découvrez comment [utiliser les outils Velocity](#use-velocity-tools).

1. La liste déroulante **Resource** s’affiche pour certains connecteurs tels que REST Client, Salsify, Akeneo et Microsoft ADO.  Sélectionnez une ressource dans la liste déroulante et connectez-vous à elle pour créer un fragment de contenu ou une rubrique à l’aide du générateur correspondant.

   >[!NOTE]
   >
   > Votre administrateur peut configurer les ressources par défaut ou ajouter des ressources pour plusieurs URL lors de la configuration des connecteurs de source de données.

1. Cliquez sur **Récupérer** pour récupérer les données de la source de données et appliquer le modèle aux données qui résultent de la requête SQL.

1. Vous pouvez afficher les données dans l’aperçu ou la vue source DITA.

   1. L&#39;aperçu montre comment les données seront affichées lorsqu&#39;elles seront insérées dans le contenu. L&#39;aperçu affiche une petite fraction des données au format du modèle sélectionné.
Par exemple :
      - Si vous avez sélectionné le modèle sql-table, vous pouvez visualiser les données SQL dans un format tabulaire.
      - Si vous avez sélectionné le modèle de liste jira, vous pouvez afficher une liste classée pour les problèmes Jira.

   1. La vue source affiche les données dans la vue source DITA.
      ![](images/add-content-snippet-generator.png){width="800" align="left"}
      *Ajoutez un générateur de fragments de contenu. Affichez les données en mode source ou aperçu.*

1. Pour enregistrer les résultats de la requête, saisissez le nom du générateur, puis cliquez sur **ADD**.   Un nouveau générateur de fragments de contenu est ajouté à la liste.

   >[!NOTE]
   >
   > Vous devez respecter la convention d’affectation des noms de fichier pour le nom du nouveau générateur de contenu. Vous ne pouvez pas avoir d’espace dans le nom du générateur de fragments de contenu. En outre, vous ne pouvez pas enregistrer un nouveau générateur de contenu avec le nom d’un générateur de contenu existant. Une erreur se produit.

### Options d’un générateur de fragment de contenu

Cliquez avec le bouton droit de la souris sur un générateur de fragments de contenu pour ouvrir les options. Les options suivantes vous permettent d’effectuer les opérations suivantes :

- **Aperçu** : utilisez cette option pour ouvrir un volet et afficher une petite partie de l’affichage des données dans la sortie.
- **Insérer** : utilisez cette option pour insérer le fragment de contenu sélectionné dans la rubrique ouverte pour modification dans l’éditeur web. Comme les données sont insérées sous forme d’extrait de code, vous pouvez également modifier les données de votre rubrique dans l’éditeur web.

  >[!NOTE]
  > 
  > L’option Insérer s’affiche uniquement lorsque vous modifiez une rubrique.

- **Modifier** : utilisez cette option pour apporter des modifications au générateur de fragments de contenu et enregistrez-la.
- **Supprimer** : utilisez cette option pour supprimer le générateur de fragments de contenu sélectionné.
- **Dupliquer** : utilisez cette option pour créer un doublon ou une copie du générateur de fragments de contenu sélectionné. Le doublon est créé par défaut avec un suffixe (tel que generator_1).

### Insertion d’un fragment de code de requête

Vous pouvez également utiliser le **Insérer un fragment de requête** ![](images/data-source-icon.svg)   de la barre d’outils principale pour insérer le fragment de données dans les rubriques.  Vous pouvez sélectionner un générateur dans la liste déroulante, modifier votre requête ou modifier le modèle et insérer les données dans votre rubrique.

![](images/insert-content-snippet.png){width="800" align="left"}

*Modifiez et insérez un fragment de données.*

## Création d’une rubrique à l’aide du générateur de rubriques

Un générateur de rubrique vous permet de créer des rubriques contenant des données provenant de vos sources. Vous pouvez rapidement créer un générateur de rubriques, puis générer les rubriques à l’aide du générateur. Chaque rubrique peut contenir des données dans différents formats, tels que des tableaux, des listes et des paragraphes.   Par exemple, dans une rubrique, vous pouvez ajouter un tableau contenant les détails de tous les nouveaux produits et une liste de tous les produits qui seront arrêtés pour vente.

Le générateur de rubriques peut créer les rubriques contenant les données et un mappage DITA pour toutes les rubriques. Vous pouvez également `<conref>` ces rubriques dans votre contenu. Cela vous permet de maintenir la synchronisation de vos données avec la source de données et vous pouvez facilement les mettre à jour.





### Création d’une rubrique

Effectuez les étapes suivantes pour créer une rubrique à l’aide du générateur de rubriques :

1. Sélectionnez une source de données pour afficher les générateurs de fragments de contenu et les générateurs de rubrique disponibles pour la source de données sélectionnée.

   ![](images/data-sources.png){width="300" align="left"}

   *Ajoutez un générateur de rubrique pour une source de données connectée.*

1. Sélectionnez **Ajouter** ![](images/Add_icon.svg) et **Générateur de rubriques** dans la liste déroulante pour ajouter un nouveau générateur de rubriques. Le panneau **Ajouter un générateur de rubrique** s’ouvre.



1. Saisissez les valeurs dans les champs sous les trois onglets suivants du panneau **Ajouter le générateur de rubrique** :

   **Récupérer la configuration**

   ![](images/topic-generator-fetch-configuration.png){width="300" align="left"}

   *Ajoutez les détails de la requête de données, du modèle de mappage de données et du noeud racine pour le générateur de rubrique et attribuez-lui un nom unique dans le panneau de configuration de récupération.*

   1. Saisissez la requête dans la zone de texte **Requête de données** . Sélectionnez **Copier l’exemple de requête** pour copier rapidement une requête de données. Au lieu de créer manuellement la requête, vous pouvez copier et coller l’exemple de requête dans la zone de texte **Requête de données** . Ensuite, modifiez simplement la requête en fonction de vos besoins de données.

      >[!NOTE]
      >
      >Experience Manager fournit différents exemples de requêtes pour toutes les ressources des différentes sources de données. Ils correspondent à la source de données à partir de laquelle vous récupérez les données.

   1. Si vous utilisez un connecteur de fichier, vous pouvez charger le fichier JSON à partir de votre ordinateur ou parcourir un fichier JSON à partir de ressources Adobe Experience Manager.

      >[!NOTE]
      >
      > Si vous utilisez un connecteur de fichier, vous verrez les options permettant de charger ou de parcourir des fichiers au lieu d’une requête de données.

   1. Sélectionnez le modèle qui mappe avec votre source de données dans la liste déroulante **Modèle de mappage de données** .

      >[!NOTE]
      >
      > Si votre administrateur a configuré des modèles personnalisés, ils s’affichent également dans la liste déroulante (en fonction des configurations de chemin d’accès au modèle effectuées par votre administrateur). Vous pouvez par exemple créer un modèle de rubrique contenant une liste classée, des tableaux, des paragraphes ou d’autres éléments DITA.

   1. Saisissez le **noeud racine**. Il s’agit du noeud sur lequel vous souhaitez accéder à vos données. Le générateur de rubrique crée ensuite chaque rubrique au niveau défini dans le noeud racine. Par exemple, vous pouvez ajouter &quot;issues&quot; en tant que noeud racine dans Jira. Ainsi, si une requête renvoie 13 problèmes, vous obtiendrez 13 rubriques, une rubrique pour chaque problème.

   1. Cliquez sur **Récupérer** pour récupérer les données de la source de données et appliquer le modèle aux données qui résultent de la requête SQL. L’aperçu affiche une petite fraction de l’affichage de la rubrique au format du modèle sélectionné. Par exemple, vous pouvez afficher un seul problème Jira avec tous les champs qui résultent de la requête.
   1. Saisissez le nom du générateur de rubriques.

      >[!NOTE]
      > 
      > Vous devez respecter la convention d’affectation des noms de fichier pour le nom du nouveau générateur de rubriques. Vous ne pouvez pas avoir d’espace dans le nom du générateur de rubriques. En outre, vous ne pouvez pas enregistrer un nouveau générateur de rubriques avec le nom d’un générateur de rubriques existant. Une erreur se produit.

   **Configuration de sortie**

   ![](images/topic-generator-output-configuration.png){width="300" align="left"}

   *Entrez les détails du chemin de sortie et de la convention d’affectation des noms des rubriques dans le panneau Configuration de sortie. Générez un mappage DITA et nommez-le.*

   1. Saisissez les détails **Chemin de sortie** où vous souhaitez enregistrer vos rubriques.
   1. Dans la **convention d’affectation de noms de rubrique**, vous pouvez saisir une valeur ou une variable avec des balises de vitesse. Les nouveaux thèmes suivront la convention. Par exemple, vous pouvez saisir le `$key` pour créer des rubriques basées sur des clés Jira.
   1. Activez l’option **Générer une carte** si vous souhaitez créer une carte contenant toutes les rubriques générées.
   1. Saisissez le nom du nouveau mappage DITA.

   >[!NOTE]
   >
   > Le générateur de rubriques génère le mappage DITA sur le même chemin de sortie que les rubriques.

   **Métadonnées**

   Sélectionnez les propriétés de métadonnées dans la liste déroulante pour les transmettre aux rubriques. La liste déroulante **Nom** répertorie les propriétés personnalisées et par défaut.

   Par exemple, dans la capture d’écran suivante, `dc:description`, `dc:language`, `dc:title` et `docstate` sont les propriétés par défaut pour lesquelles vous pouvez définir les valeurs. Vous pouvez créer une propriété personnalisée telle que author et définir sa valeur.

   ![](images/topic-generator-metadata.png){width="300" align="left"}

   *Ajoutez les propriétés de métadonnées dans le panneau Métadonnées à transmettre aux rubriques.*

1. Saisissez le nom du générateur et cliquez sur **Enregistrer** pour enregistrer les résultats de la requête. Un nouveau générateur de rubrique est ajouté à la liste.

1. Cliquez sur **Enregistrer et générer** pour enregistrer le générateur de rubriques et générer de nouvelles rubriques à partir du générateur de rubriques.



   ![](images/edit-topic-generator.png){width="650" align="left"}

   *Générer de nouvelles rubriques à partir d’un générateur de rubriques existant.*

   >[!NOTE]
   >
   > Si les rubriques existent déjà, le générateur met à jour les données dans les rubriques existantes.

### Options d’un générateur de rubrique

Cliquez avec le bouton droit de la souris sur un générateur de rubriques pour ouvrir les **Options**. Les options suivantes vous permettent d’effectuer les opérations suivantes :

- **Générer** : cette option génère les rubriques du générateur de rubriques sélectionné. Vous pouvez également utiliser cette option pour mettre à jour les rubriques existantes. Il se connecte à la source de données et récupère les données mises à jour. Lors de la génération du contenu, cette option est désactivée et vous affichez un chargeur.
  >[!NOTE]
  >
  >Si votre rubrique existe déjà, vous pouvez soit remplacer les données de la rubrique, soit l’enregistrer en tant que nouvelle version.

  ![](images/generate-topic-options.png)

  *Générez une rubrique et si le fichier existe déjà, enregistrez-la en tant que nouvelle version ou écrasez-la.*
- **Afficher le journal** : sélectionnez cette option pour afficher le fichier journal de génération du contenu. Le fichier journal s’ouvre dans un nouvel onglet. Vous pouvez afficher les erreurs, les avertissements, les messages d’information et les exceptions dans le fichier journal. Cette option est activée si vous avez généré le contenu pour le générateur de rubriques sélectionné.

- **Aperçu** : utilisez cette option pour ouvrir un volet et afficher une petite partie de l’affichage des données dans la sortie.



- **Modifier** : utilisez cette option pour modifier et enregistrer le générateur de rubriques. Cette option est désactivée lorsque vous générez le contenu.
- **Supprimer** : utilisez cette option pour supprimer le générateur de rubriques sélectionné. Cette option est désactivée lorsque vous générez le contenu.
- **Dupliquer** : cette option crée un doublon ou une copie du générateur de rubrique sélectionné. Le doublon est créé avec un suffixe (comme `topic-sample_1`) par défaut.



## Utilisation des outils Velocity dans les modèles de source de données {#use-velocity-tools}

Les modèles Experience Manager prennent également en charge les outils Velocity (version 2.0). Ces outils vous aident à appliquer diverses fonctions aux données que vous récupérez à partir des sources de données. En savoir plus sur l’utilisation des [outils Velocity](https://velocity.apache.org/tools/2.0/generic.html) et les fonctions que vous pouvez appliquer.

Effectuez les étapes suivantes pour utiliser un outil Velocity dans un modèle :
1. Modifiez un modèle Velocity dans l’éditeur web.
1. Ajoutez un outil et sa fonction au format `<tool.function>`. Par exemple :
   - Pour générer un nombre aléatoire à l’aide de l’outil mathématique, utilisez `$mathTool.random`.
   - Pour générer la somme des nombres à l’aide de l’outil mathématique, utilisez `$mathTool.add(num1, num2)`.
1. Utilisez le modèle pour créer un fragment de contenu ou une rubrique.
1. Après avoir appliqué le modèle aux données, vous pouvez afficher les données dans l’aperçu ou la vue source DITA.




Vous pouvez utiliser les outils suivants dans les modèles Velocity pour appliquer diverses fonctions aux données que vous récupérez du connecteur :
-`$alternatorTool`
- `$classTool`
- `$contextTool`
- `$conversionTool`
- `$dateTool`
- `$comparisonDateTool`
- `$displayTool`
- `$escapeTool`
- `$fieldTool`
- `$loopTool`
- `$linkTool`
- `$listTool`
- `$mathTool`
- `$numberTool`
- `$renderTool`
- `$resourceTool`
- `$sortTool`
