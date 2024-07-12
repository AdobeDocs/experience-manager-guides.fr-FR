---
title: Configuration des paramètres de génération de sortie
description: Découvrez comment configurer les paramètres de génération de sortie
exl-id: b5cf4f6c-dc56-428e-a514-6c9f879ac03d
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '5470'
ht-degree: 1%

---

# Configuration des paramètres de génération de sortie {#id181AI0B0E30}

AEM Guides propose de nombreuses options de configuration pour personnaliser le processus de génération de sortie. Cette rubrique couvre toutes les configurations et personnalisations qui vous aideront à configurer votre processus de génération de sortie.

## Configuration de l’onglet Ligne de base dans le tableau de bord de la carte DITA {#id223MD0D0YRM}

Pour masquer l’onglet Ligne de base dans le tableau de bord de la carte DITA, procédez comme suit :

1. Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration.
1. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer l’onglet de ligne de base sur le tableau de bord de carte.

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `hide.tabs.baseline` | Booléen\(`true/false`\).**Valeur par défaut** : `true` |

>[!NOTE]
>
> Cette configuration est activée par défaut et l’onglet Ligne de base n’est pas disponible dans le tableau de bord de la carte.

## Configuration de la publication mixte dans un site AEM existant {#id1691I0V0MGR}

Si vous disposez d’un site AEM qui contient du contenu DITA, vous pouvez configurer la sortie AEM site pour publier du contenu DITA vers un emplacement prédéfini de votre site. Par exemple, dans la capture d’écran suivante d’une page AEM Site, le noeud `ditacontent` est réservé au stockage du contenu DITA :

![](assets/publish-in-aem-site.png)

Les autres noeuds de la page sont créés directement à partir de l’éditeur de site AEM. La configuration du paramètre de publication pour publier du contenu DITA vers un emplacement prédéfini garantit qu’aucun de vos contenus non DITA existants n’est modifié par le processus de publication AEM Guides.

Vous devez effectuer les configurations suivantes sur votre site existant pour permettre la publication de contenu DITA sur un noeud prédéfini :

- Configuration des propriétés de modèle de votre site

- Ajout de noeuds sur votre site pour publier du contenu DITA


Effectuez les étapes suivantes pour configurer les propriétés de modèle de votre site existant :

1. Utilisez le gestionnaire de modules pour télécharger le fichier /libs/fmdita/config/templates/default .

   >[!NOTE]
   >
   > Ne rendez aucune personnalisation dans les fichiers de configuration par défaut disponible dans le noeud `libs`. Vous devez créer une superposition du noeud `libs` dans le noeud `apps` et mettre à jour les fichiers requis dans le noeud `apps` uniquement.

1. Ajoutez les propriétés suivantes :

   | Nom de la propriété | Type | Valeur |
   |-------------|----|-----|
   | `topicContentNode` | Chaîne | Indiquez le nom du noeud dans lequel vous souhaitez publier le contenu DITA. Par exemple, le noeud par défaut où AEM Guides publie le contenu DITA est : <br> `jcr:content/contentnode` |
   | `topicHeadNode` | Chaîne | Indiquez le nom du noeud dans lequel vous souhaitez stocker les informations de métadonnées de votre contenu DITA. Par exemple, le noeud par défaut où AEM Guides stocke les informations de métadonnées est : <br> `jcr:content/headnode` |


La prochaine fois que vous publierez du contenu DITA à l’aide des configurations de modèle de votre site, le contenu sera publié dans les noeuds spécifiés dans les propriétés `topicContentNode` et `topicHeadNode`.

## Personnalisation de la sortie AEM site {#id166TG0B30WR}

AEM Guides prend en charge la création de sorties dans les formats suivants :

- AEM site
- PDF
- HTML5
- EPUB
- Sortie personnalisée via DITA-OT

Pour la sortie Site AEM, vous pouvez affecter différents modèles de conception avec différentes tâches de sortie. Ces modèles de conception peuvent rendre le contenu DITA dans différentes mises en page. Par exemple, vous pouvez spécifier différents modèles de conception pour les audiences internes et externes.

Vous pouvez également utiliser les modules externes Open Toolkit DITA personnalisés \(DITA-OT\) avec AEM Guides. Vous pouvez charger ces modules externes DITA-OT personnalisés pour générer une sortie PDF d’une manière spécifique.

>[!TIP]
>
> Consultez la section *Publication AEM site* du guide Bonnes pratiques pour connaître les bonnes pratiques en matière de création d’AEM sortie de site.


### Personnaliser le modèle de conception pour générer la sortie {#customize_xml-add-on}

AEM Guides utilise un ensemble de modèles de conception prédéfinis pour générer AEM sortie Site. Vous pouvez personnaliser les modèles de conception AEM Guides pour générer la sortie conforme à la valorisation de marque de votre entreprise. Un modèle de conception est un ensemble de différents styles \(CSS\), scripts \(côté serveur et côté client\), ressources \(images, logos et autres ressources\) et noeuds JCR qui lient toutes ces ressources. Un modèle de conception peut être aussi simple qu’un seul script côté serveur avec quelques noeuds JCR ou une combinaison complexe de styles, de ressources et de noeuds JCR. Les modèles de conception sont utilisés par le sous-système de publication AEM Guides lors de la génération de la sortie AEM Site et ils contrôlent la structure, l’aspect de la sortie générée.

Il n’y a aucune restriction quant à l’emplacement des ressources du modèle de conception sur le serveur, mais elles sont généralement logiquement organisées selon leur fonction. Par exemple, tous les fichiers JavaScript et CSS du modèle par défaut sont stockés dans le dossier `/etc/designs/fmdita/clientlibs/siteoutput/default`. Où que ces fichiers soient situés, ils sont liés ensemble par une collection de noeuds JCR. Ensemble, ces noeuds JCR et les fichiers constituent l’ensemble du modèle de conception.

