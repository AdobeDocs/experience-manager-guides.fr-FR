---
title: Gestion du contenu
description: Gérer le contenu et identifier vos rôles et autorisations dans AEM Guides Découvrez les concepts clés de la gestion de contenu et de l’utilisation des profils globaux ou au niveau du dossier.
feature: Content Management
role: User
hide: true
exl-id: 54b960cf-fb00-4d4a-a836-9de4738c49a8
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 10%

---

# Gestion du contenu {#id164JBG0M0T1}

Avant de commencer à créer du contenu, vous devez vous familiariser avec certains concepts de base de la gestion de contenu dans AEM Guides. Ensuite, commencez par créer différents groupes d’utilisateurs et organiser vos ressources.

## Concepts clés

Voici quelques concepts clés de la gestion de contenu dans AEM :

**Gestion des ressources**

AEM Guides utilise la gestion des ressources numériques AEM \(DAM\) pour gérer vos fichiers DITA. Les fichiers que vous chargez ou archivez dans la gestion des ressources numériques (DAM) sont stockés en tant que ressources numériques. Vous pouvez gérer et modifier vos ressources dans AEM Assets. Pour plus d’informations sur la gestion des ressources, voir [Gestion des ressources](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=fr).

**Gestion des liens**

Déplacez ou renommez des fichiers ou modifiez la structure des dossiers dans le référentiel de contenu, sans vous soucier des références rompues. Toutes les références au contenu affecté et à partir de celui-ci sont automatiquement mises à jour. Recevez des avertissements lors de la suppression de contenu référencé à partir d’un autre emplacement afin d’éviter les ruptures involontaires.

**Gestion des versions**

AEM Guides fournit une gestion des versions pour vos ressources numériques. Vous pouvez facilement activer cette fonctionnalité à partir d&#39;une application de création DITA de votre choix. Autoriser vos rédacteurs à exécuter les fonctions de contrôle de version standard telles que l’archivage et l’extraction.

Pour plus d’informations sur la création de versions ou le rétablissement d’une version spécifique, voir [Branche, rétablissement et contrôle de version ultérieur](web-editor-preview-topics.md#id193PG0Y051X).

**Gestion native de DITA**

Bien qu&#39;AEM Guides conserve la structure de vos fichiers DITA, il permet également à AEM de gérer nativement DITA à l&#39;aide du mappage d&#39;éléments pour mapper les éléments DITA aux composants AEM. La gestion native de DITA est utilisée dans des fonctionnalités telles que la prévisualisation de rubrique, la publication AEM Sites et les workflows de révision.

## Identification de votre rôle et des autorisations {#id181TF0K0MHT}

AEM Guides fournit trois groupes prêts à l’emploi. Ces groupes sont les suivants : *Auteurs*, *Réviseurs* et *Éditeurs*. Selon le groupe auquel vous êtes associé, vous disposez des autorisations nécessaires pour effectuer des tâches spécifiques, comme indiqué dans le tableau ci-dessous. Par exemple, une tâche de publication ne peut être effectuée que par un éditeur, mais pas par un auteur ou un réviseur. De même, un auteur peut créer une rubrique et un réviseur peut uniquement réviser une rubrique.

>[!TIP]
>
> Voir la section *Autorisations* dans le guide des bonnes pratiques pour connaître les bonnes pratiques relatives à la définition des autorisations utilisateur.

Le tableau suivant répertorie les différentes tâches et les groupes qui peuvent les effectuer :

| Tâche | Auteurs | Réviseurs | Editeurs |
|----|-------|---------|----------|
| Créer une rubrique DITA | Oui |   | Oui |
| Créer un plan DITA | Oui |   | Oui |
| Mapper les collections | Oui |   | Oui |
| Créer une tâche de révision | Oui |   | Oui |
| Rubrique [ révision 1](#fntarg_1) | Oui | Oui | Oui |
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

## Conditions préalables à la création de contenu

**Utilisation de profils globaux ou de niveau dossier**

Dans une entreprise, différents groupes ou produits peuvent utiliser différents modèles de création, modèles de sortie, profils d’attributs conditionnels \(ou schémas d’objet\) et configurations de l’éditeur web. Leur configuration uniquement au niveau de l’entreprise \(ou global\) peut rendre l’expérience difficile pour les auteurs, car ils verront des modèles ou des profils qui ne les concernent pas.

AEM Guides vous permet de configurer les modèles de création \(rubrique ou mappage\), les modèles de sortie, les attributs conditionnels et les configurations de l’éditeur web au niveau de l’entreprise \(global\) ainsi qu’au niveau des dossiers. Vous pouvez ainsi séparer les configurations pour différents services ou produits de votre entreprise.

Vous pouvez également déléguer les configurations spécifiques aux dossiers à un service ou à des administrateurs de produit afin de décentraliser l’administration.

Pour plus d’informations sur la configuration des profils globaux et au niveau du dossier, voir *Configuration des profils globaux ou au niveau du dossier* dans Installation et configuration d’Adobe Experience Manager Guides as a Cloud Service.
