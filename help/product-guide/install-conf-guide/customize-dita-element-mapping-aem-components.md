---
title: Personnalisation du mappage d’éléments dita avec les composants AEM
description: Découvrez comment personnaliser le mappage d’éléments dita avec les composants d’AEM
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '1268'
ht-degree: 1%

---


# Personnaliser le mappage d&#39;éléments DITA avec des composants AEM {#id1679J600HEL}

Les éléments DITA dans AEM Guides sont mappés à leurs composants AEM correspondants. AEM Guides utilise ce mappage dans des workflows tels que la publication et la révision pour convertir un élément DITA en composant AEM correspondant. Le mappage est défini dans le fichier `elementmapping.xml`, accessible à l’aide du gestionnaire de packages pour la configuration de Cloud Service et à partir de l’URL : `/libs/fmdita/config/elementmapping.xml` en mode CRXDE Lite pour la configuration On-Premise.

>[!NOTE]
>
> Ne rendez aucune personnalisation dans les fichiers de configuration par défaut disponibles dans le nœud ``libs``. Vous devez créer un recouvrement du nœud ``libs`` dans le nœud ``apps`` et mettre à jour les fichiers requis dans le nœud ``apps`` uniquement.

Vous pouvez utiliser les mappages d&#39;éléments DITA prédéfinis ou mapper des éléments DITA à vos composants AEM personnalisés. Pour utiliser vos composants AEM personnalisés, vous devez connaître la structure du fichier `elementmapping.xml`.

## structure elementmapping.xml

Vous trouverez ci-dessous un aperçu général de la structure `elementmapping.xml` :

1. Chaque élément DITA est d&#39;abord recherché pour un mappage de composant correspondant en fonction du nom de l&#39;élément. Par exemple :

   ```XML
   <ditaelement>     
      <name>**substeps**</name>  
      <class>- topic/ol task/substeps</class>  
      <componentpath>dita/components/ditaolist</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>
   </ditaelement>
   ```

   Dans l&#39;exemple ci-dessus, tous les éléments DITA `substeps` sont rendus à l&#39;aide du composant `dita/components/ditaolist`.

1. Si un élément DITA ne trouve pas de correspondance basée sur le nom, une correspondance basée sur le `class` est effectuée. Par exemple :

   ```XML
   <ditaelement>  
      <name>topic</name>  
      <class>**- topic/topic**</class>  
      <componentpath>fmdita/components/dita/topic</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>  
      <attributemap> 
         <attribute from="id" to="id" />  
      </attributemap>
   </ditaelement>
   ```

   Dans l’exemple ci-dessus, si aucun mappage n’est défini pour l’élément `task`, l’élément `task` est mappé au composant ci-dessus, car `task` est hérité du composant `topic`.

1. Lorsqu’un élément possède un mappage de composant correspondant, le traitement ultérieur de ses éléments enfants est déterminé par `type`. Par exemple :

   ```XML
   <ditaelement>  
      <name>title</name>  
      <class>- topic/title</class>  
      <componentpath>foundation/components/title</componentpath>  
      <type>**STANDALONE**</type>  
      <target>para</target>  
      <textprop>jcr:title</textprop>
   </ditaelement>
   ```

   `type` prend les valeurs suivantes :

   - COMPOSITE : le mappage élément à composant *continue pour les éléments enfants* également.

   - AUTONOME : les éléments enfants de l’élément actif ne sont *plus mappés*.

   Dans l’exemple ci-dessus, si l’élément `<title>` comporte des éléments enfants, ils ne seront mappés à aucun autre composant. Le composant de `<title>`’élément est responsable du rendu de tous les éléments enfants dans l’élément `<title>`.

1. S&#39;il existe plusieurs composants mappés à un seul élément DITA, la meilleure correspondance pour l&#39;élément est sélectionnée. Pour sélectionner le composant qui correspond le mieux, une spécialisation de domaine et de structure des éléments DITA est prise en compte.

   S’il existe des éléments DITA avec une spécialisation de domaine et qu’un composant est mappé pour la spécialisation de domaine, la priorité élevée est accordée à ce composant.

   De même, si des éléments DITA sont dotés d&#39;une spécialisation structurelle et qu&#39;un composant est mappé pour la spécialisation structurelle, la priorité est accordée à ce composant.

