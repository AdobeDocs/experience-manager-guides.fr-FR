---
title: Ajouter des polices personnalisées à votre PDF DITA
description: Intégrez des polices personnalisées pour renforcer l’identité de la marque et la cohérence visuelle de l’ensemble de votre contenu dans les PDF DITA natifs.
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: 151e3b1c-6340-4ff2-84d4-246bc4b68065
source-git-commit: 9c53ac725618db1164b0ed310a47b258a7224778
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Ajouter des polices personnalisées à votre PDF natif DITA

## Cet article couvre les sujets suivants :

Ajout de la police personnalisée pour renforcer l’identité de la marque et la cohérence visuelle de tout votre contenu.

Ce processus comprend 3 étapes :

- [Chargement de la police personnalisée](#step-1--upload-the-custom-font-to-the-resource-folder-of-your-template)
- [Apportez les modifications nécessaires dans la feuille de style des modèles PDF.](#step-2--make-necessary-changes-in-pdf-templatess-stylesheet)

- [Incorporer les polices utilisées (facultatif)](#step-3-optional--embed-used-font-in-pdf)

## Étape 1 : chargez la police personnalisée dans le dossier des ressources de votre modèle

![Chargement et importation de polices ](../assets/publishing/custom-font1.png)

## Étape 2 : effectuez les modifications nécessaires dans la feuille de style des modèles PDF

![Police dans la feuille de style du modèle de PDF](../assets/publishing/custom-font2.png)

## Étape 3 (facultatif) : incorporez la police utilisée dans PDF

![Incorporation de polices personnalisées dans les ](../assets/publishing/custom-font3.png) DITA PDF

## Questions fréquentes

### Puis-je utiliser Adobe Fonts ?

> Oui, accédez à fonts.adobe.com et cliquez sur « Ajouter au projet web ».
> 
> Copiez le code d’importation tel que `" @import url("https://use.typekit.net/xxxx.css")` ;
>
> Collez votre contenu CSS et apportez les modifications souhaitées à votre fichier CSS.

![Utilisation de la police adobe dans DITA PDF](../assets/publishing/custom-font4.png)


### Ma police ne s’affiche pas dans PDF

> Vérifier l’orthographe du nom de la police (erreur la plus courante)
>
> Veillez à incorporer des polices si elles ne sont pas disponibles sur le système sur lequel PDF est ouvert

## Pour toute autre question, contactez vos CSM respectifs


## Autres ressources :

- [Comment inclure la table des matières de DITA Bookmap dans PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Comment inclure la table des matières dans la publication PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Vidéo de session d’experts sur le PDF natif](../../expert-sessions/native-pdf-publishing-eamples-part1-june2023.md)
