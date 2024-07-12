---
title: Gestion du contenu
description: Gérez le contenu et identifiez vos rôles et autorisations dans AEM Guides. Découvrez les concepts clés de la gestion de contenu et de l’utilisation des profils globaux ou au niveau des dossiers.
exl-id: 84926dc2-1180-48ef-85d0-50e3478bf26a
feature: Content Management
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 10%

---

# Gestion du contenu {#id164JBG0M0T1}

Avant de commencer la création proprement dite du contenu, vous devez vous familiariser avec certains concepts de base de la gestion de contenu dans AEM Guides. Commencez ensuite par créer différents groupes d’utilisateurs et organiser vos ressources.

## Principaux concepts

Voici quelques concepts clés de la gestion de contenu dans AEM :

**Gestion des ressources**

AEM Guides utilise la gestion des actifs numériques (DAM)  pour gérer vos fichiers DITA. Les fichiers que vous chargez ou archivez dans la gestion des ressources numériques sont stockés en tant que ressources numériques. Vous pouvez gérer et modifier vos ressources dans AEM Assets. Pour plus d’informations sur la gestion des ressources, voir [Gestion des ressources](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=fr).

**Gestion des liens**

Déplacez ou renommez des fichiers ou modifiez la structure de dossiers dans le référentiel de contenu, sans vous soucier des références rompues. Toutes les références au contenu concerné et à ce contenu sont automatiquement mises à jour. Recevez des avertissements lors de la suppression d’un contenu référencé à partir d’un autre emplacement afin d’éviter toute rupture involontaire.

**Gestion des versions**

AEM Guides permet de gérer les versions de vos ressources numériques. Vous pouvez facilement activer cette fonctionnalité depuis une application de création DITA de votre choix. Permet à vos auteurs d’exécuter les fonctions de contrôle de version standard telles que l’archivage et l’extraction.

Pour plus d’informations sur la création de versions ou le rétablissement d’une version spécifique, voir [Branche, restauration et contrôle de version ultérieur](web-editor-preview-topics.md#id193PG0Y051X).

**Gestion native de DITA**

Bien qu’AEM Guides conserve la structure de vos fichiers DITA, il permet également à AEM de gérer de manière native le DITA à l’aide du mappage d’éléments pour mapper les éléments DITA aux composants AEM. La gestion native du DITA est utilisée dans des fonctionnalités telles que l’aperçu de rubrique, la publication AEM Sites et les workflows de révision.

## Identification de votre rôle et de vos autorisations {#id181TF0K0MHT}

AEM Guides fournit trois groupes prêts à l’emploi. Ces groupes sont les suivants : *Auteurs*, *Réviseurs* et *Éditeurs*. Selon le groupe auquel vous êtes associé, vous disposez des autorisations nécessaires pour effectuer des tâches spécifiques, comme indiqué dans le tableau ci-dessous. Par exemple, la tâche de publication peut être effectuée uniquement par un éditeur, mais pas par un auteur ou un réviseur. De même, un auteur peut créer une rubrique et un réviseur ne peut consulter qu’une rubrique.

>[!TIP]
>
> Consultez la section *Autorisations* du guide Bonnes pratiques pour connaître les bonnes pratiques relatives à la définition des autorisations d’utilisateur.

Le tableau suivant répertorie les différentes tâches et les groupes pouvant effectuer ces tâches :

| Tâche | Auteurs | Réviseurs | Éditeurs |
|----|-------|---------|----------|
| Création d’une rubrique DITA | Oui |   | Oui |
| Création d’une carte DITA | Oui |   | Oui |
| Mappage de collections | Oui |   | Oui |
| Créer une tâche de révision | Oui |   | Oui |
| Rubrique de révision[1](#fntarg_1) | Oui | Oui | Oui |
| Résolution des clés | Oui |   | Oui |
| Extraction/archivage | Oui |   | Oui |
| Modifier le sujet | Oui |   | Oui |
| Déplacer la rubrique | Oui |   | Oui |
| Modification des propriétés de rubrique | Oui |   | Oui |
| Copier | Oui |   | Oui |
| Supprimer | Oui |   | Oui |
| Partager | Oui |   | Oui |
| **État du document** |
| Création/modification d’un profil d’état de document |   |   | Oui |
| Modifier l’état du document[2](#fntarg_2) | Oui | Oui | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(onglet Paramètres prédéfinis de sortie\)** |
| Générer |   |   | Oui |
| Modifier |   |   | Oui |
| Dupliquer |   |   | Oui |
| Créer |   |   | Oui |
| Supprimer le paramètre prédéfini |   |   | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(onglet Sorties\){1** |
| Afficher la sortie générée | Oui |   | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(onglet Rubriques\){1** |
| Créer une tâche de révision | Oui |   | Oui |
| Modifier | Oui |   | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(onglet Lignes de base\){1** |
| Créer |   |   | Oui |
| Modifier |   |   | Oui |
| Dupliquer |   |   | Oui |
| Supprimez |   |   | Oui |
| Console de mappage DITA \(onglet Rapports\) | Oui |   | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(Paramètres prédéfinis de condition\)** |
| Créer/modifier un paramètre prédéfini de condition |   |   | Oui |

[1](#fnsrc_1) Si *Auteurs* et *Éditeurs* sont invités pour une révision.

[2](#fnsrc_2) Selon les droits accordés à l’utilisateur dans le profil d’état du document.

## Conditions préalables à la création de contenu

**Utilisation de profils globaux ou au niveau du dossier**

Dans une entreprise, différents groupes ou produits peuvent utiliser différents modèles de création, modèles de sortie, profils d’attributs conditionnels \(ou schémas d’objet\) et configurations de l’éditeur web. La configuration de ces éléments au niveau d’une entreprise \(ou globale\) peut rendre l’expérience des auteurs difficile, car ils verront des modèles ou des profils qui ne sont pas pertinents pour eux.

AEM Guides vous permet de configurer la création de modèles \(rubrique ou mappage\), de modèles de sortie, d’attributs conditionnels et de configurations d’éditeur web au niveau de l’entreprise \(globale\) ainsi qu’au niveau des dossiers. Ainsi, vous pouvez séparer les configurations pour différents services ou produits de votre entreprise.

Vous pouvez également déléguer les configurations spécifiques aux dossiers à un service ou à des administrateurs de produit pour décentraliser l’administration.

Pour plus d’informations sur la configuration des profils globaux et au niveau du dossier, voir *Configuration des profils globaux ou au niveau du dossier* dans Installation et configuration d’Adobe Experience Manager Guides as a Cloud Service.
