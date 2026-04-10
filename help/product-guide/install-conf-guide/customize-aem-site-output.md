---
title: Configurer les paramètres de génération de sortie
description: Découvrez comment configurer les paramètres de génération de sortie
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '3098'
ht-degree: 1%

---


# Personnaliser la sortie du site AEM {#id166TG0B30WR}

AEM Guides prend en charge la création de sorties dans les formats suivants :

- Site AEM
- PDF
- HTML5
- EPUB
- Sortie personnalisée via DITA-OT

Pour la sortie du site AEM, vous pouvez affecter différents modèles de conception avec différentes tâches de sortie. Ces modèles de conception peuvent effectuer le rendu du contenu DITA dans différentes dispositions. Par exemple, vous pouvez spécifier différents modèles de conception pour les audiences internes et externes.

Vous pouvez également utiliser des modules externes DITA Open Toolkit \(DITA-OT\) personnalisés avec AEM Guides. Vous pouvez charger ces plug-ins DITA-OT personnalisés pour générer une sortie PDF d’une manière spécifique.

>[!TIP]
>
> Voir la section *Publication sur le site* dans le [guide des bonnes pratiques](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-mar-22/Adobe-Experience-Manager-Guides_Best-Practices_EN.pdf) pour connaître les bonnes pratiques concernant la création d’une sortie de site AEM.


## Personnaliser le modèle de conception pour générer la sortie {#customize_xml-add-on}

AEM Guides utilise un ensemble de modèles de conception prédéfinis pour générer une sortie de site AEM. Vous pouvez personnaliser les modèles de conception AEM Guides pour générer une sortie conforme à la valorisation de marque de votre entreprise. Un modèle de conception est un ensemble de différents styles \(CSS\), scripts \(côté serveur et côté client\), ressources \(images, logos et autres ressources\) et nœuds JCR qui lient toutes ces ressources. Un modèle de conception peut être aussi simple qu’un script côté serveur unique avec seulement quelques nœuds JCR ou une combinaison complexe de styles, de ressources et de nœuds JCR. Les modèles de conception sont utilisés par le sous-système de publication d’AEM Guides lors de la génération de la sortie du site AEM et contrôlent la structure, l’aspect et la fonctionnalité de la sortie générée.

Il n’existe aucune restriction quant à l’emplacement des ressources du modèle de conception sur le serveur, mais elles sont généralement organisées de manière logique en fonction de leur fonction. Par exemple, tous les fichiers JavaScript et CSS du modèle par défaut sont stockés dans `/etc/designs/fmdita/clientlibs/siteoutput/default` dossier . Où que se trouvent ces fichiers, ils sont liés entre eux par un ensemble de nœuds JCR. Ensemble, ces nœuds JCR et les fichiers constituent l’ensemble du modèle de conception.

Le modèle de conception par défaut fourni avec AEM Guides vous permet de personnaliser les composants des pages de destination, de rubrique et de recherche. Vous pouvez faire une copie de la conception par défaut et des modèles de référence correspondants et spécifier différents composants pour générer la sortie souhaitée.

Les onglets suivants fournissent des instructions pour spécifier votre propre modèle de conception à utiliser pour la génération de sortie de site AEM en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB ]

1. Utilisez le gestionnaire de packages pour télécharger le modèle de conception par défaut à partir de l’emplacement suivant :

   /libs/fmdita/config/templates

1. Créez une copie des fichiers téléchargés à l’emplacement suivant dans votre référentiel Git Cloud Manager :

   /apps/fmdita/config/templates

1. Vous devez également télécharger et copier les modèles référencés à partir du nœud de modèle par défaut. Les modèles référencés sont placés sous :

   /libs/fmdita/templates/default/cqtemplates

>[!TAB  On-Premise ]

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite .

1. Accédez au nœud du modèle de conception par défaut. L’emplacement du nœud de modèle de conception par défaut est :

   `/libs/fmdita/config/templates/`

   ![](assets/templates-node.png){width="300" align="left"}

   >[!NOTE]
   >
   > Effectuez une copie des modèles de conception par défaut du dossier `libs` vers le dossier `apps` et apportez des modifications au dossier `apps`. Vous devez également apporter des modifications aux modèles référencés à partir du nœud de modèle par défaut. Les modèles référencés sont placés sous `/libs/fmdita/templates/default/cqtemplates` nœud . Effectuez une copie des modèles référencés dans le dossier `apps` avant d’apporter des modifications.

