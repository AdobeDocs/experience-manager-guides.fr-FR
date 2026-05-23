---
title: Recouvrez les balises HTML dans une sortie AEM Sites non héritée
description: Configurez les paramètres vidéo et d’image pour la sortie aem sites en fonction du mappage des composants principaux
feature: Installation
role: Admin
level: Experienced
exl-id: 726420e0-fe52-4334-b72a-8eb8bcae4d6c
TQID: https://experienceleague.adobe.com/wWeg9MdnMPXIIQWSjrr5oiQKIqEroCHZY6Oph0wAQ38
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 168
ht-degree: 0%

---

# Recouvrir les balises HTML dans la sortie AEM Sites

Vous pouvez ajouter et personnaliser des balises HTML dans la sortie AEM Sites générée à l’aide du paramètre prédéfini AEM Sites basé sur le mappage des composants principaux à partir de l’éditeur web. Pour personnaliser les balises HTML, vous pouvez incruster le fichier `config.xml`. Vous pouvez, par exemple, configurer les zones cliquables et vidéo dans la sortie AEM Sites.

Effectuez les étapes suivantes pour recouvrir et mettre à jour le fichier `config.xml` :

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite .

1. Accédez au fichier de configuration disponible à l’emplacement suivant :

   `/libs/cq/xssprotection/config.xml`

1. Créez un nœud de recouvrement du dossier `xssprotection` dans le nœud des applications.

1. Accédez au fichier de configuration disponible dans le nœud `apps` :

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

Zones cliquables :

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




En savoir plus sur les bonnes pratiques relatives à la [sécurité](https://experienceleague.adobe.com/fr/docs/experience-manager-65/content/implementing/developing/introduction/security).
