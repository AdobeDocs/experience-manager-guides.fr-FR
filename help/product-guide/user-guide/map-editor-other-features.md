---
title: Autres fonctionnalités des éditeurs de carte
description: Découvrez certaines fonctionnalités courantes des éditeurs de mappage de base et avancé. Découvrez comment résoudre les références clés dans l’éditeur de cartes.
exl-id: f0e7a402-ac12-4c63-9d7f-92567ee29a39
feature: Authoring, Map Editor
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 0%

---

# Autres fonctionnalités des éditeurs de carte {#id1942D0T0HUI}

Voici quelques fonctions courantes des éditeurs de mappage de base et avancé :

## Résoudre les références de clés {#id176GD01H05Z}

Une référence de clé de contenu DITA, ou `conkeyref`, est un mécanisme permettant d’insérer une partie du contenu d’une rubrique dans une autre. Ce mécanisme utilise la clé pour localiser le contenu à réutiliser plutôt que le mécanisme de référencement direct du contenu. Pour plus d’informations sur le référencement direct et indirect dans DITA, voir *Adressage DITA* dans Spécification du langage OASIS DITA.

Si la rubrique DITA comporte des références clés associées, elles doivent être résolues avant de prévisualiser, modifier ou revoir une rubrique.

Les références clés sont résolues sur la base de la carte racine définie dans l’ordre de priorité suivant :

1. Préférences utilisateur
1. Panneau Vue Carte
1. Profil de dossier

La carte racine sélectionnée dans les préférences utilisateur a la priorité la plus élevée pour résoudre les références clés, suivies du panneau Vue Carte et de la carte racine du profil du dossier. Ainsi, si aucune carte n’est définie dans les préférences utilisateur, la carte ouverte dans le panneau Vue des cartes est utilisée. Si aucun mappage n’est ouvert dans le panneau Vue des cartes, l’ensemble de mappages dans les profils de dossier est utilisé pour résoudre les références clés.

Les références de clé peuvent être stockées dans un fichier de mappage DITA ou un fichier DITA distinct. Dans AEM Guides, vous pouvez spécifier des références clés au niveau du projet ou d’une session. Si une carte racine est déjà définie pour la session utilisateur, elle est utilisée pour résoudre les clés. Sinon, la carte racine par défaut de ce dossier est utilisée. Si aucun mappage racine par défaut n’est configuré, les références clés manquantes sont mises en surbrillance pour l’utilisateur.

Il existe plusieurs façons de résoudre les références clés dans une rubrique DITA en définissant le mappage DITA à utiliser aux emplacements suivants :

**Propriétés du projet** - Vous pouvez définir une carte racine pour résoudre les références clés lors de la création d’un projet dans la section Propriétés du projet.

Ce mappage racine s’applique à toutes les ressources \(dossiers et sous-dossiers\) associées à ce projet. Pour le contenu référencé dans plusieurs projets, une liste alphabétique des projets est conservée et la carte racine par défaut associée au premier projet est utilisée. Vous pouvez également choisir le mappage DITA à utiliser dans la liste pour résoudre les références clés.

**Aperçu de la rubrique** - En mode d’aperçu de la rubrique, cliquez sur l’icône Résolution de la clé dans la barre d’outils et sélectionnez le fichier DITA à utiliser pour les références de clé.

**Vue de modification de la rubrique** - Cliquez sur l’icône Résolution de la clé lors de la modification d’une rubrique DITA et sélectionnez le fichier DITA à utiliser pour résoudre les références de clé.

**Rubrique parente :**[ Utilisation de l’éditeur de cartes](map-editor.md)
