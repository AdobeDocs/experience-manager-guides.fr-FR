---
title: Annexe
description: Découvrez comment préparer des documents d’InDesign pour la migration
exl-id: 71b09039-b220-45f3-b334-c23f5b09dadc
feature: InDesign File Conversion, Troubleshooting
role: Admin
level: Experienced
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '2852'
ht-degree: 0%

---

# Annexe {#id195AD0L60Y4}

## Dépannage d’AEM Guides

Une fois que vous avez installé et configuré AEM Guides, vous pouvez résoudre les problèmes.

## Validation des références

Vous pouvez exécuter les scripts donnés pour valider les références. Ces scripts peuvent vous aider à identifier les références rompues, puis à les corriger ou les corriger.

- `/bin/fmdita/validatebtree?operation=validate` - indique les références de contenu rompues, mais ne les corrige pas.

- `/bin/fmdita/validatebtree?operation=patch` : répertorie les références de contenu rompues et les correctifs ou les corrige.


**Valider le script**

Effectuez les étapes suivantes pour vérifier les références, à l’aide du script de validation disponible dans le package de produits :

1. Exécutez le script de validation \[`/bin/fmdita/validatebtree?operation=validate`\] pour vérifier s’il existe de nouvelles références rompues.
1. Si le script de validation signale des erreurs, vous pouvez le corriger à l’aide du script de correctif.
1. Enregistrez les détails ci-dessous et, si nécessaire, partagez-les avec votre équipe de réussite client :
1. &#x200B;
   - Logs imprimés par le script de validation
- Package de &quot;`/content/fmdita/references`&quot;
- Tout autre détail requis en fonction du scénario signalé

**Script de correctif**

Effectuez les étapes suivantes pour corriger les références rompues à l’aide du script de correctif disponible dans le package de produits :

1. Exécutez le script de correctif `[/bin/fmdita/validatebtree?operation=patch]` pour corriger les références rompues. L’exécution du script prend quelques minutes et imprime les journaux au fur et à mesure de sa progression. Une fois l’exécution terminée, il imprime &quot;`Done`&quot; à la fin.

>[!NOTE]
>
> Il est recommandé de copier et d’enregistrer les journaux à des fins de référence.

1. Une fois le script de correctif exécuté avec succès, vous pouvez effectuer les vérifications suivantes :
1. &#x200B;
   - Vérifiez qu’un nouveau noeud &quot;`references_backup_<timestamp>"` a été créé sous `/content/fmdita`
- Vérifier que les références ont été corrigées

**Enregistreur**

Vous pouvez également créer un journal distinct pour cette exécution de script, selon les détails ci-dessous :

- Ajouter un journal sur la classe &quot;`adobe.fmdita.common.BTreeReferenceValidator`&quot;
- Définissez-le sur `DEBUG`

Le fichier journal créé enregistre toutes les informations relatives à l’exécution du script et s’avère utile lorsque la session du navigateur expire, tout en déclenchant le script à partir du navigateur.

## Préparation des fichiers d’InDesign pour la conversion {#id195DBF0045Z}

InDesign dote les auteurs d’un large éventail de fonctionnalités pour créer des documents attrayants et complexes. Cela signifie souvent que les différentes parties d’un document sont placées visuellement sur la page, mais sans tenter de fournir un flux entre ces zones de texte. Lorsque l’*ordre de lecture*’ des cadres de texte n’est pas défini, le fichier IDML contient des articles qui peuvent ne pas suivre un ordre significatif. Le résultat final sera une ou plusieurs rubriques DITA avec des paragraphes, des tableaux et des graphiques dans un ordre aléatoire.

Bien qu’il soit possible de modifier le contenu DITA dans un ordre raisonnable dans un éditeur DITA, il est beaucoup plus facile de corriger le fichier d’InDesign avant de créer le fichier IDML. Vous pouvez le faire sans modifier l’aspect du document source. Il permet également de rendre le document source accessible en définissant correctement l’ordre de lecture.

