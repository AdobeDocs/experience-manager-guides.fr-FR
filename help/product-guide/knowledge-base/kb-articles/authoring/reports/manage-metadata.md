---
title: Gestion des balises des fichiers DITA dans AEM Guides
description: Article bref à fournir sur la gestion des cq:tags dans AEM Guides
exl-id: 2d805c26-df9b-405a-81ca-7aa84c6f86c8
feature: Metadata Management
author: Pulkit Nagpal(punagpal)
role: User, Admin
source-git-commit: f971be4be9e2d32618616727cd9c682941dd3fb2
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 1%

---

# Comment ajouter , supprimer et gérer des balises dans votre contenu DITA

Les balises s’avèrent utiles pour classer votre contenu. Si le contenu est correctement balisé, il peut vous aider à localiser les rubriques exactes dans votre fichier ditamap et l’utilisateur final trouve le contenu approprié plus rapidement sur la sortie publiée.

> **_REMARQUE :_** L’article suivant concerne AEM Guides Build 4.2 (on-prem) /Feb 2023 (version cloud ) ou versions ultérieures


## Créer des balises

Le balisage est une fonctionnalité d’AEM native et votre administrateur AEM peut vous aider à créer et configurer initialement ces balises.


## Ajout, suppression et gestion des balises dans votre contenu DITA

**Toutes les balises créées dans AEM cq : les balises peuvent être ajoutées, supprimées et gérées pour votre contenu DITA**

Il existe plusieurs façons d’ajouter des balises dans votre contenu DITA, mais cet article se concentrera sur l’interface utilisateur de l’éditeur web AEM Guides.

### Étapes :

1. Accès à la vue du référentiel dans l’interface utilisateur des guides
2. Double-cliquez sur ditamap et ouvrez en mode Carte.
3. Onglet Gérer
4. Sous l’onglet Gérer , option Accéder aux métadonnées .
5. Tous les chargements de la liste des fichiers ditamap directs et indirects sont ici.
6. Sélectionnez un ou plusieurs fichiers et cliquez sur l’icône &quot;gérer&quot;. Vous pouvez y ajouter des balises aux fichiers sélectionnés.
Vous pouvez également supprimer les balises existantes qui sont communes aux fichiers sélectionnés.

<img title="Gestion des balises dans AEM Guides " alt="Gestion des balises dans DITA " src="ManageTags.jpg">

## Résolution des problèmes et FAQ

### Liste dans manage->metadata est vide ou incomplet

`If list is empty or  incomplete then you may need to run the indexing on your ditamap, You can refer` [Instructions de mise à niveau (indexer votre contenu)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/install-guide/on-prem-ig/download-install-upgrade-aemg/upgrade-xml-documentation.html?lang=fr#steps-to-index-the-existing-content-to-use-the-new-find-and-replace%3A)

### Les métadonnées personnalisées ne figurent pas dans la liste

`Only Tags present in cq:tags can be managed from here and custom metadata is not supported`




## Autres ressources utiles

- [Balisage en masse à l’aide du tableau de bord des cartes (interface utilisateur d’Assets)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/manaege-metadata/map-editor-bulk-tagging.html?lang=fr)
- [Rapports Ditamap dans l’éditeur web](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/reports-aem-guide/reports-web-editor.html?lang=fr)
- [Balisage dans AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/configuring/tagging.html?lang=fr)


**Contactez votre CSM respectif pour toute autre requête**