Le modèle de conception par défaut fourni avec AEM Guides vous permet de personnaliser les composants de page d’entrée, de rubrique et de recherche. Vous pouvez faire une copie de la conception par défaut et des modèles de référence correspondants et spécifier différents composants pour générer la sortie souhaitée.

Effectuez les étapes suivantes pour spécifier votre propre modèle de conception à utiliser pour AEM génération de sortie de site :

1. Utilisez le gestionnaire de modules pour télécharger le modèle de conception par défaut à partir de l’emplacement suivant :

   /libs/fmdita/config/templates

1. Créez une copie des fichiers téléchargés à l’emplacement suivant dans votre référentiel Git Cloud Manager :

   /apps/fmdita/config/templates

1. Vous devez également télécharger et copier les modèles référencés à partir du noeud de modèle par défaut. Les modèles référencés sont placés sous :

   /libs/fmdita/templates/default/cqtemplates

   Les propriétés du modèle de conception AEM Guides sont décrites dans le tableau suivant.

   | Propriété | Description |
   |--------|-----------|
   | `landingPageTemplate`, `searchPageTemplate`, `topicPageTemplate`, `shadowPageTemplate` | Spécifiez le noeud `cq:Template` pour ces pages correspondantes \(entrée, recherche et rubrique\). Par défaut, le noeud `cq:Template` de ces pages se trouve dans le noeud `/libs/fmdita/templates/default/cqtemplates` . Ce noeud définit la structure et les propriétés des pages d’entrée, de recherche et de rubrique.<br> `shadowPageTemplate` est utilisé pour optimiser le contenu tronqué. Vous devez définir la valeur de cette propriété sur : `fmdita/templates/default/cqtemplates/shadowpage` <br> **Remarque :** Vous devez spécifier une valeur pour `topicPageTemplate`. `landingPageTemplate` et `searchPageTemplate` sont des propriétés facultatives. Si vous ne souhaitez pas que la recherche et les landing pages soient générées, ne spécifiez pas ces propriétés. |
   | `title` | Nom descriptif de votre modèle de conception. |
   | `topicContentNode` | Emplacement du noeud qui contiendra le contenu DITA dans une page de rubrique. Le chemin d’accès est relatif à la page de rubrique. |
   | `topicHeadNode` | L’emplacement du noeud qui contiendra les valeurs d’en-tête \(ou metadata\) dérivées du contenu DITA. Le chemin d’accès est relatif à la page de rubrique. |
   | `tocNode` | Emplacement du noeud qui contiendra la table des matières. Le chemin d’accès est relatif à la page d’entrée ou au chemin de destination. |
   | `basePathProp` | Nom de la propriété pour stocker le chemin d’accès de la racine du site publié. |
   | `indexPathProp` | Nom de la propriété pour le stockage du chemin d’accès à la page d’entrée/d’index du site publié. |
   | `pdfPathProp` | Nom de propriété pour le stockage du chemin du PDF de rubrique, si la génération du PDF de rubrique est activée. |
   | `pdfTypeProp` | Nom de la propriété pour le stockage du type de génération de PDF. Actuellement, cette propriété contient toujours &quot;Topic&quot;. |
   | `searchPathProp` | Nom de la propriété pour stocker le chemin d’accès à la page de recherche, si le modèle inclut une page de recherche. |
   | `siteTitleProp` | Nom de la propriété pour stocker le titre du site en cours de publication. Ce titre est généralement identique au titre de la carte en cours de publication. |
   | `sourcePathProp` | Nom de la propriété pour le stockage du chemin d’accès de la rubrique DITA source pour la page active. |
   | `tocPathProp` | Nom de la propriété pour stocker le chemin d’accès de la racine de la table des matières du site publié. |


>[!NOTE]
>
> Après avoir créé un noeud de modèle de conception personnalisé, vous devez mettre à jour l’option Conception dans les paramètres prédéfinis de sortie AEM Site pour utiliser le noeud de modèle de conception personnalisé.

Pour plus d’informations, voir [Création de votre premier site web Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=fr) et [Principes de base](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/develop-wknd-tutorial.html?lang=en) du développement de votre propre site web sur AEM.

### Utiliser le titre du document pour générer AEM sortie du site

Lors de la génération de la sortie AEM site, la manière dont les URL sont générées joue un rôle important dans la découverte de votre contenu. Si vous utilisez des noms de fichier UUID, la génération d’URL basées sur l’UUID de vos fichiers ne serait pas compatible avec la recherche. En tant qu’administrateur ou éditeur, vous avez le contrôle sur la manière dont vous souhaitez générer les URL pour votre sortie de site AEM. AEM Guides vous donne une configuration par laquelle vous pouvez choisir de générer les URL de sortie d’AEM site à l’aide du titre du fichier plutôt que des noms de fichier basés sur l’UUID. Par défaut, pour les systèmes de fichiers UUID, cette option est activée. Cela impliquait que lorsque vous générez AEM sortie Site pour les systèmes de fichiers UUID, les titres du fichier sont utilisés pour générer les URL et non les UUID des fichiers.