***Thread text frames***

InDesign utilise le terme *&#39;thread&#39;* pour le processus de liaison d’un cadre à un autre. Pour plus d’informations sur les cadres de texte de thread, voir la rubrique *[Texte de thread](https://helpx.adobe.com/in/indesign/using/threading-text.html)* dans la documentation InDesign.

***Images de chevauchement***

Pour des raisons de mise en page, certains documents InDesigns utilisent des cadres superposés non threads. Il peut être très difficile de fusionner ce contenu dans le thread principal. La meilleure option peut être de modifier le résultat dans l’environnement DITA.

***InDesign d’articles***

Chaque flux de contenu thread dans un document d’InDesign est appelé &quot;*story*&quot;. Pour de meilleurs résultats, il est recommandé de limiter le nombre d’articles. Cependant, certaines parties de votre document peuvent ne pas être nécessaires dans la sortie DITA. Par exemple, les pieds de page sont rarement nécessaires, mais ils peuvent apparaître au milieu d’une rubrique s’ils ne sont pas gérés avec précaution.

Le moyen le plus simple d’exclure du texte qui n’est pas obligatoire dans le document consiste à lui attribuer une *balise de paragraphe* spéciale qui n’est utilisée que pour le contenu indésirable. Par exemple, au lieu de réutiliser un *\[Paragraphe de base\]* pour le pied de page, créez une balise *Pied de page* dédiée. Ensuite, dans le fichier MapStyle, définissez simplement les paragraphes *Footer* à déposer comme suit :

```
<paraRule style="Footer" local="0" refactor="drop">
   <attributeRules createID="false"/>
</paraRule>
```

***Mappage aux doctypes DITA***

Il est essentiel que votre document source comporte au moins un style de paragraphe ou un élément pouvant marquer le début d’une rubrique. Il est courant que les documents utilisent *Heading1* comme nom des titres de niveau supérieur dans le document. Vous pouvez ensuite créer un mappage à partir de ce style vers un doctype DITA spécifique. Si votre document est bien organisé et que l’utilisation de *Heading1* est constante, vous obtiendrez de bons résultats.

***Plusieurs doctypes DITA***

Si certains des paragraphes *Heading1* doivent être convertis en différents doctypes DITA, dupliquez le style de paragraphe dans InDesign. Attribuez à ces styles un nom facile à reconnaître, tel que *Heading1\_genTask* ou *Heading1\_troubleshooting*, le cas échéant. Ensuite, configurez le fichier mapStyle comme illustré ci-dessous :

```
<doctypes>
   <doctypeParaRule style="Heading1" local="0" mapToDoctype="concept">
      <attributeRules createID="true"/>
   </doctypeParaRule>
   <doctypeParaRule style="Heading1_genTask" local="0" mapToDoctype=" generalTask">
      <attributeRules createID="true"/>
   </doctypeParaRule>
   <doctypeParaRule style="Heading1_troubleshooting" local="0"mapToDoctype=" troubleshooting">
      <attributeRules createID="true"/>
   </doctypeParaRule>
</doctypes>
```

***Documents d’InDesign structurés***

L’InDesign a une relation déroutante avec le XML. Bien qu’un document puisse inclure une DTD XML et que l’histoire principale puisse être valide par rapport à cette DTD, il est également possible de créer des documents hybrides où une partie du contenu est XML, mais aucune DTD n’est incluse. Il s’agit des cas indésirables pour une conversion réussie en DITA. Si un document contient des parties XML, essayez d’enregistrer la sortie au format XML et vérifiez si les résultats sont acceptables. Si ce n’est pas le cas, le contenu DITA comprend également du contenu non valide ou peut échouer complètement.

***Formatage de table***

