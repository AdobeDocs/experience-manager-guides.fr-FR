---
title: Propagation des métadonnées AEM Assets vers la sortie générée par le module externe DITA-OT
description: Configuration du module externe et du contenu DITA-OT dans AEM pour pousser les métadonnées vers la sortie générée
source-git-commit: b48f5a342989d3be48bbc1e8af51a2ce477d0ac7
workflow-type: tm+mt
source-wordcount: '912'
ht-degree: 0%

---


# Propagation des métadonnées AEM Assets vers la sortie générée par le module externe DITA-OT

Dans cet article, nous expliquerons comment mettre en oeuvre les modifications apportées au module externe DITA-OT pour lire le fichier metadata.xml _(disponible dans les fichiers temporaires)_ et utiliser les propriétés, transmises par le processus de publication AEM Guides, dans les modules externes DITA-OT et les définir dans la sortie générée.

À un niveau élevé, vous trouverez ci-dessous les étapes que vous apprendrez dans cet article :
- Définition de métadonnées sur le paramètre prédéfini de sortie d’un fichier ditamap dans AEM Guides
- Lors de la génération de la sortie, accédez à ce fichier metadata.xml dans le répertoire temporaire DITA-OT.
- Mise en oeuvre dans le module externe DITA-OT pour lire ce _metadata.xml_ et utiliser les propriétés disponibles dans la sortie générée
- Vérification de la sortie générée pour afficher les métadonnées propagées

## Contexte

Avec AEM Guides, vous pouvez utiliser des modules externes DITA-OT pour publier dans les formats de sortie de votre choix à l’aide des modules externes configurés, et
vous pouvez également transmettre des métadonnées des ressources gérées dans AEM DAM au processus DITA-OT pour les utiliser dans la sortie générée. consultez la documentation sur [la configuration de ditamap/rubriques pour transmettre des métadonnées par le biais du paramètre prédéfini de sortie](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/user-guide/output-gen/pass-metadata-dita-ot)


## Hypothèses

Vous disposez d’une configuration AEM avec AEM Guides version 4.4.0/2024.6 ou ultérieure.
Vous connaissez déjà le fonctionnement de DITA-OT et sa structure de répertoires.


## Description des étapes

### Définition des métadonnées sur la ressource

Avec le schéma de métadonnées AEM Assets, vous pouvez créer des champs de propriété personnalisés pour Assets dans AEM, et les utilisateurs peuvent affecter des métadonnées aux ressources. Prenons l’exemple d’une ressource _topic_ où une métadonnée nommée _customprop_ peut être définie pour un exemple. Consultez la capture d’écran ci-dessous :

![ Définition des propriétés dans l’éditeur de métadonnées d’une ressource](../../assets/publishing/assets-metadata-properties-ui-customprop.png)


### Configuration des métadonnées sur le paramètre prédéfini de sortie ditamap à transmettre à DITA-OT

Configuration du paramètre prédéfini de sortie de votre choix sur la carte pour exporter des métadonnées et les transmettre à DITA-OT
Supposons que nous générions une sortie HTML5 à l’aide d’un module externe DITA-OT comme suit : _adobe.html_.
Voir la capture d’écran ci-dessous pour comprendre comment configurer le paramètre prédéfini de sortie pour une carte afin de transmettre des métadonnées au module externe DITA-OT.
1. Ouvrez une carte, accédez à l’onglet _Output_ pour cette carte et ouvrez le paramètre prédéfini HTML5, puis cliquez sur l’onglet _Avancé_, sur cet onglet définissez le nom de la transformation comme _adobe.html_ (il s’agit du module externe que nous allons configurer et utiliser pour notre exemple, vous pouvez également définir votre module externe personnalisé).
2. Définissez _Conserver les fichiers temporaires_ pour pouvoir télécharger les fichiers temporaires et vérifier comment le fichier metadata.xml est formé. Vous pouvez l’utiliser pour le développement.
3. Sélectionnez les propriétés de métadonnées à transmettre à DITA-OT via metadata.xml. Dans cet exemple, supposons que nous souhaitions transmettre _dc:title_ et _customprop_
4. Enregistrez le paramètre prédéfini, puis générez la sortie.
5. Téléchargez le fichier temporaire à l’aide du bouton affiché sur le paramètre prédéfini

Reportez-vous à la capture d’écran ci-dessous pour comprendre les étapes ci-dessus :
![ Configuration d’un paramètre prédéfini de sortie pour une carte afin de transmettre des métadonnées](../../assets/publishing/map-outputpreset-html5-customprop.png)


### Mise en oeuvre du module externe DITA-OT

#### Accès au fichier metadata.xml dans un répertoire temporaire

