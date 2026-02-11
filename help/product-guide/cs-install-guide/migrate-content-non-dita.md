---
title: Migration de contenu non DITA
description: Découvrez comment migrer du contenu non DITA
exl-id: cf437fb8-ed33-47af-aa7e-ffd8acd232da
feature: Migration
role: Admin
level: Experienced
source-git-commit: 85ba88f5659e066f970583d745a56ec8c51aad7a
workflow-type: tm+mt
source-wordcount: '2480'
ht-degree: 0%

---

# Migration de contenu non DITA {#id181AH0R02HT}

Cette section vous guide tout au long du processus de migration pour migrer des documents non-DITA au format DITA. AEM Guides fournit une migration à partir des sources suivantes :

- [Microsoft Word](#id1949B040Z5Z)

- [Documents InDesign](#id195AD0B0K5Z)

- [XHTML](#id1949B04L0Y4)

- [Documents FrameMaker non structurés](#id1949B050VUI)

- [Tout autre document structuré](#id1949B0590YK)


## Migrer des documents Microsoft Word {#id1949B040Z5Z}

AEM Guides vous permet de migrer vos documents Word existants \(`.docx`\) dans des documents de type rubrique DITA. Vous devez spécifier les emplacements des dossiers d&#39;entrée et de sortie avec d&#39;autres paramètres pour que le document soit converti en document DITA. Selon le contenu, vous pouvez avoir un fichier .dita et un fichier .ditamap.

Pour pouvoir convertir correctement un document Word, votre document doit être bien structuré. Par exemple, votre document doit avoir un Titre, suivi de Titre 1, Titre 2, etc. Chacun des en-têtes doit contenir du contenu. Si votre document n’est pas bien structuré, le processus peut ne pas fonctionner comme prévu.

Par défaut, AEM Guides utilise la structure de transformation [Word-to-DITA \(Word2DITA\)](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/word2dita-intro.html). Cette transformation dépend du fichier de configuration [mappage style-à-balise](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html). Pour pouvoir utiliser la transformation Word2DITA avec succès, tenez compte des instructions suivantes pour préparer votre document Word en vue de la conversion :

>[!NOTE]
>
> Si vous apportez des modifications au fichier de configuration du mappage style-balise par défaut, vous devez mettre à jour et utiliser les instructions qui confirment votre mappage de style mis à jour.

- Assurez-vous que votre document commence par un titre ; ce titre est mappé au titre du plan DITA. En outre, le titre doit être suivi d’un contenu régulier.

- Après le titre, il doit y avoir la rubrique 1, la rubrique 2, etc. Chaque en-tête doit comporter du contenu. Les en-têtes sont convertis en nouvelles rubriques de type Concept . La hiérarchie des rubriques générées est conforme aux niveaux d’en-tête du document. Par exemple, l’en-tête 1 précède l’en-tête 2 et l’en-tête 2 précède le contenu de l’en-tête 3.

- Le document doit avoir au moins un contenu de type Titre.

- Assurez-vous qu’il n’y a aucune image groupée. Si vous avez regroupé des images dans votre document, dissociez-les.

- Supprimer tous les en-têtes et pieds de page.

- Les styles intégrés tels que le gras, l’italique et le soulignement sont convertis en éléments `b`, `i` et `u`.

- Toutes les listes ordonnées et non ordonnées sont converties en éléments `ol` et `ul`. Cela s’applique également aux listes imbriquées, aux listes dans des tableaux, des notes ou des notes de bas de page.

- Tous les liens hypertexte sont convertis en `xref`.

- Le nom de fichier des fichiers convertis est basé sur le texte de l’en-tête suivi d’un numéro de fichier. Le numéro de fichier est un numéro séquentiel basé sur la position du texte d’en-tête dans le document. Par exemple, si un texte d’en-tête est « Exemple d’en-tête » et qu’il s’agit du 10e en-tête dans le document, le nom de fichier obtenu pour cette rubrique sera similaire à Sample\_Heading\_10.dita.


Effectuez les étapes suivantes pour convertir vos documents Word existants en document de type rubrique DITA :

1. Utilisez le gestionnaire de packages pour télécharger le fichier /libs/fmdita/config/w2d\_io.xml.

1. Personnalisez le fichier w2d\_io.xml téléchargé.

1. Ajoutez le fichier à l’emplacement suivant dans votre référentiel Git Cloud Manager :

   /apps/fmdita/config/w2d\_io.xml

   Le fichier `w2d_io.xml` contient les paramètres configurables suivants :

   - Dans l’élément `inputDir`, spécifiez l’emplacement du dossier d’entrée dans lequel vos documents Word sources sont disponibles. Par exemple, si vos documents Word sont stockés dans un dossier nommé `wordtodita` dans `projects` dossier , indiquez l’emplacement suivant : `/content/dam/projects/wordtodita/`

   - Dans l&#39;élément `outputDir`, spécifiez l&#39;emplacement du dossier de sortie ou conservez l&#39;emplacement de sortie par défaut pour enregistrer le document DITA converti. Si le dossier de sortie spécifié n’existe pas dans la gestion des ressources numériques, le workflow de conversion crée le dossier de sortie.

   - Pour l&#39;élément `createRev`, indiquez si une nouvelle version de la rubrique DITA convertie doit être créée \(`true`\) ou non \(`false`\).

   - Dans l&#39;élément `s2tMap`, spécifiez l&#39;emplacement du fichier de mappage contenant les mappages des styles de document Word aux éléments DITA. Le mappage par défaut est stocké dans le fichier situé à l’emplacement suivant :

     ```
     /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
     ```

     >[!NOTE]
     >
     > Pour plus d’informations sur la structure `word-builtin-styles-style2tagmap.xml` fichier et la personnalisation de celui-ci, consultez [Style to Tag Mapping](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html) dans le *Guide d’utilisation de DITA pour les éditeurs*.

   - Dans l&#39;élément props2Propagate , spécifiez les propriétés qui doivent être transmises au plan DITA. Cette propriété est requise pour transmettre les métadonnées par défaut telles que dc:title,dc:subject,dam:keywords,dam:category des métadonnées de document aux ressources DITA converties.

1. Exécutez le pipeline Cloud Manager pour déployer la configuration mise à jour.

1. Après avoir configuré les paramètres requis dans le fichier `w2d_io.xml`, connectez-vous à AEM et ouvrez l’interface utilisateur d’Assets.

1. Accédez à l’emplacement du dossier d’entrée \(`wordtodita`\).

1. Chargez les documents Word sources dans ce dossier. Pour plus d&#39;informations sur le chargement de contenu sur DAM, consultez [Charger du contenu DITA existant](migrate-content-upload-existing-dita-content.md#).


Le bloc `config` `/config` vous permet de définir un ou plusieurs blocs de configurations pour la conversion. Le workflow de conversion est exécuté et la sortie finale, sous la forme d&#39;une rubrique DITA, est enregistrée à l&#39;emplacement spécifié dans l&#39;élément `outputDir`.

**Mises à jour de la personnalisation pour les utilisateurs existants**

Si vous êtes déjà utilisateur d’AEM Guides as a Cloud Service et effectuez une mise à niveau de la version d’août 2021 vers la version de janvier 2022 ou une version ultérieure, mettez à jour les propriétés données, car peu de fichiers ont été déplacés.

>[!NOTE]
>
> Cette mise à jour ne s’applique que si vous utilisez déjà le workflow de conversion Microsoft Word vers DITA.

- Chemin d’accès du fichier : /apps/fmdita/config/w2d\_io.xml
- Remplacez la valeur de `<s2tMap>` de /apps/dxml/word2dita/word-builtin-styles-style2tagmap.xml par /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
- Effectuez les modifications nécessaires dans votre référentiel Git Cloud Manager comme pour le service cloud, tous les fichiers dans /apps sont superposés via le référentiel Git Cloud Manager.

## Migrer des documents Adobe InDesign {#id195AD0B0K5Z}

AEM Guides permet de convertir des documents InDesign. Tout comme FrameMaker, InDesign vous permet de créer des documents structurés et non structurés. Les documents non structurés utilisent les styles de paragraphe et de caractère pour mettre en forme le contenu. Le document structuré utilise des éléments et leurs attributs correspondants.

Le processus de conversion nécessite le mappage des formats de style de paragraphe et de caractère aux éléments DITA appropriés. De même, dans le cas de documents structurés, le fichier de mappage contiendra un mappage direct des éléments et attributs InDesign avec les éléments et attributs DITA.

Le processus de conversion implique les actions suivantes sur le serveur principal :

- Le fichier *InDesign Markup Language* \(IDML\) est décompressé dans un répertoire de travail.
- Le fichier designmap.xml est lu pour localiser les histoires InDesign individuelles.
- Toutes les histoires sont fusionnées en une seule instance XML, les histoires « vides » sont ignorées.
- Tous les graphiques incorporés sont exportés.
- Pré-conversion de structures standard telles que des tableaux et des graphiques au format DITA.
- Mappage de style ou de structure à la sortie finale en fonction du fichier de mappage.
- Création et validation de rubriques DITA et de fichiers map DITA individuels.
- Suppression des fichiers temporaires.

D&#39;une manière générale, le processus de conversion nécessite que vous [Préparez les fichiers InDesign pour la conversion](appendix.md#id195DBF0045Z)[appendix.md\#id195DBF0045Z](appendix.md#id195DBF0045Z) et [Préparez le fichier de mappage pour la migration d&#39;InDesign vers DITA](appendix.md#id194AF0003HT)[appendix.md\#id194AF0003HT](appendix.md#id194AF0003HT), vous devez ensuite suivre la procédure donnée d&#39;exécution du processus de conversion.

Effectuez les étapes suivantes pour convertir vos documents InDesign existants en document de type rubrique DITA :

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite .

1. Accédez au fichier de configuration par défaut disponible à l’emplacement suivant :

   `/libs/fmdita/config/idml2dita_io.xml`
1. Pour créer une configuration personnalisée en fonction de vos besoins, créez un nœud de recouvrement du dossier `config` dans le nœud `apps` .

1. Copiez les fichiers ou dossiers suivants du dossier `libs` vers le dossier des applications :

   - `/fmdita/config/idml2dita_io.xml`
   - `/fmdita/idml2dita/config`
   - `/fmdita/idml2dita/xsl`

1. Accédez au fichier de configuration disponible dans le nœud `apps` :

   `/apps/fmdita/config/idml2dita_io.xml`

1. Ajoutez le mappage des configurations présentes dans le dossier `idml12dita` dans le fichier `idml2dita_io.xml`.
1. Ajoutez les propriétés suivantes dans `idml2dita_io.xml` fichier :

   ```
   <entry          key="idml2DitaConfig">/apps/fmdita/idml2dita/config</entry>
   
   <entry key="idml2DitaXsl">/apps/fmdita/idml2dita/xsl</entry>
   ```

1. Créez un nœud de recouvrement du dossier `config` dans le nœud `apps` .


   Configurez les paramètres suivants dans le fichier `idml2dita_io.xml` :

   - Dans l’élément `inputDir` , spécifiez l’emplacement du dossier d’entrée dans lequel vos documents InDesign sources sont disponibles. Par exemple, si vos documents InDesign sont stockés dans un dossier nommé `indesigntodita` dans `projects` dossier , indiquez l’emplacement suivant : `/content/dam/idmlfiles/indesigntodita/`

   - Dans l&#39;élément `outputDir`, spécifiez l&#39;emplacement du dossier de sortie ou conservez l&#39;emplacement de sortie par défaut pour enregistrer le document DITA converti. Si le dossier de sortie spécifié n’existe pas dans la gestion des ressources numériques, le workflow de conversion crée le dossier de sortie.

   - Dans l&#39;élément `mapStyle`, spécifiez l&#39;emplacement du fichier de mappage contenant les mappages des styles de document InDesign aux éléments DITA. Le mappage par défaut est stocké dans le fichier situé à l’emplacement suivant :

     ```
     /stmap.adobeidml.xml
     ```

     >[!NOTE]
     >
     > Pour plus d’informations sur la structure `stmap.adobeidml.xml` fichier et sur la personnalisation, consultez la section [appendix.md\#id194AF0003HT](appendix.md#id194AF0003HT) dans Annexe.

1. Enregistrez le fichier `idml2dita_io.xml`.

1. Après avoir configuré les paramètres requis dans le fichier `idml2dita_io.xml`, connectez-vous à AEM et ouvrez l’interface utilisateur d’Assets.

1. Accédez à l’emplacement du dossier d’entrée \(`indesigntodita`\).

1. Chargez les documents InDesign sources dans ce dossier. Pour plus d&#39;informations sur le chargement de contenu sur DAM, consultez [Charger du contenu DITA existant](migrate-content-upload-existing-dita-content.md#).


## Migrer des documents XHTML {#id1949B04L0Y4}

AEM Guides vous permet de convertir vos documents XHTML existants en documents de type rubrique DITA. Vous devez spécifier les emplacements des dossiers d&#39;entrée et de sortie avec d&#39;autres paramètres et les documents sont convertis au format DITA. Vous pouvez utiliser deux méthodes pour convertir vos documents HTML structurés :

- Chargez tous les documents dans le dossier input, ou
- Créez un fichier ZIP contenant tous les documents avec les fichiers multimédias et chargez-le dans le dossier input. Cette approche est généralement utilisée pour un ensemble de fichiers HTML liés les uns aux autres et avec une table des matières \(index.html\). Le fichier index.html contient des liens vers tous les fichiers HTML de la visionneuse.

Que vous chargiez tous les fichiers individuellement ou en lot dans un fichier ZIP, le processus de conversion crée un mappage un-à-un entre les fichiers HTML et les fichiers DITA obtenus. Cela signifie essentiellement qu’il existe un fichier .dita créé pour chaque fichier .html dans le dossier input.

Les points suivants doivent être pris en compte pour charger vos documents dans un fichier ZIP :

- Toutes les rubriques référencées doivent être placées dans le fichier ZIP.

- Tous les fichiers multimédias référencés doivent être référencés dans les fichiers de rubrique à l’aide d’un lien relatif.

- Créez un fichier index.html et ajoutez des liens vers les rubriques que vous souhaitez ajouter à la table des matières. Ce fichier index.html est utilisé pour créer le fichier de mappage DITA. Dans le fichier index.html, vous pouvez également créer une liste de rubriques imbriquées, comme illustré dans l’exemple de code suivant :

  ```
  <?xml version="1.0" encoding="UTF-8"?>
  <html
  xmlns="http://www.w3.org/1999/xhtml">
      <head>
          <title>Sample Index File</title>
      </head>
      <body>
          <h1>Sample Index</h1>
          <div class="content">
              <ul class="book">
                  <li class="topicref">
                      <a href="Topic1.html">Topic 1</a>
                      <ul class="book">
                          <li class="topicref">
                              <a href="Topic1-1.html">Topic 1.1</a>
                          </li>
                          <li class="topicref">
                              <a href="Topic1-2.html">Topic 1.2</a>
                          </li>
                      </ul>
                  </li>
                  <li class="topicref">
                      <a href="Topic2.html">Topic 2</a>
                  </li>
              </ul>
          </div>
      </body>
  </html>
  ```

  Notez que l’attribut `ul` doit être défini sur `class` pour chaque balise `book`. De même, chaque `li` de balise `class` doit être définie sur `topicref`.

- Si vous utilisez des styles intégrés, convertissez-les en classes de style basées sur CSS dans votre fichier XHTML. Utilisez ensuite le mappage style-attribute pour convertir ces styles basés sur des classes en attribut DITA `outputclass` dans le fichier DITA converti.

  Lors de la génération de la sortie HTML ou AEM Site à partir de ces fichiers DITA, les attributs `outputclass` peuvent être utilisés pour appliquer une classe de style sur le site HTML ou AEM généré afin de correspondre à votre contenu HTML source.


Outre les considérations relatives à la création du fichier ZIP, votre document XHTML doit également être bien structuré. Par exemple, votre document doit avoir un *Titre*, suivi de *Titre 1*, *Titre 2*, etc. Chacun des en-têtes doit contenir du contenu. Si votre document n’est pas bien structuré, le processus de migration peut ne pas fonctionner comme prévu.

Pour convertir votre document XHTML existant en rubrique DITA, procédez comme suit :

1. Utilisez le gestionnaire de packages pour télécharger le fichier /libs/fmdita/config/h2d\_io.xml.

1. Personnalisez le fichier h2d\_io.xml téléchargé.

1. Ajoutez le fichier à l’emplacement suivant dans votre référentiel Git Cloud Manager :

   /apps/fmdita/config/h2d\_io.xml

   Le fichier `h2d_io.xml` contient les paramètres configurables suivants :

   - Dans l’élément `inputDir` , spécifiez l’emplacement de votre dossier d’entrée dans lequel vos documents XHTML sources sont disponibles. Par exemple, si vos documents XHTML sont stockés dans un dossier nommé `xhtmltodita` dans `projects` dossier , indiquez l’emplacement suivant : `/content/dam/projects/xhtmltodita/`

   - Dans l’élément `outputDir`, spécifiez l’emplacement de votre dossier de sortie ou conservez l’emplacement de sortie par défaut. Si le dossier de sortie spécifié n’existe pas dans la gestion des ressources numériques, le workflow de conversion crée le dossier de sortie.

   - Pour l&#39;élément `createRev`, indiquez si une nouvelle version de la rubrique DITA convertie doit être créée \(`true`\) ou non \(`false`\).

1. Exécutez le pipeline Cloud Manager pour déployer la configuration mise à jour.

1. Après avoir configuré les paramètres requis dans le fichier `w2d_io.xml`, connectez-vous à AEM et ouvrez l’interface utilisateur d’Assets.

1. *\(Facultatif\)* Vous pouvez également ajouter la section des liens associés aux documents convertis. Pour activer cette fonctionnalité, procédez comme suit :

   >[!NOTE]
   >
   > Par défaut, la section Liens associés n’est pas créée dans les documents convertis.

   1. Utilisez le gestionnaire de packages pour télécharger le fichier /libs/fmdita/html2dita/h2d.xsl.

   2. Recherchez le paramètre suivant :

      `<xsl:param name="generate-related-links" select="false()"/>`

   3. Définissez la valeur du paramètre ci-dessus sur `true()`.

   4. Validez le fichier mis à jour à l’emplacement suivant dans votre référentiel Git Cloud Manager :

      /libs/fmdita/html2dita/

   5. Exécutez le pipeline Cloud Manager pour déployer la configuration mise à jour.

1. Accédez à l’emplacement du dossier d’entrée \(`xhtmltodita`\).

1. Chargez les documents XHTML sources dans ce dossier. Pour plus d&#39;informations sur le chargement de contenu sur DAM, consultez [Charger du contenu DITA existant](migrate-content-upload-existing-dita-content.md#).


Le bloc `<config> </config>` vous permet de définir un ou plusieurs blocs de configurations pour la conversion. Le workflow de conversion est exécuté et la sortie finale, sous la forme d&#39;une rubrique DITA, est enregistrée à l&#39;emplacement spécifié dans l&#39;élément `outputDir`.

## Migration de documents FrameMaker non structurés {#id1949B050VUI}

AEM Guides vous permet de convertir vos documents FrameMaker \(`.fm` et `.book`\) non structurés existants en documents DITA. Pour plus d’informations sur le processus, consultez la section [Migration de la documentation technique de Unstructured vers DITA dans Adobe FrameMaker](https://migrate-from-unstructured-to-dita-step-by-step-guide.meetus.adobeevents.com/).

<!-- Deprecated information -
 //The first step is to create style mappings using FrameMaker and save those settings in a .sts file. Next, if you are using custom DITA, then you can map your custom elements with the source FrameMaker formats in the `ditaElems.xml` file. For example, if you have created a custom element named `impnote` to handle all important notes, then you can define this custom element in the `ditaElems.xml` file. Once this custom element is defined, AEM Guides would not raise an error while converting FrameMaker document containing `impnote` element.

Also, If you want to specify some additional attributes with your custom or valid DITA element, you can define those in the style2attrMap.xml file. For example, you can specify the `type` attribute with the value of `important` to be passed on with the `impnote` element. This additional information can be specified in the style2attrMap.xml file.

In addition to specifying

To convert your existing unstructured FrameMaker documents into DITA format, perform the following steps:

1.  Create style mappings in FrameMaker and save those settings in a .sts file.

1.  Log into AEM and open the CRXDE Lite mode.

1.  If you have custom DITA elements, define those in the `ditaElems.xml` file available at the following location:

    `/libs/fmdita/config/ditaElems.xml`

1.  Create an overlay node of the `config` folder within the `apps` node.

1.  Navigate to the configuration file available in the `apps` node:

    `/apps/fmdita/config/ditaElems.xml`

    The `ditaElems.xml` file contains a single configurable parameter:

    -   In the `elem` parameter, specify the name of the custom element that you want to use in your converted DITA documents. This element would be passed on as is in the generated DITA documents.

1.  If you want to specify additional attributes, define those in the `style2attrMap.xml` file available at the following location:

    `/libs/fmdita/config/style2attrMap.xml`

1.  Create an overlay node of the `config` folder within the `apps` node.

1.  Navigate to the configuration file available in the `apps` node:

    `/apps/fmdita/config/style2attrMap.xml`

    The `style2attrMap.xml` file contains the following configurable parameters:

    -   In the `fmStyle` parameter, specify the source format used in the FrameMaker document that you want to map.

    -   In the`ditaAttr` element, specify the DITA attribute that you want to map with the source format.

    -   In the `ditaVal` element, specify the value for the mapped attribute. If you don't have any value, you can leave this entry blank.

1.  Save the `style2attrMap.xml` file.

1. After configuring the required parameters in the `style2attrMap.xml` file, log into AEM and open the Assets UI.

1. Navigate to and click on the FrameMaker document that you want to convert.

    The DITA map console appears showing the list of Output Presets available to generate output.

1. Select DITA output format and configure the required parameters.

    >[!NOTE]
    >
    > You must use the same settings file \(.sts\) that you created in FrameMaker. Also, specify the Settings Name and Destination Path.

1. Click the **Generate** icon to start the output generation process.


Using the `<attrMap> </attrMap>` block, you can define one or multiple blocks of configurations for conversion. Depending on the content, you could have a .dita file and a .ditamap file as the converted files.

-->

## Migrer tout autre document structuré {#id1949B0590YK}

AEM Guides vous permet de convertir vos documents structurés existants en documents DITA valides. Vous devez spécifier les emplacements des dossiers d’entrée et de sortie, l’emplacement de votre fichier de transformation, l’extension avec laquelle la sortie finale est enregistrée et si une nouvelle version du document est requise ou non.

Pour convertir vos documents structurés existants au format DITA, procédez comme suit :

1. Utilisez le gestionnaire de packages pour télécharger le fichier /libs/fmdita/config/XSLConfig.xml.

1. Créez une copie du fichier XSLConfig.xml à l’emplacement suivant dans votre référentiel Git Cloud Manager :

   `/apps/fmdita/config/XSLConfig.xml`

   Le fichier `XSLConfig.xml` contient les paramètres configurables suivants :

   - Dans l’élément `inputDir` , spécifiez l’emplacement de votre dossier d’entrée dans lequel vos documents structurés sources sont disponibles. Par exemple, si vos documents structurés sont stockés dans un dossier nommé `xsltodita` dans `projects` dossier , indiquez l’emplacement suivant : `/content/dam/projects/xsltodita/`

   - Dans l’élément `outputDir`, spécifiez l’emplacement de votre dossier de sortie ou conservez l’emplacement de sortie par défaut. Si le dossier de sortie spécifié n’existe pas dans la gestion des ressources numériques, le workflow de conversion crée le dossier de sortie.

   - Dans l’élément `xslFolder` , spécifiez l’emplacement du dossier dans lequel les fichiers de transformation XSL sont stockés.

   - Dans l’élément ``xslPath``, spécifiez l’emplacement du fichier .XSL principal utilisé pour lancer le processus de conversion.

   - Dans l’élément ``outputExt``, spécifiez les extensions du fichier de sortie final créé à partir du flux de transformation.

   - Pour l&#39;élément `createRev`, indiquez si une nouvelle version de la rubrique DITA convertie doit être créée \(`true`\) ou non \(`false`\).

1. Enregistrez le fichier `XSLConfig.xml`.

1. Après avoir configuré les paramètres requis dans le fichier `XSLConfig.xml`, connectez-vous à AEM et ouvrez l’interface utilisateur d’Assets.

1. Accédez à l’emplacement du dossier d’entrée \(`xsltodita`\).

1. Chargez les documents structurés source dans ce dossier. Pour plus d&#39;informations sur le chargement de contenu sur DAM, consultez [Charger du contenu DITA existant](migrate-content-upload-existing-dita-content.md#).


Le bloc `<config> </config>` vous permet de définir un ou plusieurs blocs de configurations pour la conversion. Le workflow de conversion est exécuté et la sortie finale, sous la forme d&#39;une rubrique DITA, est enregistrée à l&#39;emplacement spécifié dans l&#39;élément `outputDir`.

**Rubrique parente :**[ Migrer le contenu existant](migrate-content.md)
