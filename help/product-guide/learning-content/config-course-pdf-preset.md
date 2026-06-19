---
title: Configuration des paramètres prédéfinis de PDF
description: Configurez le paramètre prédéfini PDF dans la formation et l’apprentissage du produit.
feature: Authoring
role: User
exl-id: 52bc8f90-e4ae-4e83-bb1c-9d152fa9bb65
TQID: https://experienceleague.adobe.com/NX3LuUjSmQKtirXc1iaJVZziVIvuDqANXwqPTi-1LIo
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: f7c0b10f032c2584fb6e951da898faaeb4ca7aaf
workflow-type: tm+mt
source-wordcount: 3002
ht-degree: 1%

---

# Configuration du paramètre prédéfini de sortie PDF

Une fois le paramètre prédéfini créé, configurez ses paramètres. Les options de configuration des paramètres prédéfinis sont organisées sous les onglets Général, Métadonnées, Disposition, Sécurité, Impression et Avancé.

**Général**

Utilisez pour spécifier des paramètres de sortie de base, tels que le chemin de sortie, le nom de fichier PDF, etc.

| Configuration | Description |
| --- | --- |
| **Chemin de sortie** | Chemin d’accès dans le référentiel AEM où est stockée la sortie PDF. Assurez-vous que le chemin de sortie ne se trouve pas dans le dossier du projet. Le chemin de sortie est défini via la variable `${base_output_path}`, qui est configurée par l’administrateur. Pour configurer le chemin de sortie, affichez [Configurer l’emplacement de sortie de base pour les services cloud](../native-pdf/configure-base-location-cs.md) ou [Configurer l’emplacement de sortie de base pour les services On-prem](../native-pdf/configure-base-output-location.md) en fonction du service que vous utilisez. <br>Vous pouvez également utiliser les variables prêtes à l’emploi suivantes pour définir le chemin de sortie. Vous pouvez utiliser une ou plusieurs variables pour définir cette option. <br> `${map_filename}` : utilise le nom des fichiers de plan DITA pour créer le chemin de destination. <br> `${map_title}` : utilise le titre du plan DITA pour créer le chemin de destination. <br>`${preset_name}` : utilise le nom du paramètre prédéfini de sortie pour créer le chemin de destination. <br> `${language_code}` : utilise le code de langue dans lequel se trouve le fichier de mappage pour créer le chemin de destination. <br> `${map_parentpath}` : utilise le chemin d’accès complet du fichier de mappage pour créer le chemin d’accès de destination.  <br>`${path_after_langfolder}` : utilise le chemin d’accès du fichier de mappage situé après le dossier de langue pour créer le chemin d’accès de destination. |
| **Fichier** | Spécifiez un nom de fichier pour enregistrer le PDF. Par défaut, le nom de fichier PDF ajoute le nom du plan DITA ainsi que le nom du paramètre prédéfini. Par exemple, ditamap est &#39;TestMap&#39; et le nom du paramètre prédéfini est &#39;preset1&#39;. Le nom par défaut du fichier pdf sera alors &#39;TestMap_preset1.pdf&#39;. <br>Vous pouvez également utiliser les variables prêtes à l’emploi suivantes pour définir le fichier PDF. Vous pouvez utiliser une ou plusieurs variables pour définir cette option. <br>`${map_filename}`<br>`${map_title}`<br>`${preset_name}` <br> `${language_code}`. |
| **Appliquer des conditions à l’aide de** | Pour le contenu conditionné, choisissez l’une des options suivantes pour générer une sortie PDF en fonction de ces conditions : <br><ul> <li> **Aucune application** sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur le mappage et le contenu source. <br><li> **Fichier DITAVAL** Sélectionnez un fichier DITAVAL pour générer du contenu conditionnel. Vous pouvez sélectionner plusieurs fichiers DITAVAL à l’aide de la boîte de dialogue de navigation ou en saisissant manuellement le chemin d’accès au fichier. Pour supprimer un fichier sélectionné, cliquez sur la croix en regard de son nom. Si un fichier non valide est sélectionné, un message d&#39;erreur s&#39;affiche indiquant **Un fichier DITAVAL non valide est sélectionné**. <br> <br>Chaque fichier DITAVAL peut contenir un éventail de propriétés, telles que des conditions de filtrage et des styles de marquage. Les indicateurs vous permettent de marquer visuellement le contenu à l’aide d’indicateurs de début et de fin, qui peuvent inclure des images ou une mise en forme de texte telle que le gras ou l’italique. En cas de chevauchement de conditions ou de conflits de style, vous pouvez définir une couleur d’arrière-plan à l’aide des paramètres de conflit de style. Pour plus d&#39;informations, voir [Utiliser l&#39;éditeur DITAVAL](../user-guide/ditaval-editor.md).<br><li> **Paramètre prédéfini de condition** Sélectionnez un paramètre prédéfini de condition dans la liste déroulante pour appliquer une condition lors de la publication de la sortie. Cette option est visible si vous avez ajouté une condition pour le fichier de plan DITA. Les paramètres conditionnels sont disponibles dans l&#39;onglet Paramètres prédéfinis de condition de la console Plan DITA. Pour en savoir plus sur les paramètres prédéfinis de condition, consultez la section [Utilisation des paramètres prédéfinis de condition](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-condition-presets.html). <br> </ul> |
| **Utiliser niveau de référence** | Si vous avez créé une ligne de base pour le plan DITA sélectionné, sélectionnez cette option pour spécifier la version que vous souhaitez publier. Voir [Utilisation de la ligne de base](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-baseline-for-publishing.html) pour plus d’informations. |
| **Créer un PDF avec Barre de modification entre les versions publiées** | Utilisez les options suivantes pour créer un PDF présentant les différences de contenu entre deux versions à l’aide des barres de modification : <br><ul><li> **Ligne de base de la version précédente** Sélectionnez la version de ligne de base à comparer à la version actuelle ou à une autre ligne de base. Une barre de modification s’affiche dans le PDF pour indiquer le contenu modifié. Une barre de modification est une ligne verticale qui identifie visuellement le contenu nouveau ou révisé. La barre de modification s’affiche à gauche du contenu qui a été inséré, modifié ou supprimé. <br> **Remarque** : Si vous sélectionnez **Utiliser niveau de référence** et choisissez un niveau de référence à publier, la comparaison est effectuée entre les deux versions de niveau de référence sélectionnées. Par exemple, si vous choisissez la version de référence 1.3 sous **Utiliser la référence** et la version 1.1 sous **Ligne de base de la version précédente**, la comparaison sera effectuée entre la version de référence 1.1 et la version de référence 1.3. <br><li> **Afficher le texte ajouté** Sélectionnez cette option pour afficher le texte inséré en vert et souligné. Cette option est sélectionnée par défaut. <br> <li> **Afficher le texte supprimé** Sélectionnez cette option pour afficher le texte supprimé en rouge et barré. Cette option est sélectionnée par défaut. <br>**Remarque** vous pouvez également personnaliser la mise en forme de la barre de modification, du contenu inséré ou du contenu supprimé à l’aide de la feuille de style.<br></ul> |
| **Langue** | Sélectionnez la langue dans laquelle vous souhaitez que la sortie soit traduite. <br> **Remarque** : les textes de référence croisée tels que « Voir sur le chapitre » ou « Voir sur la page » sont contrôlés par une variable de langue. La variable utilise la langue définie dans la rubrique via l’attribut `xml:lang`. Si aucune langue n’est spécifiée, la langue prédéfinie est utilisée. Si les deux sont manquants, la valeur par défaut est l’anglais (en_US). |
| **Arguments de ligne de commande DITA-OT** | Lorsque vous activez **Activer le prétraitement DITA-OT**, le champ **Arguments de ligne de commande DITA-OT** devient disponible. Ici, vous pouvez spécifier les arguments supplémentaires que DITA-OT doit traiter lors de la génération de la sortie. Pour plus d&#39;informations sur les arguments de ligne de commande pris en charge dans DITA-OT, consultez la [documentation DITA-OT](https://www.dita-ot.org/).<br>**REMARQUE :** les liens connexes définis dans les tables de relation DITA (`<reltable>`) ne sont pas inclus par défaut dans la sortie Native PDF. Utilisez ce champ pour transmettre les arguments DITA-OT requis et inclure ces liens connexes dans la sortie Native PDF. |
| **Workflow de post-génération** | Sélectionnez cette option pour afficher une liste déroulante contenant tous les workflows configurés dans AEM. Vous pouvez sélectionner le workflow à exécuter une fois le workflow de génération de PDF terminé. |