La conversion des règles de formatage de tableau InDesign en formatage de tableau équivalent dans DITA est un processus complexe. Cela est dû aux fonctions de formatage riches disponibles dans les fichiers source par rapport aux options de base fournies par le modèle de tableau Oasis \(CALS\) utilisé dans DITA. L’alignement vertical et horizontal du texte est fourni et donne des résultats similaires bien que le texte Justifié soit toujours justifié en fonction de la direction du texte, tandis que l’InDesign permet l’alignement Gauche Justifiée et Droite Justifiée.

La gestion par InDesign des séparateurs de colonne et de ligne est à nouveau bien plus efficace que les options de base du modèle de tableau Oasis. InDesign fournit quatre bordures de cellules : type de bordure \(solide ou modèle\), épaisseur de bordure, couleur de bordure, teinte de bordure, couleur d’écart de bordure et teinte d’écart de bordure. Tous ces éléments doivent être associés aux bordures situées à droite et au bas de chaque cellule \(élément d’entrée\), où les seuls choix possibles sont 0 ou 1 : masquez la bordure ou affichez la bordure.

La réglementation des frontières en InDesign peut être appliquée aux niveaux suivants :

- Styles de tableau
- Styles de cellule
- Remplacements locaux sur chaque cellule

Le processus de conversion d’InDesign vers DITA applique la bordure comme suit :

- Les styles de tableau sont mappés à l’attribut `colspec/@colsep` pour les règles verticales. Les règles horizontales sont mappées à l’attribut `row/@rowsep`. Dans les deux cas, si la bordure n’est pas définie, l’attribut n’est pas créé.
- Les styles de cellule sont mappés aux attributs `entry/@colsep` et `entry/@rowsep`. Ces valeurs remplacent les bordures dérivées du style de tableau.
- Les remplacements locaux appliquent directement la mise en forme à la cellule et remplacent les styles de tableau et de cellule.

***Modèles de remplacement***

Les styles de tableau d’InDesign permettent aux options de rangement de colonne et de cellule de suivre un autre modèle. Bien que cette fonctionnalité soit prise en charge pour la conversion, les résultats ne seront visibles que lorsqu’un groupe de modèles est mappé pour afficher la règle \(1\) et que l’autre groupe de modèles est mappé pour masquer la règle \(0\).

## Préparation du fichier de mappage pour l’InDesign à la migration DITA {#id194AF0003HT}

La conversion DITA correcte requiert un fichier de mappage correspondant au contenu du document source. Pour les documents d’InDesign non structurés, cela signifie que tous les styles de paragraphe et les styles de caractère disponibles doivent être mappés. Pour les documents d’InDesign structurés XML, tous les éléments de la DTD associée doivent être mappés.

Les fichiers de mappage des documents d’InDesign non structurés et structurés sont différents. Cela est dû à des exigences de traitement plus complexes pour la conversion de contenu source non structuré en DITA.

Vous trouverez ci-dessous un exemple du fichier de mappage :

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE styleMap SYSTEM "mapStyle.dtd">
<styleMap xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="mapStyle.xsd" >
   <doctypes>
      <mapDoctypeParaRule root="itpx:stories" mapToDoctype="map">
         <attributeRules createID="true">
            <addNew name="outputclass" value="map"/>
         </attributeRules>
      </mapDoctypeParaRule>
      <doctypeParaRule style="Heading 1" local="0" mapToDoctype="concept">
         <attributeRules createID="true"/>
      </doctypeParaRule>
      <doctypeParaRule style="Heading A" local="0" mapToDoctype="topic">
         <attributeRules createID="true"/>
      </doctypeParaRule>
   </doctypes>
   <wrappingRules>
      <wrap elements="li+" context="number" wrapper="ol">
         <attributeRules createID="true"/>
      </wrap>
      <wrap elements="li+" context="bullet" wrapper="ul">
         <attributeRules createID="true"/>
      </wrap>
   </wrappingRules>
   <paragraphStyleRules>
      <paraRule style="Heading 2" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Heading 3" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="p[-|-|-|-|-|b|-|-]" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="p[-|-|-|-|-|n|-|-]" context="number" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="0" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Normal" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Normal" local="p[-|-|-|-|-|b|-|-]" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Title" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
   </paragraphStyleRules>
   <characterStyleRules>
      <charRule style="Bold" local="0" mapTo="b">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="Code" local="0" mapTo="codeph">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="[No character style]" local="c[Bold|-|-|-|-|-|-|-]" mapTo="b">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="[No character style]" local="c[Italic|-|-|-|-|-|-|-]" mapTo="i">
         <attributeRules createID="false"/>
      </charRule>
   </characterStyleRules>
