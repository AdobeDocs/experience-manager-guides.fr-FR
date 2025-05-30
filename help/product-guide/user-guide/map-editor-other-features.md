---
title: Autres fonctionnalités de l’éditeur de cartes
description: Découvrez quelques fonctionnalités courantes de l’éditeur de cartes. Découvrez comment résoudre les références clés dans l’éditeur de cartes.
exl-id: f0e7a402-ac12-4c63-9d7f-92567ee29a39
feature: Authoring, Map Editor
role: User
source-git-commit: 41c6e4edb470038c4934c01f1c28539f1e4d4f86
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 0%

---

# Fonctionnalités supplémentaires de l’éditeur de cartes {#id1942D0T0HUI}

Voici quelques fonctionnalités courantes de l’éditeur de cartes :

## Résoudre les principales références {#id176GD01H05Z}

Une référence de clé de contenu DITA, ou `conkeyref`, est un mécanisme permettant d&#39;insérer une partie du contenu d&#39;une rubrique dans une autre. Ce mécanisme utilise la clé pour localiser le contenu à réutiliser plutôt que le mécanisme de référencement direct du contenu. Pour plus d&#39;informations sur le référencement direct et indirect dans DITA, consultez *Adressage DITA* dans Spécification de langage OASIS DITA.

Si la rubrique DITA est associée à des références clés, celles-ci doivent être résolues avant de prévisualiser, modifier ou réviser une rubrique.

Les références clés sont résolues sur la base du mappage racine défini dans l’ordre de priorité suivant :

1. Préférences utilisateur
1. Panneau Vue Carte
1. Profil de dossier

La carte racine sélectionnée dans les Préférences utilisateur a la priorité la plus élevée pour résoudre les références clés, suivie du panneau Vue Carte et de la carte racine Profil de dossier. Ainsi, si aucune carte n’est définie dans les Préférences utilisateur, la carte ouverte dans le panneau Vue Carte est utilisée. Si aucun mappage n’est ouvert dans le panneau Mappage , le mappage défini dans les profils de dossier est utilisé pour résoudre les références clés.

Les références de clés peuvent être stockées dans un fichier de plan DITA ou dans un fichier DITA distinct. Dans Experience Manager Guides, vous pouvez spécifier des références clés au niveau du projet ou de la session. Si une carte racine est déjà définie pour la session utilisateur, elle est utilisée pour résoudre les clés. Dans le cas contraire, le mappage racine par défaut pour ce dossier est utilisé. Si aucune carte racine par défaut n’est configurée, les références clés manquantes sont mises en surbrillance pour l’utilisateur.

Il existe plusieurs façons de résoudre les références clés d&#39;une rubrique DITA en définissant le plan DITA à utiliser aux emplacements suivants :

**Propriétés du projet** - Vous pouvez définir une carte racine pour résoudre les références clés lors de la création d’un projet dans la section Propriétés du projet .

Cette carte racine s’appliquera à toutes les ressources \(dossiers et sous-dossiers\) associées à ce projet. Pour le contenu référencé dans plusieurs projets, une liste alphabétique de projets est conservée et la carte racine par défaut associée au premier projet est utilisée. Vous pouvez également choisir le plan DITA à utiliser dans la liste pour résoudre les références clés.

**Aperçu de la rubrique** - En mode Aperçu de la rubrique, sélectionnez l&#39;icône Résolution de clé dans la barre d&#39;outils et sélectionnez le fichier DITA à utiliser pour les références de clé.

**Vue d&#39;édition de rubrique** - Sélectionnez l&#39;icône Résolution de clé lors de la modification d&#39;une rubrique DITA et sélectionnez le fichier DITA à utiliser pour résoudre les références de clé.

## Ajouter des références de navigation

L&#39;élément `navref` est utilisé dans un plan DITA pour inclure des références de navigation provenant d&#39;un autre plan DITA. Cela permet aux auteurs de réutiliser la structure de navigation, telle que les menus partagés ou les liens, sans fusionner le contenu réel de la carte référencée dans la sortie.

>[!NOTE]
>
> L’élément `navref` est destiné uniquement à des fins de navigation dans la structure de carte. Il ne contribue pas à la sortie de mappage DITA générée et est exclu du traitement et de l&#39;affichage dans la vue Carte, les rapports, la ligne de base, la traduction et la prévisualisation.

Pour ajouter des références de navigation à une carte, procédez comme suit :

1. Ouvrez le fichier DITA map dans lequel vous souhaitez ajouter une référence de navigation.

   Le fichier de mappage s’ouvre dans l’éditeur de mappages.
1. Passez à la vue Auteur et placez le curseur à un emplacement valide pour une référence de navigation.
1. Sélectionnez l’option **Élément** dans la barre d’outils.
1. Dans la boîte de dialogue **Insérer un élément**, sélectionnez **navref**.

   ![](./images/select-navref-element.png)
1. La boîte de dialogue **Sélectionner le chemin** s’affiche. Sélectionnez un fichier de mappage à inclure comme référence de navigation dans votre mappage, puis choisissez **Sélectionner**.

Une référence de navigation du fichier de mappage sélectionné est ajoutée à l’emplacement spécifié. En outre, le titre de la carte référencée s’affiche en mode Création et en mode Mise en page.

![](./images/navref-added-author-view.png)

*Vue Auteur*

![](./images/navref-added-layout-view.png)

*Mode Mise en page*


**Rubrique parente :**&#x200B;[ Présentation de l’éditeur de cartes](map-editor.md)
