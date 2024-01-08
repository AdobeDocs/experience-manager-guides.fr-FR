---
title: Base de connaissances
description: Découvrez comment créer un paramètre prédéfini de la base de connaissances à partir de l’éditeur web et du tableau de bord de mappage. Configurez le paramètre prédéfini de sortie de la base de connaissances dans AEM Guides.
source-git-commit: 899b493709ee7f1fb31789e4afc3e985fa2505f7
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 1%

---

# Base de connaissances {#knowledge-base}

Vous pouvez créer le **Base de connaissances** prédéfini à partir de l’éditeur web :

Dans le panneau Repository, ouvrez le fichier de mappage DITA dans **Vue Carte**, puis dans la variable **Sortie** , sélectionnez l’icône + pour créer un paramètre prédéfini de sortie, puis sélectionnez **Base de connaissances** de la **Type** dans la liste déroulante **Nouveau paramètre prédéfini de sortie** boîte de dialogue. Vous pouvez nommer le paramètre prédéfini et choisir la cible pour générer la sortie à l’aide de la variable **Adobe Experience Manager**, **Salesforce**, ou **ServiceNow**.




## Configuration de la base de connaissances{#knowledge-base-configuration}


Dans l&#39;éditeur Web, les configurations suivantes ont été organisées sous la **Général** et **Articles** onglets. Vous pouvez également configurer les paramètres de la variable **Base de connaissances** vous avez sélectionné comme cible, **Adobe Experience Manager**, **Salesforce**, ou **ServiceNow**.


### Général