</styleMap>
```

Le fichier de mappage est un fichier XML dont la structure est simple et qui répertorie tous les styles de paragraphe source et les codes de style de caractère. Le contenu du fichier est expliqué ci-dessous :

**Mappage de style**

Dans l’élément `styleMap` , vous pouvez spécifier deux attributs facultatifs - `@map_date` et `@map_version` pour enregistrer la version du fichier de mappage.

**Type de document**

L’élément `doctypes` répertorie le mappage DITA pris en charge et les mappages de rubrique.

**Mapper des règles de paragraphe de type de document**

L’élément `mapDoctypeParaRule` est obligatoire. Les attributs de cet élément ne doivent pas être modifiés, car l’élément racine du XML source est toujours mappé à l’élément `map` racine de la carte DITA.

**Règle de paragraphe de type de document**

L’élément `doctypeParaRule` est obligatoire. Cela permet au processus de conversion d’identifier le début d’une nouvelle rubrique. Normalement, l’attribut `@style` est utilisé seul avec l’attribut `@local` défini sur 0. Cependant, s’il existe toujours des remplacements de mise en forme locale sur le style choisi, vous devrez ajouter une règle pour chaque style, plus ses remplacements locaux. Cela est simple à reconnaître dans le fichier de mappage généré lorsqu’il est possible de trouver ceci ou similaire :

```
<paraRule style="Heading 1" local="0" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
<paraRule style="Heading 1" local="p[Italic|-|-|-|-|-|-|-]" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
```

Dans l’exemple ci-dessus, il existe deux éléments `paraRule` pour `@style` = &quot;Heading1&quot;. Créez simplement un élément `doctypeParaRule` équivalent avec l’attribut `@mapToDoctype` défini selon les besoins.

Les attributs utilisés dans le `doctypeParaRule` sont expliqués ci-dessous :

- `@style` : nom d’un style dans le document d’InDesign source.
- `@local` : Voir [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapToDoctype` : nom d’un type de rubrique DITA à partir d’une liste énumérée de tous les `doctypes` valides.

**Règles d’encapsulage des éléments**

Les règles d’encapsulation d’élément définissent les méthodes permettant d’encapsuler ou de déplacer des éléments dans le document entrant dans un élément prédéfini en fonction d’un ensemble de valeurs d’attribut.

***`wrap`element***

Il s’agit d’un élément facultatif. L’élément `wrap` répertorie les éléments qui seront encapsulés ou déplacés. L’encapsulage est généralement utilisé lorsqu’une série d’éléments doit se voir attribuer un élément parent commun. Par exemple, plusieurs éléments `li` sont encapsulés dans un élément `ol`. En outre, `wrap` peut être utilisé pour déplacer des éléments tels que des titres pour des figures et des tableaux.

Les attributs utilisés dans le `wrap` sont expliqués ci-dessous :

- `@element` : un signe plus après un nom d’élément indique que tous les éléments adjacents portant le même nom seront encapsulés dans l’élément nommé dans l’attribut `@wrapper`.
- `@wrapper` : nom de l’élément wrapping.
- `@context` : permet d’affiner davantage la manière dont un élément donné est encapsulé. L’exemple suivant montre un moyen de mapper une série d’éléments `li` dans une liste ordonnée `ol` ou une liste non ordonnée `ul` en fonction de la valeur `@context` \(le contexte est défini sur l’élément `paraRule`\) :

  ```
  <wrap elements="li+" context="number" wrapper="ol">
     <attributeRules createID="true"/>
  </wrap>
  <wrap elements="li+" context="bullet" wrapper="ul">
     <attributeRules createID="true"/>
  </wrap>
  ```