>[!NOTE]
>
> Vous pouvez configurer des règles supplémentaires pour n’autoriser qu’un jeu de caractères dans les URL d’une sortie de site AEM. Pour plus d’informations, voir [Configuration des règles d’assainissement du nom de fichier pour la création de rubriques et la publication AEM sortie du site](#id2164D0KD0XA).

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer la génération des URL dans AEM sortie Site :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `aemsite.pagetitle` | Booléen \(true/false\). Si vous souhaitez générer une sortie à l’aide du titre de la page, définissez cette propriété sur true. Par défaut, il est défini pour utiliser le nom de fichier.<br> **Valeur par défaut** : false |

### Configurez l’URL de la sortie Site AEM pour utiliser le titre du document.

Vous pouvez utiliser les titres des documents dans l’URL de la sortie AEM Site. Si le nom de fichier n’existe pas ou contient tous les caractères spéciaux, vous pouvez configurer le système pour remplacer les caractères spéciaux par un séparateur dans l’URL de la sortie Site AEM. Vous pouvez également le configurer pour les remplacer par le nom de la première rubrique enfant.


Pour configurer les noms de page, procédez comme suit :

1. Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration.
1. Dans le fichier de configuration, fournissez les détails (propriété) suivants pour configurer les noms de page des rubriques.

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeName` | `nodename.systemDefinedPageName` | Booléen (`true/false`). **Valeur par défaut** : `false` |

Par exemple, si le *@navtitle* dans `<topichead>` comporte tous les caractères spéciaux et que vous définissez la propriété `aemsite.pagetitle` sur true, alors par défaut, il utilise un séparateur. Si vous définissez la propriété `nodename.systemDefinedPageName` sur true, le nom de la première rubrique enfant s’affiche.


### Configuration des règles d’assainissement des noms de fichier pour la création de rubriques et la publication AEM sortie du site {#id2164D0KD0XA}

En tant qu’administrateur, vous pouvez définir une liste de caractères spéciaux valides autorisés dans les noms de fichier, qui forment éventuellement l’URL d’une sortie Site AEM. Dans les versions antérieures, les utilisateurs étaient autorisés à définir des noms de fichier contenant des caractères spéciaux tels que `@`, `$`, `>`, etc. Ces caractères spéciaux entraînaient l’encodage d’URL lors de la génération de pages de site AEM.

À compter de la version 3.8, des configurations ont été ajoutées pour définir une liste de caractères spéciaux autorisés dans les noms de fichier. Par défaut, la configuration de nom de fichier valide contient &quot;`a-z A-Z 0-9 - _`&quot;. Cela signifie que lors de la création d’un fichier, vous pouvez avoir n’importe quel caractère spécial dans le titre du fichier, mais qu’en interne, il sera remplacé par un trait d’union \(`-`\) dans le nom du fichier. Par exemple, le titre du fichier peut être Introduction 1 ou Introduction@1, le nom de fichier correspondant généré pour ces deux cas serait Introduction-1.

Lorsque vous définissez une liste de caractères valides, n’oubliez pas que ces caractères &quot;`*/:[\]|#%{}?&<>"/+`&quot; et `a space` seront toujours remplacés par un trait d’union \(`-`\).

>[!NOTE]
>
> Si vous ne configurez pas la liste des caractères spéciaux valides, le processus de création de fichier peut vous donner des résultats inattendus.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer les caractères spéciaux valides dans les noms de fichier et AEM sortie Site :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Assurez-vous que la propriété est définie sur ``'<>`@$``. Vous pouvez ajouter des caractères spéciaux à cette liste. |

Vous pouvez également configurer d’autres propriétés, telles que l’utilisation de minuscules dans les noms de fichier, le séparateur pour gérer les caractères non valides et le nombre maximal de caractères autorisés dans les noms de fichier. Pour configurer ces propriétés, ajoutez les paires clé-valeur suivantes dans le fichier de configuration :

| Clé de propriété | Valeur de la propriété |
|------------|--------------|
| `nodename.uselower` | Booléen \(true/false\).<br> **Valeur par défaut** : true |
| `nodename.separator` | N&#39;importe quel caractère. <br> **Valeur par défaut** : \_ *\(trait de soulignement\)* |
| `nodename.maxlength` | Valeur entière.<br> **Valeur par défaut** : 50 |

### Configuration de l’aplatissement de AEM structure de noeuds Site

Lorsque vous générez AEM sortie Site, un noeud pour chaque élément des rubriques est créé en interne. Pour un mappage DITA contenant des milliers de rubriques, cette structure de noeud peut devenir trop profonde. Ce type de structure de noeuds profondément imbriqués peut présenter des problèmes de performances pour les sites plus volumineux. L’instantané suivant affiche la structure de noeuds profondément imbriqués pour une sortie AEM Site :

![](assets/deep-nested-aem-site-node-structure.png)

Dans l’instantané ci-dessus, notez qu’un noeud est créé pour chaque élément `p` et ses sous-éléments suivants, et qu’une structure similaire est créée pour chaque autre élément utilisé dans la rubrique.

AEM Guides vous permet de configurer la création en interne de la structure de noeud de AEM sortie de site. Vous pouvez aplatir la structure du noeud au niveau des éléments spécifiés, ce qui signifie que vous pouvez définir un élément qui sera considéré comme l’élément principal et tous les sous-éléments qu’il contient seront fusionnés avec l’élément principal. Par exemple, si vous décidez d’aplatir l’élément `p`, tout élément apparaissant dans l’élément `p` sera fusionné avec l’élément principal `p`. Une note distincte ne serait créée pour aucun sous-élément dans l’élément `p`. L’instantané suivant affiche la structure de noeud aplatie à l’élément `p` :

![](assets/flattened-aem-site-node-structure.png)

Pour aplatir AEM structure de noeuds de site, procédez comme suit :

1. Identifiez l’élément\(s\) sur lequel vous souhaitez aplatir la structure de noeud :

1. Superposition du noeud `libs` dans le noeud `apps` et ouvrez le fichier elementmapping.xml .

1. Ajoutez la propriété `<flatten>true</flatten>` dans la définition de l’élément sur lequel vous souhaitez aplatir la structure de noeud. Par exemple, si vous souhaitez aplatir la structure de noeud à l’élément `p` , ajoutez l’attribut flatten dans la définition de l’élément `p` comme illustré ci-dessous :

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
   > Par défaut, la propriété de noeud d’aplatissement a été configurée sur l’élément `p` .

1. Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration.
1. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants :

   | PID | Clé de propriété | Valeur de la propriété |
   |---|------------|--------------|
   | `com.adobe.dxml.flattening.FlatteningConfigurationService` | `flattening.enabled` | Booléen \(true/false\).<br> **Valeur par défaut** : `false` |


Désormais, lorsque vous générez la sortie Site AEM, les noeuds de l’élément `p` sont aplatis et stockés dans l’élément `p` lui-même. Vous trouverez les nouvelles propriétés d’aplatissement de l’élément `p` dans CRXDE.

![](assets/flatten-aem-site-note-props-crxde.png)

**Recherchez une chaîne dans le contenu de la sortie AEM site**

Par défaut, vous pouvez rechercher une chaîne dans les titres uniquement dans la sortie AEM Site. Vous pouvez configurer le système pour rechercher une chaîne à la fois dans les titres et dans le contenu ou le corps de la sortie AEM Site.

>[!NOTE]
>
> Il arrive que votre recherche fonctionne pour certains éléments du contenu, mais vous pouvez la configurer pour qu’elle fonctionne pour l’ensemble du contenu.

![](assets/flatten-aem-site-note-props-crxde-search.png)

Pour activer la recherche, vous devez configurer l’aplatissement de AEM structure de noeuds Site.

ATTENTION :

Vous pouvez rechercher jusqu’à 1 Mo de contenu aplati. Par exemple, dans la capture d’écran précédente, vous pouvez rechercher si le contenu sous la balise &lt;p\> est &lt;= 1Mo.

>[!NOTE]
>
> La recherche ne fonctionne sur les éléments que si l&#39;attribut `<flatten>`est défini sur true. Par défaut, l’attribut `<flatten>` d’AEM Guides est défini sur true pour les éléments de texte couramment utilisés tels que &lt;p\> &lt;ul\> &lt;lI\>. Cependant, si vous avez créé certains éléments personnalisés, vous devez définir l’attribut `<flatten>` sur true dans le fichier elementmapping.xml .

**Empêcher l’aplatissement de AEM structure de noeuds de site**

Tout comme pour spécifier le noeud à aplatir dans AEM sortie Site, vous pouvez également spécifier un élément que vous souhaitez exclure de cette configuration. Par exemple, si vous souhaitez aplatir des noeuds à l’élément `body`, mais que vous ne souhaitez pas qu’un élément `table` dans `body` s’aplatisse, vous pouvez ajouter la propriété exclude dans la définition de l’élément `table`.

Pour exclure l’élément `table` de l’aplatissement, ajoutez la propriété suivante à la définition de l’élément `table` :

`<preventancestorflattening>true|false</preventancestorflattening>`

### Configuration du contrôle de version pour les pages supprimées dans AEM sortie Site

Lorsque vous générez AEM sortie Site avec l’option **Supprimer et** Créer ****sélectionnée pour le paramètre Pages de sortie existantes, une version est créée pour la ou les pages\) en cours de suppression. Vous pouvez configurer le système pour arrêter la création d’une version avant la suppression.

