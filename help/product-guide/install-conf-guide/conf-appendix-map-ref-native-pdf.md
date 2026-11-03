---
title: Configurer le rendu de l’annexe pour les références de mappage dans la sortie PDF native
description: Découvrez comment configurer Experience Manager Guides pour effectuer le rendu des rubriques ajoutées sous une sous-carte dans une annexe en tant que contenu d’annexe dans la sortie native de PDF.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 63ae0f947d50646bed34cd815db6b9fb585fc015
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%
---

# Configurer le rendu de l’annexe pour les références de mappage dans la sortie PDF native

Dans la sortie PDF native, les rubriques référencées dans un sous-mappage à l’intérieur d’un élément de `<appendix>` peuvent être rendues sous forme de chapitres au lieu d’annexes. Par défaut, Experience Manager Guides classe les références de mappage par nom d’élément, et ces informations sont perdues une fois les mappages aplatis pendant le traitement.

Utilisez ce paramètre pour classer les références de mappage à l&#39;aide de l&#39;attribut `class` généré par DITA-OT à la place. Les rubriques d’une sous-carte d’annexe sont ensuite rendues en annexes.

>[!NOTE]
>
>Ce paramètre modifie la manière dont les références de mappage sont classées. Il est désactivé par défaut. Activez-le uniquement si votre contenu place les rubriques dans une sous-carte au sein d’une `<appendix>` et que vous les voyez rendues sous forme de chapitres dans la sortie Native PDF.

## Quand utiliser cette configuration ?

Prenons l’exemple suivant d’une carte :

- Un élément `<appendix>` fait directement référence à des sujets. Ces rubriques sont rendues en tant qu’annexes dans le PDF généré.

  ```XML
  <booktitle>
      <mainbooktitle>Product Guide</mainbooktitle>
    </booktitle>
    <frontmatter>
      <booklists>
        <toc/>
        <tablelist/>
      </booklists>
      <preface href="topics/preface.dita">
      </preface>
    </frontmatter>
    <chapter class="foo" href="topics/getting-started.dita">
    </chapter>  
    <appendix href="topics/appendix-reference-tables.dita">
    </appendix>
    <appendix href="topics/appendix-troubleshooting.dita">
    </appendix>
    <backmatter>
      <booklists>
        <indexlist/>
      </booklists>
    </backmatter>
  </bookmap>`
  ```

- Un autre élément de `<appendix>` fait référence à un sous-mappage, qui fait référence aux rubriques à l’aide de `<topicref>`.

  ```xml
  <booktitle>
      <mainbooktitle>Product Guide</mainbooktitle>
    </booktitle>
    <frontmatter>
      <booklists>
        <toc/>
        <tablelist/>
      </booklists>
      <preface href="topics/preface.dita">
      </preface>
    </frontmatter>
    <chapter class="foo" href="topics/getting-started.dita">
    </chapter>  
    <appendix format="ditamap" href="submap-for-appendix.ditamap" type="map">
    </appendix>
    <backmatter>
      <booklists>
        <indexlist/>
      </booklists>
    </backmatter>
  </bookmap>
  ```

  La sous-carte-pour-annexe :

  ```xml
  <map id="GUID-cc306264-825c-455e-89db-d27af9197a2f">
    <title>submap-for-appendix</title>
    <topicref href="topics/appendix-reference-tables.dita" type="reference">
    </topicref>
    <topicref href="topics/appendix-troubleshooting.dita" type="topic">
    </topicref>
  </map>
  ```

Sans cette configuration, les rubriques de la première annexe sont rendues en tant qu’annexes, mais les rubriques de la sous-carte sont rendues en tant que chapitres. Seules les rubriques sont publiées ; le sous-mappage lui-même est utilisé pour la hiérarchie et n’apparaît pas dans la sortie.

## Configurer le paramètre

Vous trouverez ci-dessous les instructions pour configurer ce paramètre :

1. Suivez les instructions fournies dans [Remplacements de la configuration](../install-conf-guide/download-install-config-override.md) pour créer le fichier de configuration.

2. Dans le fichier de configuration, fournissez les détails (propriété) suivants :

   | PID | Clé de la propriété | Valeur de la propriété |
   | --------------------------------------- | -------------------------------- | ----------------------------- |
   | `com.adobe.fmdita.config.ConfigManager` | `guides.publish.config` | {USE_DITA_OT_GENERATED_CLASS »: false} |

3. Définissez la valeur sur `true` pour activer le paramètre, puis déployez la configuration à l’aide de Cloud Manager.