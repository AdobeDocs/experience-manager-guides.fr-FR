---
title: Propagation des métadonnées AEM Assets vers la sortie générée par le plug-in DITA-OT
description: Configuration du plug-in et du contenu DITA-OT dans AEM pour envoyer les métadonnées vers la sortie générée
exl-id: ba9db5a1-f499-48d9-976c-528fe56fd619
TQID: https://experienceleague.adobe.com/tK5b6Z1zdJVa7ghEx4CEYELjpSO2D1ZJVdWKd3NNxvg
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2:
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 971
ht-degree: 0%

---

# Propagation des métadonnées AEM Assets vers la sortie générée par le plug-in DITA-OT

Dans cet article, nous expliquerons comment implémenter des modifications apportées au plug-in DITA-OT pour lire le _metadata.xml (disponible dans les fichiers temporaires)_ et utiliser les propriétés, transmises par le workflow de publication AEM Guides, dans les plug-ins DITA-OT et les définir dans la sortie générée.

À un niveau élevé, voici les étapes que vous apprendrez dans cet article :
- Définition de métadonnées sur le paramètre prédéfini de sortie d’un ditamap dans AEM Guides
- Lors de la génération de la sortie, accédez à ce fichier metadata.xml dans le répertoire temporaire DITA-OT
- Implémentation dans le plug-in DITA-OT pour lire ce fichier _metadata.xml_ et à l&#39;aide des propriétés disponibles dans la sortie générée
- Vérification de la sortie générée pour afficher les métadonnées propagées

## Contexte