Effectuez les étapes suivantes pour arrêter la création d’une version de la page\(s\) supprimée :

1. Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration.
1. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer l’option **Ne pas créer de version pour les pages supprimées** :

   | PID | Clé de propriété | Valeur de la propriété |
   |---|------------|--------------|
   | `com.adobe.fmdita.confi g.ConfigManager` | `no.version.creation.on.deletion` | Booléen \(true/false\).<br> **Valeur par défaut** : `true` |

   >[!NOTE]
   >
   > Lorsque cette option est sélectionnée, les utilisateurs peuvent supprimer directement n’importe quelle page sans créer de version pour eux. Si cette option n’est pas sélectionnée, une version est créée avant la suppression de la ou des pages\.

### Configuration d’un module de réécriture personnalisé avec Experience Manager Guides {#custom-rewriter}

Experience Manager Guides dispose d’un module de [**rewriter**](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html) personnalisé pour gérer les liens générés en cas de mappage croisé (liens entre les rubriques de deux cartes différentes). Cette configuration de réécriture est installée à l’emplacement suivant : <br> `/apps/fmdita/config/rewriter/fmdita-crossmap-link-patcher`.

Si votre code base comporte un autre module de réécriture sling personnalisé, utilisez une valeur `'order'` supérieure à 50, car Experience Manager Guides sling rewriter utilise `'order'` 50.  Pour le remplacer, vous devez disposer d’une valeur supérieure à 50 . Pour plus d’informations, voir [ Pipelines de réécriture de sortie](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).


## Utilisation de métadonnées pour publier une sortie via DITA-OT {#id191LF0U0TY4}

AEM Guides permet de transmettre des métadonnées personnalisées lors de la publication d’une sortie à l’aide de DITA-OT. En tant qu’administrateur et éditeur, vous devez effectuer les tâches suivantes pour configurer et utiliser des métadonnées personnalisées dans la sortie publiée :

- En tant qu’administrateur, ajoutez les métadonnées requises dans le système afin qu’elles soient disponibles sur la page Propriétés du mappage DITA.

- En tant qu’administrateur, ajoutez les métadonnées personnalisées dans la liste des métadonnées afin qu’elles s’affichent dans la console de mappage DITA.

- En tant qu’éditeur, configurez et ajoutez les métadonnées personnalisées avec le mappage DITA et générez la sortie requise.


Pour ajouter les métadonnées requises dans le système, procédez comme suit :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et sélectionnez **Outils**.

1. Sélectionnez **Assets** dans la liste des outils.

1. Cliquez sur la mosaïque **Schémas de métadonnées** .

   La page Forms de schéma de métadonnées s’affiche.

1. Sélectionnez le formulaire **default** dans la liste.

   >[!NOTE]
   >
   > Les propriétés affichées sur la page Propriétés d’un mappage DITA proviennent de ce formulaire.

1. Cliquez sur **Modifier**.

1. Ajoutez les métadonnées personnalisées que vous souhaitez utiliser dans les sorties publiées. Par exemple, nous allons ajouter des métadonnées d’audience en procédant comme suit :

   1. Dans la liste des composants **Créer le formulaire** , faites glisser le composant **Texte ligne unique** sur le formulaire.

   2. Sélectionnez le nouveau champ pour ouvrir les **Paramètres** du champ.

   3. Dans le **libellé du champ**, saisissez le nom des métadonnées : Audience.

   4. Dans le paramètre **Associer à la propriété** , spécifiez ./jcr:content/metadata/&lt;nom des métadonnées\>. Dans notre exemple, nous allons le définir sur ./jcr:content/metadata/audience

   À l’aide de ces étapes, ajoutez tous les paramètres de métadonnées requis.

