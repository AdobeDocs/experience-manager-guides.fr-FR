---
title: PDF natif | Génération de sortie PDF
description: Découvrez comment utiliser la publication native de PDF, créer et générer un paramètre prédéfini de sortie PDF, télécharger des fichiers temporaires après avoir généré la sortie native de PDF et utiliser des variables de langue dans Adobe Experience Manager Guides.
exl-id: ec3d59b7-1dda-4fd1-848e-21d8a36ff5e4
feature: Publishing, Native PDF Output
role: User
source-git-commit: a6dafe6c634b872001a2b82d9d081b3e52a75b80
workflow-type: tm+mt
source-wordcount: '3293'
ht-degree: 1%

---

# Paramètre prédéfini de sortie PDF natif

Lors de la création de contenu, il devient essentiel de s’assurer que le contenu est optimisé pour l’affichage, la modification et l’impression. À l’aide de normes telles que les normes CSS3 W3C pour le style de contenu et les normes de médias paginés CSS pour les propriétés de définition de page telles que la taille, les marges, l’orientation, les sauts de page, les en-têtes, les pieds de page et la numérotation de page, vous pouvez définir l’affichage et la mise en page de votre document PDF en garantissant cohérence et convivialité. La fonction de publication Native PDF utilise ces normes pour générer un PDF.

Avec la publication native de PDF, vous pouvez utiliser des modèles prédéfinis pour assurer la cohérence de la disposition et de la structure du contenu, appliquer des feuilles de style pour modifier l’aspect de votre sortie, optimiser PDF, définir des repères d’imprimante, autoriser la prise en charge des lecteurs d’écran, définir la conformité de PDF, incorporer des polices, etc.

La génération d’un PDF à l’aide de la publication native de PDF présente deux aspects :

* Utilisation de modèles pour appliquer un style au contenu, définir des mises en page et divers paramètres afin d’affiner votre PDF. Les auteurs peuvent choisir d’utiliser ou de modifier les exemples de modèles fournis ou de créer des modèles personnalisés et définir les options de configuration avancées utilisées par les éditeurs et les développeurs.

* Créez ou configurez un paramètre prédéfini de sortie PDF pour contrôler les paramètres PDF. Une fois que vous avez créé un paramètre prédéfini de sortie PDF, vous pouvez générer le PDF.

## Création d’un paramètre prédéfini de sortie

Pour créer le paramètre prédéfini PDF à partir de la console de mappage, procédez comme suit :

