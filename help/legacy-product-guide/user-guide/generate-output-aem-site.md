---
title: AEM site
description: Créez et configurez AEM paramètre prédéfini de site dans AEM Guides. Utilisez la prise en charge AEM site pour générer une sortie basée sur un article, des rubriques de liaison de sortie, une référence de publication et rechercher une chaîne dans le contenu.
feature: Publishing
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '2621'
ht-degree: 0%

---

# AEM site {#id205BE3008SW}

Les options suivantes sont disponibles pour la sortie AEM site :

Vous pouvez créer AEM paramètre prédéfini de site de deux manières :

**À partir de l’éditeur web :** Dans le panneau Référentiel, ouvrez le fichier de mappage DITA en mode Carte, puis, dans l’onglet Sortie, sélectionnez l’icône + pour créer un paramètre prédéfini de sortie, puis sélectionnez AEM site dans la liste déroulante de type de la boîte de dialogue Ajouter un paramètre prédéfini. Dans l&#39;éditeur Web, les paramétrages ont été organisés sous les onglets Général et Avancé :

**Général**

L&#39;onglet **Général** contient les configurations suivantes :

- Nom du site
- Chemin d’accès de sortie
- Pages de sortie existantes
- Suppression de pages de site orphelines
- Appliquer les conditions à l’aide de \(si les conditions sont définies pour une carte\)
- Utiliser la ligne de base \(si une ligne de base est créée pour une carte\)
- Processus de génération de publication

**Avancé**

L&#39;onglet Avancé contient les paramétrages suivants :

- Téléchargement de fichiers temporaires
- Générer un PDF distinct pour chaque rubrique
- Utiliser les propriétés de carte comme valeur par défaut

Pour plus d&#39;informations, reportez-vous à la section [Configuration AEM site](#id231KIM004X1).

**Depuis le tableau de bord de la carte**

Pour ouvrir les paramètres prédéfinis de sortie pour AEM Site, cliquez sur un fichier de mappage DITA dans l’interface utilisateur d’Assets, puis cliquez sur Paramètres prédéfinis de sortie, puis sur l’option de sortie AEM Site. Dans le tableau de bord de mappage, cliquez sur **Modifier** en haut pour mettre à jour les différentes configurations, puis cliquez sur **Enregistrer**.

>[!TIP]
>
> Consultez la section *Publication AEM site* du guide Bonnes pratiques pour connaître les bonnes pratiques en matière de création d’AEM sortie de site.

## Configuration AEM site {#id_aem_site_config}

Les options suivantes sont disponibles pour la sortie AEM site :