1. Cliquez sur **Enregistrer**.


Le nouveau paramètre s’affiche désormais sur la page Propriétés pour tous les mappages DITA.

![](assets/properties-page-custom-metadata.PNG)

Ensuite, vous devez rendre les métadonnées personnalisées disponibles dans la console de mappage DITA. Effectuez les étapes suivantes pour rendre les métadonnées personnalisées disponibles sur le tableau de bord de mappage DITA :

1. Utilisez le gestionnaire de packages pour accéder au fichier metadataList disponible à l’emplacement suivant dans votre référentiel Git Cloud Manager :

   /libs/fmdita/config/metadataList

   >[!NOTE]
   >
   > Le fichier metadataList contient une liste de propriétés qui s’affichent dans la liste déroulante **Propriétés** d’une carte DITA dans le tableau de bord de la carte. Par défaut, quatre propriétés sont répertoriées dans ce fichier : docstate, dc:language, dc:description et dc:title.

1. Ajoutez les métadonnées personnalisées que vous avez ajoutées à la page Forms du schéma de métadonnées . Dans notre exemple, ajoutez le paramètre audience à la fin de la liste par défaut.


Désormais, les métadonnées personnalisées s’affichent dans la liste déroulante **Propriétés** de la console de mappage DITA.

Enfin, en tant qu’éditeur, vous devez inclure les métadonnées personnalisées dans la sortie publiée. Pour traiter les métadonnées personnalisées lors de la génération de la sortie, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez au mappage DITA que vous souhaitez publier.

1. Sélectionnez le fichier de mappage DITA et ouvrez sa page de propriétés.

1. Sur la page Propriétés , spécifiez la valeur des métadonnées personnalisées. Dans notre exemple, nous avons spécifié une valeur Externe pour le paramètre d’audience .

   ![](assets/properties-page-custom-metadata-value.png)

1. Cliquez sur **Enregistrer et fermer**.

1. Cliquez sur le fichier de mappage DITA pour ouvrir la console de mappage DITA.

1. Dans l’onglet **Paramètres prédéfinis de sortie**, sélectionnez le paramètre prédéfini de sortie à utiliser pour générer la sortie.

1. Cliquez sur **Modifier**.

1. Dans la liste déroulante **Propriétés** , sélectionnez les propriétés à transmettre au processus de publication.

   ![](assets/props-in-publish-output.PNG)


Les propriétés/métadonnées sélectionnées sont transmises au processus de publication et mises à disposition dans la sortie finale.

### Validation des métadonnées transmises à DITA-OT pour traitement

Pour valider les valeurs de métadonnées transmises à DITA-OT, vous pouvez utiliser un environnement local à l’aide d’un jar prêt pour le cloud. Comme nous ne pouvons pas accéder au système de fichiers local sur le cloud, seul le fichier de métadonnées peut être validé au moyen d’un fichier JAR prêt pour le cloud.

- Nom du fichier : metadata.xml
- Emplacement du fichier : crx-quickstart/profiles/ditamaps/&lt;ditamap-1234\>

  Pour accéder à metadata.xml :

   - Connectez-vous à l’emplacement du serveur sur lequel l’instance AEM est en cours d’exécution.
   - Migrez vers crx-quickstart/profiles/ditamaps/&lt;nom-répertoire-nouvellement créé\>/metadata.xml.
- Exemple de format de fichier :

  **metadata.xml**

  ```XML
  <?xml version="1.0" encoding="UTF-8" standalone="no"?>
  <root>
     <Path id="/absolutePath/sampleMap.ditamap">
        <metadata>
           <meta isArray="false" key="dc:description">This is a file</meta>
           <meta isArray="false" key="dc:title">Myfile</meta>
           <meta isArray="true" key="multivalueText">One;Two;Three</meta>
        </metadata>
     </Path>
     <Path id="/absolutePath/sampleTopic.dita">
        <metadata>
           <meta isArray="false" key="dc:description">description for the accountability</meta>
           <meta isArray="false" key="dc:title">accountability title</meta>
           <meta isArray="true" key="multivalueText">value1</meta>
        </metadata>
     </Path>
  </root>
  ```


- isArray : attribut booléen qui définit si les métadonnées sont à plusieurs valeurs \(Array\) ou non. Les valeurs sont délimitées par un point-virgule.
- ID de chemin d’accès : chemin d’accès absolu au fichier stocké dans le répertoire temporaire.

>[!NOTE]
>
> Si des métadonnées spécifiques ne sont pas présentes pour le fichier, la balise &lt;meta\> avec la clé n’apparaît pas comme propriété pour ce fichier dans le fichier metadata.xml.

## Personnalisation du mappage des éléments DITA avec les composants AEM {#id1679J600HEL}

Les éléments DITA dans AEM Guides sont mappés à leurs composants AEM correspondants. AEM Guides utilise ce mappage dans les workflows tels que la publication et la révision pour convertir l’élément DITA en composant AEM correspondant. Le mappage est défini dans le fichier `elementmapping.xml`, accessible à l’aide du gestionnaire de packages.

>[!NOTE]
>
> Ne rendez aucune personnalisation dans les fichiers de configuration par défaut disponible dans le noeud ``libs``. Vous devez créer une superposition du noeud ``libs`` dans le noeud ``apps`` et mettre à jour les fichiers requis dans le noeud ``apps`` uniquement.

Vous pouvez utiliser les mappages d’éléments DITA prédéfinis ou vous pouvez mapper des éléments DITA à vos composants d’AEM personnalisés. Pour utiliser vos composants d’AEM personnalisés, vous devez comprendre la structure du fichier `elementmapping.xml`.

### structure elementmapping.xml

