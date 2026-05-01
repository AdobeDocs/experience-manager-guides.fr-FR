---
title: Notes de mise à jour | Nouveautés de la version Adobe Experience Manager Guides de décembre 2023
description: Découvrez les nouvelles fonctionnalités et les fonctionnalités améliorées de la version de décembre 2023 d’Adobe Experience Manager Guides as a Cloud Service.
feature: What's New
role: Leader
exl-id: bf8d98e9-97fe-4195-9286-60d8517ab19c
source-git-commit: 12ba7129255257970ddd7a0989149be664ce9803
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 0%

---

# Nouveautés de la version de décembre 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cet article couvre les nouvelles fonctionnalités et les fonctionnalités améliorées de la version de décembre 2023 d’Adobe Experience Manager Guides (plus tard appelée *Experience Manager Guides as a Cloud Service*).

Pour plus d’informations sur les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans cette version, consultez [Notes de mise à jour](release-notes-2023-12-0.md).


## Utilisation de variables dans la sortie PDF

Vous pouvez utiliser des variables pour insérer et gérer de manière dynamique des informations réutilisables. Experience Manager Guides vous permet de créer, modifier et prévisualiser des variables lors de la génération de la sortie PDF. Vous pouvez modifier rapidement les valeurs des variables et rendre vos documents portables et faciles à mettre à jour.

![variables pdf natives](assets/add-variable-default.png){width="800"}

*Créer et gérer des variables dans l’éditeur web.*

Vous pouvez également créer des ensembles de variables qui remplacent les valeurs par défaut et qui attribuent des valeurs alternatives à vos variables. Insérez ces variables dans la mise en page et utilisez la même mise en page PDF. Il n’est pas nécessaire de créer des mises en page distinctes pour chaque ensemble de valeurs. Par exemple, vous pouvez créer un jeu de variables pour chaque version de produit. Cet ensemble de variables peut être constitué de variables pour différents détails de produit, tels que le nom du produit, le numéro de version et la date de publication. Vous pouvez ensuite ajouter différentes valeurs pour ces variables.

**Ensemble de variables 1 : Adobe-set1**

* Nom du produit : Experience Manager Guides
* Numéro de version : 2311
* Date de publication : 11/02/2023

**Ensemble de variables 2 : Adobe-set2**

* Nom du produit : Experience Manager Guides
* Numéro de version : 2310
* Date de publication : 09/27/2023



<img src="./assets/native-pdf-variable-output.png" alt="Pied de page dans la sortie PDF" width="500" border="2px">

*Générez la sortie PDF à l’aide de variables dans la disposition PDF.*

Vous pouvez appliquer des styles et utiliser les balises HTML pour formater les variables.  Vous pouvez également mettre à jour rapidement les valeurs de n’importe quelle variable chaque fois que nécessaire et régénérer la sortie. Par exemple, si vous devez mettre à jour les détails d’une version, vous pouvez modifier la valeur de la version dans la variable VersionNumber et régénérer la sortie.


En savoir plus sur l’utilisation de [variables dans la sortie PDF](../native-pdf/native-pdf-variables.md).





## Expérience repensée pour modifier les attributs

Vous bénéficiez désormais d’une expérience repensée permettant d’ajouter ou de modifier les attributs d’un élément à partir du panneau **Propriétés du contenu** dans l’éditeur web.

![ Panneau Attributs ](assets/attributes-multiple-properties.png){width="300"}

*Ajoutez des attributs à partir du panneau Propriétés du contenu.*

Vous pouvez également modifier et supprimer facilement les attributs.