L’exemple suivant montre comment créer un élément `fig` à partir d’un élément `title` et d’un élément `image` :

- `@elements` : les éléments répertoriés et séparés par une virgule seront placés dans l’élément nommé dans l’attribut `@wrapper`. En raison de la pratique courante d’inclusion des titres de figure sous l’image, le titre sera l’élément `title` immédiatement après le `image`.

  La règle de retour automatique à la ligne suivante :

  ```
  <wrap elements="title, image" context="FigTitle" wrapper="fig">
     <attributeRules createID="true"/>
  </wrap>
  ```

  Convertit le XML intermédiaire suivant :

  ```
  <image href="Links/myImage.png" scale="59">
     <title>IDML2DITA workflow</title>
  ```

  Dans la structure de figure DITA valide suivante :

  ```
  <fig id="id397504">
     <title>IDML2DITA workflow</title>
     <image href="Links/myImage.png" scale="59">
  </fig>
  ```

- `@wrapper` : nom de l’élément wrapping.
- `@context` : permet d’affiner davantage la manière dont un élément donné est encapsulé \(le contexte est défini sur l’élément `paraRule`\).

L’exemple suivant montre comment déplacer un `title` dans un `table` :

- `@elements` : l’élément `title` situé immédiatement avant ou immédiatement après un `table` sera encapsulé dans l’élément nommé dans l’attribut `@wrapper`. Un prédicat de style XPath peut identifier la position de l’élément de titre comme `[before]` ou `[after]`.

  Exemple : la règle de retour à la ligne suivante :

  ```
  <wrap elements="title[before]" context="TableTitle" wrapper="table">
     <attributeRules createID="true"/>
  </wrap>
  ```

  Convertit le XML intermédiaire suivant :

  ```
  <title>IDML2DITA workflow</title>
  <table id="id289742" outputclass="BasicTable">
     <tgroup cols="2">
        <colspec colname="0" colwidth="0.7*">
           <colspec colname="1" colwidth="0.3*">
  ```

  Dans cette structure de figure DITA valide :

  ```
  <table id="id289742" outputclass="BasicTable">
     <title>IDML2DITA workflow</title>
     <tgroup cols="2">
        <colspec colname="0" colwidth="0.7*">
           <colspec colname="1" colwidth="0.3*">
  ```

- `@wrapper` : nom de l’élément wrapping.

- `@context` : permet d’affiner davantage la manière dont un élément donné est encapsulé \(le contexte est défini sur l’élément `paraRule`\).


**Règles de style de paragraphe**

Les éléments `paragraphStyleRule` sont décrits ci-dessous :

**&#x200B; `paraRule` élément**

L’élément `paraRule` est obligatoire. Cela permet de spécifier les règles de mappage pour tous les styles de paragraphe. Dans un document d’InDesign, tout le texte est contenu dans la sous-structure des styles de paragraphe, même les paragraphes sans style sont nommés `\[No paragraph style\]`. Les crochets indiquent un nom de style d’InDesign intégré.

>[!NOTE]
>
> Les crochets indiquent un nom de style d’InDesign intégré.

Les attributs utilisés dans le `paraRule` sont expliqués ci-dessous :