1. Vous pouvez utiliser des `<attributemap>` dans le mappage d’éléments pour mapper des valeurs d’attribut aux propriétés de nœud correspondantes.
1. `textprop` peut être utilisé pour sérialiser le contenu texte d&#39;un élément DITA en une propriété de nœud. En outre, elle peut être utilisée plusieurs fois dans une balise d’élément pour sérialiser le contenu du texte à plusieurs emplacements dans la hiérarchie publiée. Vous pouvez également personnaliser l’emplacement et le nom de la propriété cible. Par exemple :

   ```XML
   <ditaelement>
      <name>title</name>
      <componentpath>foundation/components/title</componentpath>
      <type>STANDALONE</type>
      <target>para</target>
       <textprop>**jcr:title**</textprop>
   </ditaelement>
   ```

   Le mappage de l’élément ci-dessus indique que le contenu textuel de `<title>`’élément sera enregistré en tant que valeur d’une propriété nommée `jcr:title` sur le nœud de sortie.

1. `xmlprop` peut être utilisé pour sérialiser l’intégralité du code XML d’un élément donné en une propriété de nœud. Le composant peut ensuite lire cette propriété de nœud et effectuer un rendu personnalisé. Par exemple :

   ```XML
   <ditaelement>
       <name>svg-container</name>
      <class>+ topic/foreign svg-d/svg-container</class>
       <componentpath>fmdita/components/dita/svg</componentpath>
       <type>STANDALONE</type>
       <target>para</target>
      <xmlprop>**data**</xmlprop>
   </ditaelement>
   ```

   Le mappage d’éléments ci-dessus indique que l’intégralité du balisage XML pour l’élément `<svg-container>` sera enregistrée en tant que valeur d’une propriété nommée `data` sur le nœud de sortie.

1. Il existe un mappage d’attributs spécial pour gérer la résolution de chemin dans le processus de génération de sortie. Par exemple :

   ```XML
   <attributemap>
      <attribute from="href" to="fileReference" ispath="true" rel="source" />
      <attribute from="height" to="height" />
       <attribute from="width" to="width" />
   </attributemap>
   ```

   Pour l&#39;`attributemap` ci-dessus, l&#39;attribut `href` dans votre élément DITA sera mappé à une propriété de nœud nommée `fileReference`. Maintenant que `ispath` est défini sur `true`, le processus de génération de sortie résout ce chemin d’accès, puis le définit dans `fileReference` propriété de nœud .

   Le mode de résolution est déterminé en fonction de la valeur de l’attribut `rel` dans le mappage des attributs.

   - Si `rel=source`, la valeur de `href` est résolue par rapport au fichier source DITA en cours de traitement. La valeur de `href` est résolue et placée dans la valeur de `fileReference` propriété .

   - Si `rel=target`, la valeur de `href` est résolue par rapport à l’emplacement de publication racine. La valeur de `href` est résolue et placée dans la valeur de `fileReference` propriété .

   Si vous ne souhaitez pas qu’un prétraitement ou une résolution se produise sur les attributs de chemin, vous n’avez pas besoin de spécifier l’attribut `ispath`. La valeur est copiée telle quelle et le composant peut effectuer la résolution requise.


## Schéma de l&#39;élément DITA

Voici un exemple du schéma d&#39;élément DITA dans `elementmapping.xml` fichier :

```XML
<ditaelement>        
    <name>element_name</name>    
    <class>element_class</class>    
    <componentpath>fmdita/components/dita/component_name</componentpath>    
    <type>COMPOSITE|STANDALONE</type>     
    <attributeprop>propname_a</attributeprop>      
    <textprop>propname_t</textprop>    
    <xmlprop>propname_x</xmlprop>     
    <xpath>xpath expression string</xpath>     
    <target>head|para</target>     
    <wrapelement>div</wrapelement>     
    <wrapclass>class_name</wrapclass>     
    <attributemap>         
        <attribute from="attrname"         to="propname"         ispath="true|false"         rel="source|target" />    
    </attributemap>    
    <skip>true|false</skip> 
</ditaelement>
```

Le tableau suivant décrit les éléments du schéma d&#39;élément DITA :

