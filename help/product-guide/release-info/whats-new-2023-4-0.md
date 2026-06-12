---
title: Notes de mise à jour | Adobe Experience Manager Guides as a Cloud Service, version d’avril 2023
description: Version d’avril 2023 d’Adobe Experience Manager Guides as a Cloud Service
exl-id: 269e3a13-584d-4cff-a18a-d4fa89646a5a
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/c1aOcwHgxAs11yAalOnlW-ghsTP1Or32TnBwLsc59-M
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2:
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 370
ht-degree: 0%

---

# Nouveautés de la version d’avril 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cet article couvre les nouvelles fonctionnalités et les fonctionnalités améliorées de la version d’avril 2023 d’Adobe Experience Manager Guides (plus tard appelée *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans cette version, consultez l’article [Notes de mise à jour](release-notes-2023-4-0.md).

## Prise en charge avancée des métadonnées dans la publication PDF

AEM Guides fournit désormais une prise en charge avancée des métadonnées qui sont mappées aux métadonnées dans votre sortie PDF. Les options de métadonnées comprennent des informations sur le document et son contenu, telles que le nom de l’auteur, le titre du document, les mots-clés, les informations de copyright et d’autres champs de données.

<img src="assets/pdf-metadata.png" alt=" métadonnées pdf natives">

Vous pouvez importer un fichier XMP et AEM Guides peut sélectionner les informations dans le fichier. Vous avez également la possibilité de fournir les noms et valeurs des métadonnées à l’aide de la liste déroulante. Vous pouvez également ajouter des métadonnées personnalisées en saisissant directement dans le champ du nom.


## Panneau Mode Plan amélioré

AEM Guides propose un panneau de mode Plan amélioré dans lequel vous obtenez la vue hiérarchique des éléments utilisés dans le document.

<img src="assets/select-element-content-outline-view_cs.png" alt=" métadonnées pdf natives">

Le mode Plan apporte les améliorations suivantes :

* La liste déroulante Options d’affichage s’affiche en haut du panneau Mode Plan. Si un élément possède un identifiant, un attribut et du texte, vous pouvez les sélectionner dans la liste déroulante pour les afficher avec l’élément. Les attributs qui peuvent être affichés dans le panneau Mode Plan sont déterminés par les paramètres Attributs d’affichage qui ont été configurés par votre administrateur dans les **Paramètres de l’éditeur**.

* La fonction de recherche vous permet de rechercher un élément par son nom, son identifiant, son texte ou sa valeur d’attribut.


## Publication basée sur les microservices pour AEM Guides as a Cloud Service

AEM Guides as a Cloud Service permet d’exécuter des charges de travail de publication volumineuses en même temps que la publication basée sur des microservices et d’exploiter la plateforme Adobe I/O Runtime sans serveur de pointe.

Désormais, dans la version d’avril, vous pouvez exécuter plusieurs requêtes de publication simultanément et générer des sorties PDF en bloc très efficacement à l’aide de la publication Native PDF basée sur un microservice.
Pour plus d’informations, consultez [Configuration d’une nouvelle publication basée sur un microservice pour AEM Guides as a Cloud Service](../knowledge-base/publishing/configure-microservices.md).