- `@style` : nom d’un style dans le document d’InDesign source.
- `@local` : Voir [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo` : nom d’un élément cible DITA.

- `@context` : cet attribut est utilisé pour créer un lien vers une règle **wrap** spécifique lorsque plusieurs options d’encapsulage sont disponibles. Exemple : l’élément `li` peut être encapsulé dans un élément `ol` ou `ul`. Pour identifier les différents types de liste, vous pouvez utiliser un nom de style spécifique ou l’attribut `@local` qui peut afficher les éléments suivants :
   - `local="p[-|-|-|-|-|b|-|-]"` Où &quot;`b`&quot; dans le champ 6 indique un élément de liste à puces. Dans ce cas, définissez `@context` sur &#39;`bullet`&#39;.
   - `local="p[-|-|-|-|-|n|-|-]"` Où &quot;`n`&quot; dans le champ 6 indique un élément de liste numérotée. Dans ce cas, définissez `@context` sur &#39;`number`&#39;.

- `@commentOut` : cet attribut active l’encapsulation de l’élément cible dans les commentaires XML afin que les informations ne soient pas perdues mais puissent être gérées manuellement par l’utilisateur. Cela s’avère utile si le contenu source ne peut pas être forcé à se conformer aux règles de structure DITA.

- `@refactor` : cet attribut facultatif a le choix entre deux valeurs :

- `unwrap` : l’élément correspondant est supprimé tout en conservant son contenu.

- `drop` : l’élément correspondant et tout son contenu sont supprimés.


**Règles de style de caractère**

Les éléments `charRule` sont décrits ci-dessous :

>[!NOTE]
>
> Il n’y aura aucun mappage pour le style de caractère intégré `[No character style]` lorsque `local="0"`, car ils sont supprimés pendant le prétraitement.

***`charRule`element***

Il s’agit d’un élément facultatif.

Il s’agit des règles de mappage pour tous les styles de caractères. Dans un document d’InDesign, tout le texte est contenu dans les éléments enfants des styles de caractères.

Les attributs utilisés dans le `charRule` sont expliqués ci-dessous :

- `@style` : nom d’un style dans le document d’InDesign source.
- `@local` : Voir [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo` : nom d’un élément cible DITA.
- `@refactor` : cet attribut facultatif a le choix entre deux valeurs :
   - `unwrap` : l’élément correspondant est supprimé tout en conservant son contenu.

   - `drop` : l’élément correspondant et tout son contenu sont supprimés.


**Règles d’attribut**

Cet élément peut être un enfant des contextes d’élément suivants :

- `mapDoctypeParaRule`
- `mapDoctypeElemRule`
- `doctypeParaRule`
- `doctypeElemRule`
- `paraRule`
- `charRule`
- `elementRule`

L’objectif des règles d’attribut est de gérer les attributs pour les éléments correspondants.

Selon le contexte, les attributs suivants sont disponibles pour l’élément `attributeRules` :

- `@createID` : génère un identifiant unique pour les éléments correspondants. Valeurs autorisées `true` ou `false`. Disponible dans tous les contextes.
- `@copyAll` : copie tous les attributs du contenu XML source pour les fichiers source structurés uniquement. Les valeurs autorisées sont `true` ou `false`. Disponible pour les contextes `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` et `elementRule`.


Les attributs utilisés dans le `attributeRules` sont expliqués ci-dessous :

>[!NOTE]
>
> Cet élément peut contenir plusieurs éléments enfants.

- `addNew` : ajoute un nouvel attribut à l’élément correspondant. Disponible pour tous les contextes. Il comporte deux attributs :
   - `@name` : doit être un nom XML légal, de préférence valide pour le contexte DITA.
   - `@value` : peut être un texte littéral ou une expression XPath simple.
- `copyAtt` : copie un attribut unique vers la cible tout en le renommant éventuellement dans le processus. La valeur n’est pas modifiée. Disponible pour les contextes `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` et `elementRule`. Lorsque cet élément est présent, la valeur `@copyAllAtts` est supposée être `false`. Il comporte deux attributs :
   - `@name` : doit être le nom d’un attribut présent sur l’élément XML source.
   - `@mapTo` : doit être un nom XML légal, de préférence valide pour le contexte DITA.

**Codes de mise en forme locaux**

Dans n’importe quel document d’InDesign, il est possible que les styles de paragraphe et de caractère comportent plusieurs centaines de remplacements de mise en forme différents. La plupart de ces propriétés ne fournissent aucun rôle utile dans le processus de conversion. Cependant, nous avons identifié un ensemble principal de fonctionnalités de formatage qui affectent la sémantique du document et qui doivent influencer le processus de conversion.

Les attributs `@local` sont présentés sous la forme d’un format délimité spécial où huit champs sont fournis avec un préfixe pour afficher le type de remplacement de mise en forme. Les champs des codes de formatage sont répertoriés ci-dessous :

- Préfixe **p** pour le remplacement local du style Para ou **c** pour le remplacement local du style de caractère.
- **Style de police** qui est le nom de famille et les propriétés telles que &#39;***Bold Condensed Italic***&#39;.
- **Taille de police** en points.
- **Position du caractère** pour l’exposant ou l’indice.
- **Sous** pour le trait de soulignement.
- **Strike** pour le parcours.
- **Code liste** pour identifier le type de liste comme à puces ou numérotée - pas toujours utilisé par InDesign.
- **Code à puces** répertorie tous les types de puces définis dans le document.
- **Numéro de code** répertorie tous les styles de numérotation définis dans le document.

L’utilisation prudente de cette fonction permet une perte de mise en forme locale du reste, ce qui peut améliorer la qualité du transfert d’un contenu stylisé vers DITA. Cet exemple peut être résolu en italique, texte 16 pt dans une liste à puces : `p[Italic|16|-|-|-|b|-|-]`.

**Mappage de structure**

Le fichier de mappage de structure est similaire au fichier de mappage de style avec une structure simple qui répertorie tous les éléments source et les types d’attributs appropriés. Deux attributs, `@map_date` et `@map_version`, sont fournis pour enregistrer la version du fichier de mappage à utiliser.

**Type de document**

L’élément `doctypes` répertorie le mappage DITA pris en charge et les mappages de rubrique.

**Mappage des règles d’élément de type de document**

L’élément `mapDoctypeElemRule` est obligatoire. Les attributs de cet élément ne doivent pas être modifiés, car l’élément racine du XML source est toujours mappé à l’élément `map` racine de la carte DITA.

**Règles d’encapsulage des éléments**

Voir [\#id194CG600NY4](#id194CG600NY4).

**`elementRules`element**

Cette liste répertorie tous les éléments [\#id194CGC00SHS](#id194CGC00SHS).

**`elementRule`element**

L’élément `elementRule` est obligatoire. Il s’agit des règles de mappage pour tous les éléments source. Bien qu’un document d’InDesign contienne des éléments de style non structurés, ceux-ci sont ignorés pour le contenu structuré, sauf si le traitement &#39;***mode hybride***&#39; est activé.

Les attributs utilisés dans le `elementRule` sont expliqués ci-dessous :

- `@elementName` : nom d’un élément dans le document d’InDesign source.

- `@local` : Voir [\#id194CG0V005Z](#id194CG0V005Z). \(Utile uniquement pour les documents hybrides\).

- `@mapTo` : nom d’un élément cible DITA.

- `@refactor` : cet attribut facultatif a le choix entre deux valeurs :

   - `unwrap` : l’élément correspondant est supprimé tout en conservant son contenu.

   - `drop` : l’élément correspondant et tout son contenu sont supprimés.

- `@context` : cet attribut est utilisé pour créer un lien vers une règle de retour automatique à la ligne spécifique lorsque plusieurs options de retour à la ligne sont disponibles. Exemple : l’élément `li` peut être encapsulé dans un élément `ol` ou `ul`.

- `@commentOut` : cet attribut active l’encapsulation de l’élément cible dans les commentaires XML afin que les informations ne soient pas perdues mais puissent être gérées manuellement par l’utilisateur. Cela s’avère utile si le contenu source ne peut pas être forcé à se conformer aux règles de structure DITA.