| Options AEM site | Description |
| --- | --- |
| Type de sortie | Type de sortie à générer. Pour générer une sortie Site AEM réactive, sélectionnez l’option AEM Site . |
| Nom du paramètre | Attribuez un nom explicite aux paramètres de site AEM que vous créez. Par exemple, vous pouvez spécifier *Sortie de clients internes* ou *Sortie d’utilisateurs finaux*. |
| Nom du site | Nom du site où la sortie est stockée dans votre référentiel AEM.<br><br>Un noeud dans le référentiel AEM est créé avec le nom spécifié ici. Si vous ne spécifiez pas le nom du site, le noeud du site est créé avec le nom du fichier de mappage DITA.<br><br>Le nom du site que vous indiquez ici est également utilisé comme titre dans l’onglet du navigateur.<br><br>Vous pouvez également utiliser des variables lors de la définition du nom du site. Pour plus d’informations sur l’utilisation des variables, voir [Utilisation de variables pour définir le chemin de destination, le nom du site ou les options de nom de fichier](generate-output-use-variables.md#id18BUG70K05Z). |
| Conception | Sélectionnez le modèle de conception que vous souhaitez utiliser pour générer la sortie.<br><br>Pour plus d’informations sur l’utilisation de modèles de conception personnalisés pour générer une sortie, contactez votre administrateur de publication. |
| Chemin de destination | Chemin d’accès dans votre référentiel AEM où la sortie est stockée. Lors de la génération de la sortie finale, le nom du site et le chemin de destination sont combinés. Par exemple, si vous spécifiez le nom du site `user-guide` et le chemin de destination `/content/output/aem-guides`, la sortie finale est générée sous le noeud `/content/output/aem-guides/user-guide`.<br><br>Vous pouvez également utiliser des variables lors de la définition du chemin de destination. Pour plus d’informations sur l’utilisation des variables, voir [Utilisation de variables pour définir le chemin de destination, le nom du site ou les options de nom de fichier](generate-output-use-variables.md#id18BUG70K05Z). |
| Appliquer les conditions à l’aide de | Sélectionnez l’une des options suivantes :<br><br>**Aucun appliqué** : sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur la sortie publiée.<br>**Fichier DITAVal** : sélectionnez le ou les fichiers DITAVal pour générer du contenu conditionnel. Vous pouvez sélectionner plusieurs fichiers DITAVal à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin du fichier. Pour le supprimer, utilisez l’icône croisée située à proximité du nom du fichier. Les fichiers DITAVal sont évalués dans l’ordre spécifié. Par conséquent, les conditions spécifiées dans le premier fichier sont prioritaires sur les conditions correspondantes spécifiées dans les fichiers ultérieurs. Vous pouvez conserver l’ordre des fichiers en ajoutant ou en supprimant des fichiers. Si le fichier DITAVal est déplacé vers un autre emplacement ou supprimé, il n’est pas automatiquement supprimé du tableau de bord de la carte. Vous devez mettre à jour l’emplacement au cas où des fichiers seraient déplacés ou supprimés. Vous pouvez placer le pointeur de la souris sur le nom du fichier pour afficher le chemin d’accès dans le référentiel AEM où le fichier est stocké. Vous ne pouvez sélectionner que les fichiers DITAVal et une erreur s’affiche si vous sélectionnez un autre type de fichier.<br>**Paramètre prédéfini de condition** : sélectionnez un paramètre prédéfini de condition dans la liste déroulante pour appliquer une condition lors de la publication de la sortie. Cette option est visible si vous avez ajouté une condition pour le fichier de mappage DITA. Les paramètres conditionnels sont disponibles dans l’onglet Paramètres prédéfinis de condition de la console de mappage DITA. Pour en savoir plus sur les paramètres prédéfinis de condition, voir [Utilisation des paramètres prédéfinis de condition](generate-output-use-condition-presets.md#id1825FL004PN). |
| Pages de sortie existantes | Sélectionnez l’option **Remplacer le contenu** pour remplacer le contenu des pages existantes. Cette option remplace uniquement le contenu présent sous les noeuds content et head de la page. Cette option permet la publication mixte de contenu. Cette option permet de sélectionner la suppression de pages orphelines dans la sortie publiée. Il s’agit également de l’option *default* pour créer la sortie AEM Site.<br><br>Sélectionnez l’option **Supprimer et créer** pour forcer la suppression de toutes les pages existantes lors de la publication. Cette option supprime le noeud de page ainsi que son contenu et toutes les pages enfants qu’il contient. Utilisez cette option si vous avez modifié le modèle de conception de votre paramètre prédéfini de sortie ou si vous souhaitez supprimer des pages supplémentaires déjà présentes dans la destination. |
| Suppression de pages de site orphelines | La sélection du paramètre **Remplacer le contenu** dans le paramètre **Pages de sortie existantes** présente cette option. Si vous sélectionnez cette option, toutes les pages orphelines sont supprimées du site AEM publié. Pour que cette fonction s’exécute correctement, vous devez publier l’ensemble du mappage DITA et ne pas utiliser la publication incrémentielle.<br><br>Supposons que vous ayez publié une carte DITA, qui contient les rubriques a.dita, b.dita et c.dita. Avant de publier à nouveau la carte, vous avez supprimé la rubrique b.dita de la carte. Désormais, si vous avez sélectionné cette option, tout le contenu lié à b.dita est supprimé de la sortie AEM Site et seuls a.dita et c.dita sont publiés.<br><br>Cette fonctionnalité ne supprime pas les mappages enfants publiés. Par exemple, si votre carte parent contient une carte enfant et que vous supprimez la carte enfant entière, le contenu de la carte enfant n’est pas supprimé de la sortie publiée. Cependant, si vous supprimez une rubrique d’un mappage enfant et que vous la republiez, le contenu de la rubrique supprimée est supprimé de la sortie du site.<br><br>En outre, s’il existe un contenu référencé et que ce contenu est supprimé avant de le republier, les données du contenu référencé ne sont pas supprimées.<br><br>**Remarque** : les informations sur les pages orphelines supprimées sont également capturées dans les journaux de génération de sortie. Pour plus d’informations sur l’accès aux fichiers journaux, voir [Affichage et vérification du fichier journal](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). |
| Téléchargement de fichiers temporaires | Sélectionnez cette option pour télécharger les fichiers temporaires générés par DITA-OT. L’emplacement où DITA-OT stocke les fichiers temporaires se trouve dans le journal de génération de sortie. Si vous rencontrez des erreurs lors de la génération de la sortie via DITA-OT, sélectionnez cette option pour conserver les fichiers temporaires. Vous pouvez ensuite utiliser ces fichiers pour résoudre les erreurs de génération de sortie.<br> <br> Après avoir généré la sortie, sélectionnez l’icône **Télécharger les fichiers temporaires** ![ ](images/download-temp-files-icon.png) pour télécharger le dossier ZIP contenant les fichiers temporaires. <br><br> **Remarque** : si vous sélectionnez des propriétés de fichier, puis téléchargez les fichiers temporaires, vous obtenez également le fichier *metadata.xml* dans le dossier ZIP. |
| Générer un PDF distinct pour chaque rubrique | Si cette option est sélectionnée, un PDF est également créé pour chaque rubrique du mappage DITA. Lorsque vous choisissez cette option, une nouvelle option de Partage du chemin du PDF s’affiche.<br><br>Dans le champ Chemin du PDF de partage , spécifiez le chemin de stockage des PDF générés pour chaque rubrique.<br><br>**Remarque** : AEM Guides utilise le plug-in DITA-OT nommé pdfx pour générer le PDF pour chaque rubrique. Ce module externe est fourni avec le module DITA-OT fourni d’usine. Vous pouvez personnaliser ce module externe pour générer un PDF en fonction de vos besoins. Si vous utilisez un module externe DITA-OT personnalisé, assurez-vous d’intégrer le module externe pdfx pour bénéficier de la fonctionnalité de génération de PDF au niveau de la rubrique. |
| Exécuter le processus de génération de publication | Lorsque vous sélectionnez cette option, une nouvelle liste déroulante Processus de génération de publication s’affiche, contenant tous les workflows configurés dans AEM. Vous devez sélectionner un workflow à exécuter une fois le workflow de génération de sortie terminé. |
| Utilisation de la ligne de base | Si vous avez créé une ligne de base pour le mappage DITA sélectionné, sélectionnez cette option pour spécifier la version que vous souhaitez publier.<br><br>**Important** : lorsque vous générez une sortie incrémentielle pour le site AEM, la sortie est alors créée à l’aide de la version actuelle des fichiers et non de la ligne de base jointe.<br><br>Voir [Utilisation de la ligne de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) pour plus de détails. |
| Propriétés du fichier | Sélectionnez les propriétés que vous souhaitez traiter en tant que métadonnées. Ces propriétés sont définies à partir de la page Propriétés du mappage DITA ou du fichier bookmap. Les propriétés que vous sélectionnez dans la liste déroulante apparaissent sous le champ **Propriétés du fichier**. Sélectionnez l’icône croisée en regard de la propriété pour la supprimer. <br><br>**Remarque** : les propriétés de métadonnées sont sensibles à la casse.<br><br>*Si vous avez sélectionné une ligne de base, les valeurs des propriétés sont basées sur la version de la ligne de base sélectionnée.<br>* Si vous n’avez pas sélectionné de ligne de base, les valeurs des propriétés sont basées sur la dernière version.<br><br>Vous pouvez également transmettre les métadonnées à la sortie à l’aide de la publication DITA-OT. Pour plus d’informations, voir [Transmission des métadonnées à la sortie à l’aide de DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Remarque** : si vous n’avez pas défini le `cq:tags` dans l’option Propriétés, les valeurs de `cq:tags` sont sélectionnées dans la copie de travail actuelle même si vous avez sélectionné une ligne de base pour la publication. |
| Utiliser Les Propriétés De La Carte Si Sa Rubrique Manquante Est Absente | Si cette option est sélectionnée, les propriétés définies pour le fichier de mappage sont également copiées dans les rubriques où ces propriétés ne sont pas définies. Tenez compte des points suivants lorsque vous utilisez cette option : <br><br>*Seules les propriétés String, Date ou Long (une seule valeur et plusieurs valeurs) peuvent être transmises aux pages du site AEM.<br>* Les valeurs de métadonnées d’une propriété de type chaîne ne prennent en charge aucun caractère spécial (tel que `@, #, " "`).<br>* Cette option doit être utilisée avec l’option `Properties`. |

## Remarque supplémentaire sur le site AEM

### Génération d’une sortie basée sur des articles à partir de l’éditeur web

Vous pouvez générer la sortie Site AEM pour une ou plusieurs rubriques, ou le mappage DITA entier à partir de l’éditeur web. Vous devez créer des paramètres prédéfinis de sortie pour votre carte DITA, puis vous pouvez facilement générer la sortie AEM Site pour votre carte. Si vous avez mis à jour quelques rubriques dans votre carte, vous pouvez également générer la sortie Site AEM uniquement pour ces rubriques à partir de l’éditeur web. Pour plus d’informations, voir [Publication basée sur un article à partir de l’éditeur web](web-editor-article-publishing.md#id218CK0U019I).

### Générer des rubriques de liaison de sortie à partir d’autres mappages

Il est très courant de disposer d’un large ensemble de documents répartis dans plusieurs dossiers et mappages DITA. Il devient extrêmement complexe de publier du contenu lié à différents emplacements. Par défaut, tous les liens `<xref>` sont créés avec le `local` `@scope`. La publication de ces rubriques n’implique aucun problème, car elle utilise un lien direct vers la rubrique. Si la rubrique se trouve en dehors du mappage DITA actuel, le lien n’affiche pas le contenu lié.

Une autre manière de lier le contenu consiste à créer un lien à l’aide de `peer` `@scope`. Pour ce contenu, le lien est résolu au moment de l’exécution en sélectionnant le titre du fichier et le contexte configuré pour la rubrique liée dans le contexte de publication de la carte DITA. La capture d’écran suivante montre le panneau Propriétés d’un lien comportant le `peer` `@scope` :

![](images/peer-link-scope-link.png){width="800" align="left"}

Pour simplifier la publication de cartes et de rubriques complexes qui renvoient à d’autres rubriques dans d’autres cartes, AEM Guides vous permet de définir le contexte de publication de chaque paramètre prédéfini de sortie.

Le contexte de publication vous permet de spécifier la rubrique à utiliser à partir de laquelle mapper la publication d’une sortie spécifique. Comprenons cela à l&#39;aide d&#39;un exemple — disons que vous avez quatre dossiers : exemple a, exemple b, exemple c et exemple d. Chaque dossier contient un mappage DITA : mappage DITA A, mappage DITA B, mappage DITA C et mappage DITA D. La liaison entre les mappages se produit lorsqu’une rubrique du mappage DITA A est liée à une rubrique dans les mappages DITA B, C ou D. Dans la capture d’écran suivante, un exemple de rubrique de concept contient des liens \(ou des références\) vers des fichiers qui font partie d’autres mappages DITA.

![](images/sample-concept-link-to-other.png){width="350" align="left"}

Désormais, lorsque vous configurez les paramètres de publication de site AEM pour le fichier de mappage qui contient cette rubrique, vous pouvez sélectionner le contexte de publication du contenu lié utilisé lors de la publication. Un contexte de publication est une combinaison de mappage DITA et de son paramètre prédéfini de sortie. Le paramètre prédéfini de sortie, à son tour, contient une version spécifique du contenu et des paramètres prédéfinis conditionnels. Cette combinaison complète de la carte DITA, du paramètre prédéfini de sortie, de la version \(files\) et des conditions définit le contexte de publication pour une carte liée.

Effectuez les étapes suivantes pour spécifier le contexte de publication des fichiers liés entre eux :

1. Ouvrez l’onglet **Paramètres prédéfinis de sortie** du mappage DITA que vous souhaitez publier.

1. Sélectionnez le paramètre prédéfini de sortie **AEM Site**.

   Vous obtenez les onglets Paramètres AEM et Contexte Publish .

   ![](images/aem-site-publish-settings.png){width="800" align="left"}

1. Ouvrez l’onglet **Publish Context** .

   Une liste des rubriques dépendantes s’affiche. Il s’agit des rubriques liées à une rubrique de la carte actuelle, mais elles sont disponibles dans d’autres cartes DITA.

   >[!NOTE]
   >
   > L’onglet Contexte Publish affiche les rubriques liées à l’aide de `peer` `@scope` uniquement. Pour les liens avec `local` `@scope`, il n’est pas nécessaire de spécifier le contexte de publication.

   Par défaut, le dernier paramètre prédéfini de sortie et le mappage sont sélectionnés pour toutes les rubriques liées.

   ![](images/default-publish-context.png){width="800" align="left"}

1. Pour modifier la sélection par défaut du mappage et du paramètre prédéfini DITA, cliquez sur **Modifier** \(dans la barre d’outils principale\).

1. Si vous souhaitez utiliser la sortie publiée le plus récemment de chaque fichier dépendant dans la carte, sélectionnez **Utiliser le contexte de publication généré le plus récemment pour toutes les rubriques dépendantes**.

1. Dans la liste déroulante **Parent Map** , sélectionnez le fichier de mappage avec lequel vous souhaitez lier la sortie de la carte actuelle.

   Lors de la sélection d’un fichier de carte, l’UUID de la carte s’affiche dans la colonne UUID de carte parente. Les paramètres prédéfinis de sortie associés à la carte sélectionnée sont répertoriés dans la liste Parent Map’s Preset.

1. Dans la liste déroulante **Parent Map&#39;s Preset**, sélectionnez le paramètre prédéfini de sortie avec lequel vous souhaitez lier la sortie de la carte actuelle.

1. Sélectionnez la carte requise et son paramètre prédéfini de sortie pour toutes les rubriques dépendantes, puis cliquez sur **Terminé**.

   Le contexte des rubriques dépendantes est maintenant défini. Vous pouvez générer la sortie pour la carte actuelle. Pour plus d’informations sur la génération de la sortie, voir [Générer la sortie pour un mappage DITA à partir de la console de mappage](generate-output-for-a-dita-map.md#).

### Publication fusionnée

AEM Guides prend en charge la publication de contenu DITA sur votre site AEM existant. Par exemple, si vous disposez d’un site existant, vous pouvez utiliser la sortie AEM site pour publier uniquement le contenu DITA sur ce site. Dans ce processus, le contenu existant non DITA n’est pas modifié par le processus de publication. Pour plus d’informations sur la configuration de votre site pour publier uniquement du contenu DITA, contactez votre administrateur de publication.

### Publication `conref`

Si vous utilisez `conref` dans votre contenu, il est publié en tant que contenu normal ou incorporé avec le contenu de la rubrique source \(ou référent\). Le contenu `conref` est rendu avec le contenu principal et aucune page de site distincte n’est créée pour le même contenu. Lorsque vous recherchez le contenu référencé dans `conref`, seule la rubrique ou la page principale contenant le contenu `conref` s’affiche dans les résultats de la recherche.

>[!NOTE]
>
>Si vous avez généré des pages distinctes pour le contenu `conref` à l’aide d’AEM Guides version 3.5 ou antérieure, il est recommandé de nettoyer/supprimer ces pages à l’aide de l’option [Supprimer les pages du site orpheline](#delete-orphan-page-aem-site) .


### Recherche d’une chaîne dans le contenu

Vous pouvez rechercher une chaîne dans la sortie AEM Site. Par défaut, vous pouvez rechercher la chaîne uniquement dans les titres. Pour rechercher la chaîne dans le contenu ou le corps de la sortie AEM site, contactez votre administrateur système pour activer la propriété flattening.enabled .

![Rechercher AEM sortie du site](images/aem-output-search.png){width="650" align="left"}

Pour plus d’informations, reportez-vous à la section *Configuration de l’aplatissement de AEM structure de noeuds de site* du guide Installation et configuration d’Adobe Experience Manager Guides.

**Rubrique parente :**[ Comprendre les paramètres prédéfinis de sortie](generate-output-understand-presets.md)