Avec AEM Guides, vous pouvez utiliser des modules externes DITA-OT pour publier dans les formats de sortie de votre choix à l’aide des modules externes configurés.
vous pouvez également transmettre les métadonnées des ressources gérées dans la gestion des ressources numériques AEM au processus DITA-OT pour les utiliser dans la sortie générée. Consultez la documentation sur [comment configurer ditamap/topics pour transmettre les métadonnées via le paramètre prédéfini de sortie](https://experienceleague.adobe.com/fr/docs/experience-manager-guides/using/user-guide/output-gen/pass-metadata-dita-ot)


## Hypothèses

Vous disposez d’une configuration d’AEM avec AEM Guides version 4.4.0/2024.6 ou supérieure
Vous connaissez déjà le fonctionnement de DITA-OT et sa structure de répertoires


## Étapes expliquées

### Définition des métadonnées sur la ressource

Avec le schéma de métadonnées AEM Assets, vous pouvez créer des champs de propriété personnalisés pour Assets dans AEM et les utilisateurs peuvent affecter des métadonnées aux ressources. Prenons un exemple de ressource _topic_ dans laquelle une métadonnée nommée _customprop_ peut être définie. Consultez la capture d’écran ci-dessous :

![Définition des propriétés dans l’éditeur de métadonnées d’une ressource](../../assets/publishing/assets-metadata-properties-ui-customprop.png)


### Configuration des métadonnées sur le paramètre prédéfini de sortie ditamap à transmettre à DITA-OT

Configurez le paramètre prédéfini de sortie de votre choix sur la carte pour exporter des métadonnées et les transmettre à DITA-OT.
Supposons que nous créions une sortie HTML5 à l’aide d’un plug-in DITA-OT, tel que _adobe.html_.
Consultez la capture d’écran ci-dessous pour comprendre comment configurer le paramètre prédéfini de sortie pour un mappage afin de transmettre des métadonnées au plug-in DITA-OT.
1. Ouvrez un mappage et accédez à l’onglet _Output_ pour ce mappage, ouvrez le paramètre prédéfini HTML5, puis cliquez sur l’onglet _Avancé_. Sur celui-ci, définissez le nom de la transformation _adobe.html_ (il s’agit du plug-in que nous allons configurer et utiliser pour notre exemple, vous pouvez également définir votre plug-in personnalisé)
2. Définissez _Conserver les fichiers temporaires_ pour pouvoir télécharger les fichiers temporaires et vérifier comment le fichier metadata.xml est formé, vous pouvez l’utiliser pour le développement
3. Sélectionnez les propriétés de métadonnées à transmettre à DITA-OT via metadata.xml. Dans cet exemple, supposons que nous voulions transmettre _dc:title_ et _customprop_
4. Enregistrez le paramètre prédéfini et générez la sortie
5. Téléchargez le fichier temporaire à l’aide du bouton affiché sur le préréglage

Consultez la capture d’écran ci-dessous pour comprendre les étapes ci-dessus :
![Configuration du paramètre prédéfini de sortie pour qu’un mappage transmette des métadonnées](../../assets/publishing/map-outputpreset-html5-customprop.png)


### Mise en œuvre du plug-in DITA-OT

#### Accès au fichier metadata.xml dans le répertoire temporaire

Dans le package des fichiers temporaires téléchargés, vous remarquerez un fichier metadata.xml où vous pouvez voir la structure des propriétés et des valeurs (voir la capture d’écran ci-dessous)
![structure et éléments metadata.xml](../../assets/publishing/publish-tempfiles-metadata-structure.png)

##### Présentation de metadata.xml

- Ce fichier contient la liste de toutes les ressources publiées, chacune d’elles ayant :
   - chemin du fichier dans le répertoire DITA [attribut id de l&#39;élément Path]
   - et la liste des paires de valeurs de propriété de métadonnées [sous l’élément _metadata_]

```
        <Path id="topics\about-this-document.dita">
            <sourceProps>
                ...
            </sourceProps>
            <metadata>
                <meta isArray="false" key="dc:title">About This Document</meta>
                <meta isArray="false" key="customprop">customval</meta>
            </metadata>
        </Path>
```

#### Accès aux métadonnées de chaque ressource dans le plug-in DITA-OT

Pour que le plug-in DITA-OT lise le fichier _metadata.xml_ et les propriétés qui y sont disponibles, nous devons effectuer les opérations suivantes :
- Définissez les paramètres de plug-in personnalisés dans le fichier _plugins.xml_, où définissent les paramètres et l’intégrateur pour l’initialisation du plug-in, notre fichier d’exemple de plug-in se présentera comme suit :

```
<?xml version="1.0" encoding="UTF-8"?>
<plugin id="com.adobe.html">
    <require plugin="org.dita.html5"/>
    <feature extension="dita.conductor.transtype.check" value="adobe.html"/>
    <feature extension="ant.import" file="integrator.xml"/>
    <feature extension="dita.conductor.html5.param" file="params.xml"/>
    <feature extension="package.version" value="2024.1"/>
</plugin>
```

- Au lancement du plug-in :
   - définissez une variable pour pointer vers le fichier metadata.xml, c’est-à-dire dans le fichier _integrator.xml_ sous le plug-in, définissez une propriété pour définir le chemin d’accès du fichier de métadonnées, et
   - définissez le fichier qui exécute les règles de transformation xsl personnalisées, c’est-à-dire _args.xsl_, qui dans notre cas pointera vers le fichier _xsl/adobe-html5.xsl_.
Reportez-vous au code ci-dessous :

```
    <property name="adobe.html.xsl.dir" value="${dita.plugin.com.adobe.html.dir}${file.separator}xsl${file.separator}"/>
    <property name="args.xsl" location="${adobe.html.xsl.dir}adobe-html5.xsl" />
    <dirname property="input.dirname" file="${args.input}"/>
    <makeurl file="${input.dirname}/metadata.xml" property="metadata.url"/>
```

- Transmettez la valeur de la variable _metadata.url_ au XSL personnalisé pour l’utiliser selon vos besoins, c’est-à-dire que dans le _param.xml existant/créé_ transmettez le paramètre au plug-in. Consultez ci-dessous un exemple de fichier params.xml :

```
    <?xml version="1.0" encoding="UTF-8"?>
    <params xmlns:if="ant:if">
        <param name="metadata.url" expression="${metadata.url}" if:set="metadata.url"/>
    </params>
```

- Dans le fichier de transformation XSL personnalisé __ vous pouvez lire les valeurs de métadonnées à partir du fichier de métadonnées et les définir dans la sortie comme vous le souhaitez. Dans cet exemple, nous allons ajouter les valeurs de métadonnées à la balise html head > meta . Reportez-vous au code ci-dessous :

```
<xsl:import href="plugin:org.dita.html5:xsl/dita2html5.xsl"/>
    <xsl:param name="metadata.url"/>
    <xsl:template name="copyright">
        <xsl:if test="doc-available( $metadata.url )">
            <xsl:variable name="docName" select="tokenize( base-uri(), '/' )[ last() ]"/>
            <xsl:variable name="doc" select="doc( $metadata.url )"/>
            <xsl:for-each select="$doc//Path[ ends-with( @id, concat( '\', $docName ) ) ]/metadata/meta">
                <meta name="{ @key }" content="{ . }"/>
            </xsl:for-each>
        </xsl:if>
    </xsl:template>
```

Reportez-vous à la capture d’écran ci-dessous en mettant en évidence les étapes ci-dessus.
![procédure d’implémentation du plug-in dita-ot](../../assets/publishing/publishing-metadata-dita-ot-plugin-implementation.png)


### Test de l’implémentation du plug-in

Vous pouvez tester le plug-in en exécutant la commande suivante pour le tester avec les fichiers temporaires téléchargés à partir d’AEM (qui comporte le contenu du mappage et son fichier metadata.xml)

```
./dita --input=docsrc/samples/HTML5/aem_forms_documentation.ditamap --format=adobe.html
```

En supposant que vous ayez copié les fichiers temporaires téléchargés dans le répertoire « DITA-OT/docsrc/samples/HTML5 ».
Vous pouvez également télécharger l’exemple donné dans la section Ressources ci-dessous.

Lorsque la commande ci-dessus est exécutée, vous pouvez vérifier la sortie dans le répertoire « DITA-OT/bin/out », où vous pouvez vérifier les fichiers html générés pour le topic « about-this-document.dita » qui aura les métadonnées personnalisées dans l&#39;élément _head_

```
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <meta charset="UTF-8">
    <meta name="copyright" content="(C) Copyright 2024">
    <meta name="DC.format" content="HTML5">
    <meta name="DC.identifier" content="GUID-f193ea85-989d-4d80-99e2-2f5dea3d5310">
    <meta name="DC.language" content="en-US">
    <meta name="dc:title" content="About This Document">
    <meta name="customprop" content="customval">
    <title>About This Document</title>
</head>
```

### Déploiement

Une fois que vous avez développé le plug-in DITA-OT, vous pouvez l&#39;intégrer dans DITA-OT à l&#39;aide de la commande _dita —install_ sous le répertoire DITA-OT, et le déployer sur le serveur AEM [voir cet article pour plus de détails](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/steps-to-setup-a-custom-dita-ot/td-p/407659?profile.language=fr)


## Ressources

1. Exemples de fichiers temporaires téléchargés à partir de l’exemple de ditamap - [télécharger en utilisant ce lien](../../assets/publishing/sample-temp-html5-adobe.html-content.zip)
2. Plug-in DITA-OT avec la mise en œuvre expliquée ci-dessus [télécharger à l’aide de ce lien](../../assets/publishing/sample-custom-plugin-com.adobe.html.zip)
