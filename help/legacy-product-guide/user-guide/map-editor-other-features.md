---
title: Autres fonctionnalités dans les éditeurs de carte
description: Découvrez quelques fonctionnalités courantes des éditeurs de carte de base et avancés. Découvrez comment résoudre les références clés dans l’éditeur de cartes.
feature: Authoring, Map Editor
role: User
hide: true
exl-id: d6e00884-e17c-499e-9568-0807a75051ad
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 0%

---

# Autres fonctionnalités dans les éditeurs de carte {#id1942D0T0HUI}

Voici quelques fonctionnalités courantes des éditeurs de carte de base et avancés :

## Résoudre les principales références {#id176GD01H05Z}

Une référence de clé de contenu DITA, ou `conkeyref`, est un mécanisme permettant d&#39;insérer une partie du contenu d&#39;une rubrique dans une autre. Ce mécanisme utilise la clé pour localiser le contenu à réutiliser plutôt que le mécanisme de référencement direct du contenu. Pour plus d&#39;informations sur les références directes et indirectes dans DITA, consultez *Adressage DITA* dans Spécification de langage OASIS DITA.

Si la rubrique DITA est associée à des références clés, celles-ci doivent être résolues avant de prévisualiser, modifier ou réviser une rubrique.

Les références clés sont résolues sur la base du mappage racine défini dans l’ordre de priorité suivant :

1. Préférences utilisateur
1. Panneau Vue Carte
1. Profil de dossier

La carte racine sélectionnée dans les Préférences utilisateur a la priorité la plus élevée pour résoudre les références clés, suivie du panneau Vue Carte et de la carte racine Profil de dossier. Ainsi, si aucune carte n’est définie dans les Préférences utilisateur, la carte ouverte dans le panneau Vue Carte est utilisée. Si aucun mappage n’est ouvert dans le panneau Mappage , le mappage défini dans les profils de dossier est utilisé pour résoudre les références clés.

Les références de clés peuvent être stockées dans un fichier de plan DITA ou dans un fichier DITA distinct. Dans AEM Guides, vous pouvez spécifier des références clés au niveau du projet ou de la session. Si une carte racine est déjà définie pour la session utilisateur, elle est utilisée pour résoudre les clés. Dans le cas contraire, le mappage racine par défaut pour ce dossier est utilisé. Si aucune carte racine par défaut n’est configurée, les références clés manquantes sont mises en surbrillance pour l’utilisateur.

Il existe plusieurs façons de résoudre les références clés d&#39;une rubrique DITA en définissant le plan DITA à utiliser aux emplacements suivants :

**Propriétés du projet** - Vous pouvez définir une carte racine pour résoudre les références clés lors de la création d’un projet dans la section Propriétés du projet .

Cette carte racine s’appliquera à toutes les ressources \(dossiers et sous-dossiers\) associées à ce projet. Pour le contenu référencé dans plusieurs projets, une liste alphabétique de projets est conservée et la carte racine par défaut associée au premier projet est utilisée. Vous pouvez également choisir le plan DITA à utiliser dans la liste pour résoudre les références clés.

**Aperçu de la rubrique** - En mode Aperçu de la rubrique, cliquez sur l&#39;icône Résolution de clé de la barre d&#39;outils et sélectionnez le fichier DITA à utiliser pour les références de clé.

**Vue d&#39;édition de rubrique** - Cliquez sur l&#39;icône Résolution de clé lors de la modification d&#39;une rubrique DITA et sélectionnez le fichier DITA à utiliser pour résoudre les références de clé.

**Rubrique parente :**[ Utilisation de l’éditeur de cartes](map-editor.md)