| Elément | Description |
|-------|-----------|
| `<ditaelement>` | Nœud de niveau supérieur pour chaque élément de mappage. |
| `<class>` | Attribut class de l&#39;élément DITA cible pour lequel vous créez le composant.<br> Par exemple, l&#39;attribut class pour la rubrique DITA est : <br> `- topic/topic` |
| `<componentpath>` | Chemin CRXDE du composant AEM mappé. |
| `<type>` | Valeurs possibles : <br> -   **COMPOSITE** : traitez également les éléments enfants <br> -   **AUTONOME** : ignore le traitement des éléments enfants |
| `<attributeprop>` | Utilisé pour mapper des attributs et des valeurs DITA sérialisés aux nœuds AEM en tant que propriété. Par exemple, si vous disposez d’`<note type="Caution">` élément et que le composant mappé pour cet élément a `<attributeprop>attr_t</ attributeprop>`, l’attribut et la valeur du nœud sont sérialisés sur `attr_t` propriété du nœud AEM correspondant \( `attr_t->type="caution"`\). |
| `<textprop>propname_t</textprop>` | Enregistrez la sortie `getTextContent()` dans la propriété définie par `propname_t.` <br> **Remarque :** il s’agit d’une propriété optimisée. |
| `<xmlprop>propname_x </xmlprop>` | Enregistrez le code XML sérialisé de ce nœud dans la propriété définie par `propname_x.<br> `**Remarque :** il s’agit d’une propriété optimisée. |
| `<xpath>` | Si l’élément XPath est fourni dans le mappage d’éléments, alors, avec le nom et la classe de l’élément, la condition XPath doit également être remplie pour le mappage de composants à utiliser. |
| `<target>` | Placez l&#39;élément DITA dans le référentiel crx à l&#39;emplacement spécifié.<br> Valeurs possibles : <br> - **head** : sous le nœud head <br> - **text** : sous le nœud paragraph |
| `<wrapelement>` | Élément HTML dans lequel encapsuler le contenu. |
| `<wrapclass>` | La valeur de l’élément dans la propriété `wrapclass.` |
| `<attributemap>` | Nœud conteneur contenant un ou plusieurs nœuds `<attribute>`. |
| `<attribute from="attrname" to="propname" ispath="true\|false" rel="source\|target" />` | Mappe les attributs DITA aux propriétés AEM : <br> -   **`from`** : nom d&#39;attribut DITA <br> -   **`to`** : nom de propriété du composant AEM <br> -   **`ispath`** : si l’attribut est une valeur de chemin \(par exemple : *image*\) <br> -   **`rel`** : si le chemin d’accès est le <br> source ou cible **Remarque :** si `attrname` commence par `%`, mappez `attrname minus '%'` à la prop &#39; `propname`&#39;. |

**Remarques complémentaires**

- Si vous prévoyez de remplacer le mappage d’élément par défaut, il est recommandé de ne pas apporter les modifications dans le fichier `elementmapping.xml` par défaut. Créez un fichier XML de mappage et placez-le à un autre emplacement, de préférence dans le dossier d’applications personnalisées que vous créez.

- Dans le fichier `elementmapping.xml`, il existe de nombreuses entrées de mappage faisant référence au composant fmdita/components/dita/wrapper. Wrapper est un composant générique qui effectue le rendu de constructions DITA relativement simples à l’aide de propriétés sur le nœud de leur site pour générer des HTML pertinentes. Elle utilise la propriété `wrapelement` pour générer des balises englobantes et délègue le rendu enfant aux composants correspondants. Cela s’avère utile dans les cas où vous ne souhaitez qu’un composant de conteneur. Au lieu de créer un composant qui effectue le rendu d’une balise conteneur spécifique telle que `div` ou `p`, vous pouvez utiliser le composant Wrapper avec les propriétés `wrapelement` et `wrapclass` pour obtenir le même effet.

- Il n’est pas recommandé d’enregistrer de grandes quantités de texte dans les propriétés String JCR. Le calcul du type de propriété optimisé dans la génération de sortie garantit que le contenu de texte volumineux n’est pas enregistré en tant que type de chaîne. Au lieu de cela, lorsque du contenu supérieur à un certain seuil doit être enregistré, le type de la propriété est remplacé par binaire. Par défaut, ce seuil est configuré sur 512 octets, mais peut être modifié dans Configuration Manager \(*com.adobe.fmdita.config.ConfigManager*\) en modifiant le paramètre **Enregistrer en tant que seuil binaire**.

- Si vous prévoyez de remplacer certains \(et pas tous\) des mappages d’éléments, vous n’avez pas à répliquer le fichier `elementmapping.xml` entier. Vous devez créer un nouveau fichier de mapping XML et définir uniquement les éléments que vous remplacez.

- Après avoir créé le fichier XML à l’emplacement personnalisé, mettez à jour le paramètre `Override Element Mapping` dans le lot `com.adobe.fmdita.config.ConfigManager`.


