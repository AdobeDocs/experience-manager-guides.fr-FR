---
title: Fonctionnalité native de publication PDF | Ajouter un code-barres
description: Découvrez comment ajouter des codes à barres.
exl-id: 206bdcf9-2bcd-4bf1-815a-c97cdf0dc415
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 1%

---

# Ajout d’un code à barres à la sortie PDF

Un code à barres est un modèle de données que les machines peuvent lire. Les clients peuvent scanner des codes-barres avec un scanner de codes-barres ou leur appareil photo de smartphone. Le codage d’informations telles que les détails du produit, les numéros d’inventaire ou les URL de site web peut s’avérer utile. L’ajout de codes à barres permet de capturer facilement les données, d’améliorer l’expérience client et de faciliter une meilleure gestion et sécurité des données.

Vous pouvez créer un style pour le code à barres. et utilisez-le pour insérer un code-barres dans une mise en page. Vous pouvez appliquer le style à un exemple de code-barres dans la mise en page souhaitée.


Ce tutoriel vous aide à ajouter des codes à barres dans la sortie PDF.

## Procédure de génération d’un code-barres

Pour générer un code à barres, procédez comme suit :

### Mettez à jour le CSS du modèle pour effectuer le rendu d’une valeur de code à barres

Modifiez le fichier `layout.css` pour effectuer le rendu d’un code à barres pendant la génération PDF. Différents types de code à barres tels que &#39;qrcode&#39; et &#39;pdf417&#39; sont pris en charge.  Pour plus d’informations, voir [Types de code-barres](#barcode-types).



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

Vous pouvez générer le code-barres de différentes manières. Voici quelques exemples :

**Exemple 1**

Ajoutez un espace réservé de code à barres dans l’en-tête du modèle et appliquez le style :

1. Modifiez **Modèles** > **Mises En Page**
1. Sélectionnez une mise en page. Par exemple, vous pouvez sélectionner la disposition Page de couverture arrière, qui contient l’en-tête ou le pied de page.
1. Ajoutez l’étendue suivante à l’emplacement où vous souhaitez insérer le code à barres.

   `<span class="barcode">Sample barcode</span></p>`.

   >[!NOTE]
   >
   > Utilisez le même nom de classe que celui que vous avez défini dans le `layout.css`.

1. Remplacez `<Sample barcode>` par la valeur que le lecteur de code-barres doit lire.

Vous pouvez afficher le code à barres lors de la génération du PDF de sortie à l’aide du modèle, qui inclut la mise en page. Une fois les étapes précédentes effectuées, vous pouvez générer la sortie PDF avec un code à barres.

La capture d’écran suivante affiche un exemple de code à barres dans une sortie PDF.

<img src="./assets/barcode-output-sample.png" alt="Exemple de sortie avec code-barres" width="700" border="2px">

**Exemple 2**

Modifiez le fichier `Common.plt` dans le modèle **De base** pour ajouter un code à barres après le titre du projet.

Pour créer un code-barres pour un numéro ISBN, ajoutez un numéro ISBN. Utilisez ensuite le numéro ISBN pour générer le code à barres.

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

Pour créer un code à barres à l’aide des métadonnées de carte :

Utilisez les métadonnées présentes dans l&#39;élément `<topicmeta>` d&#39;un plan DITA à afficher sous forme de code-barres. Veillez à utiliser le XPath correct. Par exemple, vous pouvez ajouter un `<resourceid>` dans le `<topicmeta>` d&#39;un plan DITA.

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



Vous pouvez utiliser l’identifiant de ressource dans une mise en page comme suit :


```html
  <div data-region="header">
    <p class="chapter-header"><span data-field="project-title" data-format="default">Project Title</span> </p>
    <p><span class="barcode" data-field="metadata" data-format="default" data-subtype="//resourceid/@id">Resource ID (barcode)</span></p>
  </div>
} 
```

## Types de code-barres {#barcode-types}

Voici quelques-uns des codes à barres couramment utilisés :

| Type | -ro-code-barres-type | Détails supplémentaires |
| ---| --- | --- |
| Code QR | qrcode | La symbologie du code à barres QR Code selon ISO/IEC 18004:2015. |
| Code 128 | code128 | Symbologie du code à barres Code 128 telle que définie dans la norme ISO/IEC 15417:2007. |
| Code 32 | code32 | Code 32, également connu sous le nom de pharmacode italienne. |
| Code 49 | code49 | Code 49 selon ANSI/AIM-BC6-2000. |
| Code 11 | code11 |                            |
| Code 93 | code93 |                            |
| Code16k | code16k |                            |
| PDF417 | pdf417 | Les symboles de code-barres PDF417/MicroPDF417 sont conformes aux normes ISO/IEC 15438:2006 et ISO/IEC 24728:2006. |
| Code 3 sur 9 | code39 | Le code 3 de 9 code-barres symbologie selon ISO/IEC 16388:2007. |
| MSI Plessey | msiplessey |                            |
| Code de canal | channelcode | Code de canal selon ANSI/AIM BC12-1998. |
| Codabar | cabaret | Symbologie code-barres Codabar selon BS EN 798:1996. |
| EAN-8 | ean-8 | Symbologie du code-barres EAN selon BS EN 797:1996. |
| EAN-13 | ean-13 | Symbologie du code-barres EAN selon BS EN 797:1996. |
| UPC-A | upc-a | Symbologie du code-barres UPC selon BS EN 797:1996. |
| UPC-E | upc-e | Symbologie du code-barres UPC selon BS EN 797:1996. |
| Module complémentaire Ean/UPC | addon | Symbologie du code-barres complémentaire EAN/UPC selon BS EN 797:1996. |
| Téléphoner | raccrocher | Également appelé Telepen Alpha. |
| GS1 Databar / Databar 14 | barre de données | GS1 DataBar selon ISO/IEC 24724:2011. |
| GS1 Databar Expanded / Databar 14 Expanded | databar-expanded | Barre de données GS1 développée selon ISO/IEC 24724:2011. |
| GS1 Databar Limited | limité à une barre de données | GS1 DataBar Limited selon ISO/IEC 24724:2011. |
| POSTNET (Postal Numeric Encoding Technique) | réseau postal | Symbologie des codes à barres POSTNET (Postal Numeric Encoding Technique) utilisée par le service postal des États-Unis. |
| Pharmazentralnummer (PZN-8) | pzn8 | Symbologie fondée sur le code 39 utilisée par l&#39;industrie pharmaceutique en Allemagne. |
| Pharmacode | pharmacode |                            |
| Blocage de code F | codablockf | Symbologie selon AIM Europe « Uniform Symbology Specification Codablock F », 1995. |
| Logmars | logmars | La norme LOGMARS (Logistics Applications of Automated Marking and Reading Symbols) utilisée par le ministère américain de la Défense. |
| Aztec Runes | aztec-runes | Symbologie du code-barres Aztec Runes conformément à l&#39;annexe A de la norme ISO/IEC 24778:2008. |
| Aztec Code | aztec-code | Symbologie du code à barres Aztec Code selon ISO/IEC 24778:2008. |
| DataMatrix | data-matrice | Data Matrix ECC 200 bar code symbology Selon ISO/IEC 16022:2006. |
| Code Un | code-un |                            |