Un aperçu général de la structure `elementmapping.xml` est expliqué ci-dessous :

1. Chaque élément DITA est d’abord recherché dans un mappage de composant correspondant en fonction du nom de l’élément. Par exemple :

   ```XML
   <ditaelement>     
      <name>**substeps**</name>  
      <class>- topic/ol task/substeps</class>  
      <componentpath>dita/components/ditaolist</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>
   </ditaelement>
   ```

   Dans l’exemple ci-dessus, tous les éléments DITA `substeps` sont rendus à l’aide du composant `dita/components/ditaolist`.

1. Si un élément DITA ne trouve pas de correspondance basée sur le nom, alors une correspondance basée sur le `class` est effectuée. Par exemple :

   ```XML
   <ditaelement>  
      <name>topic</name>  
      <class>**- topic/topic**</class>  
      <componentpath>fmdita/components/dita/topic</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>  
      <attributemap> 
         <attribute from="id" to="id" />  
      </attributemap>
   </ditaelement>
   ```

   Dans l’exemple ci-dessus, si aucun mappage n’est défini pour l’élément `task`, l’élément `task` est mappé sur le composant ci-dessus car `task` est hérité du composant `topic`.

1. Lorsqu’un élément possède un mappage de composant correspondant, le traitement supplémentaire de ses éléments enfants est déterminé par `type`. Par exemple :

   ```XML
   <ditaelement>  
      <name>title</name>  
      <class>- topic/title</class>  
      <componentpath>foundation/components/title</componentpath>  
      <type>**STANDALONE**</type>  
      <target>para</target>  
      <textprop>jcr:title</textprop>
   </ditaelement>
   ```

   `type` utilise les valeurs suivantes :

   - COMPOSITE : le mappage de l’élément au composant *se poursuit également pour les éléments enfants*.

   - STANDALONE : les éléments enfants de l’élément actuel ne sont *pas mappés plus*.

   Dans l’exemple ci-dessus, si l’élément `<title>` comporte des éléments enfants, ils ne seront mappés à aucun autre composant. Le composant de l’élément `<title>` est responsable du rendu de tous les éléments enfants à l’intérieur de l’élément `<title>`.

1. S’il existe plusieurs composants mappés à un seul élément DITA, la meilleure correspondance pour l’élément est sélectionnée. Pour sélectionner le meilleur composant de correspondance, la spécialisation du domaine et de la structure des éléments DITA est prise en compte.

   S’il existe des éléments DITA avec spécialisation de domaine et qu’un composant est mappé pour la spécialisation de domaine, ce composant reçoit une priorité élevée.

   De même, s’il existe des éléments DITA avec une spécialisation structurelle et qu’un composant est mappé pour la spécialisation structurelle, ce composant reçoit une priorité élevée.

1. Vous pouvez utiliser `<attributemap>` dans le mappage des éléments pour mapper les valeurs d’attribut aux propriétés de noeud correspondantes.
1. `textprop` peut être utilisé pour sérialiser le contenu texte d’un élément DITA vers une propriété de noeud. En outre, il peut être utilisé plusieurs fois dans une balise d’élément pour sérialiser le contenu du texte à plusieurs emplacements dans la hiérarchie publiée. Vous pouvez également personnaliser l’emplacement et le nom de la propriété cible. Par exemple :

   ```XML
   <ditaelement>
      <name>title</name>
      <componentpath>foundation/components/title</componentpath>
      <type>STANDALONE</type>
      <target>para</target>
       <textprop>**jcr:title**</textprop>
   </ditaelement>
   ```

   Le mappage d’élément ci-dessus indique que le contenu textuel de l’élément `<title>` sera enregistré comme valeur d’une propriété nommée `jcr:title` sur le noeud de sortie.

1. `xmlprop` peut être utilisé pour sérialiser le XML entier pour un élément donné vers une propriété de noeud. Le composant peut ensuite lire cette propriété de noeud et effectuer un rendu personnalisé. Par exemple :

   ```XML
   <ditaelement>
       <name>svg-container</name>
      <class>+ topic/foreign svg-d/svg-container</class>
       <componentpath>fmdita/components/dita/svg</componentpath>
       <type>STANDALONE</type>
       <target>para</target>
      <xmlprop>**data**</xmlprop>
   </ditaelement>
   ```

   Le mappage d’élément ci-dessus indique que l’ensemble du balisage XML pour l’élément `<svg-container>` sera enregistré comme valeur d’une propriété nommée `data` sur le noeud de sortie.

1. Il existe un mappage d’attributs spécial pour gérer la résolution du chemin dans le processus de génération de sortie. Par exemple :

   ```XML
   <attributemap>
      <attribute from="href" to="fileReference" ispath="true" rel="source" />
      <attribute from="height" to="height" />
       <attribute from="width" to="width" />
   </attributemap>
   ```

   Pour les `attributemap` ci-dessus, l’attribut `href` de votre élément DITA sera mappé à une propriété de noeud nommée `fileReference`. Maintenant que `ispath` est défini sur `true`, le processus de génération de sortie résout ce chemin et le définit dans la propriété de noeud `fileReference`.

   La manière dont cette résolution se produit est déterminée sur la base de la valeur de l’attribut `rel` dans le mappage des attributs.

   - Si `rel=source`, la valeur de `href` est résolue par rapport au fichier source DITA en cours de traitement. La valeur de `href` est résolue et placée dans la valeur de la propriété `fileReference`.

   - Si `rel=target`, la valeur de `href` est résolue par rapport à l’emplacement de publication racine. La valeur de `href` est résolue et placée dans la valeur de la propriété `fileReference`.

   Si vous ne souhaitez pas qu’un prétraitement ou une résolution se produise sur les attributs de chemin d’accès, vous n’avez pas besoin de spécifier l’attribut `ispath`. La valeur est copiée telle quelle et le composant peut effectuer la résolution requise.


### Schéma d’élément DITA

Voici un exemple du schéma d’élément DITA dans le fichier `elementmapping.xml` :

