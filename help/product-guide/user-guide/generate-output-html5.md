---
title: Utiliser HTML5
description: Découvrez comment créer un paramètre prédéfini HTML5 à partir de la console de mappage et du tableau de bord de mappage. Configurez le paramètre prédéfini de sortie HTML5 dans AEM Guides.
exl-id: b54bf3a0-7a13-41a0-ae72-cdf2caf8d974
feature: Publishing
role: User
source-git-commit: a953de289530457b257259bda3d9af2b68790592
workflow-type: tm+mt
source-wordcount: '1516'
ht-degree: 0%

---

# HTML5 {#id205BE700XO1}

Vous pouvez créer le paramètre prédéfini de sortie HTML5 pour publier la sortie à l’aide de DITA-OT et FMPS (si configuré par votre administrateur).

Vous pouvez créer le paramètre prédéfini HTML5 de deux manières :

- [Création d’un paramètre prédéfini de sortie HTML5 à partir de la console Carte](#create-html5-output-preset-from-the-map-console)
- [Création d’un paramètre prédéfini de sortie HTML5 à partir du tableau de bord de mappage](#create-html5-output-preset-from-the-map-dashboard)

## Création d’un paramètre prédéfini de sortie HTML5 à partir de la console Carte

Pour créer le paramètre prédéfini HTML5 à partir de la console Carte, procédez comme suit :

1. [Ouvrez un fichier de mappage DITA dans la console Mappage](./open-files-map-console.md).

   Vous pouvez également accéder au fichier de mappage à partir du widget **Fichiers récents** dans la section [Aperçu](./intro-home-page.md#overview). Le fichier de mappage sélectionné s’ouvre dans la console Mappage .
1. Dans l’onglet **Paramètres prédéfinis de sortie**, sélectionnez l’icône + pour créer un paramètre prédéfini de sortie.
1. Sélectionnez **HTML5** dans la liste déroulante Type de la boîte de dialogue **Nouveau paramètre prédéfini de sortie**.
1. Dans le champ **Nom**, attribuez un nom à ce paramètre prédéfini.
1. Dans le champ **Générer HTML à l’aide de**, sélectionnez DITA-OT.
1. Sélectionnez l’option **Ajouter au profil du dossier actuel** pour créer un paramètre prédéfini de sortie dans le profil du dossier actuel. L’![icône de profil de dossier](images/global-preset-icon.svg) indique un paramètre prédéfini au niveau du profil de dossier.

   En savoir plus sur la [Gestion des paramètres prédéfinis de sortie de profil globaux et de dossier](./web-editor-manage-output-presets.md).

1. Sélectionnez **Ajouter**.

   Le paramètre prédéfini d’HTML5 est créé.

   ![](images/html5-preset-dialog-new.png){width="300" align="left"}

Dans la console Carte, les options de configuration des paramètres prédéfinis sont organisées sous les onglets **Général** et **Avancé**.

L&#39;onglet **Général** contient les options de paramétrage suivantes :

- Chemin de sortie
- Arguments de ligne de commande DITA-OT
- Nom du fichier
- Filtrage conditionnel \(si les conditions sont définies pour un mappage\)
- Utiliser la ligne de base \(Si une ligne de base est créée pour une carte\)
- Workflow de post-génération

**Avancé**

L’onglet Avancé contient les options de configuration suivantes :

- Nom de la transformation
- Conserver les fichiers temporaires
- Aplatir la hiérarchie des fichiers
- Propriétés du fichier

Pour plus d’informations sur les options de configuration des paramètres prédéfinis, consultez la section [Configuration des paramètres prédéfinis HTML5](#html5-preset-configuration).

## Création d’un paramètre prédéfini de sortie HTML5 à partir du tableau de bord de mappage

Pour créer le paramètre prédéfini HTML5 à partir du tableau de bord de mappage, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez à et sélectionnez le plan DITA pour l’ouvrir dans le tableau de bord Plan .
1. Assurez-vous que l’onglet **Paramètres prédéfinis de sortie** est sélectionné.
1. Sélectionnez **Créer** dans la barre d’outils.

   Un nouveau formulaire de création de paramètre prédéfini de sortie s’affiche.

1. Saisissez les détails de configuration requis pour le préréglage HTML5.
1. Sélectionnez **Terminé** pour enregistrer les paramètres prédéfinis.

Pour plus d’informations sur les options de configuration des paramètres prédéfinis, consultez la section [Configuration des paramètres prédéfinis HTML5](#html5-preset-configuration).

## Configuration des paramètres prédéfinis HTML5

Les options de configuration varient légèrement selon que vous configurez le paramètre prédéfini depuis la console Map ou le tableau de bord Map. Certaines options s’appliquent uniquement au tableau de bord des cartes, tandis que d’autres s’appliquent aux deux.

Si une même configuration comporte deux libellés de champ différents, un **/** les sépare dans le tableau ci-dessous. Le premier représente le libellé dans la console Mappage , et le second représente le libellé dans le tableau de bord Mappage .

Par exemple, **Chemin de sortie/Chemin de destination** - Ici, **Chemin de sortie** est le libellé utilisé dans la console de mappage, tandis que **Chemin de destination** est le libellé utilisé dans le tableau de bord de mappage pour la même configuration.

| Options HTML5 | Description |
| --- | --- |
| Type de sortie (*applicable uniquement au tableau de bord des cartes*) | Type de sortie que vous souhaitez générer. Pour générer une sortie HTML5, choisissez l’option HTML5 . |
| Nom du paramètre (*applicable uniquement au tableau de bord de carte*) | Attribuez un nom explicite aux paramètres de sortie HTML5 que vous êtes en train de créer. Par exemple, vous pouvez spécifier _sortie des clients internes_ ou _sortie des utilisateurs finaux_. |
| Générer en responsive design avec (*Applicable uniquement au tableau de bord des cartes*) | Sélectionnez **DITA-OT** pour générer la sortie HTML5. Sélectionnez **FrameMaker Publishing Server** si votre administrateur a configuré cette option. Certaines des options de configuration varient lorsque FMPS est sélectionné. |
| Chemin de sortie/chemin de destination | Chemin d’accès dans votre référentiel AEM où est stockée la sortie HTML5. Le chemin de sortie est défini via la variable `${base_output_path}`, qui est configurée par l’administrateur. Pour configurer le chemin de sortie, affichez [Configurer l’emplacement de sortie de base pour les services cloud](../native-pdf/configure-base-location-cs.md) ou [Configurer l’emplacement de sortie de base pour les services On-prem](../native-pdf/configure-base-output-location.md) en fonction du service que vous utilisez. |
| Arguments de ligne de commande DITA-OT | Spécifiez les arguments supplémentaires que DITA-OT doit traiter lors de la génération de la sortie. <br><br> REMARQUE : à compter de la version 2502 de Experience Manager Guides, le paramètre `generate.copy.outer` n’est plus géré en interne. Cette modification signifie que si votre contenu HTML5 se trouve en dehors du répertoire map, vous devez définir explicitement le paramètre `-Dgenerate.copy.outer=3` dans le champ **Arguments de ligne de commande DITA-OT**. Cela permet de s’assurer que le contenu est correctement traité et inclus dans votre sortie. Pour plus d&#39;informations sur la gestion du contenu en dehors du répertoire map, consultez la [documentation DITA-OT](https://www.dita-ot.org/dev/parameters/generate-copy-outer#:~:text=The%20generate.,located%20outside%20the%20map%20directory/). |
| Nom du fichier | Indiquez le nom du fichier avec lequel vous souhaitez enregistrer la sortie HTML5.<br><br>**Remarque** : si vous ne fournissez pas de nom de fichier, le titre du plan DITA est utilisé pour générer le nom de fichier de sortie HTML5 final. Si le mappage n&#39;a pas de titre, le nom de fichier du mappage DITA est utilisé pour désigner la sortie HTML5 finale. Le nom du fichier est assaini à l’aide des règles configurées dans le système pour gérer tout caractère non valide. |
| Conditionner le filtrage/appliquer des conditions à l’aide d’ | Sélectionnez l’une des options suivantes :<br><br>* **Aucune appliquée** : sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur la sortie publiée.<br>* **Fichier DITAVAL** : Sélectionnez le ou les fichiers DITAVAL pour générer du contenu personnalisé. Vous pouvez sélectionner plusieurs fichiers DITAVAL à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin du fichier. Utilisez la croix près du nom du fichier pour le supprimer. Les fichiers DITAVAL sont évalués dans l&#39;ordre spécifié. Les conditions spécifiées dans le premier fichier sont donc prioritaires sur les conditions correspondantes spécifiées dans les fichiers ultérieurs. Vous pouvez conserver l’ordre des fichiers en ajoutant ou en supprimant des fichiers.<br>Vous pouvez également appliquer des indicateurs dans un fichier DITAVAL pour marquer visuellement le contenu. Chaque indicateur peut inclure une image et être mis en forme à l’aide d’une mise en forme telle que gras ou italique. Pour plus d’informations sur la personnalisation des styles de drapeau ou la résolution des conflits de mise en forme, voir [Utiliser l’éditeur DITAVAL](../user-guide/ditaval-editor.md). Si le fichier DITAVAL est déplacé vers un autre emplacement ou est supprimé, il n&#39;est pas automatiquement supprimé du tableau de bord de carte. Vous devez mettre à jour l’emplacement au cas où les fichiers seraient déplacés ou supprimés. Vous pouvez pointer sur le nom du fichier pour afficher le chemin d’accès dans le référentiel AEM où le fichier est stocké. Vous ne pouvez sélectionner que des fichiers DITAVAL et une erreur s&#39;affiche si vous avez sélectionné un autre type de fichier. FrameMaker Publishing Server ne prend pas en charge les fichiers DITAVAL multiples.<br>* **Paramètre prédéfini de condition** : sélectionnez un paramètre prédéfini de condition dans la liste déroulante pour appliquer une condition lors de la publication de la sortie. Cette option est visible si vous avez ajouté une condition présente dans l&#39;onglet Paramètres prédéfinis de condition de la console de mappage DITA. Pour en savoir plus sur les paramètres prédéfinis de condition, consultez [Utilisation des paramètres prédéfinis de condition](generate-output-use-condition-presets.md#id1825FL004PN).<br><br>**Remarque** : FrameMaker Publishing Server ne prend pas en charge les fichiers DITAVAL multiples. |
| Workflow de post-génération | Lorsque vous sélectionnez cette option, une nouvelle liste déroulante Workflow de post-génération s’affiche, contenant tous les workflows configurés dans AEM. Vous devez sélectionner un workflow à exécuter une fois le workflow de génération de sortie terminé.<br><br>**Remarque**:For pour plus d’informations sur la création d’un workflow de génération post-sortie personnalisé, consultez _Personnaliser le workflow de génération post-sortie_ dans Installation et configuration d’Adobe Experience Manager Guides as a Cloud Service. |
| Nom de la transformation | Indiquez le type de sortie que vous souhaitez générer. Cela est nécessaire si vous souhaitez générer une sortie à l’aide de votre propre plug-in personnalisé, qui est intégré au plug-in DITA-OT. Par exemple, si vous souhaitez générer une sortie XHTML, spécifiez `xhtml`. Pour obtenir la liste des transformations disponibles dans DITA-OT, consultez [Transformations DITA-OT (formats de sortie)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) dans le guide d&#39;utilisation OASIS DITA-OT. |
| Conserver les fichiers temporaires | Sélectionnez cette option pour conserver les fichiers temporaires générés par DITA-OT. Si vous rencontrez des erreurs lors de la génération de la sortie via DITA-OT, sélectionnez cette option pour conserver les fichiers temporaires. Vous pouvez ensuite utiliser ces fichiers pour résoudre les erreurs de génération de sortie.<br> <br> Après avoir généré la sortie, sélectionnez l’icône **Télécharger les fichiers temporaires** ![Télécharger les fichiers temporaires](images/download-temp-files-icon.svg) pour télécharger le dossier ZIP contenant les fichiers temporaires. Les fichiers téléchargés incluraient également `system_config.xml` fichier qui vous donne des informations sur l’URL de création, l’URL locale et l’URL de publication. Ces URL sont configurées dans les paramètres d’externalisation d’AEM et sont reflétées dans le fichier `system_config.xml`. <br><br> **Remarque** : si des propriétés de fichier sont ajoutées pendant la génération, les fichiers temporaires de sortie incluent également un fichier *metadata.xml* contenant ces propriétés. |
| Utiliser niveau de référence | Si vous avez créé une ligne de base pour le plan DITA sélectionné, sélectionnez cette option pour spécifier la version que vous souhaitez publier.<br><br>Affichage [Utilisation de la ligne de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) pour plus d’informations. |
| Aplatir la hiérarchie des fichiers | Sélectionnez cette option pour générer la sortie HTML5 dans une hiérarchie de dossiers plate. L’intégralité du contenu est publiée au format de sortie HTML5 dans une hiérarchie de fichiers plats et enregistrée dans un seul dossier. <br> Si vous désélectionnez cette option, la sortie est générée dans une hiérarchie de dossiers imbriquée et l’ensemble de la structure de dossiers est répliqué. |
| Propriétés du fichier | Sélectionnez les propriétés à traiter en tant que métadonnées. Ces propriétés sont définies à partir de la page Propriétés du fichier DITA map ou bookmap. Les propriétés que vous sélectionnez dans la liste déroulante s’affichent sous le champ **Propriétés du fichier**. Sélectionnez l’icône croisée en regard de la propriété pour la supprimer. <br><br>**Remarque** : vous pouvez également transmettre les métadonnées à la sortie à l’aide de la publication DITA-OT. Pour plus de détails, [Transmettez les métadonnées à la sortie à l’aide de DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |







**Rubrique parente :**&#x200B;[&#x200B; Présentation des paramètres prédéfinis de sortie](generate-output-understand-presets.md)
