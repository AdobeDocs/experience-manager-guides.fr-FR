---
title: Notes de mise à jour | Nouveautés d’Adobe Experience Manager Guides version 2024.06.0
description: Découvrez les nouvelles fonctionnalités et les fonctionnalités améliorées de la version 2024.06.0 d’Adobe Experience Manager Guides as a Cloud Service.
exl-id: c885b8ba-5230-4d51-8f38-311b3a33fe0a
TQID: https://experienceleague.adobe.com/yw75NaMre6IwRbTBHS-V-XdZgVqdhY3H2-GDrB3ZRcQ
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2:
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 649
ht-degree: 2%

---

# Nouveautés de la version 2024.06.0

Cet article présente les nouvelles fonctionnalités améliorées de la version 2024.06.0 d’Adobe Experience Manager Guides.

Pour connaître la liste des problèmes résolus dans cette version, voir la section [Problèmes résolus dans la version 2024.06.0](fixed-issues-2024-06-0.md).

Découvrez les [instructions de mise à niveau pour la version 2024.06.0](upgrade-instructions-2024-06-0.md).


## Publier une rubrique ou ses éléments dans un fragment d’expérience

Un fragment d’expérience est une unité de contenu modulaire au sein de Adobe Experience Manager qui intègre du contenu et une mise en page. Les fragments d’expérience sont essentiels à la création d’expériences cohérentes et attrayantes, qui peuvent être réutilisées sur plusieurs canaux.


Experience Manager Guides vous permet désormais de publier une rubrique ou ses éléments dans un fragment d’expérience. Vous pouvez créer un mappage JSON entre une rubrique et ses éléments dans un fragment d’expérience. Par exemple, vous pouvez créer des fragments d’expérience pour les en-têtes ou pieds de page avec des éléments de marque, des bannières promotionnelles, des témoignages de clients et des promotions d’événement.




Pour plus d’informations, consultez [Publication de fragments d’expérience](../user-guide/publish-experience-fragment.md).


## Améliorations apportées à la publication de fragments de contenu

Experience Manager Guides propose également des améliorations utiles dans les fragments de contenu :

- Vous pouvez facilement filtrer le contenu avec des conditions lors de la publication dans un fragment de contenu, à l’aide d’un fichier DITAVAL ou d’attributs conditionnels.
- Vous pouvez également publier et afficher les fragments de contenu d’une rubrique à partir de la section **Sorties** de la section **Propriétés du fichier**.

![onglet options des propriétés du fichier](./assets/file-properties-outputs-tab.png){width="300"}

Pour plus d’informations, voir [Publication de fragments de contenu](../user-guide/publish-content-fragment.md).


## Possibilité de transmettre des métadonnées des propriétés de fichier de rubrique à la sortie native de PDF

Désormais, Experience Manager Guides vous permet d’ajouter les métadonnées des propriétés de fichier d’une rubrique aux mises en page tout en générant la sortie Native PDF. Utilisez cette fonctionnalité pour ajouter des métadonnées spécifiques à la rubrique telles que le titre, les balises et la description aux mises en page. Vous pouvez également personnaliser le PDF publié en fonction des métadonnées de la rubrique, par exemple en ajoutant un filigrane à l’arrière-plan de la rubrique en fonction de l’état du document de la rubrique.

![ajout d’un pdf natif de métadonnées](./assets/add-metadata-native-pdf.png) {width="300"}

*Ajouter des métadonnées aux champs dans vos mises en page.*

Découvrez comment [ajouter des champs et des métadonnées](../native-pdf/design-page-layout.md#add-fields-metadata) dans une mise en page.

## Sélection de contenu partiel sur plusieurs éléments pour les opérations

Experience Manager Guides améliore votre expérience de sélection du contenu dans les éléments de l’éditeur web. Vous pouvez facilement sélectionner du contenu sur différents éléments et effectuer des opérations telles que le mettre en gras, en italique ou en souligné. Cette fonctionnalité vous permet d’appliquer ou de supprimer facilement la mise en forme du contenu partiellement sélectionné. Vous pouvez également supprimer rapidement le contenu que vous avez sélectionné dans plusieurs éléments. Une fois le contenu supprimé, si nécessaire, le contenu restant est automatiquement fusionné sous un seul élément valide.

Vous pouvez également sélectionner du contenu partiel sur plusieurs éléments, puis entourer le contenu sous un élément DITA valide.
![boîte de dialogue entourer l’élément](./assets/surround-element.png) {width="300"}

*Entourez le contenu sélectionné d’un élément valide.*

Dans l’ensemble, ces améliorations vous offrent une meilleure expérience et vous aident à améliorer votre efficacité lors de la modification de vos documents.

Pour plus d’informations, consultez la section [Sélection partielle du contenu sur plusieurs éléments](../user-guide/web-editor-edit-topics.md#partial-selection-of-content-across-elements).

## Prise en charge des documents Markdown dans la publication native de PDF

Experience Manager Guides prend également en charge les documents Markdown dans la publication native de PDF. Cette fonctionnalité est pratique et vous permet de générer des fichiers PDF pour les fichiers Markdown dans votre plan DITA. La prise en charge de Markdown dans la publication native de PDF vous permet de créer, gérer et partager facilement vos documents.

Pour plus d’informations, consultez la section [Prise en charge des documents Markdown](../web-editor/native-pdf-web-editor.md#support-for-markdown-documents).


## Amélioration des performances et de l’évolutivité pour les grands projets de traduction

La fonction de traduction est plus rapide et plus évolutive que jamais. Il s’accompagne d’une nouvelle architecture qui offre des performances améliorées. Le temps de création du projet est maintenant plus rapide qu&#39;auparavant et les conflits pendant le processus sont presque inexistants. Ces performances améliorées vous permettent de réaliser des traductions plus rapides, ce qui garantit un fonctionnement fluide, même pour les projets de traduction volumineux.

Cette amélioration est très bénéfique, car elle améliore la productivité et l’expérience globale.

En savoir plus sur la [traduction de documents à partir de l’éditeur web](../user-guide/translate-documents-web-editor.md).