| Options de la base de connaissances | Description |
| --- | --- |
| Appliquer les conditions à l’aide de | Sélectionnez l’une des options suivantes :<br><br>* **Aucun appliqué**: sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur la sortie publiée.<br>* **Fichier DITAVAL**: sélectionnez le ou les fichiers DITAVAL pour générer du contenu personnalisé. Vous pouvez sélectionner plusieurs fichiers DITAVAL à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin du fichier. Pour le supprimer, utilisez l’icône croisée située à proximité du nom du fichier. Les fichiers DITAVAL sont évalués dans l’ordre spécifié. Par conséquent, les conditions spécifiées dans le premier fichier sont prioritaires sur les conditions correspondantes spécifiées dans les fichiers ultérieurs. Vous pouvez conserver l’ordre des fichiers en ajoutant ou en supprimant des fichiers. Si le fichier DITAVAL est déplacé ou supprimé, il n’est pas automatiquement supprimé du paramètre prédéfini. Vous devez mettre à jour l’emplacement au cas où des fichiers seraient déplacés ou supprimés. Vous pouvez placer le pointeur de la souris sur le nom du fichier pour afficher le chemin d’accès dans le référentiel Adobe Experience Manager où le fichier est stocké. Vous ne pouvez sélectionner que les fichiers DITAVAL et une erreur s’affiche si vous sélectionnez un autre type de fichier.<br>* **Paramètre prédéfini de condition**: sélectionnez un paramètre prédéfini de condition dans la liste déroulante pour appliquer une condition lors de la publication de la sortie. L’option est visible si vous avez ajouté une condition présente dans l’onglet Paramètres prédéfinis de condition de la console de mappage DITA. Pour en savoir plus sur les paramètres prédéfinis de condition, consultez [Utilisation des paramètres de condition prédéfinis](generate-output-use-condition-presets.md#id1825FL004PN). |
| Utilisation de la ligne de base | Si vous avez créé une ligne de base pour le mappage DITA sélectionné, sélectionnez cette option pour spécifier la version que vous souhaitez publier.<br><br>Affichage [Utilisation de la ligne de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) pour plus d’informations. |
| Processus de génération de publication | Lorsque vous sélectionnez cette option, une nouvelle liste déroulante Processus de génération de publication contenant tous les workflows configurés dans Adobe Experience Manager s’affiche. Vous devez sélectionner un workflow à exécuter une fois la génération de la sortie terminée.<br><br>**Remarque**: en savoir plus sur la manière de procéder [personnaliser le workflow de génération de sortie](../cs-install-guide/customize-workflows.md#id17A6GI004Y4) dans le Guide d’installation et de configuration pour les Cloud Service. |

### ServiceNow

| Options ServiceNow | Description |
| --- | --- |
| Profil de publication | Utilisez la liste déroulante pour sélectionner parmi les profils de connexion ServiceNow configurés par l’administrateur. Pour en savoir plus sur la manière dont votre administrateur peut créer un profil de publication, consultez la **Paramètres de l’éditeur** description des fonctionnalités dans la section [Panneau gauche](./web-editor-features.md#id2051EA0M0HS) . |
| Base de connaissances | Utilisez ce champ pour sélectionner la base de connaissances ServiceNow requise. Vous pouvez configurer des bases de connaissances sur le site ServiceNow pour stocker le contenu en fonction des autorisations. Les articles de cette carte DITA peuvent être publiés dans ces bases de connaissances. |
| Catégorie et sous-catégorie | Les catégories sont comme des arborescences hiérarchiques utilisées pour rechercher et classer les articles de la base de connaissances ServiceNow. Ajoutez une catégorie et une sous-catégorie pour publier les rubriques et sous-rubriques de la table des matières dans cette catégorie et sous-catégorie sur le site ServiceNow. |

### Salesforce

| Options Salesforce | Description |
| --- | --- |
| Profil de publication | Utilisez la liste déroulante pour sélectionner parmi les profils de connexion Salesforce configurés par votre administrateur. Pour en savoir plus sur la manière dont votre administrateur peut créer un profil de publication, consultez la **Paramètres de l’éditeur** description des fonctionnalités dans la section [Panneau gauche](./web-editor-features.md#id2051EA0M0HS) . |
| Type d’enregistrement | Utilisez la liste déroulante pour sélectionner parmi les types d’enregistrement configurés dans Salesforce selon les paramètres de visibilité basés sur votre profil utilisateur. Les types d’enregistrement Salesforce permettent de regrouper de nombreux enregistrements d’un type pour cet objet. Ils définissent la manière dont votre publication est organisée. Par exemple, vous pouvez sélectionner FAQ Type d’enregistrement et publier selon la mise en page et les champs de la page FAQ. |
| Champ de contenu de l’article | Vous pouvez avoir différents champs et une disposition unique pour chaque modèle de type d’enregistrement. Utilisez ces champs pour saisir des informations spécifiques en fonction du type d&#39;article. Vous pouvez, par exemple, afficher le titre, la réponse et l’équation d’un article de la FAQ. |
| Catégories | Sélectionnez une catégorie dans la liste déroulante pour publier les rubriques de la table des matières de cette catégorie sur le site Salesforce. |

Vous pouvez également afficher les options suivantes dans les paramètres prédéfinis Salesforce et ServiceNow : | Options | Description | | — | — | |Supprimez l’en-tête de rubrique du corps de l’article.|Sélectionnez cette option pour supprimer l’en-tête de rubrique de l’article dans la sortie publiée. | |Télécharger en tant que brouillon | Sélectionnez cette option pour charger la rubrique à partager en tant que brouillon avant de la mettre à la disposition des utilisateurs.| |Télécharger les images| Sélectionnez cette option si vous souhaitez que les images des rubriques soient incluses dans la sortie publiée.| |Télécharger les documents liés| Sélectionnez cette option pour inclure les documents liés dans les rubriques de la sortie publiée.|


### Adobe Experience Manager

>[!NOTE]
>
>Vous pouvez utiliser le paramètre prédéfini de la base de connaissances Adobe Experience Manager si votre administrateur l’a configuré. Pour plus d’informations, voir [Publication basée sur des articles à partir de l’éditeur web](../install-guide/configure-article-based-publishing.md) dans le Guide d&#39;installation et de configuration.

| Options Adobe Experience Manager | Description |
| --- | --- |
| Utilisation du chemin de l’article | Sélectionnez cette option pour afficher la **Chemin de l’article** du dossier contenant les modèles de la base de connaissances. |
| Chemin de l’article | Ce champ s’affiche si vous sélectionnez l’option **Utilisation du chemin de l’article**. Sélectionnez le site de la base de connaissances dans votre référentiel Adobe Experience Manager où est stockée la sortie. |
| Site | Utilisez ce champ pour sélectionner la base de connaissances Adobe Experience Manager requise. Vous pouvez configurer des bases de connaissances sur le site Adobe Experience Manager pour stocker le contenu en fonction des autorisations. Les articles de cette carte DITA peuvent être publiés dans ces bases de connaissances. |
| Catégorie | Sélectionnez une catégorie dans la liste déroulante pour publier les rubriques de la table des matières dans cette catégorie sur le site Adobe Experience Manager. |
| Modèle de section et modèle d’article | Il s’agit des composants structurels utilisés pour organiser le contenu de votre sortie. Elles sont prédéfinies dans le modèle Site Adobe Experience Manager . |
| Processus de génération de publication | Lorsque vous sélectionnez cette option, une nouvelle liste déroulante Processus de génération de publication contenant tous les workflows configurés dans Adobe Experience Manager s’affiche. Vous devez sélectionner un workflow à exécuter une fois le workflow de génération de sortie terminé.<br>En savoir plus sur la manière de procéder [personnaliser le workflow de génération de sortie](../install-guide/customize-workflows.md#id17A6GI004Y4) dans le Guide d&#39;installation et de configuration. |
>[!TIP]
> 
>Sélectionner **Actualiser** ![icône d’actualisation](images/navtitle-refresh-icon.svg) pour renseigner les modèles respectifs dans les champs conformément au modèle de la base de connaissances que vous avez sélectionné.

### Articles

Cet onglet affiche l’arborescence ou la vue hiérarchique de la carte. Choisissez les rubriques que vous souhaitez publier dans une base de connaissances. Développez un noeud de table des matières et sélectionnez les rubriques que vous souhaitez publier.

**Rubrique parente :** [Présentation des paramètres prédéfinis de sortie](generate-output-understand-presets.md)
