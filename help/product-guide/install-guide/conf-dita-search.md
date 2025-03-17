---
title: Configuration de la recherche de l’interface utilisateur d’AEM Assets
description: Découvrez comment configurer la recherche pour l’interface utilisateur d’AEM Assets
exl-id: b920ba7f-e8fc-4af6-aa8a-b8516b1cffc0
feature: Search Configuration
role: Admin
level: Experienced
source-git-commit: 8ee4863470f69bca52a9b36cde52703e4d6643bc
workflow-type: tm+mt
source-wordcount: '1695'
ht-degree: 1%

---

# Configuration de la recherche de l’interface utilisateur d’AEM Assets {#id192SC800MY4}

Par défaut, AEM ne reconnaît pas le contenu DITA. Par conséquent, il ne fournit aucun mécanisme pour rechercher du contenu DITA dans son référentiel. AEM Guides vous permet d’ajouter la fonctionnalité de recherche de contenu DITA dans le référentiel AEM.

Par défaut, AEM ne reconnaît pas le contenu DITA. Par conséquent, il ne fournit aucun mécanisme pour rechercher du contenu DITA dans son référentiel. En outre, il n’existe aucune fonctionnalité prête à l’emploi pour rechercher du contenu en fonction de son UUID. AEM Guides vous permet d&#39;ajouter les fonctionnalités de recherche de contenu DITA et de recherche basée sur l&#39;UUID dans le référentiel AEM.

La configuration de la recherche de contenu DITA implique les tâches suivantes :