1. Cliquez sur le composant *default* dans le nœud *templates* pour accéder à ses propriétés.

>[!ENDTABS]

Les propriétés du modèle de conception AEM Guides sont décrites dans le tableau ci-après.

| Propriété | Description |
|--------|-----------|
| `landingPageTemplate`, `searchPageTemplate`, `topicPageTemplate`, `shadowPageTemplate` | Spécifiez le nœud `cq:Template` pour ces pages correspondantes \(destination, recherche et rubrique\). Par défaut, le nœud `cq:Template` de ces pages se trouve dans `/libs/fmdita/templates/default/cqtemplates` nœud . Ce nœud définit la structure et les propriétés des pages de destination, de recherche et de rubrique.<br> Le `shadowPageTemplate` est utilisé pour optimiser le contenu segmenté. Vous devez définir la valeur de cette propriété sur : `fmdita/templates/default/cqtemplates/shadowpage` <br> **Remarque :** vous devez spécifier une valeur pour le `topicPageTemplate`. Les propriétés `landingPageTemplate` et `searchPageTemplate` sont facultatives. Si vous ne souhaitez pas que les pages de recherche et de destination soient générées, ne spécifiez pas ces propriétés. |
| `title` | Nom descriptif de votre modèle de conception. |
| `topicContentNode` | Emplacement du nœud qui contiendra le contenu DITA dans une page de rubrique. Le chemin d’accès est relatif à la page du topic. |
| `topicHeadNode` | Emplacement du nœud qui contiendra les valeurs head \(ou metadata\) dérivées du contenu DITA. Le chemin d’accès est relatif à la page du topic. |
| `tocNode` | Emplacement du nœud qui contiendra la table des matières. Le chemin est relatif à la page de destination ou au chemin de destination. |
| `basePathProp` | Nom de la propriété servant à stocker le chemin d’accès de la racine du site publié. |
| `indexPathProp` | Nom de la propriété servant à stocker le chemin d’accès de la page de destination/d’index du site publié. |
| `pdfPathProp` | Nom de la propriété permettant de stocker le chemin d’accès au PDF de rubrique, si la génération du PDF de rubrique est activée. |
| `pdfTypeProp` | Nom de la propriété permettant de stocker le type de génération PDF. Actuellement, cette propriété contient toujours « Topic ». |
| `searchPathProp` | Nom de la propriété servant à stocker le chemin d’accès à la page de recherche, si le modèle inclut une page de recherche. |
| `siteTitleProp` | Nom de la propriété servant à stocker le titre du site en cours de publication. Ce titre est généralement identique au titre de la carte en cours de publication. |
| `sourcePathProp` | Nom de la propriété servant à stocker le chemin d&#39;accès de la rubrique DITA source pour la page active. |
| `tocPathProp` | Nom de la propriété servant à stocker le chemin d’accès de la racine de la table des matières pour le site publié. |


>[!NOTE]
>
> Après avoir créé un nœud de modèle de conception personnalisé, vous devez mettre à jour l’option Conception dans les paramètres prédéfinis de sortie du site AEM pour utiliser le nœud du modèle de conception personnalisé.

Pour plus d’informations, consultez les sections [Création de votre premier site web Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=fr) et [Principes de base](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/develop-wknd-tutorial.html?lang=en) du développement de votre propre site web sur AEM.

## Utiliser le titre du document pour générer la sortie du site AEM

Lors de la génération de la sortie du site AEM, la manière dont les URL sont générées joue un rôle important dans la capacité de découverte de votre contenu. Si vous utilisez des noms de fichiers basés sur l’UUID, la génération d’URL basées sur l’UUID de vos fichiers ne sera pas adaptée à la recherche. En tant qu’administrateur ou éditeur, vous avez le contrôle sur la manière dont vous souhaitez générer les URL pour la sortie de votre site AEM. AEM Guides vous offre une configuration qui vous permet de générer les URL de sortie du site AEM à l’aide du titre du fichier plutôt que des noms de fichier basés sur l’UUID. Par défaut, pour les systèmes de fichiers basés sur UUID, cette option est activée. Cela signifie que lorsque vous générez une sortie AEM Site pour des systèmes de fichiers basés sur l’UUID, les titres des fichiers sont utilisés pour générer les URL et non les UUID des fichiers.

