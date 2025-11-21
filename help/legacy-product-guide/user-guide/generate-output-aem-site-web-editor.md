---
title: AEM Sites
description: Créez et configurez le paramètre prédéfini AEM Sites dans l'éditeur web et générez une sortie AEM Sites pour le plan DITA, les rubriques sélectionnées et les rubriques liées.
feature: Publishing
role: User
hide: true
exl-id: 9a9ae44f-8fed-4a4e-812c-451bcf138d0a
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '2732'
ht-degree: 0%

---

# Paramètres prédéfinis AEM Sites dans l’éditeur web


Vous pouvez créer des paramètres prédéfinis AEM Sites à partir de l’éditeur web et les configurer pour générer la sortie AEM Sites. La sortie AEM Sites repose sur le mappage des composants composites avec le `guides-components`, ce qui facilite la création et la gestion efficaces du contenu.

Experience Manager Guides fournit des modèles prédéfinis pour la création d’AEM Sites. Ces paramètres prédéfinis vous permettent d’assurer la cohérence de la disposition et de la structure du contenu.
- [Créez des pages d’accueil](/help/product-guide/cs-install-guide/download-install-aem-sites-templates-cs.md#create-a-home-page-using-the-template) basées sur ces modèles prédéfinis.
- Vous pouvez [modifier des modèles de rubrique](/help/product-guide/cs-install-guide/download-install-aem-sites-templates-cs.md#package-installation) et appliquer des styles en fonction de vos besoins.
- Vous pouvez également [personnaliser les modèles AEM Sites existants](/help/product-guide/cs-install-guide/download-install-aem-sites-templates-cs.md#customize-existing-aem-sites-templates).



## Création de paramètres prédéfinis AEM Sites

Pour créer les paramètres prédéfinis AEM Sites à partir de l’éditeur web, procédez comme suit :

1. Dans le panneau Référentiel, ouvrez le fichier DITA map en mode Carte.
1. Dans l’onglet **Sortie**, sélectionnez l’icône + pour créer un paramètre prédéfini de sortie.
1. Sélectionnez **AEM Sites** dans la liste déroulante **Type** de la boîte de dialogue **Nouveau paramètre prédéfini de sortie**.
1. Désélectionnez l’option **Utiliser le mappage de composant hérité** dans la boîte de dialogue **Nouveau paramètre prédéfini de sortie**.

![Nouveau ](images/new-aem-sites-dialog-box.png)





>[!NOTE]
>
>Avant de configurer les paramètres prédéfinis AEM Sites pour Experience Manager Guides, votre administrateur ou administratrice doit créer une structure AEM Sites à l’aide des modèles.
- **Logiciel On-premise** : découvrez comment [télécharger et installer des modèles AEM Sites](/help/product-guide/install-guide/download-install-aem-sites-templates.md) pour les logiciels On-premise.
- **Cloud Service** : en savoir plus sur la [téléchargement et installation de modèles AEM Sites](/help/product-guide/cs-install-guide/download-install-aem-sites-templates-cs.md) pour Cloud Service.




### Ajouter des paramètres prédéfinis au profil du dossier actuel

En tant qu’administrateur, Experience Manager Guides vous permet de créer et de gérer des paramètres prédéfinis de sortie pour les profils globaux et de dossiers. Sélectionnez l’option **Ajouter au profil du dossier actuel** dans la boîte de dialogue **Nouveau paramètre prédéfini de sortie** pour créer un paramètre prédéfini de sortie pour le profil du dossier actuel. ![icône de profil de dossier](images/global-preset-icon.svg) l’icône indique un paramètre prédéfini de niveau de profil de dossier.  En savoir plus sur la [Gestion des paramètres prédéfinis de sortie de profil global et de dossier](./web-editor-manage-output-presets.md).

### Paramètres prédéfinis d’AEM Sites basés sur le mappage des composants hérités

Vous pouvez également créer les paramètres prédéfinis d’AEM Sites à l’aide du mappage des composants hérités. Pour créer les paramètres prédéfinis AEM Sites en fonction du mappage des composants hérités, sélectionnez l’option **Utiliser le mappage des composants hérités** dans la boîte de dialogue **Nouveau paramètre prédéfini de sortie**.

Certaines options peuvent différer pour les paramètres prédéfinis qui utilisent le mappage des composants hérités.



## Configuration des paramètres prédéfinis d’AEM Sites

Les configurations sont organisées sous les onglets **Général**, **Contenu**, **Liste de rubriques** et **Références de mappage croisé**.

![ paramètres prédéfinis d’aem sites ](images/aem-sites-new-config.png)
**Général**

L’onglet **Général** contient les paramétrages suivants relatifs à la génération des sorties :

- Utiliser le chemin du site
- Chemin du site
- Site
- Chemin de publication
- Modèle de page de rubrique
- Générer des noms de page en fonction de
   - Nom du fichier de rubrique
   - Titre du sujet
- Nettoyage des pages générées précédemment
   - Supprimer les pages précédemment générées pour les rubriques supprimées de la carte
   - Supprimez toutes les pages créées par d’autres sources à cet emplacement :
- Workflow de post-génération



**Contenu**

L&#39;onglet **Contenu** contient les paramétrages suivants :

- Utiliser niveau de référence
- Filtrage des conditions
- Arguments de ligne de commande DITA-OT supplémentaires
- Métadonnées
   - Propriétés du fichier (Assets)
   - Utilisation des propriétés de mappage comme solution de secours


Pour plus d’informations, consultez la configuration d’AEM Sites [](#aem_sites_config).

**Liste de sujets**

La **Liste de rubriques** affiche la liste des rubriques présentes dans la copie de travail actuelle du plan DITA. Par défaut, toutes les rubriques sont incluses. Vous pouvez sélectionner des rubriques spécifiques et générer la sortie AEM Sites uniquement pour celles-ci. Par exemple, vous avez mis à jour certaines rubriques afin de ne publier que ces rubriques au lieu de publier l&#39;ensemble du plan DITA.

L’onglet **Liste de rubriques** est présent dans les paramètres prédéfinis d’AEM qui ne sont pas créés à partir d’un mappage hérité.

**Références croisées**
Cette liste contient des rubriques contenant des références croisées avec `scope ="peer"`. Vous pouvez spécifier le contexte de publication d&#39;une liste de références croisées avec des `scope="peer"` aux rubriques disponibles dans d&#39;autres plans DITA. Cet onglet s’affiche si vous utilisez la version Experience Manager Guides (UUID).



En savoir plus sur comment [publier des rubriques liées](#publish-linked-topics).





## Configuration d’AEM Sites {#aem_sites_config}

Les options suivantes sont disponibles pour la sortie AEM Sites :

| Options d’AEM Sites | Description |
| --- | --- |
| Utiliser le chemin du site | Utilisez cette option pour publier votre contenu sur un site Experience Manager. Sélectionnez cette option si vous connaissez le chemin d’accès exact du site où vous souhaitez que la sortie soit publiée. Indiquez également le chemin d’accès complet dans le champ Chemin du site . |
| Chemin du site | Cette option s’affiche si vous sélectionnez l’option **Utiliser le chemin du site**. Parcourez le chemin d’accès exact du site Experience Manager où vous souhaitez que la sortie soit publiée. |
| Site | Nom du Experience Manager Sites sur lequel vous souhaitez publier votre contenu. Les options de la liste déroulante sont renseignées en fonction de la liste des sites disponibles dans AEM Sites. <br>Sélectionnez **Actualiser** ![icône d’actualisation](images/navtitle-refresh-icon.svg) pour récupérer une nouvelle liste d’options et refléter les données mises à jour. |
| Chemin de publication | Chemin d’accès dans votre référentiel AEM où la sortie est stockée. Le chemin de publication est renseigné avec tous les chemins qui contiennent les pages créées à partir du modèle Page d’accueil . La sortie AEM Sites du plan DITA est générée sous ce chemin d&#39;accès.  Par exemple, si vous spécifiez le site en tant que `AEMG-Docs` et le chemin de publication en tant que `aemg-docs-en/docs/product-abc.`, la sortie AEM Sites est générée sous le nœud `aemg-docs-en/docs/product-abc/` dans `crx/de`. |
| Modèle de page de rubrique | Composants structurels que vous pouvez utiliser pour organiser le contenu de manière cohérente sur plusieurs documents. Ces modèles sont prédéfinis dans le modèle de site Adobe Experience Manager. Les options sont renseignées avec tous les modèles de page de rubrique disponibles pour le site sélectionné. Sélectionnez le modèle à appliquer à toutes les rubriques de sortie. |
| Générer des noms de page en fonction de | **Nom de fichier de rubrique** : utilise le nom de fichier de la rubrique DITA pour créer l&#39;URL du site. <br> **Titre de la rubrique** : utilise le titre de la rubrique DITA pour créer les noms de site Experience Manager. |
| Nettoyage des pages générées précédemment | - **Supprimer les pages générées précédemment pour le sujet supprimé de la carte** : si la structure de la carte DTIA change, vous pouvez utiliser cette option pour supprimer les pages générées précédemment pour les sujets supprimés. Cette fonctionnalité est disponible uniquement pour la publication de carte complète.<br><br>Supposons que vous ayez publié un plan DITA, qui contient les rubriques a.dita, b.dita et c.dita. Avant de republier la carte, vous avez supprimé la rubrique b.dita de la carte. Désormais, si vous avez sélectionné cette option, tout le contenu associé à b.dita est supprimé de la sortie AEM Sites et seuls a.dita et c.dita sont publiés.<br><br>**Remarque** : les informations sur les pages supprimées sont également capturées dans les journaux de génération de sortie. Pour plus d’informations sur l’accès aux fichiers journaux, [Afficher et vérifier le fichier journal](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). <br><br>**Attention** : lors de la suppression des rubriques, les pages ne sont plus disponibles sur le site publié. Ainsi, avant que les rubriques ne soient supprimées, un avertissement s’affiche. Vous devez confirmer la suppression.<br><br>- **Supprimer toutes les pages créées par d’autres sources à ce chemin d’accès** : si vous sélectionnez cette option, toutes les pages publiées sur ce chemin d’accès à partir d’autres cartes, rubriques individuelles ou toute autre source sont supprimées. Les pages ne sont plus disponibles sur le site publié. Ainsi, avant que les rubriques ne soient supprimées, un avertissement s’affiche. Vous devez confirmer la suppression. |
| Workflow de post-génération | Lorsque vous sélectionnez cette option, une nouvelle liste déroulante Workflow de post-génération s’affiche, contenant tous les workflows configurés dans AEM. Vous devez sélectionner un workflow à exécuter une fois le workflow de génération de sortie terminé. |
| Utiliser niveau de référence | Si vous avez créé une ligne de base pour le plan DITA sélectionné, sélectionnez cette option pour spécifier la version que vous souhaitez publier.<br><br>**Important** : lorsque vous générez une sortie incrémentielle pour le site AEM, la sortie est créée à l’aide de la version actuelle des fichiers et non de la ligne de base jointe.<br><br>Affichage [Utilisation de la ligne de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) pour plus d’informations. |
| Filtrage conditionnel | Sélectionnez l’une des options suivantes :<br><br>**Aucune** : sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur la sortie publiée.<br>**Utilisation de DITAVAL** : Sélectionnez le ou les fichiers DITAVAL pour générer du contenu conditionné. Vous pouvez sélectionner plusieurs fichiers DITAVal à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin du fichier. Utilisez la croix près du nom du fichier pour le supprimer. Les fichiers DITAVal sont évalués dans l&#39;ordre spécifié. De ce fait, les conditions spécifiées dans le premier fichier sont prioritaires sur les conditions correspondantes spécifiées dans les fichiers ultérieurs. Vous pouvez conserver l’ordre des fichiers en ajoutant ou en supprimant des fichiers. Si le fichier DITAVal est déplacé vers un autre emplacement ou est supprimé, il n&#39;est pas automatiquement supprimé du tableau de bord de mappage. Vous devez mettre à jour l’emplacement au cas où les fichiers seraient déplacés ou supprimés. Vous pouvez pointer sur le nom du fichier pour afficher le chemin d’accès dans le référentiel AEM où le fichier est stocké. Vous ne pouvez sélectionner que les fichiers DITAVal et une erreur s&#39;affiche si vous sélectionnez un autre type de fichier.<br>**Paramètre prédéfini de condition** : sélectionnez un paramètre prédéfini de condition dans la liste déroulante pour appliquer une condition lors de la publication de la sortie. Cette option est visible si vous avez ajouté une condition pour le fichier de plan DITA. Les paramètres conditionnels sont disponibles dans l&#39;onglet Paramètres prédéfinis de condition de la console Plan DITA. Pour en savoir plus sur les paramètres prédéfinis de condition, consultez [Utilisation des paramètres prédéfinis de condition](generate-output-use-condition-presets.md#id1825FL004PN). |
| Arguments de ligne de commande DITA-OT supplémentaires | Spécifiez les arguments supplémentaires que DITA-OT doit traiter lors de la génération de la sortie. Pour plus d&#39;informations sur les arguments de ligne de commande pris en charge dans DITA-OT, consultez la [documentation DITA-OT](https://www.dita-ot.org/). |
| Métadonnées <br> Propriétés <br>Fichier (Assets) | Sélectionnez les propriétés à traiter en tant que métadonnées. Ces propriétés sont définies à partir de la page Propriétés du fichier DITA map ou bookmap. Les propriétés que vous sélectionnez dans la liste déroulante s’affichent sous le champ **Propriétés du fichier**. Sélectionnez l’icône croisée en regard de la propriété pour la supprimer. <br><br>**Remarque** : les propriétés de métadonnées sont sensibles à la casse.<br><br>*Si vous avez sélectionné une ligne de base, les valeurs des propriétés sont basées sur la version de la ligne de base sélectionnée.<br>* Si vous n&#39;avez pas sélectionné de ligne de base, les valeurs des propriétés sont basées sur la dernière version.<br><br>Vous pouvez également transmettre les métadonnées à la sortie à l’aide de la publication DITA-OT. Pour plus de détails, [Transmettez les métadonnées à la sortie à l’aide de DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Remarque** : si vous n&#39;avez pas défini le `cq:tags` dans l&#39;option Propriétés, les valeurs de `cq:tags` sont sélectionnées à partir de la copie de travail en cours, même si vous avez sélectionné une ligne de base pour la publication. |
| Métadonnées <br> <br>Utilisation des propriétés de mappage comme solution de secours | Si cette option est sélectionnée, les propriétés définies pour le fichier de mappage sont également copiées dans les rubriques où ces propriétés ne sont pas définies. Tenez compte des points suivants lors de l’utilisation de cette option :<br><br>*seules les propriétés de type Chaîne, Date ou Long (à une et plusieurs valeurs) peuvent être transmises aux pages du site AEM.<br>* Les valeurs de métadonnées d’une propriété de type Chaîne ne prennent pas en charge les caractères spéciaux (`@, #, " "`, par exemple).<br>* Cette option doit être utilisée avec l’option `Properties`. |
| Conserver les fichiers temporaires | Sélectionnez cette option pour conserver les fichiers temporaires générés par DITA-OT. Si vous rencontrez des erreurs lors de la génération de la sortie via DITA-OT, sélectionnez cette option pour conserver les fichiers temporaires. Vous pouvez ensuite utiliser ces fichiers pour résoudre les erreurs de génération de sortie.<br> <br> Après avoir généré la sortie, sélectionnez l’icône **Télécharger les fichiers temporaires** ![Télécharger les fichiers temporaires](images/download-temp-files-icon.png) pour télécharger le dossier ZIP contenant les fichiers temporaires. <br><br> **Remarque** : si des propriétés de fichier sont ajoutées pendant la génération, les fichiers temporaires de sortie incluent également un fichier *metadata.xml* contenant ces propriétés. |


### Générer la sortie AEM Sites à l’aide des modèles

Experience Manager Guides vous permet d’utiliser les modèles prêts à l’emploi ou d’ajouter vos propres modèles AEM Sites.

Avant de configurer les paramètres prédéfinis d’AEM Sites, veillez à créer une structure AEM Sites à l’aide des modèles.\
Pour plus d’informations, consultez la section [Télécharger et installer des modèles AEM Sites](/help/product-guide/install-guide/download-install-aem-sites-templates.md).



Pour créer et configurer un paramètre prédéfini AEM Sites, procédez comme suit :
1. Ouvrez l&#39;onglet **Paramètres prédéfinis de sortie** du plan DITA que vous souhaitez publier.
1. Sélectionnez le paramètre prédéfini de sortie **AEM Sites**.
1. (Facultatif) Désélectionnez l’option **Utiliser le mappage de composant hérité** pour créer un paramètre prédéfini AEM Sites non hérité .
1. Cliquez sur **Ajouter**. Le paramètre prédéfini d’AEM Sites est créé.
1. Vous pouvez configurer le modèle de sites d’usine de deux manières :
   1. Sélectionnez **Site** puis choisissez le chemin de publication et les modèles de page de rubrique dans les options renseignées :
      1. Sélectionnez le site.
      1. Sélectionnez **Site**. Par exemple, `AEMG Docs`.
      1. Les options **Chemin de publication** et **Modèle de page de rubrique** sont automatiquement définies dans la liste déroulante. Vous pouvez également choisir les options. Par exemple, `AEMG-Docs-Site/en/docs/product1` et `Topic page` sont définis respectivement.
   1. Sélectionnez le chemin d’accès complet au site :
      1. Sélectionnez l’option **Utiliser le chemin du site**.
      1. Sélectionnez le chemin d’accès complet au site. Par exemple, `/content/AEMG-Docs-Site/en/docs/product1`.
      1. Le « modèle de page de rubrique » est automatiquement défini comme `Topic Page`.


1. Enregistrez les modifications apportées au paramètre prédéfini.
1. Sélectionnez l’option **Générer**.
1. Générez AEM Sites pour le mapping correspondant. Par exemple, `/content/AEMG-Docs-Site/en/docs/product`.


   >[!NOTE]
   >
   > Si vous publiez du contenu pour la première fois sur un site AEM, il est recommandé de publier les pages au niveau du site. Cela permet de s’assurer que la sortie s’affiche correctement sur l’instance de **publication** sans aucune interruption CSS.



### Publication des rubriques liées

Experience Manager Guides simplifie la publication de documents complexes en vous permettant de créer des références de rubrique à l’aide de l’`peer @scope` . Vous pouvez ensuite définir le contexte de publication de ces références à partir des paramètres prédéfinis d’AEM Sites et enfin générer la sortie des rubriques liées.
Pour plus de détails, voir [Générer la sortie des rubriques de liaison à partir d&#39;autres cartes](../user-guide/generate-output-aem-site.md#generate-output-linking-topics-from-other-maps).




Pour spécifier le contexte de publication des fichiers liés, procédez comme suit :
1. Ouvrez l&#39;onglet **Paramètres prédéfinis de sortie** du plan DITA que vous souhaitez publier.
1. Sélectionnez le paramètre prédéfini de sortie **AEM Sites**.

   Vous pouvez afficher les onglets **Général**, **Contenu**, **Liste de rubriques** et **Références croisées**. L’onglet **Références de mappage croisé** s’affiche si vous utilisez la version Experience Manager Guides (UUID).

   Vous ne pourrez pas afficher le lien entre les cartes dans les cas suivants :
   - Pour les préréglages créés avant la version 4.6. L’onglet Références croisées est désactivé et une info-bulle, Référence au tableau de bord des cartes, s’affiche.
   - Pour les paramètres prédéfinis créés à partir du tableau de bord de mappage. Pour plus d&#39;informations, consultez la section Mapper l’info-bulle du tableau de bord .
   - Pour les paramètres prédéfinis prêts à l’emploi, reportez-vous à l’info-bulle Mapper le tableau de bord .
   - Pour les paramètres prédéfinis globaux, créez une copie locale de ce paramètre prédéfini global pour définir les références croisées.
Si vous souhaitez utiliser des paramètres prédéfinis AEM Sites à partir de l’éditeur web, créez un nouveau paramètre prédéfini ou dupliquez le paramètre prédéfini existant.

1. Ouvrez l’onglet **Références de mappage croisé**.

   Une liste de rubriques et leurs références s’affichent. Vous pouvez spécifier le contexte de publication d&#39;une liste de références croisées à des rubriques disponibles dans d&#39;autres plans DITA avec `scope="peer"`.

   Pour utiliser le panneau de référence croisée de l’éditeur web, `<xrefs>` devez disposer d’identifiants uniques. Les ID uniques des `<xrefs>` seront automatiquement générés lors de la modification/enregistrement de l’ancien contenu si l’ID n’existe pas.

   >[!NOTE]
   >
   >L’onglet **Références de mappage croisé** affiche les rubriques liées à l’aide de l’`scope="peer"` uniquement. Pour les liens avec `scope="local"`, il n’est pas nécessaire de spécifier le contexte de publication.

   Toutes les rubriques liées ont leur dernier paramètre prédéfini de sortie et leur dernier mappage sélectionnés par défaut. Par défaut, le contexte de publication de toutes les rubriques liées est défini sur `<Most recently generated>` mappage .

   ![Références de mappage croisé](images/aem-sites-cross-map-references.png)

1. Si vous souhaitez utiliser la sortie la plus récemment publiée de chaque fichier dépendant dans le mappage, sélectionnez **Utiliser la dernière générée** contexte de publication pour toutes les rubriques dépendantes.
Vous devez publier le mappage sélectionné comme mappage parent avant de publier le mappage contenant les rubriques liées. Si la carte avec des rubriques liées n’est pas publiée, les liens s’affichent sous la forme de texte normal au lieu de liens hypertexte dans la sortie AEM Sites.
Vous devez sélectionner le même type de paramètre prédéfini AEM Sites pour la rubrique liée. Par exemple, si le paramètre prédéfini AEM Sites actuel utilise le mappage des composants hérités, sélectionnez un paramètre prédéfini AEM Sites similaire de la rubrique liée.
1. Dans la liste déroulante Mappage parent , sélectionnez le fichier de mappage avec la sortie duquel vous souhaitez lier la sortie du mappage actuel.
La sélection d’un fichier de mappage affiche l’UUID du mappage dans la colonne UUID du mappage parent . Les paramètres prédéfinis de sortie associés à la carte sélectionnée sont répertoriés dans la liste Paramètre prédéfini de la carte parent. Par exemple, la rubrique 1 de la carte A contient une référence à la rubrique 2. La rubrique 2 peut être présente dans une ou plusieurs cartes. Vous pouvez sélectionner le mappage parent et un paramètre prédéfini spécifique ou la sortie publiée le plus récemment pour chaque lien.

1. Si la même rubrique est référencée plusieurs fois dans un fichier, vous pouvez ajouter un contexte de publication différent pour chaque instance. Vous bénéficiez ainsi d’une plus grande flexibilité et d’un meilleur contrôle sur leur contenu. Par exemple, la rubrique 3 est présente à la fois dans la carte B et dans la carte C. La rubrique 1 contient deux références à la rubrique 3. Vous pouvez choisir Mappage B comme mappage parent pour le premier lien et Mappage C comme parent pour le deuxième lien.

1. Dans la liste déroulante Paramètre prédéfini du mappage parent , sélectionnez le paramètre prédéfini de sortie avec lequel vous souhaitez lier la sortie du mappage actuel.
   >[!NOTE]
   >
   > Les différents paramètres prédéfinis AEM Sites de la carte actuelle apparaissent dans la liste déroulante. Si vous ne sélectionnez pas de paramètre prédéfini, une icône d’avertissement s’affiche et la génération de la sortie échoue.
1. Sélectionnez la carte requise et son paramètre prédéfini de sortie pour toutes les rubriques sources, puis sélectionnez **Générer**.







**Rubrique parente :** [Présentation des paramètres prédéfinis de sortie](generate-output-understand-presets.md)
