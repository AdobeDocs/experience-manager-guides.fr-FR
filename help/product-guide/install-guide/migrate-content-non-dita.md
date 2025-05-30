---
title: Migration de contenu non DITA
description: Découvrez comment migrer du contenu non DITA
exl-id: 4597d1be-5426-4eba-8490-e42d0e565427
feature: Migration
role: Admin
level: Experienced
source-git-commit: 1644bfba3332b0f023aa8d70aefd2680d4220d8a
workflow-type: tm+mt
source-wordcount: '2802'
ht-degree: 0%

---

# Migration de contenu non DITA {#id181AH0R02HT}

Cette section vous guide tout au long du processus de migration pour migrer des documents non DITA au format DITA. AEM Guides permet la migration à partir des sources suivantes :

- [Microsoft Word](#id1949B040Z5Z)

- [InDesign de documents](#id195AD0B0K5Z)

- [XHTML](#id1949B04L0Y4)

- [Documents de FrameMaker non structurés](#id1949B050VUI)

- [Tout autre document structuré](#id1949B0590YK)


## Migration de documents Microsoft Word {#id1949B040Z5Z}

AEM Guides vous permet de migrer vos documents Word existants \(`.docx`\) vers des documents de type rubrique DITA. Vous devez spécifier les emplacements de dossiers d’entrée et de sortie avec d’autres paramètres et le document est converti en document DITA. Selon le contenu, vous pouvez avoir un fichier .dita et un fichier .ditamap .

Pour pouvoir convertir un document Word avec succès, votre document doit être bien structuré. Par exemple, votre document doit comporter un titre, suivi de l’en-tête 1, de l’en-tête 2, etc. Chacun des en-têtes doit contenir du contenu. Si votre document n’est pas correctement structuré, le processus risque de ne pas fonctionner comme prévu.

Par défaut, AEM Guides utilise la structure de transformation [Word-to-DITA \(Word2DITA\)](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/word2dita-intro.html). Cette transformation dépend du fichier de configuration [style-to-tag mapping](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html). Pour pouvoir utiliser la transformation Word2DITA avec succès, vous devez tenir compte des instructions suivantes pour préparer votre document Word à la conversion :

>[!NOTE]
>
> Si vous apportez des modifications au fichier de configuration de mappage de style à balise par défaut, vous devez mettre à jour et utiliser les instructions pour confirmer le mappage de style mis à jour.

- Assurez-vous que votre document commence par un titre ; ce titre est mappé sur le titre du mappage DITA. En outre, le titre doit être suivi d’un contenu normal.

- Après le titre, il doit y avoir Titre 1, En-tête 2, etc. Chaque En-tête doit contenir du contenu. Les en-têtes sont convertis en nouvelles rubriques de type Concept . La hiérarchie des rubriques générées correspond aux niveaux d’en-tête du document. Par exemple, l’en-tête 1 précède l’en-tête 2 et l’en-tête 2 précède le contenu de l’en-tête 3.

- Le document doit comporter au moins un contenu de type En-tête .

- Assurez-vous que vous ne disposez d’aucune image groupée. Si vous avez groupé des images dans votre document, dissociez toutes ces images.

- Supprimez tous les en-têtes et pieds de page.

- Les styles intégrés tels que le gras, l’italique et le soulignement sont convertis en éléments `b`, `i` et `u`.

- Toutes les listes triées et non triées sont converties en éléments `ol` et `ul` . Cela s’applique également aux listes imbriquées, aux listes dans les tableaux, aux notes ou aux notes de bas de page.

- Tous les hyperliens sont convertis en `xref`.

- Le nom de fichier des fichiers convertis est basé sur le texte du titre suivi d’un numéro de fichier. Le numéro de fichier est un numéro séquentiel basé sur la position du texte de l’en-tête dans le document. Par exemple, si un titre est &quot;Exemple d’en-tête&quot; et qu’il est 10e dans le document, le nom de fichier généré pour cette rubrique sera similaire à Sample\_Heading\_10.dita.


Effectuez les étapes suivantes pour convertir vos documents Word existants en document de type rubrique DITA :

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite.

1. Accédez au fichier de configuration par défaut disponible à l’emplacement suivant :

   `/libs/fmdita/config/w2d_io.xml`

1. Créez un noeud de recouvrement du dossier `config` dans le noeud `apps`.

1. Accédez au fichier de configuration disponible dans le noeud `apps` :

   `/apps/fmdita/config/w2d_io.xml`

   Le fichier `w2d_io.xml` contient les paramètres configurables suivants :

   - Dans l’élément `inputDir` , spécifiez l’emplacement du dossier input dans lequel vos documents Word sources sont disponibles. Par exemple, si vos documents Word sont stockés dans un dossier nommé `wordtodita` dans le dossier `projects`, indiquez l’emplacement suivant : `/content/dam/projects/wordtodita/`

   - Dans l’élément `outputDir` , spécifiez l’emplacement du dossier output ou conservez l’emplacement de sortie par défaut pour enregistrer le document DITA converti. Si le dossier de sortie spécifié n’existe pas sur DAM, le workflow de conversion crée le dossier de sortie.

   - Pour l’élément `createRev`, indiquez si une nouvelle version de la rubrique DITA convertie doit être créée \(`true`\) ou non \(`false`\).

   - Dans l’élément `s2tMap` , spécifiez l’emplacement du fichier map contenant les mappages des styles de document Word aux éléments DITA. Le mappage par défaut est stocké dans le fichier situé à l’emplacement suivant :

     ```XML
     /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
     ```

     >[!NOTE]
     >
     > Pour plus d’informations sur la structure du fichier `word-builtin-styles-style2tagmap.xml` et sur la manière dont vous pouvez le personnaliser, voir [Mappage style/balise](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html) dans le *Guide de l’utilisateur DITA pour les éditeurs*.

   - Dans l’élément props2Propagate , spécifiez les propriétés à transmettre au mappage DITA. Cette propriété est requise pour transmettre les métadonnées par défaut telles que dc:title,dc:subject,dam:keywords,dam:category des métadonnées de document aux ressources DITA converties.

1. Enregistrez le fichier `w2d_io.xml`.

1. Après avoir configuré les paramètres requis dans le fichier `w2d_io.xml`, connectez-vous à AEM et ouvrez l’interface utilisateur d’Assets.

1. Accédez à l’emplacement du dossier d’entrée \(`wordtodita`\).

1. Téléchargez les documents Word source dans ce dossier. Pour plus d’informations sur le chargement de contenu sur DAM, voir [Chargement de contenu DITA existant](migrate-content-upload-existing-dita-content.md#).


En utilisant le bloc `config` `/config` , vous pouvez définir un ou plusieurs blocs de configurations pour la conversion. Le workflow de conversion est exécuté et la sortie finale sous la forme d’une rubrique DITA est enregistrée à l’emplacement spécifié dans l’élément `outputDir` .

## Migration de documents Adobe InDesign {#id195AD0B0K5Z}

AEM Guides vous permet de convertir des documents InDesigns. Tout comme FrameMaker, InDesign vous permet de créer des documents structurés et non structurés. Les documents non structurés utilisent les styles de paragraphe et de caractère pour formater le contenu. Le document structuré utilise des éléments et leurs attributs correspondants.

Le processus de conversion nécessite le mappage des formats de paragraphe et de style de caractère aux éléments DITA pertinents. De même, dans le cas des documents structurés, le fichier de mappage contient un mappage un-à-un des éléments et attributs d’InDesign avec des éléments et attributs DITA.

Le processus de conversion implique les actions suivantes dans le serveur principal :

- Le fichier *InDesign Markup Language* \(IDML\) est décompressé dans un répertoire de travail.
- Le fichier designmap.xml est lu pour localiser les différents articles d’InDesign.
- Tous les articles sont fusionnés en une seule instance XML, les articles &quot;vides&quot; sont ignorés.
- Tous les graphiques incorporés sont exportés.
- Préconversion des structures standard telles que les tableaux et les graphiques au format DITA.
- Mappage de style ou de structure à la sortie finale en fonction du fichier de mappage.
- Création et validation de rubriques DITA individuelles et de fichiers de mappage DITA.
- Suppression des fichiers temporaires.

De manière générale, le processus de conversion requiert que vous [Préparez les fichiers d’InDesign pour la conversion](appendix.md#id195DBF0045Z) et [Préparez le fichier de mappage pour l’InDesign à la migration DITA](appendix.md#id194AF0003HT). Vous devez ensuite suivre la procédure d’exécution donnée du processus de conversion.

Effectuez les étapes suivantes pour convertir vos documents InDesign existants en document de type rubrique DITA :

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite.

1. Accédez au fichier de configuration par défaut disponible à l’emplacement suivant :

   `/libs/fmdita/config/idml2dita_io.xml`

1. Pour créer une configuration personnalisée en fonction de vos besoins, créez un noeud de recouvrement du dossier `config` dans le noeud `apps`.

1. Copiez les fichiers ou dossiers suivants du dossier `libs` vers le dossier des applications :

   - `/fmdita/config/idml2dita_io.xml`
   - `/fmdita/idml2dita/config`
   - `/fmdita/idml2dita/xsl`

1. Accédez au fichier de configuration disponible dans le noeud `apps` :

   `/apps/fmdita/config/idml2dita_io.xml`

1. Ajoutez le mappage des configurations présentes dans le dossier `idml12dita` du fichier `idml2dita_io.xml`.
1. Ajoutez les propriétés suivantes dans le fichier `idml2dita_io.xml` :

   ```
   <entry key="idml2DitaConfig">/apps/fmdita/idml2dita/config</entry>
   
   <entry key="idml2DitaXsl">/apps/fmdita/idml2dita/xsl</entry>
   ```

Configurez les paramètres suivants dans le fichier `idml2dita_io.xml` :

- Dans l’élément `inputDir` , spécifiez l’emplacement du dossier input dans lequel vos documents d’InDesign source sont disponibles. Par exemple, si vos documents d’InDesign sont stockés dans un dossier nommé `indesigntodita` dans le dossier `projects`, spécifiez l’emplacement suivant : `/content/dam/idmlfiles/indesigntodita/`

- Dans l’élément `outputDir` , spécifiez l’emplacement du dossier output ou conservez l’emplacement de sortie par défaut pour enregistrer le document DITA converti. Si le dossier de sortie spécifié n’existe pas sur DAM, le workflow de conversion crée le dossier de sortie.

- Dans l’élément `mapStyle` , spécifiez l’emplacement du fichier map contenant les mappages des styles de document InDesign aux éléments DITA. Le mappage par défaut est stocké dans le fichier situé à l’emplacement suivant :

```XML
    /stmap.adobeidml.xml
```

>[!NOTE]
>
> Pour plus d’informations sur la structure du fichier `stmap.adobeidml.xml` et sur la manière dont vous pouvez le personnaliser, consultez la section [Préparation du fichier de mappage pour l’InDesign à la migration DITA](appendix.md#id194AF0003HT) dans *Annexe*.

1. Enregistrez le fichier `idml2dita_io.xml`.

1. Après avoir configuré les paramètres requis dans le fichier `idml2dita_io.xml`, connectez-vous à AEM et ouvrez l’interface utilisateur d’Assets.

1. Accédez à l’emplacement du dossier d’entrée \(`indesigntodita`\).

1. Téléchargez les documents d’InDesign source dans ce dossier. Pour plus d’informations sur le chargement de contenu sur DAM, voir [Chargement de contenu DITA existant](migrate-content-upload-existing-dita-content.md#).


## Migration de documents XHTML {#id1949B04L0Y4}

AEM Guides vous permet de convertir vos documents XHTML existants en documents de type rubrique DITA. Vous devez spécifier les emplacements de dossiers d’entrée et de sortie avec d’autres paramètres et les documents sont convertis au format DITA. Vous pouvez utiliser deux méthodes pour convertir vos documents HTML structurés :

- Télécharger tous les documents dans le dossier input ou
- Créez un fichier ZIP de tous les documents avec les fichiers multimédias et chargez-le dans le dossier input. Cette approche est généralement utilisée pour un ensemble de fichiers d’HTML liés les uns aux autres et il existe une table des matières \(index.html\). Le fichier index.html contient des liens vers tous les fichiers d’HTML de l’ensemble.

Que vous téléchargiez tous les fichiers individuellement ou regroupés dans un fichier ZIP, le processus de conversion crée un mappage un-à-un entre les fichiers HTMLS et les fichiers DITA qui en résultent. Cela signifie essentiellement qu’un fichier .dita est créé pour chaque fichier .html dans le dossier input.

Les points suivants doivent être pris en compte pour le téléchargement de vos documents dans un fichier ZIP :

- Toutes les rubriques référencées doivent être placées dans le fichier ZIP.

- Tous les fichiers multimédias référencés doivent être référencés dans les fichiers de rubrique à l’aide d’un lien relatif.

- Créez un fichier index.html et ajoutez des liens vers les rubriques que vous souhaitez ajouter dans la table des matières. Ce fichier index.html est utilisé pour créer le fichier de mappage DITA. Dans le fichier index.html, vous pouvez également créer une liste de rubriques imbriquées, comme illustré dans l’exemple de code suivant :

  ```XML
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

  Notez que l’attribut `class` doit être défini sur `book` pour chaque balise `ul`. De même, `class` de chaque balise `li` doit être défini sur `topicref`.

- Si vous utilisez des styles intégrés, convertissez-les en classes de style CSS dans votre fichier XHTML. Ensuite, utilisez le mappage style-attribut pour convertir ces styles basés sur des classes en attribut DITA `outputclass` dans le fichier DITA converti.

  Lors de la génération d’une sortie de site d’HTML ou d’AEM à partir de ces fichiers DITA, les attributs `outputclass` peuvent être utilisés pour appliquer une classe de style à l’HTML généré ou AEM site pour correspondre au contenu de votre HTML source.


Outre les considérations relatives à la création du fichier ZIP, votre document XHTML doit également être bien structuré. Par exemple, votre document doit avoir un *titre*, suivi de *en-tête 1*, *en-tête 2*, etc. Chacun des en-têtes doit contenir du contenu. Si votre document n’est pas correctement structuré, le processus de migration risque de ne pas fonctionner comme prévu.

Pour convertir votre document XHTML existant en rubrique DITA, procédez comme suit :

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite.

1. Accédez au fichier de configuration par défaut disponible à l’emplacement suivant :

   `/libs/fmdita/config/h2d_io.xml`

1. Créez un noeud de recouvrement du dossier `config` dans le noeud `apps`.

1. Accédez au fichier de configuration disponible dans le noeud `apps` :

   `/apps/fmdita/config/h2d_io.xml`

   Le fichier `h2d_io.xml` contient les paramètres configurables suivants :

   - Dans l’élément `inputDir` , spécifiez l’emplacement de votre dossier d’entrée dans lequel vos documents XHTML sources sont disponibles. Par exemple, si vos documents XHTML sont stockés dans un dossier nommé `xhtmltodita` dans le dossier `projects`, indiquez l’emplacement suivant : `/content/dam/projects/xhtmltodita/`

   - Dans l’élément `outputDir` , spécifiez l’emplacement de votre dossier de sortie ou conservez l’emplacement de sortie par défaut. Si le dossier de sortie spécifié n’existe pas sur DAM, le workflow de conversion crée le dossier de sortie.

   - Pour l’élément `createRev`, indiquez si une nouvelle version de la rubrique DITA convertie doit être créée \(`true`\) ou non \(`false`\).

1. Enregistrez le fichier `h2d_io.xml`.

1. Après avoir configuré les paramètres requis dans le fichier `h2d_io.xml`, connectez-vous à AEM et ouvrez l’interface utilisateur d’Assets.

1. *\(Facultatif\)* Vous pouvez également ajouter la section des liens associés aux documents convertis. Pour activer cette fonction, procédez comme suit :

   >[!NOTE]
   >
   > Par défaut, la section des liens associés n’est pas créée dans les documents convertis.

   1. Accédez au fichier h2d.xsl à l’emplacement suivant :

      /libs/fmdita/html2dita/

   2. Recherchez le paramètre suivant :

      `<xsl:param name="generate-related-links" select="false()"/>`

   3. Définissez la valeur du paramètre ci-dessus sur `true()`.
   4. Enregistrez et fermez le fichier.
1. Accédez à l’emplacement du dossier d’entrée \(`xhtmltodita`\).

1. Téléchargez les documents XHTML sources dans ce dossier. Pour plus d’informations sur le chargement de contenu sur DAM, voir [Chargement de contenu DITA existant](migrate-content-upload-existing-dita-content.md#).


En utilisant le bloc `<config> </config>`, vous pouvez définir un ou plusieurs blocs de configurations pour la conversion. Le workflow de conversion est exécuté et la sortie finale sous la forme d’une rubrique DITA est enregistrée à l’emplacement spécifié dans l’élément `outputDir` .

## Migration de documents de FrameMaker non structurés {#id1949B050VUI}

AEM Guides vous permet de convertir vos documents de FrameMaker non structurés existants \(`.fm` et `.book`\) en documents DITA. La première étape consiste à créer des mappages de style à l’aide de FrameMaker et à enregistrer ces paramètres dans un fichier .sts. Ensuite, si vous utilisez un DITA personnalisé, vous pouvez mapper vos éléments personnalisés aux formats de FrameMaker source dans le fichier `ditaElems.xml`. Par exemple, si vous avez créé un élément personnalisé nommé `impnote` pour gérer toutes les notes importantes, vous pouvez définir cet élément personnalisé dans le fichier `ditaElems.xml`. Une fois cet élément personnalisé défini, AEM Guides ne génère pas d’erreur lors de la conversion d’un document FrameMaker contenant un élément `impnote`.

En outre, si vous souhaitez spécifier des attributs supplémentaires avec votre élément DITA personnalisé ou valide, vous pouvez les définir dans le fichier style2projMap.xml . Par exemple, vous pouvez spécifier l’attribut `type` avec la valeur `important` à transmettre avec l’élément `impnote`. Ces informations supplémentaires peuvent être spécifiées dans le fichier style2projMap.xml .

En plus de la spécification

Pour convertir vos documents de FrameMaker non structurés existants au format DITA, procédez comme suit :

1. Créez des mappages de style dans FrameMaker et enregistrez ces paramètres dans un fichier .sts.

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite.

1. Si vous disposez d’éléments DITA personnalisés, définissez-les dans le fichier `ditaElems.xml` disponible à l’emplacement suivant :

   `/libs/fmdita/config/ditaElems.xml`

1. Créez un noeud de recouvrement du dossier `config` dans le noeud `apps`.

1. Accédez au fichier de configuration disponible dans le noeud `apps` :

   `/apps/fmdita/config/ditaElems.xml`

   Le fichier `ditaElems.xml` contient un seul paramètre configurable :

   - Dans le paramètre `elem` , spécifiez le nom de l’élément personnalisé que vous souhaitez utiliser dans vos documents DITA convertis. Cet élément serait transmis tel quel dans les documents DITA générés.

1. Si vous souhaitez spécifier des attributs supplémentaires, définissez-les dans le fichier `style2attrMap.xml` disponible à l’emplacement suivant :

   `/libs/fmdita/config/style2attrMap.xml`

1. Créez un noeud de recouvrement du dossier `config` dans le noeud `apps`.

1. Accédez au fichier de configuration disponible dans le noeud `apps` :

   `/apps/fmdita/config/style2attrMap.xml`

   Le fichier `style2attrMap.xml` contient les paramètres configurables suivants :

   - Dans le paramètre `fmStyle` , spécifiez le format source utilisé dans le document de FrameMaker que vous souhaitez mapper.

   - Dans l’élément `ditaAttr` , spécifiez l’attribut DITA à mapper avec le format source.

   - Dans l’élément `ditaVal` , spécifiez la valeur de l’attribut mappé. Si vous ne disposez d’aucune valeur, vous pouvez laisser cette entrée vide.

1. Enregistrez le fichier `style2attrMap.xml`.

1. Après avoir configuré les paramètres requis dans le fichier `style2attrMap.xml`, connectez-vous à AEM et ouvrez l’interface utilisateur d’Assets.

1. Accédez au document de FrameMaker à convertir et cliquez dessus.

   La console de mappage DITA apparaît et affiche la liste des paramètres prédéfinis de sortie disponibles pour générer la sortie.

1. Sélectionnez le format de sortie DITA et configurez les paramètres requis.

   >[!NOTE]
   >
   > Vous devez utiliser le même fichier de paramètres \(.sts\) que celui créé dans FrameMaker. Spécifiez également le Nom des paramètres et le Chemin de destination.

1. Cliquez sur l&#39;icône **Générer** pour lancer le processus de génération de sortie.


En utilisant le bloc `<attrMap> </attrMap>`, vous pouvez définir un ou plusieurs blocs de configurations pour la conversion. Selon le contenu, vous pouvez avoir un fichier .dita et un fichier .ditamap comme fichiers convertis.

## Migration de tout autre document structuré {#id1949B0590YK}

AEM Guides vous permet de convertir vos documents structurés existants en documents DITA valides. Vous devez spécifier les emplacements des dossiers d’entrée et de sortie, l’emplacement de votre fichier de transformation, l’extension avec laquelle la sortie finale est enregistrée et si une nouvelle version du document est requise ou non.

Pour convertir vos documents structurés existants au format DITA, procédez comme suit :

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite.

1. Accédez au fichier de configuration par défaut disponible à l’emplacement suivant :

   `/libs/fmdita/config/XSLConfig.xml`

1. Créez un noeud de recouvrement du dossier `config` dans le noeud `apps`.

1. Accédez au fichier de configuration disponible dans le noeud `apps` :

   `/apps/fmdita/config/XSLConfig.xml`

   Le fichier `XSLConfig.xml` contient les paramètres configurables suivants :

   - Dans l’élément `inputDir` , spécifiez l’emplacement de votre dossier d’entrée dans lequel vos documents structurés sources sont disponibles. Par exemple, si vos documents structurés sont stockés dans un dossier nommé `xsltodita` dans le dossier `projects`, indiquez l’emplacement comme suit : `/content/dam/projects/xsltodita/`

   - Dans l’élément `outputDir` , spécifiez l’emplacement de votre dossier de sortie ou conservez l’emplacement de sortie par défaut. Si le dossier de sortie spécifié n’existe pas sur DAM, le workflow de conversion crée le dossier de sortie.

   - Dans l’élément `xslFolder` , spécifiez l’emplacement du dossier où sont stockés les fichiers de transformation XSL.

   - Dans l’élément ``xslPath`` , spécifiez l’emplacement du fichier .XSL principal utilisé pour lancer le processus de conversion.

   - Dans l’élément ``outputExt`` , spécifiez les extensions de fichier du fichier de sortie final créé à partir du flux de transformation.

   - Pour l’élément `createRev`, indiquez si une nouvelle version de la rubrique DITA convertie doit être créée \(`true`\) ou non \(`false`\).

1. Enregistrez le fichier `XSLConfig.xml`.

1. Après avoir configuré les paramètres requis dans le fichier `XSLConfig.xml`, connectez-vous à AEM et ouvrez l’interface utilisateur d’Assets.

1. Accédez à l’emplacement du dossier d’entrée \(`xsltodita`\).

1. Chargez les documents structurés source dans ce dossier. Pour plus d’informations sur le chargement de contenu sur DAM, voir [Chargement de contenu DITA existant](migrate-content-upload-existing-dita-content.md#).


En utilisant le bloc `<config> </config>`, vous pouvez définir un ou plusieurs blocs de configurations pour la conversion. Le workflow de conversion est exécuté et la sortie finale sous la forme d’une rubrique DITA est enregistrée à l’emplacement spécifié dans l’élément `outputDir` .

**Rubrique parente :**&#x200B;[ Migrer le contenu existant](migrate-content.md)