**Métadonnées**

Les métadonnées sont la description ou la définition de votre contenu. Les métadonnées facilitent la gestion de contenu et la recherche de fichiers sur Internet.

Utilisez l’onglet Métadonnées pour définir les champs de métadonnées tels que le nom de l’auteur, le titre du document, les mots-clés, les informations de copyright et d’autres champs de données pour la sortie PDF. Vous pouvez également ajouter des métadonnées personnalisées pour votre sortie PDF.

Ces métadonnées sont mappées aux métadonnées dans l’onglet **Description** de la **Propriétés du document** du PDF de sortie.

Dans les paramètres prédéfinis de sortie, sélectionnez **&#x200B;**&#x200B;> **Native-PDF** > **Métadonnées** pour ajouter et personnaliser des options de métadonnées.

* **Utiliser les métadonnées ajoutées dans topicmeta**

  Cette option est sélectionnée par défaut. Vous pouvez utiliser les métadonnées que vous avez ajoutées dans l&#39;élément topicmeta du plan DITA pour renseigner les champs de métadonnées de la sortie PDF.

* **Fournir un fichier XMP**

  Vous pouvez également remplir directement les champs de métadonnées en important le fichier [&#128279;](https://www.adobe.com/fr/products/xmp.html) (Extensible Metadata Platform). Vous pouvez télécharger un exemple de fichier XMP ici.

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

**Disposition**

Utilisez pour définir les mises en page et spécifier les options d’affichage des pages pour la sortie PDF, telles que l’affichage de la page et définir les niveaux de zoom.

| Configuration | Description |
| --- | --- |
| **Modèle** | Les modèles PDF fournissent une structure claire pour définir les mises en page, le style du contenu et l’application de divers paramètres à votre sortie PDF. Faites votre choix parmi les options de la liste déroulante Modèle PDF . <br> Vous pouvez également sélectionner **Parcourir le modèle** <img src="./assets/browse-templates-icon.svg"  alt= "icône parcourir les modèles" width="25"> de choisir un modèle. Dans la boîte de dialogue **Sélectionner le modèle PDF**, vous pouvez également prévisualiser la miniature et afficher le titre et la description du modèle sélectionné. |
| **Affichage de la page** | Utilisez l’option Affichage de la page pour l’affichage de la page qui indique l’affichage du PDF à l’ouverture. Faites votre choix dans les options de la liste déroulante Affichage de la page pour choisir un affichage préféré. <br><ul><li> **Par défaut** s’affiche conformément au paramètre par défaut de la visionneuse PDF sur l’ordinateur d’un utilisateur.  <br> <li> **Une seule page vue** affiche une page à la fois.   <br> <li> **Défilement d’une seule page** affiche une seule page dans une colonne verticale continue.  <br> <li> **Deux pages vues** affiche deux pages côte à côte à la fois. .<br> <li> **Défilement de deux pages** affiche deux pages côte à côte avec défilement continu. </ul> |
| **Zoom** | Sélectionnez cette option pour redimensionner la page vue qui affiche le PDF à son ouverture.  <br><ul><li> **Par défaut** s’affiche selon le paramètre par défaut de la visionneuse PDF sur l’ordinateur d’un <br> utilisateur <li> **100 %** fait apparaître la page dans sa taille réelle.     <br> <li> **Ajuster la page** Ajuste la largeur et la hauteur de la page dans le volet du document.   .<br> <li> **Ajuster la largeur de page** Permet de faire en sorte que la largeur de la page soit égale à celle du volet du document.  <br> <li> **Ajuster la hauteur de la page** Fait en sorte que la hauteur de la page remplisse la hauteur du panneau de visualisation. </ul> |

**Sécurité**

Protégez votre PDF en ajoutant des restrictions pour l’ouverture et la lecture du fichier. Utilisez les options ci-dessous pour éviter tout accès non autorisé.

| Configuration | Description |
| --- | --- |
| **Définir le mot de passe pour ouvrir le document** | Sélectionnez pour ajouter un mot de passe sécurisé pour afficher votre fichier PDF. Indiquez un mot de passe dans le champ **Mot de passe utilisateur**. Les utilisateurs ne peuvent ouvrir le PDF qu’en saisissant le mot de passe fourni dans ce champ. |
| **Définir les restrictions du document** | Sélectionnez cette option pour restreindre la façon dont les utilisateurs peuvent interagir avec votre PDF. Indiquez un mot de passe dans le champ **Mot de passe du propriétaire** pour que les paramètres de restriction ci-dessous fonctionnent.  <br><ul><li> **Impression** sélectionnez cette option pour permettre à l’utilisateur d’imprimer le PDF. <br> <li> **Impression de qualité Brouillon** sélectionnez cette option pour permettre à l’utilisateur d’imprimer le PDF dans une résolution inférieure.  <br> <li> **Copie de contenu** sélectionnez cette option pour permettre à l’utilisateur de copier du contenu du PDF. <br> <li> **Annotations** sélectionnez cette option pour permettre à l’utilisateur d’ajouter une note ou un commentaire dans le PDF. <br> <li> **Modifications du contenu** sélectionnez cette option pour permettre à l’utilisateur de modifier le contenu dans le PDF. <br> <li> **Copie de contenu pour l’accessibilité** Sélectionnez cette option pour permettre aux lecteurs d’écran de lire et de parcourir le contenu dans PDF. <br>  **Assemblage de document** sélectionnez cette option pour permettre aux utilisateurs d&#39;insérer des pages dans le PDF. <br> **Remarque** : les utilisateurs doivent saisir le mot de passe du propriétaire pour modifier les restrictions sous Fichier > Propriétés dans Adobe Acrobat. |

**Imprimer**

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

**Avancé**

Utilisez les options suivantes pour spécifier des paramètres avancés pour fusionner des PDF, utiliser la compression, sélectionner la norme de conformité, etc.

| Configuration | Description |
| --- | --- |
| **Créer un PDF accessible (balisé)** | Sélectionnez cette option pour générer un PDF avec des balises. Un PDF balisé permet aux lecteurs d’écran de lire et de parcourir plus facilement le contenu, les liens hypertexte, les signets, etc. Par exemple, si un tableau est balisé, le lecteur d’écran saura qu’il lit le tableau et pas seulement les lignes et le texte. |
| **Fusion des PDF inclus dans la table des matières** | Sélectionnez cette option pour fusionner les fichiers PDF existants dans votre sortie en les ajoutant à votre plan DITA sous forme de fichier de ressources. Les fichiers PDF seront insérés à l’emplacement représenté sur la carte et les pages seront incrémentées en conséquence. |
| **Incorporer les polices utilisées** | Sélectionnez cette option lors de l’utilisation de polices qui ne peuvent pas être installées sur l’ordinateur de l’utilisateur final. Lorsque cette option est sélectionnée, les polices utilisées sont incorporées dans le PDF, ce qui permet à l’utilisateur d’afficher le PDF comme prévu, même si les polices ne sont pas installées sur son ordinateur. <br> **Remarque** : une police ne peut être incorporée que si elle contient un paramètre défini par le fournisseur de la police qui permet son incorporation. Assurez-vous de disposer du paramètre ou de la licence requis avant d’incorporer une police. |
| **Utiliser la césure automatique** | Lorsque la coupure de mots automatique est activée, les mots à l&#39;extrémité des lignes sont rompus aux endroits grammaticalement corrects avec un trait d&#39;union. |
| **Activer JavaScript** | Activez cette option si vous disposez d’un code JavaScript que vous souhaitez utiliser pour transformer votre contenu de manière dynamique avant de générer un PDF. |
| **Incorporer des fichiers multimédias** | Sélectionnez cette option pour incorporer les ressources multimédias prises en charge, telles que des fichiers audio et vidéo, directement dans le PDF généré. Lorsqu’il est activé, le contenu vidéo est représenté à l’aide d’une image d’affiche ou d’une miniature dans le PDF et peut être lu dans des visionneuses PDF compatibles qui prennent en charge le multimédia incorporé. Pour la lecture vidéo, ouvrez le PDF dans une application prise en charge, telle que la dernière version d’Adobe Acrobat, et approuvez le document lorsque vous y êtes invité. La plupart des visionneuses PDF basées sur un navigateur ne prennent pas en charge la lecture multimédia incorporée. |
| **Utiliser la compression complète pour optimiser la taille du PDF** | Sélectionnez cette option si vous souhaitez compresser/réduire la taille d’un PDF volumineux. N’oubliez pas que la compression du PDF peut réduire la qualité du fichier. |
| **Utiliser la compression d’image pour optimiser la taille du PDF** | Sélectionnez cette option si vous souhaitez compresser/réduire la taille des images utilisées, dans votre PDF. N’oubliez pas que la compression d’une image peut en réduire la qualité. |
| **Utiliser une résolution personnalisée (pixels par pouce)** | Il s’agit de la résolution d’affichage de la page en pixels par pouce. Saisissez la valeur souhaitée dans le champ qui s’affiche lorsque cette option est sélectionnée. La valeur par défaut est de 96 pixels par pouce. Définissez une valeur plus élevée pour adapter davantage de contenu en pouces, et vice versa, si vous définissez une valeur plus faible. |
| **Afficher le filigrane** | Sélectionnez cette option pour superposer un filigrane dans votre sortie. Vous pouvez saisir une nouvelle chaîne de texte dans la zone de texte en respectant la casse souhaitée. <br><br>Utilisez du texte statique ou des variables de langue pour publier la version localisée du filigrane.  Selon la langue choisie, la valeur localisée est automatiquement sélectionnée dans la sortie PDF. Par exemple, vous pouvez imprimer « Publisher » sous forme de filigrane en anglais et « Auteure » en français.  <br> Format : `${lng:<variable name>}`. Par exemple, `$ {lng:publisher-label}` où `publisher-label` est une variable de langue. |
| **Activer les équations de MathML** | Sélectionnez cette option pour effectuer le rendu des équations MathML présentes dans votre contenu. Les équations seront ignorées par défaut. |
| **Créer un formulaire PDF interactif** | Sélectionnez cette option si vous souhaitez inclure des champs de formulaire PDF interactifs et personnalisables pour une entrée utilisateur améliorée dans les sorties PDF générées. |
| **Inclure le suivi des modifications** | Sélectionnez cette option si vous souhaitez inclure les modifications suivies dans le PDF généré pour faciliter la révision et la comparaison. |
| **Conserver les fichiers temporaires** | Sélectionnez cette option si vous souhaitez conserver les fichiers HTML intermédiaires créés lors de la génération de la sortie Native PDF. Vous pouvez ensuite télécharger les fichiers temporaires après avoir généré la sortie. Les fichiers téléchargés incluraient également `system_config.xml` fichier qui vous donne des informations sur l’URL de création, l’URL locale et l’URL de publication. Ces URL sont configurées dans les paramètres d’externalisation d’AEM et sont reflétées dans le fichier `system_config.xml`. |
| **Conformité de** | Il s’agit de la norme à laquelle vous avez l’intention d’enregistrer votre PDF pour vous assurer qu’elle est conforme. Faites votre choix dans la liste déroulante parmi les normes PDF disponibles. Pour plus d’informations sur les normes prises en charge, voir [À propos des normes PDF](https://helpx.adobe.com/fr/acrobat/using/pdf-conversion-settings.html#about_pdf_x_pdf_e_and_pdf_a_standards). |
| **Propriétés du fichier** | Sélectionnez les métadonnées que vous souhaitez transmettre à la publication native de PDF. La liste déroulante répertorie les propriétés personnalisées et par défaut. Par exemple, `dc:description`, `dc:language`, `dc:title` et `docstate` sont les propriétés par défaut, tandis que vous pouvez utiliser `author` comme propriété personnalisée. Les propriétés de métadonnées sélectionnées sont transmises au fichier PDF généré à l’aide de PDF natif. <br> Ces propriétés sont sélectionnées à partir du fichier `metadataList` disponible à l’adresse `/libs/fmdita/config/metadataList`. <br>Ce fichier peut être recouvert à l’adresse : `/apps/fmdita/config/metadataList`. |