Pour plus d’informations, reportez-vous à la description de la fonctionnalité **Propriétés du contenu** dans la section [Panneau de droite](../user-guide/web-editor-features.md#id2051EB003YK).


## Modification de métadonnées lors de la création

Désormais, lors de la création, vous pouvez mettre à jour les balises de métadonnées de fichier à l’aide de la liste déroulante dans le **Propriétés du fichier** du panneau de droite. Vous pouvez également sélectionner **Modifier d’autres propriétés** pour mettre à jour d’autres métadonnées.

![file-properties](assets/file-properties-general.png){width="300"}

*Mettez à jour les métadonnées et modifiez les propriétés du fichier dans le panneau de droite.*

Pour plus d’informations, reportez-vous à la description de la fonctionnalité **Propriétés du fichier** dans la section [Panneau de droite](../user-guide/web-editor-features.md#id2051EB003YK).

## Capacité à publier du contenu dans la base de connaissances ServiceNow

Vous pouvez désormais également publier votre contenu sur la plateforme de la base de connaissances ServiceNow.

Avec la version de décembre 2023, en tant qu’administrateur, vous pouvez créer un profil de publication pour le serveur de la base de connaissances ServiceNow. Ensuite, en tant qu’auteur ou éditeur, vous pouvez choisir ce profil de publication ServiceNow dans le paramètre prédéfini de sortie pour publier la sortie dans la base de connaissances spécifiée.

Cette fonctionnalité vous permet de publier du contenu, tel que du texte, des vidéos et des images, sur la plateforme de la base de connaissances ServiceNow et de gérer un référentiel complet.


![préréglage de la base de connaissances service now](assets/knowledgebase--output-preset.png){width="300"}

*Créez un paramètre prédéfini de sortie pour la base de connaissances ServiceNow.*

En savoir plus sur les paramètres prédéfinis de sortie de la [Base de connaissances](../user-guide/generate-output-knowledge-base.md).

## Tableau de bord de collecte de cartes améliorée

Experience Manager Guides fournit un tableau de bord amélioré de collecte de cartes. Dans une collection de cartes, vous pouvez configurer rapidement les propriétés de métadonnées en bloc pour les cartes DITA. Cette fonctionnalité est pratique car vous n&#39;avez pas à mettre à jour les propriétés de métadonnées de chaque plan DITA individuellement.

Vous pouvez maintenant afficher le nom de fichier du plan DITA. Vous pouvez également afficher les références. Vous pouvez ainsi trouver rapidement la ligne de base utilisée pour un paramètre prédéfini.

![Tableau de bord de collection Map](assets/map-collection-dashboard.png){width="800"}

*Afficher, modifier et générer une sortie à partir du tableau de bord de collecte de carte.*

Découvrez comment [utiliser la collecte de mappages pour la génération de sortie](../user-guide/generate-output-use-map-collection-output-generation.md).

## Affichage des attributs clés dans la vue Carte

Lorsque vous définissez des attributs de clé pour les références de rubrique ou de mappage, vous pouvez également afficher le titre, l’icône correspondante et la clé dans le panneau de gauche. La clé s’affiche sous la forme `key=<key-name>`.

Pour plus d’informations, reportez-vous à la description de la fonctionnalité **Vue Carte** dans la section [Panneau de gauche](../user-guide/web-editor-features.md#id2051EA0M0HS).

![clés en vue carte](assets/view-key-title-map-view.png) {width="300"}

*Afficher l’attribut de clé dans la vue Carte.*

## Possibilité de dupliquer une ligne de base en fonction du libellé

Experience Manager Guides offre désormais une expérience utilisateur améliorée pour la création de lignes de base à partir de l’éditeur web.\
![créer une nouvelle ligne de base](assets/create-new-baseline.png) {width="300"}
*Créer une ligne de base à partir de l’éditeur web.*

Elle permet également de dupliquer une ligne de base en fonction du libellé. La version de référence est sélectionnée en fonction du libellé donné (s’il existe) lors de la duplication, ou sélectionne la version à partir de la ligne de base dupliquée.


![dupliquer un ](assets/duplicate-baseline.png) {width="300"} de référence

*Dupliquez une ligne de base en fonction d’un libellé ou créez une copie exacte.*

Découvrez comment [créer et gérer des lignes de base à partir de l’éditeur web](../user-guide/web-editor-baseline.md).

## Résoudre les liens croisés dans la sortie du site AEM

Les liens entre mappages (XREF avec étendue homologue) rendus dans la sortie du site AEM sont désormais résolus conformément au titre du fichier du contexte de publication défini pour le mappage généré.


## Configurez l’URL de sortie du site AEM pour utiliser le titre du document

Experience Manager Guides vous permet, en tant qu’administrateur ou administratrice, de configurer l’URL de la sortie du site AEM. Si le nom de fichier n’existe pas ou contient tous les caractères spéciaux, vous pouvez configurer pour les remplacer par un séparateur dans l’URL de la sortie du site AEM. Vous pouvez également les remplacer par le nom de la première rubrique enfant. Découvrez comment [configurer l’URL de la sortie du site AEM pour utiliser le titre du document](../cs-install-guide/conf-output-generation.md#configure-the-url-of-the-aem-site-output-to-use-the-document-title).