1. [Ouvrez un fichier de mappage DITA dans la console Mappage](../user-guide/open-files-map-console.md).

   Vous pouvez également accéder au fichier de mappage à partir du widget **Fichiers récents** dans la section [Aperçu](../user-guide/intro-home-page.md#overview). Le fichier de mappage sélectionné s’ouvre dans la console Mappage .
1. Dans l’onglet **Paramètres prédéfinis de sortie**, sélectionnez l’icône + pour créer un paramètre prédéfini de sortie.
1. Sélectionnez **PDF** dans la liste déroulante Type de la boîte de dialogue **Nouveau paramètre prédéfini de sortie**.
1. Dans le champ **Nom**, attribuez un nom à ce paramètre prédéfini.
1. Dans le champ **Générer le PDF à l’aide de**, sélectionnez **Native-PDF**.
1. Sélectionnez l’option **Ajouter au profil du dossier actuel** pour créer un paramètre prédéfini de sortie dans le profil du dossier actuel. L’![icône de profil de dossier](./assets/global-preset-icon.svg) indique un paramètre prédéfini au niveau du profil de dossier.

   En savoir plus sur la [Gestion des paramètres prédéfinis de sortie de profil globaux et de dossier](../user-guide/web-editor-manage-output-presets.md).

1. Sélectionnez **Ajouter**.

   Le paramètre prédéfini de PDF est créé.

## Configuration du préréglage PDF natif

Une fois le paramètre prédéfini créé, configurez les paramètres prédéfinis de PDF natifs. Les options de configuration prédéfinies pour DITA-OT sont organisées sous les onglets **Général**, **Métadonnées**, **Disposition**, **Sécurité**, **Impression** et **Avancé**.

<img src="assets/preset-panel-new.png" alt="panneau des paramètres prédéfinis" width="800">

**Général**

Utilisez pour spécifier des paramètres de sortie de base, tels que le chemin de sortie, le nom de fichier PDF, etc.

| Configuration | Description |
| --- | --- |
| **Chemin de sortie** | Chemin d’accès dans le référentiel AEM où est stockée la sortie PDF. Assurez-vous que le chemin de sortie ne se trouve pas dans le dossier du projet. Le chemin de sortie est défini via la variable `${base_output_path}`, qui est configurée par l’administrateur. Pour configurer le chemin de sortie, affichez [Configurer l’emplacement de sortie de base pour les services cloud](../native-pdf/configure-base-location-cs.md) ou [Configurer l’emplacement de sortie de base pour les services On-prem](../native-pdf/configure-base-output-location.md) en fonction du service que vous utilisez. <br>Vous pouvez également utiliser les variables prêtes à l’emploi suivantes pour définir le chemin de sortie. Vous pouvez utiliser une ou plusieurs variables pour définir cette option. <br> `${map_filename}` : utilise le nom des fichiers de plan DITA pour créer le chemin de destination. <br> `${map_title}` : utilise le titre du plan DITA pour créer le chemin de destination. <br>`${preset_name}` : utilise le nom du paramètre prédéfini de sortie pour créer le chemin de destination. <br> `${language_code}` : utilise le code de langue dans lequel se trouve le fichier de mappage pour créer le chemin de destination. <br> `${map_parentpath}` : utilise le chemin d’accès complet du fichier de mappage pour créer le chemin d’accès de destination.  <br>`${path_after_langfolder}` : utilise le chemin d’accès du fichier de mappage situé après le dossier de langue pour créer le chemin d’accès de destination. |
| **Fichier PDF** | Spécifiez un nom de fichier pour enregistrer le PDF. Par défaut, le nom de fichier PDF ajoute le nom du plan DITA ainsi que le nom du paramètre prédéfini. Par exemple, ditamap est &#39;TestMap&#39; et le nom du paramètre prédéfini est &#39;preset1&#39;. Le nom par défaut du fichier pdf sera alors &#39;TestMap_preset1.pdf&#39;. <br>Vous pouvez également utiliser les variables prêtes à l’emploi suivantes pour définir le fichier PDF. Vous pouvez utiliser une ou plusieurs variables pour définir cette option. <br>`${map_filename}`<br>`${map_title}`<br>`${preset_name}` <br> `${language_code}`. |
| **Appliquer des conditions à l’aide de** | Pour le contenu conditionné, choisissez l’une des options suivantes pour générer une sortie PDF en fonction de ces conditions : <br><ul> <li> **Aucune application** sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur le mappage et le contenu source. <br><li> **Fichier DITAVAL** Sélectionnez un fichier DITAVAL pour générer du contenu conditionnel. Vous pouvez sélectionner plusieurs fichiers DITAVAL à l’aide de la boîte de dialogue de navigation ou en saisissant manuellement le chemin d’accès au fichier. Pour supprimer un fichier sélectionné, cliquez sur la croix en regard de son nom. Si un fichier non valide est sélectionné, un message d&#39;erreur s&#39;affiche indiquant **Un fichier DITAVAL non valide est sélectionné**. <br> <br>Chaque fichier DITAVAL peut contenir un éventail de propriétés, telles que des conditions de filtrage et des styles de marquage. Les indicateurs vous permettent de marquer visuellement le contenu à l’aide d’indicateurs de début et de fin, qui peuvent inclure des images ou une mise en forme de texte telle que le gras ou l’italique. En cas de chevauchement de conditions ou de conflits de style, vous pouvez définir une couleur d’arrière-plan à l’aide des paramètres de conflit de style. Pour plus d&#39;informations, voir [Utiliser l&#39;éditeur DITAVAL](../user-guide/ditaval-editor.md).<br><li> **Paramètre prédéfini de condition** Sélectionnez un paramètre prédéfini de condition dans la liste déroulante pour appliquer une condition lors de la publication de la sortie. Cette option est visible si vous avez ajouté une condition pour le fichier de plan DITA. Les paramètres conditionnels sont disponibles dans l&#39;onglet Paramètres prédéfinis de condition de la console Plan DITA. Pour en savoir plus sur les paramètres prédéfinis de condition, consultez la section [Utilisation des paramètres prédéfinis de condition](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-condition-presets.html). <br> </ul> |
| **Utiliser niveau de référence** | Si vous avez créé une ligne de base pour le plan DITA sélectionné, sélectionnez cette option pour spécifier la version que vous souhaitez publier. Voir [Utilisation de la ligne de base](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-baseline-for-publishing.html) pour plus d’informations. |
| **Créer un PDF avec Barre de modification entre les versions publiées** | Utilisez les options suivantes pour créer un PDF présentant les différences de contenu entre deux versions à l’aide des barres de modification :   <br><ul><li> **Ligne de base de la version précédente** Sélectionnez la version de ligne de base à comparer à la version actuelle ou à une autre ligne de base. Une barre de modification s’affiche dans le PDF pour indiquer le contenu modifié. Une barre de modification est une ligne verticale qui identifie visuellement le contenu nouveau ou révisé. La barre de modification s’affiche à gauche du contenu qui a été inséré, modifié ou supprimé. <br> **Remarque** : Si vous sélectionnez **Utiliser niveau de référence** et choisissez un niveau de référence à publier, la comparaison est effectuée entre les deux versions de niveau de référence sélectionnées. Par exemple, si vous choisissez la version de référence 1.3 sous **Utiliser la référence** et la version 1.1 sous **Ligne de base de la version précédente**, la comparaison sera effectuée entre la version de référence 1.1 et la version de référence 1.3. <br><li> **Afficher le texte ajouté** Sélectionnez cette option pour afficher le texte inséré en vert et souligné. Cette option est sélectionnée par défaut. <br> <li> **Afficher le texte supprimé** Sélectionnez cette option pour afficher le texte supprimé en rouge et barré. Cette option est sélectionnée par défaut. <br>**Remarque** vous pouvez également personnaliser la mise en forme de la barre de modification, du contenu inséré ou du contenu supprimé à l’aide de la feuille de style.<br></ul> |
| **Langue** | Sélectionnez la langue dans laquelle vous souhaitez que la sortie soit traduite. <br> **Remarque** : les textes de référence croisée tels que « Voir sur le chapitre » ou « Voir sur la page » sont contrôlés par une variable de langue. La variable utilise la langue définie dans la rubrique via l’attribut `xml:lang`. Si aucune langue n’est spécifiée, la langue prédéfinie est utilisée. Si les deux sont manquants, la valeur par défaut est l’anglais (en_US). |

| **Workflow de post-génération** |Sélectionnez cette option pour afficher une liste déroulante contenant tous les workflows configurés dans AEM. Vous pouvez sélectionner le workflow à exécuter une fois le workflow de génération de PDF terminé.|

**Métadonnées**

Les métadonnées sont la description ou la définition de votre contenu. Les métadonnées facilitent la gestion de contenu et la recherche de fichiers sur Internet.

Utilisez l’onglet Métadonnées pour définir les champs de métadonnées tels que le nom de l’auteur, le titre du document, les mots-clés, les informations de copyright et d’autres champs de données pour la sortie PDF. Vous pouvez également ajouter des métadonnées personnalisées pour votre sortie PDF.

Ces métadonnées sont mappées aux métadonnées dans l’onglet **Description** de la **Propriétés du document** du PDF de sortie.



<img src="assets/pdf-metadata.png" alt="onglet métadonnées" width="600">

Dans les paramètres prédéfinis de sortie, sélectionnez **PDF** > **Native-PDF** > **Métadonnées** pour ajouter et personnaliser des options de métadonnées.
* **Utiliser les métadonnées ajoutées dans topicmeta**

  Cette option est sélectionnée par défaut. Vous pouvez utiliser les métadonnées que vous avez ajoutées dans l&#39;élément topicmeta du plan DITA pour renseigner les champs de métadonnées de la sortie PDF.

* **Fournir un fichier XMP**

  Vous pouvez également remplir directement les champs de métadonnées en important le fichier [XMP](https://www.adobe.com/products/xmp.html) (Extensible Metadata Platform). Vous pouvez télécharger un exemple de fichier XMP ici.

[Téléchargement](assets/SampleXMP.xmp)

  Vous pouvez également générer un fichier XMP à l’aide d’Adobe Acrobat.
   1. Sélectionnez **Fichier** > **Propriétés** dans Acrobat.
   1. Sous **Description**, sélectionnez **Métadonnées supplémentaires**.
   1. Dans le panneau de gauche, sélectionnez **Avancé**.
   1. Sélectionnez **Enregistrer**.

  Le fichier XMP est enregistré sur l’appareil.

* **Fournissez des noms et des valeurs de métadonnées**

   1. Ajoutez un nom en le sélectionnant dans la liste déroulante ou ajoutez des métadonnées personnalisées en saisissant directement dans le champ du nom.
   1. Saisissez la valeur pour les métadonnées et sélectionnez l’icône « + ».
Les métadonnées sont ajoutées à la liste des métadonnées du PDF.

Vous pouvez également utiliser des variables pour définir les valeurs des métadonnées.  Vous pouvez utiliser les métadonnées définies pour le fichier DITA map ou bookmap en tant que variables. Les métadonnées se trouvent sous le nœud `/jcr:content/metadata` du fichier de plan DITA ou de bookmap.
Lorsque vous utilisez une variable, sa valeur est sélectionnée dans les propriétés de métadonnées.

Pour utiliser une variable, vous devez la définir au format `${<variable>}`.

Par exemple, une des propriétés de métadonnées définies dans le nœud /`jcr:content/metadata` est
`dc:title`. Vous pouvez indiquer `${dc:title}` et la valeur du titre est utilisée dans la sortie finale.

Vous pouvez utiliser une seule variable ou une combinaison de variables pour définir les métadonnées. Par exemple, `${dc:title} ${dc:docstate}`. Vous pouvez également utiliser la combinaison d’une variable et d’une chaîne.  Par exemple, `View ${dc:title} in ${dc:language}`.

Utilisez des variables de langue pour définir la valeur localisée des propriétés de métadonnées. Selon la langue choisie, la valeur localisée est automatiquement sélectionnée dans la sortie PDF. Par exemple, vous pouvez imprimer « Author » comme valeur de métadonnées en anglais et « Autorin » en allemand.

Format : `${lng:<variable name>}`. Par exemple, `${lng:author-label}` où `author-label` est une variable de langue.

Survoler <img src="./assets/info-details.svg" alt= "icône info" width="25"> près de l’option pour en savoir plus.


**Disposition**

Utilisez pour définir les mises en page et spécifier les options d’affichage des pages pour la sortie PDF, telles que l’affichage de la page et définir les niveaux de zoom.

| Configuration | Description |
| --- | --- |
| **Modèle PDF** | Les modèles PDF fournissent une structure claire pour définir les mises en page, le style du contenu et l’application de divers paramètres à votre sortie PDF. Faites votre choix parmi les options de la liste déroulante Modèle PDF . <br> Vous pouvez également sélectionner **Parcourir le modèle** <img src="./assets/browse-templates-icon.svg"  alt= "icône parcourir les modèles" width="25"> de choisir un modèle. Dans la boîte de dialogue **Sélectionner le modèle PDF**, vous pouvez également prévisualiser la miniature et afficher le titre et la description du modèle sélectionné. |
| **Affichage de la page** | Utilisez l’option Affichage de la page pour l’affichage de la page qui indique l’affichage du PDF à l’ouverture. Faites votre choix dans les options de la liste déroulante Affichage de la page pour choisir un affichage préféré. <br><ul><li> **Par défaut** s’affiche conformément au paramètre par défaut de la visionneuse PDF sur l’ordinateur d’un utilisateur.  <br> <li> **Une seule page vue** affiche une page à la fois.   <br> <li> **Défilement d’une seule page** affiche une seule page dans une colonne verticale continue.  <br> <li> **Deux pages vues** affiche deux pages côte à côte à la fois. .<br> <li> **Défilement de deux pages** affiche deux pages côte à côte avec défilement continu. </ul> |
| **Zoom** | Sélectionnez cette option pour redimensionner la page vue qui affiche le PDF à son ouverture.  <br><ul><li> **Par défaut** s’affiche selon le paramètre par défaut de la visionneuse PDF sur l’ordinateur d’un utilisateur ou d’une utilisatrice    <br> <li> **100 %** fait apparaître la page dans sa taille réelle.     <br> <li> **Ajuster la page** Ajuste la largeur et la hauteur de la page dans le volet du document.   .<br> <li> **Ajuster la largeur de page** Permet de faire en sorte que la largeur de la page soit égale à celle du volet du document.  <br> <li> **Ajuster la hauteur de la page** Fait en sorte que la hauteur de la page remplisse la hauteur du panneau de visualisation. </ul> |

**Sécurité**

Protégez votre PDF en ajoutant des restrictions pour l’ouverture et la lecture du fichier. Utilisez les options ci-dessous pour éviter tout accès non autorisé.

| Configuration | Description |
| --- | --- |
| **Définir le mot de passe pour ouvrir le document** | Sélectionnez pour ajouter un mot de passe sécurisé pour afficher votre fichier PDF. Indiquez un mot de passe dans le champ **Mot de passe utilisateur**. Les utilisateurs ne peuvent ouvrir le PDF qu’en saisissant le mot de passe fourni dans ce champ. |
| **Définir les restrictions du document** | Sélectionnez cette option pour restreindre la façon dont les utilisateurs peuvent interagir avec votre PDF. Indiquez un mot de passe dans le champ **Mot de passe du propriétaire** pour que les paramètres de restriction ci-dessous fonctionnent.  <br><ul><li> **Impression** sélectionnez cette option pour permettre à l’utilisateur d’imprimer le PDF. <br> <li> **Impression de qualité Brouillon** sélectionnez cette option pour permettre à l’utilisateur d’imprimer le PDF dans une résolution inférieure.  <br> <li> **Copie de contenu** sélectionnez cette option pour permettre à l’utilisateur de copier du contenu du PDF.   <br> <li> **Annotations** sélectionnez cette option pour permettre à l’utilisateur d’ajouter une note ou un commentaire dans le PDF. <br> <li> **Modifications du contenu** sélectionnez cette option pour permettre à l’utilisateur de modifier le contenu dans le PDF. <br> <li> **Copie de contenu pour l’accessibilité** Sélectionnez cette option pour permettre aux lecteurs d’écran de lire et de parcourir le contenu dans PDF. <br>  **Assemblage de document** sélectionnez cette option pour permettre aux utilisateurs d&#39;insérer des pages dans le PDF. <br> **Remarque** : les utilisateurs doivent saisir le mot de passe du propriétaire pour modifier les restrictions sous Fichier > Propriétés dans Adobe Acrobat. |

**Imprimer**

>[!NOTE]
>
> À partir de la version Experience Manager Guides 5.0/2025.02.0, la section Impression fait désormais partie du **paramètre prédéfini de sortie PDF natif**. Pour les modèles existants avec des paramètres d’impression enregistrés, les données d’impression restent intactes, mais n’apparaissent plus dans l’interface utilisateur ou ne s’appliquent plus lors de la sortie. Pour continuer à utiliser ces paramètres, vous devez les reconfigurer dans le paramètre prédéfini de sortie PDF natif.

Configurez les paramètres de production d’impression pour attribuer des repères d’impression, sélectionner des modèles de couleurs et spécifier les propriétés liées à l’impression de votre sortie PDF.

* **Repères d’impression** : lorsque vous préparez un document pour l’impression, des repères d’impression sont ajoutés aux limites de la page pour faciliter l’alignement, le rognage et la sélection des couleurs lors de l’impression. En sélectionnant un repère d’imprimante, la limite de page est étendue pour accueillir le repère, qui est ajusté lors de l’impression. Vous pouvez choisir d’afficher les repères d’impression suivants dans votre sortie PDF :
   * **Rogner les marques** : sélectionnez cette option pour placer une marque à chaque coin de la zone de rognage afin d’indiquer où le papier doit être rogné après l’impression.
   * **Repères de fond perdu** : sélectionnez cette option pour placer un repère à chaque coin de la zone de fond perdu afin d’indiquer la zone de rognage de l’image étendue.
   * **Marques d’enregistrement** : sélectionnez cette option pour placer une marque en dehors de la zone de recadrage afin d’aligner les différentes séparations dans un document en couleur.
   * **Barres de couleurs** : sélectionnez cette option pour ajouter une bande de couleurs en dehors de la zone de rognage afin de conserver la cohérence des couleurs et d’ajuster la densité d’encre lors de l’impression.

  Définissez les dimensions des repères d’impression sélectionnés à l’aide des options **Largeur de ligne**, **Couleur de ligne** et **Largeur de zone de fond perdu**.

* **Taille du cadre du support** : il s’agit de la taille globale de la page, y compris la zone étendue occupée par les repères d’impression. Utilisez l’option de liste déroulante pour sélectionner le format de page de votre sortie PDF ou créer votre propre format personnalisé.

* **Espace colorimétrique** : vous avez la possibilité de choisir parmi les espaces colorimétriques RGB ou CMJN pour imprimer votre document PDF. Choisissez RGB pour afficher le PDF généré numériquement et CMJN pour l’impression physique. Les couleurs définies dans le document sont converties dans l’espace colorimétrique choisi.

* **Profil ICC** : vous pouvez gérer la précision des couleurs sur l’ensemble des appareils en spécifiant un profil ICC. Cela garantit un rendu des couleurs cohérent dans la sortie imprimée.

Pour configurer ce paramètre, spécifiez le chemin d’accès au fichier de profil ICC sur votre serveur et indiquez le nom du profil ICC pour une identification facile. Si le profil ICC est stocké en ligne, vous pouvez également fournir son URL au lieu du chemin d’accès au fichier.

>[!NOTE]
>
> Un profil colorimétrique ICC est nécessaire pour la création de PDF/A si vous utilisez l’espace colorimétrique CMJN.

<!--For more information on applying these print settings, see *Printing preferences*.-->

**Avancé**

Utilisez les options suivantes pour spécifier des paramètres avancés pour fusionner des PDF, utiliser la compression, sélectionner la norme de conformité, etc.

| Configuration | Description |
| --- | --- |
| **Créer un PDF accessible (balisé)** | Sélectionnez cette option pour générer un PDF avec des balises. Un PDF balisé permet aux lecteurs d’écran de lire et de parcourir plus facilement le contenu, les liens hypertexte, les signets, etc. Par exemple, si un tableau est balisé, le lecteur d’écran saura qu’il lit le tableau et pas seulement les lignes et le texte. |
| **Fusion des PDF inclus dans la table des matières** | Sélectionnez cette option pour fusionner les fichiers PDF existants dans votre sortie en les ajoutant à votre plan DITA sous forme de fichier de ressources. Les fichiers PDF seront insérés à l’emplacement représenté sur la carte et les pages seront incrémentées en conséquence. |
| **Incorporer les polices utilisées** | Sélectionnez cette option lors de l’utilisation de polices qui ne peuvent pas être installées sur l’ordinateur de l’utilisateur final. Lorsque cette option est sélectionnée, les polices utilisées sont incorporées dans le PDF, ce qui permet à l’utilisateur d’afficher le PDF comme prévu, même si les polices ne sont pas installées sur son ordinateur. <br> **Remarque** : une police ne peut être incorporée que si elle contient un paramètre défini par le fournisseur de la police qui permet son incorporation. Assurez-vous de disposer du paramètre ou de la licence requis avant d’incorporer une police. |
| **Utiliser la césure automatique** | Lorsque la coupure de mots automatique est activée, les mots à l&#39;extrémité des lignes sont rompus aux endroits grammaticalement corrects avec un trait d&#39;union. |
| **Activer JavaScript** | Activez cette option si vous disposez d’un code JavaScript que vous souhaitez utiliser pour transformer votre contenu de manière dynamique avant de générer un PDF. |
| **Incorporer des fichiers multimédias** | Sélectionnez cette option pour inclure du contenu audio, vidéo et interactif dans le PDF. |
| **Utiliser la compression complète pour optimiser la taille du PDF** | Sélectionnez cette option si vous souhaitez compresser/réduire la taille d’un PDF volumineux. N’oubliez pas que la compression du PDF peut réduire la qualité du fichier. |
| **Utiliser la compression d’image pour optimiser la taille du PDF** | Sélectionnez cette option si vous souhaitez compresser/réduire la taille des images utilisées, dans votre PDF. N’oubliez pas que la compression d’une image peut en réduire la qualité. |
| **Utiliser une résolution personnalisée (pixels par pouce)** | Il s’agit de la résolution d’affichage de la page en pixels par pouce. Saisissez la valeur souhaitée dans le champ qui s’affiche lorsque cette option est sélectionnée. La valeur par défaut est de 96 pixels par pouce. Définissez une valeur plus élevée pour adapter davantage de contenu en pouces, et vice versa, si vous définissez une valeur plus faible. |
| **Afficher le filigrane** | Sélectionnez cette option pour superposer un filigrane dans votre sortie. Vous pouvez saisir une nouvelle chaîne de texte dans la zone de texte en respectant la casse souhaitée. <br><br>Utilisez du texte statique ou des variables de langue pour publier la version localisée du filigrane.  Selon la langue choisie, la valeur localisée est automatiquement sélectionnée dans la sortie PDF. Par exemple, vous pouvez imprimer « Publisher » sous forme de filigrane en anglais et « Auteure » en français.  Format <br> : `${lng:<variable name>}`. Par exemple, `$ {lng:publisher-label}` où `publisher-label` est une variable de langue. <br> pointer <img src="./assets/info-details.svg" alt= "icône info" width="25"> près de l’option pour en savoir plus. |
| **Activer les équations de MathML** | Sélectionnez cette option pour effectuer le rendu des équations MathML présentes dans votre contenu. Les équations seront ignorées par défaut. |
| **Créer un formulaire PDF interactif** | Sélectionnez cette option si vous souhaitez inclure des champs de formulaire PDF interactifs et personnalisables pour une entrée utilisateur améliorée dans les sorties PDF générées. |
| **Inclure le suivi des modifications** | Sélectionnez cette option si vous souhaitez inclure les modifications suivies dans le PDF généré pour faciliter la révision et la comparaison. |
| **Conserver les fichiers temporaires** | Sélectionnez cette option si vous souhaitez conserver les fichiers HTML intermédiaires créés lors de la génération de la sortie Native PDF. Vous pouvez ensuite télécharger les fichiers temporaires après avoir généré la sortie. Les fichiers téléchargés incluraient également `system_config.xml` fichier qui vous donne des informations sur l’URL de création, l’URL locale et l’URL de publication. Ces URL sont configurées dans les paramètres d’externalisation d’AEM et sont reflétées dans le fichier `system_config.xml`. |
| **Conformité de PDF** | Il s’agit de la norme à laquelle vous avez l’intention d’enregistrer votre PDF pour vous assurer qu’elle est conforme. Faites votre choix dans la liste déroulante parmi les normes PDF disponibles. Pour plus d’informations sur les normes prises en charge, voir [À propos des normes PDF](https://helpx.adobe.com/fr/acrobat/using/pdf-conversion-settings.html#about_pdf_x_pdf_e_and_pdf_a_standards). |
| **Propriétés du fichier** | Sélectionnez les métadonnées que vous souhaitez transmettre à la publication native de PDF. La liste déroulante répertorie les propriétés personnalisées et par défaut. Par exemple, `dc:description`, `dc:language`, `dc:title` et `docstate` sont les propriétés par défaut, tandis que vous pouvez utiliser `author` comme propriété personnalisée. Les propriétés de métadonnées sélectionnées sont transmises au fichier PDF généré à l’aide de PDF natif. <br> Ces propriétés sont sélectionnées à partir du fichier `metadataList` disponible à l’adresse : `/libs/fmdita/config/metadataList`. <br>Ce fichier peut être recouvert à l’adresse : `/apps/fmdita/config/metadataList`. |



<!--------------


### Additional notes for PDF output

**Download temporary files after generating the Native PDF output**

If you select the **Download temporary files** option in the Advanced settings, you can also download the interim HTML files created while generating the Native PDF output. Once you've generated the output, you can download the temporary files using the **Download temporary files** ![download temporary files](assets/native-pdf-download-temporary-files-icon.svg)icon on the top bar. This feature helps you view your interim HTML styles and layouts and helps you correct or change your CSS styles according to your requirements.


>[!NOTE]
>
> The **Download temporary files**  ![download temporary files](assets/native-pdf-download-temporary-files-icon.svg) icon appears only if you have generated the last PDF output using the preset wherein you have selected the option in the **Advanced** tab. 


**Use language variables**

AEM Guides also provides the support for language variables. Select **Language Variables** <img src="assets/language-variables.svg" width="25">  in the left panel to define a localized version of the out-of-the-box labels like Note, Caution, and Warning or static text in the PDF output. For more details, view [Support for language variables](../native-pdf/native-pdf-language-variables.md).


**Support for Markdown documents**

Experience Manager Guides also provides support for your Markdown documents.  Markdown files are easy to author and also provide a variety of formatting options. Learn how to [author Markdown documents from the Editor](../user-guide/web-editor-markdown-topic.md). 

You can add the Markdown topics to your DITA map and generate the PDF output using the Native PDF output presets.  Learn how to configure or [create a PDF output preset](#create-a-pdf-output-preset-create-output-preset). 

--------------->