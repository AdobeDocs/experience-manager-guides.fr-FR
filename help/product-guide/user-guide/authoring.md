---
title: Gestion du contenu
description: Gérer le contenu et identifier vos rôles et autorisations dans AEM Guides Découvrez les concepts clés de la gestion de contenu et de l’utilisation des profils globaux ou au niveau du dossier.
exl-id: 84926dc2-1180-48ef-85d0-50e3478bf26a
feature: Content Management
role: User
TQID: https://experienceleague.adobe.com/IoB9Dk9vwDaGSsqR-M7VobGnVcD5fMnACBhwkJrLN-I
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: da3860b0-d637-47df-bef0-273751180266
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 604
ht-degree: 15%

---

# Gestion du contenu {#id164JBG0M0T1}

Avant de commencer à créer du contenu, vous devez vous familiariser avec certains concepts de base de la gestion de contenu dans Adobe Experience Manager Guides. Ensuite, commencez par créer différents groupes d’utilisateurs et organiser vos ressources.

## Concepts clés

Voici quelques concepts clés de la gestion de contenu dans Adobe Experience Manager :

**Gestion des ressources**

Experience Manager Guides utilise la gestion des ressources numériques Adobe Experience Manager \(DAM\) pour gérer vos fichiers DITA. Les fichiers que vous chargez ou archivez dans la gestion des ressources numériques (DAM) sont stockés en tant que ressources numériques. Vous pouvez gérer et modifier vos ressources dans Adobe Experience Manager Assets. Pour plus d’informations sur la gestion des ressources, voir [Gestion des ressources](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=fr).

**Gestion des liens**

Déplacez ou renommez des fichiers ou modifiez la structure des dossiers dans le référentiel de contenu, sans vous soucier des références rompues. Toutes les références au contenu affecté et à partir de celui-ci sont automatiquement mises à jour. Recevez des avertissements lors de la suppression de contenu référencé à partir d’un autre emplacement afin d’éviter les ruptures involontaires.

**Gestion des versions**

Experience Manager Guides fournit une gestion des versions pour vos ressources numériques. Vous pouvez facilement activer cette fonctionnalité à partir d&#39;une application de création DITA de votre choix. Autoriser vos rédacteurs à exécuter les fonctions de contrôle de version standard telles que l’archivage et l’extraction.

Pour plus d’informations sur la création de versions ou le rétablissement d’une version spécifique, consultez [Branche, rétablissement et contrôle de version ultérieur](web-editor-preview-topics.md#branch-revert-and-subsequent-versioning).

**Gestion native de DITA**

Bien que Experience Manager Guides conserve la structure de vos fichiers DITA, il permet également à Adobe Experience Manager de gérer nativement DITA à l&#39;aide du mappage d&#39;éléments pour mapper les éléments DITA aux composants Adobe Experience Manager. La gestion native de DITA est utilisée dans des fonctionnalités telles que la prévisualisation de rubrique, la publication Adobe Experience Manager Sites et les workflows de révision.

## Identification de votre rôle et des autorisations {#id181TF0K0MHT}

Experience Manager Guides fournit trois groupes prêts à l’emploi. Ces groupes sont les suivants : *Auteurs*, *Réviseurs* et *Éditeurs*. Selon le groupe auquel vous êtes associé, vous disposez des autorisations nécessaires pour effectuer des tâches spécifiques, comme indiqué dans le tableau ci-dessous. Par exemple, une tâche de publication ne peut être effectuée que par un éditeur, mais pas par un auteur ou un réviseur. De même, un auteur peut créer une rubrique et un réviseur peut uniquement réviser une rubrique.

>[!TIP]
>
> Consultez la section *Autorisations* dans le guide des bonnes pratiques pour connaître les bonnes pratiques relatives à la définition des autorisations utilisateur.

Le tableau suivant répertorie les différentes tâches et les groupes qui peuvent les effectuer :

| Tâche | Auteurs | Réviseurs | Editeurs |
|----|-------|---------|----------|
| Créer une rubrique DITA | Oui |   | Oui |
| Créer un plan DITA | Oui |   | Oui |
| Mapper les collections | Oui |   | Oui |
| Créer une tâche de révision | Oui |   | Oui |
| Rubrique [&#x200B; révision 1](#fntarg_1) | Oui | Oui | Oui |
| Résolution de la clé | Oui |   | Oui |
| Extraction/enregistrement | Oui |   | Oui |
| Modifier le sujet | Oui |   | Oui |
| Déplacer rubrique | Oui |   | Oui |
| Modifier les propriétés de rubrique | Oui |   | Oui |
| Copier | Oui |   | Oui |
| Supprimer | Oui |   | Oui |
| Partager | Oui |   | Oui |
| **État du document** |  |  |  |
| Créer/modifier un profil d’état de document |   |   | Oui |
| Modifier l’état du document [2](#fntarg_2) | Oui | Oui | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(onglet Paramètres prédéfinis de sortie\)** |  |  |  |
| Générer |   |   | Oui |
| Modifier |   |   | Oui |
| Doublon |   |   | Oui |
| Créer |   |   | Oui |
| Supprimer le paramètre prédéfini |   |   | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(onglet Sorties\)** |  |  |  |
| Afficher la sortie générée | Oui |   | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(Onglet Rubriques\)** |  |  |  |
| Créer une tâche de révision | Oui |   | Oui |
| Modifier | Oui |   | Oui |
| **Fonctionnalités disponibles dans la console de plan DITA \(onglet Lignes de base\)** |  |  |  |
| Créer |   |   | Oui |
| Modifier |   |   | Oui |
| Doublon |   |   | Oui |
| Supprimer |   |   | Oui |
| Console de mappage DITA \(onglet Rapports\) | Oui |   | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(Paramètres prédéfinis de condition\)** |  |  |  |
| Créer/modifier un paramètre prédéfini de condition |   |   | Oui |

[1](#fnsrc_1) Si *Auteurs* et *Éditeurs* sont invités pour une révision.

[2](#fnsrc_2) selon les droits accordés à l’utilisateur dans le profil d’état du document.