```XML
<ditaelement>        
    <name>element_name</name>    
    <class>element_class</class>    
    <componentpath>fmdita/components/dita/component_name</componentpath>    
    <type>COMPOSITE|STANDALONE</type>     
    <attributeprop>propname_a</attributeprop>      
    <textprop>propname_t</textprop>    
    <xmlprop>propname_x</xmlprop>     
    <xpath>xpath expression string</xpath>     
    <target>head|para</target>     
    <wrapelement>div</wrapelement>     
    <wrapclass>class_name</wrapclass>     
    <attributemap>         
        <attribute from="attrname"         to="propname"         ispath="true|false"         rel="source|target" />    
    </attributemap>    
    <skip>true|false</skip> 
</ditaelement>
```

Le tableau suivant décrit les éléments du schéma d’élément DITA :

| Elément | Description |
|-------|-----------|
| `<ditaelement>` | Noeud de niveau supérieur pour chaque élément de mappage. |
| `<class>` | L’attribut de classe de l’élément DITA cible pour lequel vous écrivez le composant.<br> Par exemple, l’attribut de classe pour la rubrique DITA est : <br> `- topic/topic` |
| `<componentpath>` | Chemin d’accès CRXDE du composant AEM mappé. |
| `<type>` | Valeurs possibles :<br> -   **COMPOSITE** : traitez également les éléments enfants <br> -   **STANDALONE** : ignore le traitement des éléments enfants |
| `<attributeprop>` | Utilisé pour mapper les attributs et valeurs DITA sérialisés sur les noeuds AEM en tant que propriété. Par exemple, si vous disposez de l’élément `<note type="Caution">` et que le composant mappé pour cet élément comporte `<attributeprop>attr_t</ attributeprop>`, l’attribut et la valeur du noeud sont sérialisés en propriété `attr_t` du noeud d’AEM correspondant \( `attr_t->type="caution"`\). |
| `<textprop>propname_t</textprop>` | Enregistrez la sortie `getTextContent()` sur la propriété définie par `propname_t.` <br> **Remarque :** Il s’agit d’une propriété optimisée. |
| `<xmlprop>propname_x </xmlprop>` | Enregistrez le XML sérialisé de ce noeud dans la propriété définie par `propname_x.<br> `**Remarque :** Il s’agit d’une propriété optimisée. |
| `<xpath>` | Si l’élément XPath est fourni dans le mappage d’élément, alors avec le nom de l’élément et la classe, la condition XPath doit également être satisfaite pour que le mappage de composant soit utilisé. |
| `<target>` | Placez l’élément DITA dans le référentiel crx à l’emplacement spécifié.<br> Valeurs possibles : <br> - **head** : Sous le noeud head <br> - **text** : Sous le noeud paragraph |
| `<wrapelement>` | L’élément HTML dans lequel placer le contenu. |
| `<wrapclass>` | La valeur de l’élément à la propriété `wrapclass.` |
| `<attributemap>` | Noeud conteneur contenant un ou plusieurs noeuds `<attribute>`. |
| `<attribute from="attrname" to="propname" ispath="true|false" rel="source|target" />` | Mappe les attributs DITA aux propriétés AEM : <br> -   **`from`** : nom de l’attribut DITA <br> -   **`to`** : AEM nom de propriété du composant <br> -   **`ispath`** : si l’attribut est une valeur de chemin \(par exemple : *image*\) <br> -   **`rel`** : si le chemin est la source ou la cible <br> **Remarque :** Si `attrname` commence par `%`, mappez `attrname minus '%'` sur la prop &#39; `propname`&#39;. |

**Remarques supplémentaires**

- Si vous prévoyez de remplacer le mappage d’élément par défaut, il est recommandé de ne pas apporter les modifications au fichier par défaut `elementmapping.xml`. Vous devez créer un fichier XML de mappage et le placer à un autre emplacement, de préférence dans le dossier d’applications personnalisées que vous créez.

- Dans le fichier `elementmapping.xml`, il existe de nombreuses entrées de mappage faisant référence au composant fmdita/components/dita/wrapper. Wrapper est un composant générique qui effectue le rendu de constructions DITA relativement simples à l’aide de propriétés sur leur noeud de site pour générer un HTML pertinent. Il utilise la propriété `wrapelement` pour générer des balises englobantes et délègue le rendu enfant aux composants correspondants. Cela s’avère utile lorsque vous souhaitez uniquement un composant de conteneur. Au lieu de créer un composant qui effectue le rendu d’une balise conteneur spécifique telle que `div` ou `p`, vous pouvez utiliser le composant Wrapper avec les propriétés `wrapelement` et `wrapclass` pour obtenir le même effet.

- Il n’est pas recommandé d’enregistrer de grandes quantités de texte dans les propriétés JCR de chaîne. Le calcul du type de propriété optimisé dans la génération de sortie garantit que le contenu texte volumineux n’est pas enregistré comme type de chaîne. Au lieu de cela, lorsque le contenu supérieur à un certain seuil doit être enregistré, le type de la propriété est remplacé par binaire. Par défaut, ce seuil est configuré à 512 octets, mais peut être modifié dans Configuration Manager \(*com.adobe.fmdita.config.ConfigManager*\) en modifiant le paramètre **Enregistrer comme seuil binaire**.

- Si vous envisagez de remplacer certains \(et pas tous\) des mappages d’éléments, vous n’avez pas à répliquer l’intégralité du fichier `elementmapping.xml`. Vous devez créer un nouveau fichier de mappage XML et définir uniquement les éléments que vous remplacez.

- Après avoir créé le fichier XML à l’emplacement personnalisé, mettez à jour le paramètre `Override Element Mapping` dans le lot `com.adobe.fmdita.config.ConfigManager`.


## Personnalisation de la console de mappage DITA {#id188HC08M0CZ}