1. [Ajout du composant Recherche d’éléments DITA dans l’interface utilisateur d’Assets](#id192SF0F50HS)
1. [Ajouter un composant de recherche basé sur l’UUID dans l’interface utilisateur d’Assets](#id2034F04K05Z)
1. [Fournir des autorisations aux utilisateurs](#id192SF0G0RUI)
1. [Ajout d’éléments ou d’attributs personnalisés dans la recherche](#id192SF0G10YK)
1. [Extraction de métadonnées à partir de contenu existant](#id192SF0GA0HT)

Outre l’ajout de la fonctionnalité de recherche, vous pouvez également configurer les dossiers qui ne doivent pas être inclus dans la recherche. Pour plus d’informations, voir [Exclure les fichiers temporaires des résultats de la recherche](#id197AHI0035Z).

## Ajout du composant Recherche d’éléments DITA dans l’interface utilisateur d’Assets {#id192SF0F50HS}

Pour ajouter un composant de recherche de contenu DITA à l&#39;interface utilisateur d&#39;AEM Assets, procédez comme suit :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Cliquez sur le lien **Adobe Experience Manager** en haut et choisissez **Outils**.

1. Sélectionnez **Général** dans la liste des outils, puis cliquez sur la mosaïque **Rechercher dans Forms**.

1. Dans la liste **Search Forms**, sélectionnez le **Rail de recherche d’administration Assets**.

1. Cliquez sur **Modifier**.
1. Dans l’onglet **Sélectionner le prédicat**, faites défiler la liste jusqu’à la fin.

1. Faites glisser et déposez **prédicat d’élément DITA** à l’emplacement requis dans le formulaire de recherche.

   ![](assets/drag-search-predicate.png){width="650" align="left"}

1. Cliquez sur **Terminé** pour enregistrer vos modifications.

   Lorsque vous accédez à l’option Filtres dans l’interface utilisateur d’Assets, vous obtenez l’option Filtrage de recherche par élément DITA .

   ![](assets/search-filter-asset-console.png){width="350" align="left"}


## Ajouter un composant de recherche basé sur l’UUID dans l’interface utilisateur d’Assets {#id2034F04K05Z}

Pour ajouter un composant de recherche basé sur l’UUID à l’interface utilisateur d’AEM Assets, procédez comme suit :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Cliquez sur le lien **Adobe Experience Manager** en haut et choisissez **Outils**.

1. Sélectionnez **Général** dans la liste des outils, puis cliquez sur la mosaïque **Rechercher dans Forms**.

1. Dans la liste **Search Forms**, sélectionnez le **Rail de recherche d’administration Assets**.

1. Cliquez sur **Modifier**.
1. Dans l’onglet **Sélectionner le prédicat**, choisissez **Prédicat de propriété** et faites-le glisser à l’emplacement requis dans le formulaire de recherche.

1. Dans l’onglet **Paramètres**, fournissez les détails suivants pour le composant **Prédicat de propriété** nouvellement ajouté :

   - **Libellé du champ** : UUID
   - **Nom de la propriété** : jcr:content/fmUuid
1. Cliquez sur **Terminé** pour enregistrer vos modifications.

   Lorsque vous accédez à l’option Filtres dans l’interface utilisateur d’Assets, vous obtenez l’option de filtrage de recherche basé sur l’interface utilisateur.


## Fournir des autorisations aux utilisateurs {#id192SF0G0RUI}

Les auteurs et les éditeurs doivent disposer d’autorisations explicites pour pouvoir accéder aux fonctionnalités de recherche à partir de l’interface utilisateur d’Assets. Si vous n&#39;accordez pas ces autorisations, vos utilisateurs ne pourront pas rechercher du contenu DITA en fonction de leurs valeurs d&#39;élément/attribut ou de leur UUID.

Pour fournir l&#39;accès à la fonction de recherche DITA, procédez comme suit :

1. Accédez à la page des autorisations des utilisateurs et des groupes. L’URL par défaut pour accéder à la page est :

   `http://<server name>:<port>/useradmin.html`

1. Recherchez le groupe d’utilisateurs ou un utilisateur individuel auquel vous souhaitez accorder l’accès. Par exemple, pour donner accès à tous les utilisateurs du groupe auteurs, saisissez auteurs dans le champ **Filtrer la requête** et appuyez sur **Entrée**.

   ![](assets/authors-group-permission.png){width="350" align="left"}

1. Sélectionnez le groupe **auteurs**.

1. Dans le volet de droite, sélectionnez l’onglet **Autorisations**.

1. Accédez à l’emplacement du dossier suivant :

   /conf/global/settings/dam/search

1. Donnez l’autorisation **Lecture** au dossier de recherche.

   ![](assets/read-permission-authors.png){width="650" align="left"}

1. Cliquez sur **Enregistrer**.


L’utilisateur ou le groupe d’utilisateurs sélectionné aura désormais accès à la fonction de recherche de contenu DITA dans l’interface utilisateur d’Assets.

## Ajout d’éléments ou d’attributs personnalisés dans la recherche {#id192SF0G10YK}

Pour que la recherche DITA fonctionne, un prétraitement du contenu DITA est nécessaire. Cette étape de prétraitement extrait le contenu sélectif des cartes et rubriques DITA individuelles afin de pouvoir l&#39;indexer pour accélérer la recherche. En interne, ce processus est appelé *Sérialisation*. La sérialisation des fichiers DITA a lieu pendant le chargement du contenu ou peut également être exécutée à la demande. Il utilise un fichier de configuration pour déterminer la quantité de contenu de chaque fichier DITA à indexer. L&#39;emplacement par défaut du fichier de sérialisation est :

/libs/fmdita/config/serializationconfig.xml

La configuration de recherche par défaut vous permet de rechercher tous les éléments et attributs dans l&#39;élément DITA `prolog`. Si vous souhaitez effectuer une recherche sur la base d’autres éléments ou attributs, vous devez configurer le fichier de sérialisation de recherche.

>[!NOTE]
>
> Si vous souhaitez utiliser la configuration de recherche par défaut dans l’élément `prolog`, vous pouvez ignorer ce processus.

Ce fichier contient deux sections principales : jeu d’attributs et jeu de règles. Un extrait de la section Ensemble de règles est fourni ci-dessous :

```XML
<ruleset filetypes="xml dita"><!-- Element rules --><rule xpath="//[contains(@class, 'topic/topic')]/[contains(@class, 'topic/prolog')]//*[not(*)]" text="yes" attributeset="all-attrs" /><!-- Attribute rules --><rule xpath="//[contains(@class, 'topic/topic')]/[contains(@class, 'topic/prolog')]///@[local-name() != 'class']" /></ruleset>
```

Dans la section Ensemble de règles , vous pouvez indiquer les informations suivantes :

- Règles d’extraction des éléments

- Règles d’extraction des attributs


Une règle se compose des éléments suivants :

**xpath** - Il s&#39;agit de la requête XPath qui récupère les éléments ou attributs des fichiers DITA. La configuration par défaut de la règle d’élément récupère tous les éléments `prolog`. De plus, la configuration par défaut de la règle d’attribut récupère tous les attributs des éléments `prolog`. Vous pouvez spécifier une requête XPath pour sérialiser les éléments ou attributs à rechercher.

La requête XPath contient le nom de classe du type de document. La classe `topic/topic` est utilisée pour les documents DITA de type rubrique. Si vous souhaitez créer une règle pour d&#39;autres documents DITA, vous devez utiliser les noms de classe suivants :

| Type de document | Nom de la classe |
|-------------|----------|
| Thème | - topic/topic |
| Tâche | - topic/topic task/task |
| Concept | - sujet/sujet concept/concept |
| Référence | - topic/topic reference/reference |
| Map | - map/map |

**text** - Si vous souhaitez rechercher du texte dans l’élément spécifié, spécifiez la valeur oui. Si vous spécifiez la valeur no, seuls les attributs de l’élément sont sérialisés. Les attributs que vous souhaitez rechercher doivent être spécifiés dans la section du jeu d’attributs.

**attributeset** - Indiquez l’identifiant du jeu d’attributs à associer à cette règle. La valeur all-attrs est un cas particulier qui indique que tous les attributs de cette règle doivent être sérialisés.

Un jeu d&#39;attributs contient une liste d&#39;attributs que vous souhaitez rechercher dans le contenu DITA. Le jeu d’attributs contient les éléments suivants :

**id** - Identifiant unique du jeu d’attributs. Cet identifiant est spécifié dans le paramètre de jeu d’attributs d’un ensemble de règles.

**attribute** - Liste des attributs que vous souhaitez rechercher. Pour chaque attribut, vous devez créer une entrée individuelle dans l’élément `attribute`.

Procédez comme suit pour ajouter des éléments ou attributs DITA personnalisés dans le fichier de sérialisation de recherche :

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite .

1. Accédez au fichier de configuration de sérialisation disponible à l’emplacement suivant :

   /libs/fmdita/config/serializationconfig.xml

1. Créez un nœud de recouvrement du dossier `config` dans le nœud `apps` .

1. Accédez au fichier de configuration disponible dans le nœud `apps` :

   `/apps/fmdita/config/serializationconfig.xml`

1. Ajoutez les ensembles de règles d’attribut ou d’élément requis.

1. Enregistrez le fichier.

1. Ouvrez la page de configuration de la console web Adobe Experience Manager . L’URL par défaut pour accéder à la page de configuration est :

   http://&lt;nom du serveur\>:&lt;port\>/system/console/configMgr

1. Recherchez et cliquez sur le lot *com.adobe.fmdita.config.ConfigManager* et cliquez dessus.

1. Cliquez sur **Enregistrer**.


Les nouvelles informations de sérialisation sont stockées et activées pour la recherche. Toutefois, vous devez extraire les métadonnées de votre contenu DITA existant pour pouvoir effectuer des recherches.

## Extraction de métadonnées à partir de contenu existant {#id192SF0GA0HT}

Une fois que vous avez apporté des modifications au fichier de sérialisation de recherche par défaut, vous devez activer l&#39;option Extraction de métadonnées DITA dans le lot *com.adobe.fmdita.config.ConfigManager*, puis exécuter le workflow pour extraire les métadonnées. Cette opération extrait les métadonnées requises des fichiers DITA existants, puis les met à disposition pour la recherche.

Si vous créez de nouveaux fichiers ou modifiez un fichier après la mise à jour du fichier de sérialisation, les métadonnées sont automatiquement extraites de ces fichiers. Le processus d’extraction des métadonnées n’est nécessaire que pour les fichiers qui existent déjà dans le référentiel AEM.

L&#39;extraction de métadonnées à partir de fichiers DITA existants implique deux tâches :

1. Activation de l’option d’extraction des métadonnées dans configMgr
1. Exécution du workflow d’extraction des métadonnées

Pour activer l’option d’extraction des métadonnées dans configMgr, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager . L’URL par défaut pour accéder à la page de configuration est :

   http://&lt;nom du serveur\>:&lt;port\>/system/console/configMgr

1. Recherchez et cliquez sur le lot *com.adobe.fmdita.config.ConfigManager* et cliquez dessus.

1. Sélectionnez l&#39;option **Activer l&#39;extraction des métadonnées DITA**.

1. Cliquez sur **Enregistrer**.


Pour exécuter le workflow d’extraction des métadonnées, procédez comme suit :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Cliquez sur le lien **Adobe Experience Manager** en haut et choisissez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils, puis cliquez sur la mosaïque **Extraction des métadonnées DITA**.

1. Si vous souhaitez extraire des métadonnées d’un seul fichier et de ses dépendances, cliquez sur le lien **Sélectionner un fichier** et recherchez un fichier.

1. Si vous souhaitez extraire des métadonnées de plusieurs fichiers dans un dossier, cliquez sur le lien **Sélectionner un ou plusieurs dossiers\(s\)**, recherchez et sélectionnez le dossier requis. Cliquez sur le bouton **Ajouter** pour ajouter le dossier à la liste des tâches de sérialisation.

   >[!NOTE]
   >
   > Vous pouvez sélectionner et ajouter plusieurs dossiers à une tâche de sérialisation.

1. Cliquez sur **Démarrer**.

1. Dans la boîte de dialogue Confirmer l’extraction des métadonnées , cliquez sur **OK**.


## Exclure les fichiers temporaires des résultats de recherche {#id197AHI0035Z}

Par défaut, la recherche est effectuée sur l’ensemble du référentiel d’AEM. Certains emplacements peuvent être à exclure de la recherche. Par exemple, lorsque vous lancez le workflow de traduction de contenu, les fichiers non approuvés restent dans un emplacement de dossier temporaire. Lorsque vous effectuez la recherche, les fichiers de cet emplacement temporaire sont également renvoyés dans les résultats de la recherche.

Pour empêcher AEM Guides de rechercher l’emplacement du dossier de traduction temporaire, vous devez ajouter l’emplacement du dossier temporaire dans la liste d’exclusion.

Pour exclure le dossier de traduction temporaire de la recherche, procédez comme suit :

>[!NOTE]
>
> Cette procédure vous permet d’ajouter n’importe quel autre emplacement de dossier à la liste d’exclusion.

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite .

1. Accédez au nœud damAssetLucene disponible à l’emplacement suivant :

   /oak:index/damAssetLucene

1. Ajoutez la propriété suivante au nœud damAssetLucene :

   | Nom de la propriété | Type | Valeur |
   |-------------|----|-----|
   | excludePaths | Chaîne\[\] | Ajoutez la valeur suivante à cette propriété : <br>/content/dam/projects/translation\_output |

1. Accédez au nœud Lucene disponible à l’emplacement suivant :

   /oak:index/lucene

1. Ajoutez la propriété suivante au nœud Lucene :

   | Nom de la propriété | Type | Valeur |
   |-------------|----|-----|
   | excludePaths | Chaîne\[\] | Ajoutez les valeurs suivantes à cette propriété : <br><ul><li>/var/dxml</li><li>/content/dam/projects/translation\_output</li></ul> |
