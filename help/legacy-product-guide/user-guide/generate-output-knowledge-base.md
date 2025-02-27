---
title: Base de connaissances
description: Découvrez comment créer un paramètre prédéfini de la base de connaissances à partir de l’éditeur web et du tableau de bord de carte. Configurez le paramètre prédéfini de sortie de la base de connaissances dans AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: 5fc81de9-9ae0-4cd4-a7ef-b52eed2479f7
source-git-commit: 1426cdaecdd358f06e76908b09330e65997e8452
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 1%

---

# Base de connaissances {#knowledge-base}

Vous pouvez créer le préréglage **Base de connaissances** à partir de l’éditeur web :

Dans le panneau Référentiel, ouvrez le fichier de mappage DITA dans **Vue Carte**, puis dans l&#39;onglet **Sortie**, sélectionnez l&#39;icône + pour créer un paramètre prédéfini de sortie, puis sélectionnez **Base de connaissances** dans la liste déroulante **Type** de la boîte de dialogue **Nouveau paramètre prédéfini de sortie**. Vous pouvez nommer le paramètre prédéfini et choisir la cible pour générer la sortie à l’aide de **Adobe Experience Manager**, **Salesforce** ou **ServiceNow**.




## Configuration de la base de connaissances{#knowledge-base-configuration}


Dans l&#39;éditeur Web, les paramétrages suivants ont été organisés sous les onglets **Général** et **Articles**. Vous pouvez également configurer les paramètres de la **Base de connaissances** spécifique que vous avez sélectionnée en tant que cible, **Adobe Experience Manager**, **Salesforce** ou **ServiceNow**.


### Général