Pour la configuration On-Premise avec des systèmes de fichiers non basés sur UUID, la sortie du site AEM est générée à l’aide des noms de fichier et non des titres du fichier. Par défaut, cette option est désactivée. Cela signifie que lorsque vous générez une sortie de site AEM, les noms de fichier sont utilisés pour générer les URL et non le titre du fichier. Vous pouvez choisir de générer les URL en fonction des titres des fichiers en activant cette option.

Les onglets suivants fournissent des instructions pour configurer la génération d’URL dans la sortie de site AEM en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!NOTE]
>
> Vous pouvez continuer à configurer des règles pour n’autoriser qu’un ensemble de caractères dans les URL d’une sortie de site AEM. Pour plus d’informations, consultez [Configuration des règles d’assainissement de nom de fichier pour créer des rubriques et publier la sortie du site AEM](#id2164D0KD0XA).

>[!BEGINTABS]

>[!TAB ]

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(property\) suivants pour configurer la génération des URL dans la sortie du site AEM :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `aemsite.pagetitle` | Booléen \(true/false\). Si vous souhaitez générer une sortie à l’aide du titre de la page, définissez cette propriété sur true. Par défaut, il est défini pour utiliser le nom de fichier <br>. **Valeur par défaut** : false |


>[!TAB  On-Premise ]

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.config.ConfigManager** et cliquez dessus.

1. Sélectionnez l’option **Utiliser le titre pour les noms de page du site AEM**.

   >[!NOTE]
   >
   > Si vous souhaitez générer une sortie à l’aide des noms de fichier, désélectionnez cette option.

1. Cliquez sur **Enregistrer**.

>[!ENDTABS]

## Configurez l’URL de sortie du site AEM pour utiliser le titre du document (uniquement pour Cloud Service)

Vous pouvez utiliser les titres du document dans l’URL de la sortie Site AEM. Si le nom de fichier n’existe pas ou contient tous les caractères spéciaux, vous pouvez configurer le système pour remplacer les caractères spéciaux par un séparateur dans l’URL de la sortie du site AEM. Vous pouvez également le configurer pour les remplacer par le nom de la première rubrique enfant.


Pour configurer les noms de page, procédez comme suit :

1. Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md#) pour créer le fichier de configuration.
1. Dans le fichier de configuration, fournissez les détails (propriété) suivants pour configurer les noms de page pour les rubriques.

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeName` | `nodename.systemDefinedPageName` | Booléen (`true/false`). **Valeur par défaut** : `false` |

Par exemple, si le caractère ** dans `<topichead>` contient tous les caractères spéciaux et que vous définissez la propriété `aemsite.pagetitle` sur true, alors, par défaut, il utilise un séparateur. Si vous définissez la propriété `nodename.systemDefinedPageName` sur true, elle affiche le nom de la première rubrique enfant.


## Configurez les règles d’assainissement de nom de fichier pour créer des rubriques et publier la sortie dans AEM Sites et d’autres formats {#id2164D0KD0XA}

En tant qu’administrateur, vous pouvez définir une liste de caractères spéciaux valides autorisés dans les noms de fichier, qui constituent à terme l’URL d’une sortie de site AEM. Dans les versions antérieures, les utilisateurs étaient autorisés à définir des noms de fichier contenant des caractères spéciaux tels que `@`, `$`, `>`, etc. Ces caractères spéciaux entraînaient un encodage de l’URL lors de la génération des pages du site AEM.

À partir de la version 3.8, des configurations ont été ajoutées pour définir une liste de caractères spéciaux autorisés dans les noms de fichier. Par défaut, la configuration de nom de fichier valide contient « `a-z A-Z 0-9 - _` ». Cela signifie que lors de la création d’un fichier, vous pouvez avoir n’importe quel caractère spécial dans le titre du fichier, mais qu’en interne, il sera remplacé par un trait d’union \(`-`\) dans le nom du fichier. Par exemple, si le titre du fichier est Introduction 1 ou Introduction@1, le nom de fichier correspondant généré pour ces deux cas serait Introduction-1.

Lorsque vous définissez une liste de caractères valides, n&#39;oubliez pas que ces caractères « `*/:[\]|#%{}?&<>"/+` » et `a space` seront toujours remplacés par un trait d&#39;union \(`-`\).

>[!NOTE]
>
> Si vous ne configurez pas la liste de caractères spéciaux valide, le processus de création de fichier peut vous donner des résultats inattendus.

Les onglets suivants fournissent des instructions pour configurer les caractères spéciaux valides dans les noms de fichier et la sortie du site AEM en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB ]

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(property\) suivants pour configurer les caractères spéciaux valides dans les noms de fichier et la sortie de site AEM :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Assurez-vous que la propriété est définie sur ``'<>`@$``. Vous pouvez ajouter d’autres caractères spéciaux à cette liste. |

