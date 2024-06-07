---
title: Fonction de publication native d’un PDF | Ajouter un code à barres
description: Découvrez comment ajouter des codes à barres.
source-git-commit: a766353908829ab433173f8fd003ecad0c9d1bf1
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 1%

---


# Ajout d’un code à barres à la sortie PDF

Un code à barres est un modèle de données que les machines peuvent lire. Les clients peuvent analyser les codes à barres à l’aide d’un scanner de codes à barres ou d’un appareil photo de leur smartphone. Il peut s’avérer utile de coder des informations telles que des détails de produit, des numéros de stock ou des URL de site web. L’ajout de codes à barres permet de capturer facilement les données, d’améliorer l’expérience client et de faciliter une meilleure gestion et sécurité des données.

Vous pouvez créer un style pour le code à barres. et l’utiliser pour insérer un code-barres dans une mise en page. Vous pouvez appliquer le style à un exemple de code à barres dans la mise en page souhaitée.


Ce tutoriel vous aide à ajouter des codes à barres dans la sortie PDF.

## Procédure de génération d’un code à barres

Pour générer un code-barres, procédez comme suit :

### Mettre à jour le CSS du modèle pour générer une valeur de code à barres

Modifiez la variable `layout.css` pour générer un code à barres pendant la génération du PDF. Divers types de codes à barres tels que &quot;qrcode&quot; et &quot;pdf417&quot; sont pris en charge.  Pour plus d’informations, voir [Types de codes à barres](#barcode-types).



```css
...
.barcode { 
-ro-replacedelement: barcode;   
-ro-barcode-type: code128;   
-ro-barcode-size: 100%;   
-ro-barcode-content: content();   
object-fit: contain;   
margin-top: 2mm;
 
}
...
```

### Utiliser le style CSS pour générer le code à barres

Vous pouvez générer le code à barres de différentes manières. Voici quelques exemples :

**Exemple 1**

Ajoutez un espace réservé de code-barres dans l’en-tête du modèle et appliquez le style :

1. Modifier **Modèles** > **Disposition de page**
1. Sélectionnez une mise en page. Par exemple, vous pouvez sélectionner la mise en page de la page BackCover, qui contient l’en-tête ou le pied de page.
1. Ajoutez l’étendue suivante à l’emplacement où vous souhaitez insérer le code à barres.

   `<span class="barcode">Sample barcode</span></p>`.

   >[!NOTE]
   >
   > Utilisez le même nom de classe que celui défini dans la variable `layout.css`.

1. Remplacer `<Sample barcode>` avec la valeur que vous souhaitez que le scanner de code-barres lise.

Vous pouvez afficher le code à barres lors de la génération du PDF de sortie à l’aide du modèle, qui inclut la mise en page. Une fois que vous avez effectué les étapes précédentes, vous pouvez générer la sortie du PDF avec un code à barres.

La capture d’écran suivante affiche un exemple de code-barres dans une sortie PDF.

<img src="./assets/barcode-output-sample.png" alt="Exemple de sortie avec code-barres" width="700" border="2px">

**Exemple 2**

Modifiez la variable `Common.plt` dans le fichier **De base** pour ajouter un code à barres après le titre du projet.

Pour créer un code-barres pour un numéro ISBN, ajoutez un numéro ISBN. Utilisez ensuite le numéro ISBN pour générer le code-barres.

```html
...

  <div data-region="header">
    <p class="chapter-header"><span data-field="project-title" data-format="default">Project Title</span> </p>
    <p><span class="barcode">978-1-56619-909-4</span></p>
  </div>
} 
...
```

**Exemple 3**

Pour créer un code à barres à l’aide des métadonnées de mappage :

Utilisez les métadonnées figurant dans la variable `<topicmeta>` élément d’un mappage DITA à afficher en tant que code à barres. Assurez-vous d’utiliser le XPath correct. Par exemple, vous pouvez ajouter une `<resourceid>` dans le `<topicmeta>` d’un mappage DITA.

Dans l’exemple suivant, l’ID de ressource sert d’entrée principale pour générer le code à barres.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<map id="GUID-3c330691-4dac-4020-904a-d2d6246aeeb1-en">
  <title>Barcode Sample</title>
  <topicmeta>
    <resourceid id="7a5bda1c-b1db-4fd8-8763-a731e2e8abba">
    </resourceid>
  </topicmeta>
  <topicref href="GUID-139f6c64-bea3-4f17-8b22-ee131557e249-en.dita" type="topic">
  </topicref>
</map>  
```



Vous pouvez utiliser l’ID de ressource dans une mise en page comme suit :


```html
  <div data-region="header">
    <p class="chapter-header"><span data-field="project-title" data-format="default">Project Title</span> </p>
    <p><span class="barcode" data-field="metadata" data-format="default" data-subtype="//resourceid/@id">Resource ID (barcode)</span></p>
  </div>
} 
```

## Types de codes à barres {#barcode-types}

Voici quelques-uns des codes à barres les plus couramment utilisés :

| Type | -ro-barcode-type | Informations supplémentaires |
| ---| --- | --- |
| Code QR | qrcode | Symbologie du code-barres QR Code selon ISO/IEC 18004:2015. |
| Code 128 | code128 | Symbologie du code à barres Code 128 telle que définie dans ISO/IEC 15417:2007. |
| Code 32 | code32 | Code 32, également appelé pharmacode italienne. |
| Code 49 | code49 | Code 49 selon ANSI/AIM-BC6-2000. |
| Code 11 | code11 |                            |
| Code 93 | code93 |                            |
| Code16k | code16k |                            |
| PDF417 | pdf417 | Les symbologies de code-barres PDF417/MicroPDF417 sont conformes à la norme ISO/IEC 15438:2006 et ISO/IEC 24728:2006. |
| Code 3 sur 9 | code39 | Le code 3 sur 9 code-barres est une symbologie conforme à la norme ISO/IEC 16388:2007. |
| MSI Plessey | msiplessey |                            |
| Code du canal | channel code | Code de canal conformément à ANSI/AIM BC12-1998. |
| Codabar | codabar | Symbologie des codes à barres Codabar selon BS EN 798:1996. |
| EAN-8 | ean-8 | Symbologie du code-barres EAN selon BS EN 797:1996. |
| EAN-13 | ean-13 | Symbologie du code-barres EAN selon BS EN 797:1996. |
| UPC-A | upc-a | Symbologie du code-barres UPC selon BS EN 797:1996. |
| UPC-E | upc-e | Symbologie du code-barres UPC selon BS EN 797:1996. |
| Ajout Ean/UPC | addon | Symbologie du code-barres EAN/UPC selon BS EN 797:1996. |
| Telepen | telepen | Également appelé Alpha Telepen. |
| Base de données GS1 / Base de données 14 | base de données | Barre de données GS1 conformément à la norme ISO/IEC 24724:2011. |
| Base de données GS1 étendue / Balise de données 14 étendue | databar-expand | Barre de données GS1 étendue selon ISO/IEC 24724:2011. |
| Base de données GS1 limitée | databar-limited | GS1 DataBar Limited selon ISO/IEC 24724:2011. |
| POSTNET (Technique de codage numérique des postaux) | postnet | Symbologie de code à barres POSTNET (Postal Numeric Encoding Technique vous utilisez pour la poste aux États-Unis. |
| Pharmazentralnummer (PZN-8) | pzn8 | Une symbologie basée sur le code 39 utilisée par l&#39;industrie pharmaceutique en Allemagne. |
| Pharmacode | pharmacode |                            |
| Codablock F | codablockf | Symbologie selon AIM Europe &quot;Uniform Symbology Specification Codablock F&quot;, 1995. |
| Logmars | logmars | La norme LOGMARS (Logistics Applications of Automated Marking and Reading Symbols) utilisée par le département américain de la Défense. |
| Aztec Runes | aztec-runes | Symbologie du code-barres Aztec Runes conformément à l’annexe A de la norme ISO/IEC 24778:2008. |
| Code Aztec | aztec-code | Symbologie du code-barres Aztec Selon ISO/IEC 24778:2008. |                            |
| DataMatrix | matrice de données | Symbologie de code-barres ECC 200 Data Matrix selon la norme ISO/IEC 16022:2006. |
| Code 1 | code-one |                            |