| Options de la base de connaissances | Description |
| --- | --- |
| Application de conditions à l’aide de | Sélectionnez l’une des options suivantes :<br><br>* **Aucune appliquée** : sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur la sortie publiée.<br>* **Fichier DITAVAL** : Sélectionnez le ou les fichiers DITAVAL pour générer du contenu personnalisé. Vous pouvez sélectionner plusieurs fichiers DITAVAL à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin d’accès au fichier. Utilisez la croix près du nom du fichier pour le supprimer. Les fichiers DITAVAL sont évalués dans l&#39;ordre spécifié. Les conditions spécifiées dans le premier fichier sont donc prioritaires sur les conditions correspondantes spécifiées dans les fichiers ultérieurs. Vous pouvez conserver l’ordre des fichiers en ajoutant ou en supprimant des fichiers. Si le fichier DITAVAL est déplacé vers un autre emplacement ou supprimé, il n’est pas automatiquement supprimé du paramètre prédéfini. Vous devez mettre à jour l’emplacement au cas où les fichiers seraient déplacés ou supprimés. Vous pouvez pointer sur le nom du fichier pour afficher le chemin d’accès dans le référentiel Adobe Experience Manager où le fichier est stocké. Vous ne pouvez sélectionner que des fichiers DITAVAL et une erreur s&#39;affiche si vous sélectionnez un autre type de fichier.<br>* **Paramètre prédéfini de condition** : sélectionnez un paramètre prédéfini de condition dans la liste déroulante pour appliquer une condition lors de la publication de la sortie. Cette option est visible si vous avez ajouté une condition présente dans l&#39;onglet Paramètres prédéfinis de condition de la console de mappage DITA. Pour en savoir plus sur les paramètres prédéfinis de condition, voir [Utilisation des paramètres prédéfinis de condition](generate-output-use-condition-presets.md#id1825FL004PN). |
| Utiliser niveau de référence | Si vous avez créé une ligne de base pour le plan DITA sélectionné, sélectionnez cette option pour spécifier la version que vous souhaitez publier.<br><br>Affichage [Utilisation de la ligne de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) pour plus d’informations. |
| Workflow de post-génération | Lorsque vous sélectionnez cette option, une nouvelle liste déroulante Workflow de post-génération contenant tous les workflows configurés dans Adobe Experience Manager s’affiche. Vous devez sélectionner un workflow à exécuter une fois la génération de sortie terminée.<br><br>**Remarque** : pour en savoir plus sur la [personnalisation du workflow de génération post-sortie](/help/product-guide/cs-install-guide/customize-workflows.md#id17A6GI004Y4), consultez le Guide d’installation et de configuration des services cloud. |

### ServiceNow

| Options ServiceNow | Description |
| --- | --- |
| Profil de publication | Utilisez la liste déroulante pour sélectionner un profil de connexion ServiceNow configuré par votre administrateur. Pour en savoir plus sur la manière dont votre administrateur peut créer un profil de publication, consultez la description de la fonctionnalité **Paramètres de l’éditeur** dans la section [Panneau de gauche](./web-editor-features.md#id2051EA0M0HS). |
| Base de connaissances | Utilisez ce champ pour sélectionner la base de connaissances ServiceNow requise. Vous pouvez configurer les bases de connaissances sur le site ServiceNow pour stocker le contenu en fonction des autorisations. Les articles de ce plan DITA peuvent être publiés dans ces bases de connaissances. |
| Catégorie et sous-catégorie | Les catégories sont comme des arborescences hiérarchiques utilisées pour rechercher et classer les articles de la base de connaissances ServiceNow. Ajoutez une catégorie et une sous-catégorie pour publier les rubriques et sous-rubriques de la table des matières dans cette catégorie et sous-catégorie sur le site ServiceNow. |

### Salesforce

| Options de Salesforce | Description |
| --- | --- |
| Profil de publication | Utilisez la liste déroulante pour effectuer une sélection parmi les profils de connexion Salesforce configurés par votre administrateur. Pour en savoir plus sur la manière dont votre administrateur peut créer un profil de publication, consultez la description de la fonctionnalité **Paramètres de l’éditeur** dans la section [Panneau de gauche](./web-editor-features.md#id2051EA0M0HS). |
| Type d’enregistrement | Utilisez la liste déroulante pour sélectionner parmi les types d’enregistrements configurés dans Salesforce en fonction des paramètres de visibilité basés sur votre profil utilisateur. Les types d’enregistrements Salesforce permettent de regrouper de nombreux enregistrements d’un type pour cet objet. Elles définissent l&#39;organisation de votre publication. Par exemple, vous pouvez sélectionner le type d’enregistrement FAQ et publier en fonction de la mise en page et des champs de la page FAQ. |
| Champ de contenu d’article | Vous pouvez disposer de différents champs et d’une mise en page unique pour chaque modèle de type d’enregistrement. Utilisez ces champs pour saisir des informations spécifiques en fonction du type d’article. Par exemple, vous pouvez afficher le titre, la réponse et l’équation d’un article de FAQ. |
| Catégories | Sélectionnez une catégorie dans la liste déroulante pour publier les rubriques de la table des matières de cette catégorie sur le site Salesforce. |

Vous pouvez également afficher les options suivantes dans les paramètres prédéfinis Salesforce et ServiceNow :

| Options | Description |
| --- | --- |
| Supprimez l’en-tête de rubrique du corps de l’article. | Sélectionnez cette option pour supprimer l’en-tête de rubrique de l’article dans la sortie publiée. |
| Charger en tant que brouillon | Sélectionnez cette option pour charger la rubrique afin de la partager en tant que brouillon avant de la rendre disponible pour les utilisateurs. |
| Chargement des images | Sélectionnez cette option si vous souhaitez que des images des rubriques soient incluses dans la sortie publiée. |
| Charger les documents liés | Sélectionnez cette option pour inclure les documents liés dans les rubriques dans la sortie publiée. |


### Adobe Experience Manager

>[!NOTE]
>
>Vous pouvez utiliser le paramètre prédéfini de la base de connaissances Adobe Experience Manager si votre administrateur l’a configuré. Pour plus d’informations, consultez la section [ Publication basée sur des articles dans l’éditeur web ](/help/product-guide/install-guide/configure-article-based-publishing.md) du guide d’installation et de configuration.

| Options de Adobe Experience Manager | Description |
| --- | --- |
| Utiliser le chemin de l’article | Sélectionnez cette option pour afficher le **chemin d’accès à l’article** du dossier contenant les modèles de la base de connaissances. |
| Chemin de l’article | Ce champ s’affiche si vous sélectionnez l’option **Utiliser le chemin de l’article**. Accédez au site de la base de connaissances de votre référentiel Adobe Experience Manager où la sortie est stockée. |
| Site | Utilisez ce champ pour sélectionner la base de connaissances Adobe Experience Manager requise. Vous pouvez configurer les bases de connaissances sur le site Adobe Experience Manager pour stocker le contenu en fonction des autorisations. Les articles de ce plan DITA peuvent être publiés dans ces bases de connaissances. |
| Catégorie | Sélectionnez une catégorie dans la liste déroulante pour publier les rubriques de la table des matières de cette catégorie sur le site Adobe Experience Manager. |
| Modèle de section et modèle d’article | Il s’agit des composants structurels utilisés pour organiser le contenu de votre sortie. Ils sont prédéfinis dans le modèle de site Adobe Experience Manager. |
| Workflow de post-génération | Lorsque vous choisissez cette option, une nouvelle liste déroulante Workflow de post-génération contenant tous les workflows configurés dans Adobe Experience Manager s’affiche . Vous devez sélectionner un workflow à exécuter une fois le workflow de génération de sortie terminé.<br>Découvrez comment [personnaliser le workflow de génération post-sortie](/help/product-guide/install-guide/customize-workflows.md#id17A6GI004Y4) dans le Guide d’installation et de configuration. |

>[!TIP]
> 
>Sélectionnez **Actualiser** ![icône d’actualisation](images/navtitle-refresh-icon.svg) pour renseigner les modèles respectifs dans les champs en fonction du modèle de la base de connaissances que vous avez sélectionné.

### Articles

Cet onglet affiche l&#39;arborescence ou la vue hiérarchique de la carte. Choisissez les rubriques que vous souhaitez publier dans une base de connaissances. Développez un nœud de table des matières et sélectionnez les rubriques à publier.

**Rubrique parente :** [Présentation des paramètres prédéfinis de sortie](generate-output-understand-presets.md)