AEM Guides vous offre la possibilité d’étendre les fonctionnalités de la console de mappage DITA. Si, par exemple, vous disposez d’un ensemble de rapports différent de celui disponible dans AEM Guides, vous pouvez ajouter ces rapports à la console de mappage. Pour personnaliser la console de mappage, vous devez créer une AEM bibliothèque cliente \(ou ClientLib\) qui contiendra le code pour exécuter les fonctionnalités dont vous avez besoin.

>[!NOTE]
>
> La modification directe aux composants de page n’est pas recommandée, car elle sera écrasée par les nouvelles versions du produit.

AEM Guides fournit la catégorie `apps.fmdita.dashboard-extn` pour personnaliser la console de mappage. Chaque fois que la console de mappage est chargée, la fonctionnalité créée sous la catégorie `apps.fmdita.dashboard-extn` est exécutée et chargée.

>[!NOTE]
>
> Pour plus d’informations sur la création AEM bibliothèque cliente, voir [Utilisation de bibliothèques côté client](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html?lang=en).

## Gérer le rendu d’image lors de la génération de la sortie {#id177BF0G0VY4}

AEM est fourni avec un ensemble de workflows et de gestionnaires de médias par défaut pour traiter les ressources. Dans AEM, il existe des workflows prédéfinis pour gérer le traitement des ressources pour les types MIME les plus courants. En règle générale, pour chaque image que vous téléchargez, AEM crée plusieurs rendus du même format binaire. Ces rendus peuvent être de taille différente, avec une résolution différente, avec un filigrane ajouté ou d’autres caractéristiques modifiées. Pour plus d’informations sur la manière dont AEM gère les ressources, voir [Traitement d’Assets à l’aide de gestionnaires et de workflows de médias](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html?lang=en) dans AEM documentation.

AEM Guides vous permet de configurer le rendu d’image à utiliser lors de la génération de la sortie pour vos documents. Par exemple, vous pouvez choisir parmi l’un des rendus d’image par défaut ou en créer un et l’utiliser pour publier vos documents. Le mappage de rendu d’image pour la publication de vos documents est stocké dans le fichier `/libs/fmdita/config/ **renditionmap.xml**`. Voici un extrait de fichier `renditionmap.xml` :

>[!NOTE]
>
> Il est recommandé de créer une copie du fichier `renditionmap.xml` dans le dossier `apps` pour toutes les personnalisations.

```XML
<renditionmap>
   <mapelement>
      <mimetype>image/png</mimetype>
      <rendition output="AEMSITE">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="PDF">original</rendition>
      <rendition output="HTML5">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="EPUB">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="CUSTOM">cq5dam.web.1280.1280.jpeg</rendition>
   </mapelement>
...
</renditionmap>
```

L’élément `mimetype` spécifie le type MIME du format de fichier. L’élément `rendition output` spécifie le type de format de sortie et le nom du rendu \(par exemple, `cq5dam.web.1280.1280.jpeg`\) qui doit être utilisé pour publier la sortie spécifiée. Vous pouvez spécifier les rendus d’image à utiliser pour tous les formats de sortie pris en charge : AEMSITE, PDF, HTML5, EPUB et PERSONNALISÉ.

Si le rendu spécifié n’est pas présent, le processus de publication AEM Guides commence par rechercher le rendu web de l’image donnée. Si même le rendu web est introuvable, le rendu d’origine de l’image est utilisé.

>[!NOTE]
>
> Ces rendus d’image contrôlent uniquement la génération de sortie. Le rendu web d’une image est utilisé lorsque vous ouvrez un document à des fins d’aperçu ou de révision.

## Configuration de la période de purge automatique pour l’historique de sortie {#id19AAI070V8Q}

Lorsque vous générez une sortie, la sortie est créée avec les logs de sortie. Pour les mappages DITA volumineux, ces journaux peuvent prendre beaucoup d’espace dans votre référentiel. Par défaut, les journaux sont stockés à l’emplacement suivant dans le référentiel :

`/var/dxml/metadata/outputHistory`

Sur une certaine période, la taille collective de tous les fichiers journaux peut atteindre 1 Go. AEM Guides vous permet de configurer une période pour conserver ces fichiers journaux dans le référentiel. Après la période spécifiée, les journaux ainsi que l’historique de génération de sortie sont supprimés du référentiel.

>[!NOTE]
>
> L&#39;historique de génération de sortie est l&#39;entrée de journal dans la liste Sorties générées de l&#39;onglet Sorties .

La configuration de la fonction de purge de l’historique a un impact sur la génération de sortie pour tous les mappages DITA dans le référentiel. Dans l’onglet Sorties d’un mappage DITA, l’historique est purgé après le nombre de jours spécifié et à l’heure spécifiée dans le paramètre .

>[!NOTE]
>
> La suppression des fichiers journaux et de l’historique de génération de sortie n’a aucun impact sur la sortie générée.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour définir un jour et une heure pour purger l’historique de sortie et les journaux :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `output.history.purgeperiod` | Indiquez le nombre de jours après lesquels l’historique de sortie avec les journaux de sortie est purgé. Si vous souhaitez désactiver cette fonction, définissez cette propriété sur 0. Chaque jour, au moment spécifié, le processus de purge est exécuté sur les sorties générées avant le nombre de jours spécifié dans cette propriété. <br> **Valeur par défaut** : 5 |
| `output.history.purgetime` | Spécifiez l’heure à laquelle le processus de purge est lancé. <br> **Valeur par défaut** : 0:00 \(ou 12:00 minuit\) |

## Modification de la limite de la liste des sorties récemment générées {#id1679JH0H0O2}

Vous pouvez modifier le nombre maximal de sorties générées qui s’affichent dans l’onglet Sorties pour un mappage DITA.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour modifier le nombre de sorties à afficher dans la liste :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `output.historylimit` | Valeur entière.<br> **Valeur par défaut** : 25 |

>[!TIP]
>
> Consultez la section *Historique de sortie* du guide Bonnes pratiques pour connaître les bonnes pratiques relatives à l’utilisation de l’historique de sortie.
