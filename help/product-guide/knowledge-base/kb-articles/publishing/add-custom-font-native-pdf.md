---
title: Ajout de polices personnalisées à votre PDF DITA
description: Réalisez l’intégration de polices personnalisées pour renforcer l’identité de la marque et la cohérence visuelle de tout votre contenu dans les PDF DITA natifs.
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
source-git-commit: 518bec870dc07e88a422d889a1c54be26c248799
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Ajout de polices personnalisées à votre PDF natif DITA

## Cet article traite des sujets suivants :

Ajout d’une police personnalisée afin de renforcer l’identité de la marque et la cohérence visuelle de l’ensemble de votre contenu.

Ce processus comprend 3 étapes :

- [Chargement de la police personnalisée](#step-1--upload-the-custom-font-to-the-resource-folder-of-your-template)
- [Apporter les modifications nécessaires à la feuille de style des modèles de PDF](#step-2--make-necessary-changes-in-pdf-templatess-stylesheet)

- [Incorporer les polices utilisées (facultatif)](#step-3-optional--embed-used-font-in-pdf)

## Étape 1 : téléchargement de la police personnalisée vers le dossier de ressources de votre modèle

![Chargement et importation de polices personnalisées ](../assets/publishing/custom-font1.png)

## Étape 2 : apportez les modifications nécessaires à la feuille de style des modèles PDF

![Police face dans la feuille de style du modèle du PDF ](../assets/publishing/custom-font2.png)

## Étape 3 (facultative) : incorporation de la police utilisée dans PDF

![Intégration de polices personnalisées dans le PDF DITA ](../assets/publishing/custom-font3.png)

## Questions fréquentes

- ### Puis-je utiliser Adobe Fonts ?

> Oui, accédez à fonts.adobe.com et cliquez sur &quot;Ajouter au projet web&quot;.
> 
> Copiez le code d’importation tel que `" @import url("https://use.typekit.net/xxxx.css")`;
>
> Collez votre contenu CSS et apportez les modifications souhaitées dans votre fichier CSS.

![ Utilisation de la police adobe dans le PDF DITA](../assets/publishing/custom-font4.png)


- ### Ma police ne s’affiche pas en PDF

> Vérifier l&#39;orthographe des noms de police (erreur la plus courante)
>
> Assurez-vous d’incorporer la police si les polices ne sont pas disponibles sur le système où PDF est ouvert.

- ## Pour toute autre requête, contactez vos CSM respectifs.


## Autres ressources :

- [Comment inclure la table des matières du signet DITA en PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Comment inclure la table des matières dans la publication en PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Vidéo d’experts sur le PDF natif](../../expert-sessions/native-pdf-publishing-eamples-part1-june2023.md)