Dans le package de fichiers temporaires téléchargé, vous remarquerez un fichier metadata.xml dans lequel vous pouvez voir la structure des propriétés et des valeurs (voir la capture d’écran ci-dessous).
![Structure et constructions de metadata.xml](../../assets/publishing/publish-tempfiles-metadata-structure.png)

##### Présentation de metadata.xml

- Ce fichier contient la liste de toutes les ressources publiées, chacune ayant :
   - chemin du fichier dans le répertoire DITA [attribut id de l’élément Path]
   - et liste des paires de valeurs de propriété de métadonnées [sous l’élément _metadata_ ]

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

#### Accès aux métadonnées de chaque ressource dans le module externe DITA-OT

Pour que le module externe DITA-OT lise le _metadata.xml_ et les propriétés qui y sont disponibles, nous devons procéder comme suit :
- Définissez les paramètres personnalisés du module externe dans _plugins.xml_, où définissez les paramètres et l’intégrateur pour l’initialisation du module externe. Notre exemple de fichier de module externe se présentera comme suit :

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

- Au lancement du module externe :
   - définissez une variable pour qu’elle pointe vers le fichier metadata.xml , c’est-à-dire dans le fichier _integrator.xml_ sous le module externe, définissez une propriété pour définir le chemin d’accès du fichier de métadonnées, et
   - définissez le fichier qui exécute des règles de transformation xsl personnalisées, c&#39;est-à-dire _args.xsl_, qui dans notre cas pointe vers le fichier _xsl/adobe-html5.xsl_.
Consultez le code ci-dessous :

```
    <property name="adobe.html.xsl.dir" value="${dita.plugin.com.adobe.html.dir}${file.separator}xsl${file.separator}"/>
    <property name="args.xsl" location="${adobe.html.xsl.dir}adobe-html5.xsl" />
    <dirname property="input.dirname" file="${args.input}"/>
    <makeurl file="${input.dirname}/metadata.xml" property="metadata.url"/>
```

- Transmettez la valeur de la variable _metadata.url_ au fichier XSL personnalisé pour l’utiliser selon vos besoins, c’est-à-dire dans le fichier _param.xml_ existant/créé, transmettez le paramètre au module externe, voir ci-dessous un exemple de fichier params.xml :

```
    <?xml version="1.0" encoding="UTF-8"?>
    <params xmlns:if="ant:if">
        <param name="metadata.url" expression="${metadata.url}" if:set="metadata.url"/>
    </params>
```

- Dans le fichier de transformation XSL personnalisé _xsl/adobe-html5.xsl_, vous pouvez lire les valeurs de métadonnées du fichier de métadonnées et les définir en sortie comme vous le souhaitez. Dans cet exemple, nous allons ajouter les valeurs de métadonnées aux balises html head > meta . Consultez le code ci-dessous :

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

Reportez-vous à la capture d’écran ci-dessous pour mettre en évidence les étapes ci-dessus
![ étapes pour mettre en oeuvre le module externe dita-ot](../../assets/publishing/publishing-metadata-dita-ot-plugin-implementation.png)


### Test de l’implémentation du module externe

Vous pouvez tester le module externe en exécutant la commande suivante pour le tester avec les fichiers temporaires téléchargés à partir d’AEM (qui comporte le contenu map et son fichier metadata.xml).

```
./dita --input=docsrc/samples/HTML5/aem_forms_documentation.ditamap --format=adobe.html
```

En supposant que vous ayez copié les fichiers temporaires téléchargés dans le répertoire &quot;DITA-OT/docsrc/samples/HTML5&quot;.
Vous pouvez également télécharger l’exemple donné dans la section des ressources ci-dessous.

Lorsque la commande ci-dessus est exécutée, vous pouvez vérifier la sortie dans le répertoire &quot;DITA-OT/bin/out&quot;, où vous pouvez vérifier les fichiers HTML générés pour la rubrique &quot;about-this-document.dita&quot; qui contiendra les métadonnées personnalisées dans l’élément _head_ .

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

Une fois que vous avez développé le module externe DITA-OT, vous pouvez l’intégrer dans DITA-OT à l’aide de la commande _dita —install_ sous le répertoire DITA-OT, et le déployer sur le serveur AEM [reportez-vous à cet article pour plus de détails](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/steps-to-setup-a-custom-dita-ot/td-p/407659?profile.language=fr)


## Ressources

1. Exemples de fichiers temporaires téléchargés à partir de l’exemple de fichier ditamap - [télécharger à l’aide de ce lien](../../assets/publishing/sample-temp-html5-adobe.html-content.zip)
2. Module externe DITA-OT avec mise en oeuvre décrite ci-dessus [télécharger à l’aide de ce lien](../../assets/publishing/sample-custom-plugin-com.adobe.html.zip)