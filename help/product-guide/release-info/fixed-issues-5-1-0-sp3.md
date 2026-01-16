---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides 5.1.0 Service Pack 3
description: Découvrez les correctifs de bugs dans la version 5.1.0 Service Pack 3 d’Adobe Experience Manager Guides
role: Leader
source-git-commit: 82eb0e18eb285006c66b1fe2b6ecc3ca86fefe61
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 1%

---

# Correction de problèmes dans la version 5.1.0 Service Pack 3 (décembre 2025)


Cet article couvre les bugs corrigés dans différentes zones de la version 5.1.0 Service Pack 3 d’Adobe Experience Manager Guides.

Découvrez les [instructions de mise à niveau pour la version 5.1.0 du pack de services 3](upgrade-instructions-5-1-0-sp3.md).


## Création

- Le CSS personnalisé appliqué à un profil au niveau du dossier pour les rubriques ou les mappages est rétabli au style par défaut dans le mode Aperçu lors de l’actualisation du navigateur. (GUIDES-31098)
- Impossible d’ajouter plusieurs **libellés de version** à une rubrique dans la boîte de dialogue **Enregistrer en tant que nouvelle version**. (GUIDES-32716)


## Gestion des ressources numériques

- Impossible de supprimer les libellés de version du panneau **Historique des versions** dans l’interface utilisateur Assets. (GUIDES-38276)


## Révision

- Lorsque le réviseur termine une tâche de révision ou que l’initiateur met à jour la tâche de révision sans saisir de commentaires, l’e-mail de notification envoyé affiche le commentaire précédent le plus récent. (GUIDES-33590)

## Publication

- Lorsque vous générez une sortie AEM Sites à l’aide du mappage des composants hérités, les rubriques qui utilisent l’attribut `copy-to` sont publiées avec le nom de la rubrique `copy-from` au lieu du nom défini dans l’attribut `copy-to`. (GUIDES-22155)
- Lorsque la sortie native de PDF est générée à l’aide d’une ligne de base dynamique, le terme **PDFProject** s’affiche en tant que titre de PDF au lieu du titre de mappage réel. (GUIDES-31102)

## Plateforme

- L’utilisation de `scope="external"` pour une référence au contenu de gestion des ressources numériques dans une rubrique ou un mappage entraîne la substitution du chemin relatif de la ressource par un GUID. (GUIDES-35605)

## Problème connu

Adobe a identifié le problème connu suivant pour la version 5.1.0 du pack de services 3 :

- Lorsque vous marquez une tâche de révision comme terminée à partir de la page Détails de la tâche, la tâche est terminée et fermée ; cependant, son statut continue de s’afficher comme **En cours** dans le tableau de bord de révision. (GUIDES-39375)




