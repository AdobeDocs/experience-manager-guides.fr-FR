---
title: Recouvrez les balises d’HTML dans une sortie AEM Sites non héritée.
description: Configurez les paramètres vidéo et d’image pour la sortie d’aem Sites en fonction du mappage des composants principaux.
feature: Installation
role: Admin
level: Experienced
source-git-commit: 8310ae8d2e2eeda0fcfba9ec50650c806263cd49
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%

---


# Recouvrement des balises d’HTML dans la sortie AEM Sites

Vous pouvez ajouter et personnaliser des balises d’HTML dans la sortie AEM Sites générée à l’aide du paramètre prédéfini AEM Sites en fonction du mappage des composants principaux à partir de l’éditeur web. Pour personnaliser les balises d’HTML, vous pouvez superposer le fichier `config.xml`. Par exemple, vous pouvez configurer les zones cliquables et vidéo dans la sortie AEM Sites.

Effectuez les étapes suivantes pour superposer et mettre à jour le fichier `config.xml` :

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite.

1. Accédez au fichier de configuration disponible à l’emplacement suivant :

   `/libs/fmdita/cq/xssprotection/config.xml`

1. Créez un noeud de recouvrement du dossier `xssprotection` dans le noeud apps.

1. Accédez au fichier de configuration disponible dans le noeud `apps` :

   `/apps/fmdita/config/config.xml`

1. Mettez à jour les balises suivantes pour les vidéos et les images. Enregistrez ensuite le fichier.

Vidéos :

```XML
    <tag name="video" action="validate">
   	<attribute name="src">
      <regexp-list>
        <regexp name="anything"/>
      </regexp-list>
    </attribute>
    <attribute name="width">
       <regexp-list>
           <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="height">
       <regexp-list>
          <regexp name="anything"/>
       </regexp-list>
     </attribute>
     <attribute name="data">
       <regexp-list>
         <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="class">
       <regexp-list>
           <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="poster">
      <regexp-list>
        <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="controls">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    </tag>
    <tag name="source" action="validate">
      <attribute name="src">
        <regexp-list>
           <regexp name="anything"/>
        </regexp-list>
      </attribute>
    </tag>
```

Mappages :

```XML
    	<tag name="map" action="validate">
	<attribute    name="name">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
    </tag>
    <!-- Image & image related tags -->
    <tag name="img" action="validate">
	<attribute name="src" onInvalid="removeTag">
		<regexp-list>
			<regexp name="onsiteURL"/>
			<regexp name="offsiteURL"/>
		</regexp-list>
	</attribute>
	<attribute name="name"/>
	<attribute name="alt"/>
	<attribute name="height"/>
	<attribute name="width"/>
	<attribute name="border"/>
	<attribute name="align"/>
	<attribute name="usemap">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
	<attribute name="hspace">
		<regexp-list>
			<regexp name="number"/>
		</regexp-list>
	</attribute>
	<attribute name="vspace">
		<regexp-list>
			<regexp name="number"/>
		</regexp-list>
	</attribute>
    </tag>
    <tag name="area" action="validate">
	<attribute name="shape">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
	<attribute name="coords">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
	<attribute name="href">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
   </tag>
```




En savoir plus sur les bonnes pratiques de [Security](https://experienceleague.adobe.com/fr/docs/experience-manager-65/content/implementing/developing/introduction/security).