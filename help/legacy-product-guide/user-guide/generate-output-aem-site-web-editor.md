---
title: AEM Sites
description: Créez et configurez le paramètre prédéfini AEM Sites dans l’éditeur web et générez une sortie AEM Sites pour le mappage DITA, les rubriques sélectionnées et les rubriques liées.
feature: Publishing
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '2732'
ht-degree: 0%

---

# Paramètres prédéfinis AEM Sites dans l’éditeur web


Vous pouvez créer des paramètres prédéfinis AEM Sites à partir de l’éditeur web et les configurer pour générer la sortie AEM Sites. La sortie AEM Sites est basée sur le mappage des composants composites avec `guides-components`, ce qui facilite la création et la gestion de contenu efficaces.

Experience Manager Guides fournit des modèles prédéfinis pour la création d’AEM Sites. Ces paramètres prédéfinis vous aident à assurer la cohérence de la disposition et de la structure du contenu.
- [Créez des pages d’accueil](../cs-install-guide/download-install-aem-sites-templates-cs.md#create-a-home-page-using-the-template) en fonction de ces modèles prédéfinis.
- Vous pouvez [modifier les modèles de rubrique](../cs-install-guide/download-install-aem-sites-templates-cs.md#package-installation) et appliquer des styles en fonction de vos besoins.
- Vous pouvez également [personnaliser les modèles AEM Sites existants](../cs-install-guide/download-install-aem-sites-templates-cs.md#customize-existing-aem-sites-templates).



## Création de paramètres prédéfinis AEM Sites

Pour créer les paramètres prédéfinis AEM Sites à partir de l’éditeur web, procédez comme suit :

1. Dans le panneau Repository, ouvrez le fichier de mappage DITA en mode Carte.
1. Dans l’onglet **Output** , sélectionnez l’icône + pour créer un paramètre prédéfini de sortie.
1. Sélectionnez **AEM Sites** dans la liste déroulante **Type** de la boîte de dialogue **Nouveau paramètre prédéfini de sortie**.
1. Désélectionnez l’option **Utiliser le mappage de composant hérité** dans la boîte de dialogue **Nouveau paramètre prédéfini de sortie** .

![Nouveau ](images/new-aem-sites-dialog-box.png)





>[!NOTE]
>
>Avant de configurer les paramètres prédéfinis AEM Sites pour Experience Manager Guides, votre administrateur doit créer une structure AEM Sites à l’aide des modèles.
- **Logiciel on-premise** : découvrez comment [télécharger et installer des modèles AEM Sites](../install-guide/download-install-aem-sites-templates.md) pour le logiciel on-premise.
- **Cloud Service** : découvrez comment [télécharger et installer des modèles AEM Sites](../cs-install-guide/download-install-aem-sites-templates-cs.md) pour Cloud Service.




### Ajout de paramètres prédéfinis au profil de dossier actuel

En tant qu’administrateur, Experience Manager Guides vous permet de créer et de gérer des paramètres prédéfinis de sortie pour les profils globaux et de dossiers. Sélectionnez l’option **Ajouter au profil de dossier actuel** dans la boîte de dialogue **Nouveau paramètre prédéfini de sortie** pour créer un paramètre prédéfini de sortie pour le profil de dossier actuel. L’icône ![icône de profil de dossier](images/global-preset-icon.svg) indique un paramètre prédéfini de niveau profil de dossier.  En savoir plus sur [Gérer les paramètres prédéfinis de sortie de profil globaux et de dossier](./web-editor-manage-output-presets.md).

### Paramètres prédéfinis AEM Sites basés sur le mappage de composants hérités

Vous pouvez également créer les paramètres prédéfinis AEM Sites à l’aide du mappage de composant hérité. Pour créer les paramètres prédéfinis AEM Sites en fonction du mappage des composants hérités, sélectionnez l’option **Utiliser le mappage des composants hérités** dans la boîte de dialogue **Nouveau paramètre prédéfini de sortie**.

Certaines options peuvent différer pour les paramètres prédéfinis qui utilisent le mappage de composant hérité.



## Configuration des paramètres prédéfinis AEM Sites

Les configurations sont organisées sous les onglets **Général**, **Contenu**, **Liste de rubriques** et **Références de mappage croisé**.

![ Paramètres prédéfinis aem sites](images/aem-sites-new-config.png)
**Général**

L’onglet **Général** contient les configurations suivantes liées à la génération de sorties :

- Utilisation du chemin du site
- Chemin du site
- Site
- Chemin Publish
- Modèle de page de rubrique
- Générer des noms de page en fonction de
   - Nom du fichier de rubrique
   - Titre de la rubrique
- Nettoyage des pages générées précédemment
   - Suppression des pages générées précédemment pour les rubriques supprimées de la carte
   - Supprimez toutes les pages créées par d’autres sources à ce chemin :
- Workflow de post-génération



**Contenu**

L&#39;onglet **Contenu** contient les configurations suivantes :

- Utilisation de la ligne de base
- Filtrage des conditions
- Arguments de ligne de commande DITA-OT supplémentaires
- Métadonnées
   - Propriétés File (Assets)
   - Utilisation des propriétés de mappage comme solution de secours


Pour plus d&#39;informations, reportez-vous à la section [Configuration AEM Sites](#aem_sites_config).

**Liste de rubriques**

La **liste de rubriques** affiche la liste des rubriques présentes dans la copie de travail actuelle du mappage DITA. Par défaut, toutes les rubriques sont incluses. Vous pouvez sélectionner des rubriques spécifiques et générer la sortie AEM Sites uniquement pour elles. Par exemple, vous avez mis à jour certaines rubriques afin de pouvoir publier uniquement ces rubriques au lieu de publier l’ensemble du mappage DITA.

L’onglet **Liste de rubriques** est présent dans les AEM paramètres prédéfinis qui ne sont pas créés en fonction du mappage hérité.

**Références croisées**
Cette liste contient des rubriques contenant des références croisées avec `scope ="peer"`. Vous pouvez spécifier le contexte de publication d’une liste de références croisées avec `scope="peer"` pour les rubriques disponibles dans d’autres mappages DITA. Cet onglet s’affiche si vous utilisez la version Experience Manager Guides (UUID).



Découvrez comment [publier des rubriques liées](#publish-linked-topics).





## Configuration AEM Sites {#aem_sites_config}

Les options suivantes sont disponibles pour la sortie AEM Sites :

| Options AEM Sites | Description |
| --- | --- |
| Utilisation du chemin du site | Utilisez cette option pour publier du contenu sur un site Experience Manager. Sélectionnez cette option si vous connaissez le chemin exact du site où vous souhaitez que la sortie soit publiée. En outre, mentionnez le chemin complet dans le champ Chemin du site . |
| Chemin du site | Cette option s’affiche si vous sélectionnez l’option **Utiliser le chemin du site** . Parcourez le chemin exact du site Experience Manager où vous souhaitez que la sortie soit publiée. |
| Site | Nom du Experience Manager Sites auquel vous souhaitez publier votre contenu. Les options de la liste déroulante sont renseignées en fonction de la liste des sites disponibles dans AEM Sites. <br> Sélectionnez **Actualiser** ![Icône d’actualisation](images/navtitle-refresh-icon.svg) pour récupérer une nouvelle liste d’options et refléter les données mises à jour. |
| Chemin Publish | Chemin d’accès dans votre référentiel AEM où la sortie est stockée. Le chemin Publish est renseigné avec tous les chemins contenant les pages créées à partir du modèle Page d’accueil . La sortie AEM Sites du mappage DITA est générée sous ce chemin.  Par exemple, si vous spécifiez Site comme `AEMG-Docs` et Publish Path comme `aemg-docs-en/docs/product-abc.`, la sortie AEM Sites est générée sous le noeud `aemg-docs-en/docs/product-abc/` de `crx/de`. |
| Modèle de page de rubrique | Composants structurels que vous pouvez utiliser pour organiser le contenu de manière cohérente dans plusieurs documents. Ces modèles sont prédéfinis dans le modèle Site Adobe Experience Manager . Les options sont renseignées avec tous les modèles de page de rubrique disponibles pour le site sélectionné. Sélectionnez le modèle à appliquer à toutes les rubriques de sortie. |
| Générer des noms de page en fonction de | **Nom de fichier de la rubrique** : utilise le nom de fichier de la rubrique DITA pour créer l’URL du site. <br> **Titre de la rubrique** : utilise le titre de la rubrique DITA pour créer les noms de site Experience Manager. |
| Nettoyage des pages générées précédemment | - **Supprimer les pages générées précédemment pour la rubrique supprimée de la carte** : si la structure de la carte DTIA change, vous pouvez utiliser cette option pour supprimer les pages générées précédemment pour les rubriques supprimées. Cette fonctionnalité est disponible uniquement pour la publication de cartes complètes.<br><br>Supposons que vous ayez publié une carte DITA, qui contient les rubriques a.dita, b.dita et c.dita. Avant de publier à nouveau la carte, vous avez supprimé la rubrique b.dita de la carte. Désormais, si vous avez sélectionné cette option, tout le contenu associé à b.dita est supprimé de la sortie AEM Sites et seuls a.dita et c.dita sont publiés.<br><br>**Remarque** : les informations sur les pages supprimées sont également capturées dans les journaux de génération de sortie. Pour plus d’informations sur l’accès aux fichiers journaux, [Affichez et vérifiez le fichier journal](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). <br><br>**Attention** : lors de la suppression des rubriques, les pages ne sont plus disponibles sur le site publié. Ainsi, avant que les rubriques ne soient supprimées, un avertissement s’affiche. Vous devez confirmer leur suppression.<br><br>- **Supprimez toutes les pages créées par d’autres sources à ce chemin d’accès** : si vous sélectionnez cette option, toutes les pages publiées sur ce chemin d’accès à partir d’autres mappages, de rubriques individuelles ou de toute autre source sont supprimées. Les pages deviennent également indisponibles à partir du site publié. Ainsi, avant que les rubriques ne soient supprimées, un avertissement s’affiche. Vous devez confirmer leur suppression. |
| Processus de génération de publication | Lorsque vous sélectionnez cette option, une nouvelle liste déroulante Processus de génération de publication s’affiche, contenant tous les workflows configurés dans AEM. Vous devez sélectionner un workflow à exécuter une fois le workflow de génération de sortie terminé. |
| Utilisation de la ligne de base | Si vous avez créé une ligne de base pour le mappage DITA sélectionné, sélectionnez cette option pour spécifier la version que vous souhaitez publier.<br><br>**Important** : lorsque vous générez une sortie incrémentielle pour le site AEM, la sortie est alors créée à l’aide de la version actuelle des fichiers et non de la ligne de base jointe.<br><br>Afficher [Utilisation de la ligne de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) pour plus d’informations. |
| Filtrage conditionnel | Sélectionnez l’une des options suivantes :<br><br>**Aucun** : sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur la sortie publiée.<br>**Utilisation de DITAVAL** : sélectionnez le ou les fichiers DITAVal pour générer du contenu conditionnel. Vous pouvez sélectionner plusieurs fichiers DITAVal à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin du fichier. Pour le supprimer, utilisez l’icône croisée située à proximité du nom du fichier. Les fichiers DITAVal sont évalués dans l’ordre spécifié. Par conséquent, les conditions spécifiées dans le premier fichier sont prioritaires sur les conditions correspondantes spécifiées dans les fichiers ultérieurs. Vous pouvez conserver l’ordre des fichiers en ajoutant ou en supprimant des fichiers. Si le fichier DITAVal est déplacé vers un autre emplacement ou supprimé, il n’est pas automatiquement supprimé du tableau de bord de la carte. Vous devez mettre à jour l’emplacement au cas où des fichiers seraient déplacés ou supprimés. Vous pouvez placer le pointeur de la souris sur le nom du fichier pour afficher le chemin d’accès dans le référentiel AEM où le fichier est stocké. Vous ne pouvez sélectionner que les fichiers DITAVal et une erreur s’affiche si vous sélectionnez un autre type de fichier.<br>**Paramètre prédéfini de condition** : sélectionnez un paramètre prédéfini de condition dans la liste déroulante pour appliquer une condition lors de la publication de la sortie. Cette option est visible si vous avez ajouté une condition pour le fichier de mappage DITA. Les paramètres conditionnels sont disponibles dans l’onglet Paramètres prédéfinis de condition de la console de mappage DITA. Pour en savoir plus sur les paramètres prédéfinis de condition, consultez la section [Utiliser les paramètres prédéfinis de condition](generate-output-use-condition-presets.md#id1825FL004PN). |
| Arguments de ligne de commande DITA-OT supplémentaires | Spécifiez les arguments supplémentaires que vous souhaitez que DITA-OT traite lors de la génération de la sortie. Pour plus d’informations sur les arguments de ligne de commande pris en charge dans DITA-OT, consultez la [documentation DITA-OT](https://www.dita-ot.org/). |
| Métadonnées <br> <br>Propriétés de fichier (Assets) | Sélectionnez les propriétés que vous souhaitez traiter en tant que métadonnées. Ces propriétés sont définies à partir de la page Propriétés du mappage DITA ou du fichier bookmap. Les propriétés que vous sélectionnez dans la liste déroulante apparaissent sous le champ **Propriétés du fichier**. Sélectionnez l’icône croisée en regard de la propriété pour la supprimer. <br><br>**Remarque** : les propriétés de métadonnées sont sensibles à la casse.<br><br>*Si vous avez sélectionné une ligne de base, les valeurs des propriétés sont basées sur la version de la ligne de base sélectionnée.<br>* Si vous n’avez pas sélectionné de ligne de base, les valeurs des propriétés sont basées sur la dernière version.<br><br>Vous pouvez également transmettre les métadonnées à la sortie à l’aide de la publication DITA-OT. Pour plus de détails, [Transmettez les métadonnées à la sortie à l’aide de DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Remarque** : si vous n’avez pas défini le `cq:tags` dans l’option Propriétés, les valeurs de `cq:tags` sont sélectionnées dans la copie de travail actuelle même si vous avez sélectionné une ligne de base pour la publication. |
| Métadonnées <br> <br> Utiliser les propriétés de mappage comme secours | Si cette option est sélectionnée, les propriétés définies pour le fichier de mappage sont également copiées dans les rubriques où ces propriétés ne sont pas définies. Tenez compte des points suivants lorsque vous utilisez cette option : <br><br>*Seules les propriétés String, Date ou Long (une seule valeur et plusieurs valeurs) peuvent être transmises aux pages du site AEM.<br>* Les valeurs de métadonnées d’une propriété de type chaîne ne prennent en charge aucun caractère spécial (tel que `@, #, " "`).<br>* Cette option doit être utilisée avec l’option `Properties`. |
| Conserver les fichiers temporaires | Sélectionnez cette option pour conserver les fichiers temporaires générés par DITA-OT. Si vous rencontrez des erreurs lors de la génération de la sortie via DITA-OT, sélectionnez cette option pour conserver les fichiers temporaires. Vous pouvez ensuite utiliser ces fichiers pour résoudre les erreurs de génération de sortie.<br> <br> Après avoir généré la sortie, sélectionnez l’icône **Télécharger les fichiers temporaires** ![ ](images/download-temp-files-icon.png) pour télécharger le dossier ZIP contenant les fichiers temporaires. <br><br> **Remarque** : Si des propriétés de fichier sont ajoutées pendant la génération, les fichiers temporaires de sortie incluent également un fichier *metadata.xml* contenant ces propriétés. |


### Générer la sortie AEM Sites à l&#39;aide des modèles

Experience Manager Guides vous permet d’utiliser les modèles prêts à l’emploi ou d’ajouter vos propres modèles AEM Sites.

Avant de configurer les paramètres prédéfinis AEM Sites, veillez à créer une structure AEM Sites à l’aide des modèles.\
Pour plus d’informations, voir [Télécharger et installer des modèles AEM Sites](../install-guide/download-install-aem-sites-templates.md).



Effectuez les étapes suivantes pour créer et configurer un paramètre prédéfini AEM Sites :
1. Ouvrez l’onglet **Paramètres prédéfinis de sortie** du mappage DITA que vous souhaitez publier.
1. Sélectionnez le paramètre prédéfini de sortie **AEM Sites**.
1. (Facultatif) Décochez l’option **Utiliser le mappage de composant hérité** pour créer un paramètre prédéfini AEM Sites non hérité .
1. Cliquez sur **Ajouter**. Le paramètre prédéfini pour AEM Sites est créé.
1. Vous pouvez configurer le modèle Sites d’usine de deux manières :
   1. Sélectionnez **Site** , puis le chemin de publication et les modèles de page de rubrique parmi les options renseignées :
      1. Sélectionnez le site.
      1. Sélectionnez **Site**. Par exemple, `AEMG Docs`.
      1. Les options **Chemin d’accès Publish** et **Modèle de page de rubrique** sont automatiquement définies dans la liste déroulante. Vous pouvez également choisir les options. Par exemple, `AEMG-Docs-Site/en/docs/product1` et `Topic page` sont définis, respectivement.
   1. Sélectionnez le chemin complet du site :
      1. Sélectionnez l’option **Utiliser le chemin du site** .
      1. Sélectionnez le chemin complet du site. Par exemple, `/content/AEMG-Docs-Site/en/docs/product1`.
      1. Le &quot;modèle de page de rubrique&quot; est automatiquement défini sur `Topic Page`.


1. Enregistrez les modifications apportées au paramètre prédéfini.
1. Sélectionnez l&#39;option **Générer** .
1. Générez AEM Sites pour le mappage correspondant. Par exemple, `/content/AEMG-Docs-Site/en/docs/product`.


   >[!NOTE]
   >
   > Si vous publiez du contenu sur un site AEM pour la première fois, il est recommandé de publier les pages au niveau du site. Cela permet de s’assurer que la sortie s’affiche correctement sur l’instance **Publish** sans interruption CSS.



### Rubriques liées à Publish

Experience Manager Guides simplifie la publication de documents complexes en vous permettant de créer des références de rubrique à l’aide de `peer @scope`. Vous pouvez ensuite définir le contexte de publication de ces références à partir des paramètres prédéfinis AEM Sites et enfin générer la sortie des rubriques liées.
Pour plus d&#39;informations, voir [Générer une sortie de liaison de rubriques à partir d&#39;autres cartes](../user-guide/generate-output-aem-site.md#generate-output-linking-topics-from-other-maps).




Effectuez les étapes suivantes pour spécifier le contexte de publication des fichiers liés entre eux :
1. Ouvrez l’onglet **Paramètres prédéfinis de sortie** du mappage DITA que vous souhaitez publier.
1. Sélectionnez le paramètre prédéfini de sortie **AEM Sites**.

   Vous pouvez afficher les onglets **Général**, **Contenu**, **Liste de rubriques** et **Références de mappage croisé**. L’onglet **Références de mappage croisé** s’affiche si vous utilisez la version Experience Manager Guides (UUID).

   Vous ne pourrez pas afficher la liaison croisée dans les cas suivants :
   - Pour les paramètres prédéfinis créés avant la version 4.6. L’onglet Références croisées est désactivé et une info-bulle (voir Tableau de bord des cartes) s’affiche.
   - Pour les paramètres prédéfinis créés à partir du tableau de bord de mappage. Reportez-vous à la section Info-bulle du tableau de bord de carte qui s’affiche.
   - Pour les paramètres prédéfinis prêts à l’emploi, reportez-vous à l’info-bulle du tableau de bord des cartes qui s’affiche.
   - Pour les paramètres prédéfinis globaux, créez une copie locale de ce paramètre prédéfini global pour définir des références croisées.
Si vous souhaitez utiliser des paramètres prédéfinis AEM Sites à partir de l’éditeur web, créez un nouveau paramètre prédéfini ou dupliquez le paramètre prédéfini existant.

1. Ouvrez l’onglet **Références de mappage croisé** .

   Une liste de rubriques et leurs références s’affiche. Vous pouvez spécifier le contexte de publication pour une liste de références croisées à des rubriques disponibles dans d’autres mappages DITA avec `scope="peer"`.

   Pour utiliser le panneau de référence croisée à partir de Web Editor, `<xrefs>` doit avoir des identifiants uniques. Les identifiants uniques pour `<xrefs>` seront automatiquement générés lors de la modification/enregistrement de l’ancien contenu si l’identifiant n’est pas présent.

   >[!NOTE]
   >
   >L’onglet **Références de mappage croisé** affiche les rubriques liées à l’aide de `scope="peer"` uniquement. Pour les liens avec `scope="local"`, il n’est pas nécessaire de spécifier le contexte de publication.

   Toutes les rubriques liées ont leur dernier paramètre prédéfini de sortie et leur mappage sélectionné par défaut. Le contexte de publication pour toutes les rubriques liées est défini sur `<Most recently generated>` map par défaut.

   ![Références de mappage croisé](images/aem-sites-cross-map-references.png)

1. Si vous souhaitez utiliser la sortie publiée le plus récemment de chaque fichier dépendant dans la carte, sélectionnez **Utiliser le contexte de publication généré le plus récemment** pour toutes les rubriques dépendantes.
Vous devez publier le mappage sélectionné comme mappage parent avant de publier le mappage contenant les rubriques liées. Si le mappage avec des rubriques liées n’est pas publié, les liens apparaissent sous forme de texte normal au lieu d’hyperliens dans la sortie AEM Sites.
Vous devez sélectionner le même type de paramètre prédéfini AEM Sites pour la rubrique liée. Par exemple, si le paramètre prédéfini AEM Sites actuel utilise le mappage de composant hérité, sélectionnez un paramètre prédéfini AEM Sites similaire à la rubrique liée.
1. Dans la liste déroulante Mappage parent , sélectionnez le fichier de mappage avec lequel vous souhaitez lier la sortie de la carte actuelle.
La sélection d’un fichier de carte affiche l’UUID de la carte dans la colonne UID de carte parente. Les paramètres prédéfinis de sortie associés au mappage sélectionné sont répertoriés dans la liste Parent Map’s Preset. Par exemple, la rubrique 1 de la carte A contient une référence à la rubrique 2. La rubrique 2 peut être présente dans une ou plusieurs cartes. Vous pouvez sélectionner le mappage parent et un paramètre prédéfini spécifique ou la sortie publiée le plus récemment pour chaque lien.

1. Si la même rubrique est référencée plusieurs fois dans un fichier, vous pouvez ajouter un contexte de publication différent pour chaque instance. Vous bénéficiez ainsi d’une plus grande flexibilité et d’un meilleur contrôle sur leur contenu. Par exemple, la rubrique 3 est présente dans les cartes B et C. La rubrique 1 contient deux références à la rubrique 3. Vous pouvez choisir la carte B comme mappage parent pour le premier lien et la carte C comme parent pour le second lien.

1. Dans la liste déroulante Parent Map’s Preset (Parent Map), sélectionnez le paramètre prédéfini de sortie avec lequel vous souhaitez lier la sortie de la carte active.
   >[!NOTE]
   >
   > Les différents paramètres prédéfinis AEM Sites de la carte actuelle apparaissent dans la liste déroulante. Si vous ne sélectionnez pas de paramètre prédéfini, une icône d’avertissement s’affiche et la génération de la sortie échoue.
1. Sélectionnez la carte requise et son paramètre prédéfini de sortie pour toutes les rubriques source et sélectionnez **Générer**.







**Rubrique parente :** [Comprendre les paramètres prédéfinis de sortie](generate-output-understand-presets.md)