>[!NOTE]
> 
> La configuration ci-dessus s’applique à tous les formats de sortie. Cela signifie que lors de la génération d’une sortie PDF, HTML ou personnalisée, la sortie finale suivra les règles d’assainissement de nom de fichier configurées.

Vous pouvez également configurer d’autres propriétés, telles que l’utilisation de minuscules dans les noms de fichier, un séparateur pour gérer les caractères non valides et le nombre maximal de caractères autorisés dans les noms de fichier. Pour configurer ces propriétés, ajoutez les paires clé-valeur suivantes dans le fichier de configuration :

| Clé de la propriété | Valeur de la propriété |
|------------|--------------|
| `nodename.uselower` | Booléen \(true/false\).<br> **Valeur par défaut** : true |
| `nodename.separator` | N’importe quel caractère. <br> **Valeur par défaut** : \_ *\(trait de soulignement\)* |
| `nodename.maxlength` | Valeur entière.<br> **Valeur par défaut** : 50 |

>[!TAB  On-Premise ]

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot *com.adobe.fmdita.common.SanitizeNodeNameImpl* et cliquez dessus.

1. Dans la propriété **Jeu de caractères non autorisé pour la publication sur AEM Sites**, assurez-vous que la propriété est définie sur ```'<>`@$```. Vous pouvez ajouter d’autres caractères spéciaux à cette liste. Toutefois, elle doit comporter ces caractères spéciaux obligatoires.

   >[!NOTE]
   >
   > Vous pouvez également configurer d’autres propriétés telles que **Utiliser les minuscules** dans les noms de fichier, **Séparateur** pour gérer les caractères non valides et **Nombre maximal de caractères** autorisé dans les noms de fichier.

1. Cliquez sur **Enregistrer**.

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.config.ConfigManager** et cliquez dessus.

1. Dans la propriété **Regex pour les caractères valides**, assurez-vous que la propriété est définie sur `[-a-zA-Z0-9_]`. Vous pouvez ajouter d’autres caractères à cette liste. Toutefois, elle doit comporter ces caractères de base et la liste doit commencer par un trait d’union \(`-`\).

   >[!NOTE]
   >
   > Cette propriété définit la liste des caractères valides utilisés pour créer un fichier.

1. Cliquez sur **Enregistrer**.

>[!ENDTABS]

## Configuration de l’aplatissement de la structure du nœud de site AEM

Lorsque vous générez une sortie de site AEM, un nœud pour chaque élément des rubriques est créé en interne. Pour un plan DITA comportant des milliers de rubriques, cette structure de nœud peut devenir trop profonde. Ce type de structure de nœud profondément imbriquée peut présenter des problèmes de performances pour les sites de plus grande taille. L’instantané suivant affiche la structure de nœud profondément imbriquée pour une sortie de site AEM :

![](assets/deep-nested-aem-site-node-structure.png)

Dans l’instantané ci-dessus, notez qu’un nœud est créé pour chaque élément `p` et ses sous-éléments suivants et qu’une structure similaire est créée pour tous les autres éléments utilisés dans la rubrique.

AEM Guides vous permet de configurer la manière dont la structure de nœud de sortie du site AEM est créée en interne. Vous pouvez aplatir la structure du nœud sur des éléments spécifiés, ce qui signifie que vous pouvez définir un élément qui sera considéré comme l’élément principal et tous les sous-éléments qu’il contient seront fusionnés avec l’élément principal. Par exemple, si vous décidez d’aplatir l’élément `p`, tout élément apparaissant dans l’élément `p` sera fusionné avec l’élément `p` principal. Aucune note distincte ne serait créée pour un sous-élément dans l’élément `p`. L’instantané suivant affiche la structure du nœud aplatie au niveau de `p` élément :

![](assets/flattened-aem-site-node-structure.png)

Les onglets suivants fournissent des instructions pour aplatir la structure du nœud du site AEM en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB ]

1. Identifiez le ou les éléments auxquels vous souhaitez aplatir la structure de nœud :

1. Recouvrez le nœud `libs` dans le nœud `apps` et ouvrez le fichier elementmapping.xml .

1. Ajoutez la propriété `<flatten>true</flatten>` dans la définition de l’élément au niveau duquel vous souhaitez aplatir la structure de nœud. Par exemple, si vous souhaitez aplatir la structure du nœud au niveau de l’élément `p`, ajoutez l’attribut flatten dans la définition de `p`’élément comme illustré ci-dessous :

   ```XML
   <ditaelement>
         <name>p</name>
         <class>- topic/p</class>
         <componentpath>fmdita/components/dita/wrapper</componentpath>
         <type>COMPOSITE</type>
         <target>para</target>
         <flatten>true</flatten>
         <wrapelement>div</wrapelement>
      </ditaelement>
   ```

   >[!NOTE]
   >
   > Par défaut, la propriété de nœud flatten a été configurée au niveau de l’élément `p`.

1. Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md#) pour créer le fichier de configuration.
1. Dans le fichier de configuration, fournissez les détails \(property\) suivants :

   | PID | Clé de la propriété | Valeur de la propriété |
   |---|------------|--------------|
   | `com.adobe.dxml.flattening.FlatteningConfigurationService` | `flattening.enabled` | Booléen \(true/false\).<br> **Valeur par défaut** : `false` |


Désormais, lorsque vous générez la sortie du site AEM, les nœuds de l’élément `p` sont aplatis et stockés dans l’élément `p` lui-même. Vous trouverez les nouvelles propriétés d’aplatissement de l’élément `p` dans CRXDE.

![](assets/flatten-aem-site-note-props-crxde.png)

>[!TAB  On-Premise ]

1. Indiquez l’élément sur lequel vous souhaitez aplatir la structure du nœud.

   1. Recouvrez le nœud `libs` dans le nœud `apps` et ouvrez le fichier elementmapping.xml .

   1. Ajoutez la propriété `<flatten>true</flatten>` dans la définition de l’élément au niveau duquel vous souhaitez aplatir la structure de nœud. Par exemple, si vous souhaitez aplatir la structure du nœud au niveau de l’élément `p`, ajoutez l’attribut flatten dans la définition de `p`’élément comme illustré ci-dessous :

      ```XML
      <ditaelement>
          <name>p</name>
          <class>- topic/p</class>
          <componentpath>fmdita/components/dita/wrapper</componentpath>
          <type>COMPOSITE</type>
          <target>para</target>
          <flatten>true</flatten>
          <wrapelement>div</wrapelement>
      </ditaelement>
      ```

      >[!NOTE]
      >
      > Par défaut, la propriété de nœud flatten a été configurée au niveau de l’élément `p`.

1. Activez la configuration de l’aplatissement des nœuds de site dans configMgr.

   1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

      L’URL par défaut pour accéder à la page de configuration est :

      ```http
      http://<server name>:<port>/system/console/configMgr
      ```

   1. Recherchez et cliquez sur le lot *com.adobe.dxml.flattening.FlateningConfigurationService* et cliquez dessus.

   1. Sélectionnez l’option **Propriété flatting.enabled**.

   1. Cliquez sur **Enregistrer**.


>[!IMPORTANT]
>
> Si vous avez apporté des modifications au fichier elementmapping.xml, assurez-vous d’ouvrir configMgr et d’enregistrer le lot pour que les modifications prennent effet.

Désormais, lorsque vous générez la sortie du site AEM, les nœuds de l’élément `p` sont aplatis et stockés dans l’élément `p` lui-même. Vous trouverez les nouvelles propriétés d’aplatissement de l’élément `p` dans CRXDE.

![](assets/flatten-aem-site-note-props-crxde.png){width="650" align="left"}

>[!ENDTABS]

**Recherche d’une chaîne dans le contenu de la sortie du site AEM (uniquement pour Cloud Service)**

Par défaut, vous pouvez rechercher une chaîne dans les titres uniquement dans la sortie du site AEM. Vous pouvez configurer le système pour rechercher une chaîne à la fois dans les titres et dans le contenu ou le corps de la sortie du site AEM.

>[!NOTE]
>
> Parfois, votre recherche peut fonctionner pour certains éléments du contenu, mais vous pouvez la configurer pour qu’elle fonctionne pour l’ensemble du contenu.

![](assets/flatten-aem-site-note-props-crxde-search.png)

Pour activer la recherche, vous devez configurer l’aplatissement de la structure de nœud du site AEM.

ATTENTION :

Vous pouvez rechercher jusqu’à 1 Mo de contenu aplati. Par exemple, dans la capture d’écran précédente, vous pouvez rechercher si le contenu situé sous la balise &lt;p\> est &lt;= 1 Mo.

>[!NOTE]
>
> La recherche fonctionne sur les éléments uniquement si l’attribut `<flatten>` est défini sur true. Par défaut, l’attribut `<flatten>` d’AEM Guides est défini sur true pour les éléments de texte couramment utilisés, tels que &lt;p\> &lt;ul\> &lt;lI\>. Cependant, si vous avez créé des éléments personnalisés, vous devez définir l’attribut `<flatten>` sur true dans le fichier elementmapping.xml.

**Empêcher l’aplatissement de la structure du nœud du site AEM**

Tout comme pour la spécification du nœud à aplatir dans la sortie du site AEM, vous pouvez également spécifier un élément que vous souhaitez exclure de cette configuration. Par exemple, si vous souhaitez aplatir les nœuds au niveau de `body` élément, mais que vous ne souhaitez pas aplatir les éléments `table` dans `body`, vous pouvez ajouter la propriété exclude dans la définition de l’élément `table`.

Pour exclure l’élément `table` de l’aplatissement, ajoutez la propriété suivante à la définition de l’élément `table` :

`<preventancestorflattening>true|false</preventancestorflattening>`

## Configurer le contrôle de version des pages supprimées dans la sortie du site AEM

Lorsque vous générez une sortie de site AEM avec les options **Supprimer et** Créer ****sélectionnées pour le paramètre Pages de sortie existantes , une version est créée pour la ou les pages en cours de suppression. Vous pouvez configurer le système pour arrêter la création d’une version avant la suppression.

Les onglets suivants fournissent des instructions pour arrêter la création d’une version pour la ou les pages supprimées en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB ]

1. Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md#) pour créer le fichier de configuration.
1. Dans le fichier de configuration, fournissez les détails \(property\) suivants pour configurer l’option **Ne pas créer de version pour les pages supprimées** :

   | PID | Clé de la propriété | Valeur de la propriété |
   |---|------------|--------------|
   | `com.adobe.fmdita.confi g.ConfigManager` | `no.version.creation.on.deletion` | Booléen \(true/false\).<br> **Valeur par défaut** : `true` |

   >[!NOTE]
   >
   > Lorsque cette option est sélectionnée, les utilisateurs peuvent supprimer directement une ou plusieurs pages sans créer de version pour eux. Si l’option n’est pas sélectionnée, une version est créée avant la suppression de la ou des pages .

>[!TAB  On-Premise ]

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot *com.adobe.fmdita.config.ConfigManager* et cliquez dessus.

1. Sélectionnez l **option Ne pas créer de version pour les pages supprimées**.

   >[!NOTE]
   >
   > Lorsque cette option est sélectionnée, les utilisateurs peuvent supprimer directement une ou plusieurs pages sans créer de version pour eux. Si l’option n’est pas sélectionnée, une version est créée avant la suppression de la ou des pages .

1. Cliquez sur **Enregistrer**.

>[!ENDTABS]

## Configuration d’une réécriture personnalisée avec Experience Manager Guides (uniquement pour Cloud Service) {#custom-rewriter}

Experience Manager Guides dispose d’un module sling [**rewriter**](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html) personnalisé destiné à gérer les liens générés en cas de mappages croisés (liens entre les rubriques de deux mappages différents). Cette configuration de réécriture est installée au chemin suivant : <br> `/apps/fmdita/config/rewriter/fmdita-crossmap-link-patcher`.

Si votre base de code contient un autre module de réécriture Sling personnalisé, utilisez une valeur de `'order'` supérieure à 50, car le module de réécriture Sling de Experience Manager Guides utilise `'order'` 50.  Pour remplacer ce paramètre, vous avez besoin d’une valeur > 50 . Pour plus d’informations, consultez la section [Pipelines de réécriture de sortie](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).



