---
title: Gestion des balises des fichiers DITA dans AEM Guides
description: Bref article à raconter sur la gestion de cq:tags dans AEM Guides
exl-id: 2d805c26-df9b-405a-81ca-7aa84c6f86c8
feature: Metadata Management
author: Pulkit Nagpal(punagpal)
role: User, Admin
TQID: https://experienceleague.adobe.com/u3MZ3fUZIp-FYQE895I7kDRkF3l96KhwYMRMJ-rG2RE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 0%

---

# Comment ajouter , supprimer et gérer des balises dans votre contenu DITA

Les balises s’avèrent utiles pour classer votre contenu. Si le contenu est correctement balisé, il peut vous aider à localiser les rubriques exactes dans votre diamap et permettre à l’utilisateur final de trouver plus rapidement le contenu approprié dans votre sortie publiée

> **_REMARQUE:_** l’article suivant concerne AEM Guides Build 4.2 (on-prem) /Feb 2023 (version cloud ) ou versions ultérieures


## Créer des balises

Le balisage est une fonctionnalité native d’AEM. Votre administrateur AEM peut vous aider à créer et à configurer initialement ces balises.


## Ajouter, supprimer et gérer des balises dans votre contenu DITA

**Toutes les balises créées dans AEM cq : les balises peuvent être ajoutées, supprimées et gérées pour votre contenu DITA**

Il existe différentes manières d’ajouter des balises à votre contenu DITA, mais cet article se concentrera sur l’interface utilisateur de l’éditeur web d’AEM Guides.

### Étapes :

1. Accéder à la vue du référentiel dans l’interface utilisateur des guides
2. Double-cliquez sur ditamap et ouvrez dans la vue Carte
3. Accéder à l’onglet Gérer
4. Dans l’onglet Gérer , accédez à l’option Métadonnées .
5. La liste de tous vos fichiers ditamap directs et indirects est chargée ici.
6. Sélectionnez un ou plusieurs fichiers et cliquez sur l&#39;icône &#39;gérer&#39;. Ici, vous pouvez ajouter des balises aux fichiers sélectionnés.
Vous pouvez également supprimer les balises existantes qui sont communes dans les fichiers sélectionnés.

<img title="Gestion des balises dans AEM Guides " alt="Gestion des balises dans DITA " src="ManageTags.jpg">

## Résolution des problèmes et FAQ

### La liste dans manage->metadata est vide ou incomplète

`If list is empty or  incomplete then you may need to run the indexing on your ditamap, You can refer` [Instructions de mise à niveau (indexation de votre contenu)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/install-guide/on-prem-ig/download-install-upgrade-aemg/upgrade-xml-documentation.html?lang=fr#steps-to-index-the-existing-content-to-use-the-new-find-and-replace%3A)

### Les métadonnées personnalisées ne sont pas répertoriées dans la liste

`Only Tags present in cq:tags can be managed from here and custom metadata is not supported`




## Autres ressources utiles

- [Balisage en bloc à l’aide du tableau de bord des cartes (interface utilisateur d’Assets)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/manaege-metadata/map-editor-bulk-tagging.html?lang=fr)
- [Rapports Ditamap dans l’éditeur web](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/reports-aem-guide/reports-web-editor.html?lang=fr)
- [Balisage dans AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/configuring/tagging.html?lang=fr)


**Pour toute autre question, contactez votre CSM respectif**
