---
title: Branchement dans AEM Guides | Adobe Experience Manager Guides
description: Découvrez comment créer et gérer les branches d'un plan DITA dans AEM Guides pour prendre en charge la création parallèle, la publication indépendante et la fusion des modifications de la documentation.
TQID: https://experienceleague.adobe.com/pg9zeEg8m3NeDbN-j945SqPbaMX0GgBmuquAsQcrjOM
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: ec4263d9-bf7c-44c7-b3f1-3e664861c8f2
    internal-label: Generative AI
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
    internal-label: Content reuse
source-git-commit: 3f0d8e31537ade58a4eab5ddf73eb6d263d3dd96
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 0%
---
# Vue d’ensemble

>[!NOTE]
>
> La fonctionnalité d’embranchement et de fusion est introduite dans la version 2026.11.0 de Experience Manager Guides as a Cloud Service et est désactivée par défaut. Pour activer cette fonctionnalité dans votre environnement, contactez votre équipe du succès client.

L&#39;embranchement dans Adobe Experience Manager Guides vous permet de créer et de gérer plusieurs branches en dehors de la branche **principale** pour qu&#39;un plan DITA fonctionne sur différentes versions de documentation en parallèle. Chaque branche permet aux auteurs de gérer les modifications de contenu de manière indépendante, sans affecter le contenu correspondant dans les autres branches.

Avec l&#39;embranchement, plusieurs équipes peuvent travailler simultanément sur différentes versions, fonctionnalités ou correctifs associés à un même plan DITA. Vous pouvez fusionner les modifications d’une branche dans la branche par défaut (`main`) lorsque les mises à jour sont prêtes.

## Fonctionnement de l’embranchement

Vous pouvez créer une branche à partir de la **principale** ou de n&#39;importe quelle branche existante d&#39;un plan DITA. Après avoir créé une branche, vous pouvez y accéder et commencer à modifier la carte et son contenu. Vous pouvez également publier du contenu à partir de la branche sélectionnée ou fusionner les modifications dans `main` lorsque vous êtes prêt.

Prenons l&#39;exemple d&#39;un plan DITA nommé `install-the-lift.ditamap` qui contient les instructions d&#39;installation d&#39;un produit. Votre équipe de documentation peut créer deux branches de ce mappage à partir de `main` :

- **Version 1 :** L’équipe A conserve les instructions d’installation existantes et les correctifs d’adresses.
- **Version 2 :** L’équipe B développe des instructions d’installation pour les nouvelles fonctionnalités.

Les deux équipes peuvent travailler indépendamment sur leurs branches de carte respectives sans affecter les modifications de l’une et de l’autre.

>[!NOTE]
>
>Une branche est créée à partir d&#39;un plan DITA. Vous pouvez également ajouter et modifier des rubriques qui ne sont pas référencées par le mappage dans la branche sélectionnée. Pour plus d&#39;informations, voir [Ouvrir ou modifier les rubriques en dehors de la carte actuelle](./create-manage-branch.md#open-or-edit-topics-outside-the-current-map-context).

Lorsque vous créez une branche d&#39;un plan DITA, Experience Manager Guides ne copie pas automatiquement les rubriques référencées du plan dans la nouvelle branche. Les rubriques inchangées sont lues à partir de la branche source ou de la branche par défaut (principale). Une rubrique n’est copiée dans la nouvelle branche que lorsque vous la modifiez et l’enregistrez dans cette branche.

Par exemple, un plan DITA fait référence à 100 rubriques et le référentiel contient 50 rubriques supplémentaires qui ne sont pas référencées par le plan. Lorsque vous créez une branche (version 1.0), les 100 rubriques référencées font automatiquement partie de la version 1.0, même si aucune d’entre elles n’est modifiée. Les 50 rubriques non référencées ne font pas automatiquement partie de la nouvelle branche. Si vous modifiez 10 d’entre elles, seules ces 10 deviennent partie intégrante de la version 1.0. Les 40 autres rubriques inchangées continuent d’être utilisées à partir de la branche par défaut (principale).

>[!NOTE]
>
> Le contrôle de version de rubrique continue de fonctionner avec l’embranchement. Vous pouvez créer et gérer des versions de rubriques dans une branche sélectionnée d&#39;un plan DITA. Chaque branche conserve son propre historique de versions, indépendant des autres branches.

## Principaux avantages

L’utilisation d’une branche dans Experience Manager Guides offre les avantages suivants :

- **Modification isolée :** effectuez des modifications dans une branche map sélectionnée sans affecter le contenu correspondant dans les autres branches.
- **Création parallèle :** permet à plusieurs équipes de travailler simultanément sur différentes versions, fonctionnalités ou correctifs au sein de leurs branches de mappage respectives.
- **Publication indépendante :** publiez la documentation à partir de branches de mappage individuelles sans attendre que les modifications d’autres branches soient terminées.
- **Fusion contrôlée :** permet de fusionner les modifications d’une branche de mappage dans la branche par défaut (`main`), avec la possibilité de vérifier et de résoudre les conflits.

## Branchement ou lignes de base

>[!NOTE]
>
> Les lignes de base et les embranchements s&#39;excluent mutuellement. Lorsque l’embranchement est activé, la fonctionnalité de ligne de base n’est plus disponible. Toutefois, les références existantes restent intactes et ne sont pas supprimées. Si l&#39;embranchement est désactivé ultérieurement, les lignes de base existantes peuvent à nouveau être utilisées.

Une **ligne de base** identifie une combinaison spécifique de versions de rubrique pour un plan DITA, ce qui vous permet de générer une sortie à l&#39;aide de ces versions sélectionnées.

Une **branche** fournit un environnement de modification distinct pour un plan DITA et son contenu, ce qui permet aux auteurs d&#39;apporter des modifications sans affecter d&#39;autres branches du même plan.

| Niveaux de référence | Branchement |
|---|---|
| Sélectionnez des versions spécifiques des rubriques dans un plan DITA. | Créez des branches distinctes d&#39;un plan DITA pour gérer les modifications de manière indépendante. |
| Utilisé pour publier des combinaisons spécifiques de versions de rubrique. | Permet de développer et de publier différentes versions en parallèle. |
| Ne fournissez pas de contextes de modification isolés. | Prendre en charge la modification et la fusion isolées. |

## Fonctionnalités à venir

Les fonctionnalités suivantes ne sont actuellement prises en charge que dans la branche par défaut (`main`) et devraient l&#39;être dans d&#39;autres branches d&#39;un plan DITA dans les prochaines versions de Experience Manager Guides :

- Rechercher
- Rechercher et remplacer
- Vérifier les workflows

