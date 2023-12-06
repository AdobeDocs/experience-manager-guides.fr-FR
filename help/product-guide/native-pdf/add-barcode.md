---
title: Fonction de publication native d’un PDF | Ajouter un code à barres
description: Découvrez comment ajouter des codes à barres.
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---

# Ajout d’un code à barres à la sortie PDF

Les codes à barres sont utiles pour inclure des informations qui peuvent être facilement traitées par les machines. De même, les codes QR sont utilisés pour les liens que les lecteurs peuvent ouvrir avec leurs appareils mobiles.

Ce tutoriel vous permet d’ajouter des codes à barres en haut de chaque page dans la sortie du PDF.

## Procédure de génération d’un code à barres

Pour générer un code-barres, procédez comme suit :

### Ajout d’un ID de ressource au mappage DITA

Ajoutez un élément d’ID de ressource au mappage DITA. L’ID de ressource sert d’entrée principale pour générer le code à barres.

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

Vous pouvez également modifier l’ID de la ressource en mode Création.

<img src="./assets/barcode-map.png" alt="Exemple de sortie avec code-barres" width="700" border="2px solid blue">


### Ajout d’un espace réservé de code à barres dans l’en-tête du modèle

Modifiez la variable `Common.plt` dans le fichier **De base** pour ajouter un code à barres après le titre du projet.

```html
...
  <div data-region="header">
    <p class="chapter-header"><span data-field="project-title" data-format="default">Project Title</span> </p>
    <p><span class="barcode" data-field="metadata" data-format="default" data-subtype="//resourceid/@id">Resource ID (barcode)</span></p>
  </div>
} 
...
```


### Mettre à jour le CSS du modèle pour générer une valeur de code à barres

Modifiez la variable `content.css` pour générer un code à barres pendant la génération du PDF. Divers types de codes à barres tels que &quot;qrcode&quot; et &quot;pdf417&quot; sont pris en charge.  Pour plus d’informations, voir [Types de codes à barres](#barcode-types).



```css
...
.barcode {
  -ro-replacedelement: barcode;
  -ro-barcode-type: code128;
}
...
```

Une fois que vous avez effectué les étapes précédentes, vous pouvez générer la sortie du PDF avec un code à barres.

La capture d’écran suivante affiche un exemple de code-barres dans une sortie PDF.

<img src="./assets/barcode-output-sample.png" alt="Exemple de sortie avec code-barres" width="700">


## Types de codes à barres {#barcode-types}

| Type | Attribut CSS | Attributs supplémentaires |
| ------------------------------- | ----------------------- | -------------------------- |
| Code QR | qrcode |                            |
| PDF417 | pdf417 |                            |
| DataMatrix | matrice de données |                            |
| Code Aztec | aztec-code |                            |
| Matrice de grille | grid-grid |                            |
| Maxicode | maxicode mode-4 |                            |
| Micro QR | microqr |                            |
| Code 1 | code-one |                            |
| Codablock F | codablockf |                            |
| Base de données GS1 limitée | databar-limited |                            |
| Omnidirectionnel de la base de données GS1 | omnidirectionnel de la base de données |                            |
| EAN-13 | ean-13 |                            |
| GS1-128 (EAN-128) | code128 | -ro-barcode-encoding: gs1; |
| ITF-14 | itf14 |                            |
| UPC-A | upc-a |                            |
| Code 128 | code128 |                            |
| Interleaved 2 sur 5 | code2of5 entrelacé |                            |
| POSTNET | postnet |                            |
| Dutch Post Kixcode | kixcode |                            |
| Corée : Post | corée-post |                            |
| Deutsche Post Leitcode | dp-leitcode |                            |
| Australia Post | auspost |                            |
| Logmars | logmars |                            |
| Pharmacode | pharmacode |                            |
| USPS OneCode (Intelligent Mail) | usps-onecode |                            |


