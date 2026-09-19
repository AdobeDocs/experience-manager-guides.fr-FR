---
title: Documentation de Experience Manager Guides
description: Recherchez la documentation d’Adobe Experience Manager Guides. Découvrez la prise en charge native de DITA, la création structurée et la publication multicanale dans Experience Manager.
feature: AEM Guides Tutorials
role: User
TQID: https://experienceleague.adobe.com/S4wTM-7gfU7D-JfKVbb9nK3qoQIG6PdiY7jtpsc6kDs
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
    internal-label: Reports
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: aad65a09-20cc-4780-ad44-329d14dc8481
    internal-label: Workflows
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
    internal-label: Content reuse
source-git-commit: a45df7e9eef75b0c4684e944fd9611eb6e7b060e
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 6%
---
# Documentation de Experience Manager Guides

Experience Manager Guides est un système de gestion de contenu d’entreprise avec prise en charge native de DITA pour la création structurée, la publication multicanal et la gestion du cycle de vie du contenu.

**Déploiement :** [!BADGE Cloud Service]{type=Positive} [!BADGE On-Premise]{type=Informative}

## Commencer par votre rôle

::::landing-cards-container
:::card
![ Icône Administrateurs ](../assets/admin.png)

Administrateurs

Configurez les profils de dossier, les autorisations, les paramètres de workflow et les modèles de sortie.

[Guide d’administration](./install-conf-guide/introduction.md)
:::

:::card
![ Icône Auteurs ](../assets/author.png)

Auteurs

Créez et gérez des rubriques, des mappages, une réutilisation du contenu et des workflows de révision DITA.

[Présentation de la création](./user-guide/authoring-content.md)
:::

:::card
![icône Éditeurs](../assets/publisher.png)

Editeurs

Configurez les paramètres prédéfinis de sortie, gérez les lignes de base et générez une sortie sur plusieurs canaux.

[Gestion et publication des cartes](./user-guide/map-console-overview.md)
:::

::::

<!--
:::card
![Architects icon](./user-guide/images/architect.svg)

Architects

Design DITA specializations, schemas, and content architecture for your implementation.

[DITA specialization](./install-conf-guide/dita-ot-specialization.md)
:::

::::
-->

## Explorer par domaine

<!-- Author note: Six cards wrap to two rows of three in production. The landing-cards-container component is in beta — verify rendering in production before publishing. -->

::::landing-cards-container

:::card
![Icône de création](../assets/authoring.png)

Création

Éditeur web, intégration de FrameMaker, contenu réutilisable et cycles de révision.

[Créer votre contenu](./user-guide/web-editor.md)
:::

:::card
![Icône Vérifier](../assets/review.png)

Révision

Consultez les rubriques, gérez les tâches et les notifications de révision.

[Présentation de la révision](./user-guide/review.md)
:::

:::card
![ Icône de publication ](../assets/publishing.png)

Publication

Types de sortie PDF, AEM Sites, HTML5, EPUB et JSON.

[Publier votre contenu](./user-guide/generate-output.md)
:::

:::card
![ Icône de traduction ](../assets/translation.png)

Traduction

Workflows de traduction humaine et automatique de contenu multilingue.

[Traduction du contenu](./user-guide/translation.md)
:::

:::card
![icône Rapports](../assets/reports.png)

Rapports

Liste de rubriques, multimédia, liens rompus et rapports de métadonnées.

[Génération de rapports](./user-guide/reports-intro.md)
:::

:::card
![Icône Configuration](../assets/configure.png)

Configuration

Profils de dossier, personnalisation DITA-OT et modèles de sortie.

[Configuration des profils de dossier](./install-conf-guide/conf-profiles.md)
:::

::::

## Nouveautés

<!-- Author note: Update images, badge labels, feature titles, descriptions, and links each release cycle. Images are stored in /assets/. The shade box with a borderless HTML table provides the three-column layout. Blank lines inside each <td> are required for ExL to process badge and bold-link markdown syntax. -->

>[!BEGINSHADEBOX]

<table>
<tr style="border: 0;">
<td>

![ Connecteur Git ](../assets/whats-new-git-connector.svg)

**[Importer du contenu à l’aide du connecteur Git](./user-guide/web-editor-git-connector.md)**

Importez le contenu dans les guides directement à partir des référentiels Git.

</td>
<td>

![Collection Map](../assets/whats-new-map-collection.svg)

**[Nouvelle collection de cartes](./user-guide/generate-output-use-new-map-collection-output-generation.md)**

Interface unifiée pour la gestion des cartes et la publication des sorties.

</td>
<td>

![Révision déléguée](../assets/whats-new-delegate-review.svg)

**[Déléguer une tâche de révision](./user-guide/review-complete-review-tasks.md#delegate-a-review-task-to-another-reviewer)**

Les réviseurs peuvent déléguer une tâche de révision à un autre réviseur.

</td>
</tr>
</table>

>[!ENDSHADEBOX]

## Ressources supplémentaires

* [Notes de mise à jour de Cloud Service](./release-info/latest-release-info-cs.md)
* [Notes de mise à jour d’On-Premise](./release-info/latest-release-info.md)
* [Communauté AEM Guides](https://experienceleaguecommunities.adobe.com/adobe-experience-manager-guides-11){target="_blank"}
* [Référentiel GitHub](https://github.com/AdobeDocs/experience-manager-guides.en){target="_blank"}
* [Assistance](https://experienceleague.adobe.com/support/v2/en/){target="_blank"}
* [Tutoriels vidéo](https://experienceleague.adobe.com/en/docs/experience-manager-guides-learn/videos/getting-started/overview){target="_blank"}
