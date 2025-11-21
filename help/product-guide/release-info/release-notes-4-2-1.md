---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans la version 4.2.1 d’Adobe Experience Manager Guides
description: Découvrez les correctifs et comment effectuer une mise à niveau vers la version 4.2.1 d’Adobe Experience Manager Guides
exl-id: a75ec83f-564b-4243-b5c5-341049521adb
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 1%

---

# Version 4.2.1 d’Adobe Experience Manager Guides (mai 2023)

Cette note de mise à jour couvre les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans la version 4.2.1 d’Adobe Experience Manager Guides (plus tard appelée *AEM Guides*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version 4.2.1 d’Adobe Experience Manager Guides](whats-new-4-2-1-release.md).

## Mise à niveau vers la version 4.2.1 d’AEM Guides


Vous pouvez facilement mettre à niveau votre version actuelle d’AEM Guides vers la version 4.2.1. Avant de procéder à la mise à niveau vers la version 4.2.1 d’AEM Guides, vous devez tenir compte des points suivants :
Vous pouvez mettre à niveau votre version actuelle d’AEM Guides vers la version 4.2.1
* Si vous utilisez la version 4.1, 4.1.x ou 4.2, vous pouvez directement effectuer la mise à niveau vers la version 4.2.1.
* Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant d’effectuer la mise à niveau vers la version 4.2.1.
* Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
* Si vous utilisez une version antérieure à la version 3.8.5, reportez-vous à la section Mise à niveau d’AEM Guides dans le guide d’installation spécifique au produit.

>[!NOTE]
>
>Vous devez installer le pack de services AEM avant de mettre à niveau la version d’AEM Guides.

Pour plus d’informations, voir [Instructions de mise à niveau](../install-guide/upgrade-xml-documentation.md).

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par AEM Guides 4.2. version 1.

### Adobe Experience Manager

**Non-UUID**
Version 6.5 Service Pack 15, 14, 13 ou 12

**UUID**
Version 6.5 Service Pack 15, 14, 13 ou 12

Pour plus d’informations, consultez la section *Exigences techniques* du guide Installation et configuration d’Adobe Experience Manager Guides .

### FrameMaker et FrameMaker Publishing Server

| Version | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.2.1 (Non-UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.3 ou version ultérieure |
| 4.2.1 (UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.4 ou version ultérieure |
| | | | |  |

*La ligne de base et les conditions créées dans AEM sont prises en charge dans les versions FMPS à compter de 2020.2.

### Connecteur D&#39;Oxygène

| Version | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.2.1 (Non-UUID) | 2.2-standard-3 | 2.2-standard-3 | 1,6 | 1,6 |
| 4.2.1 (UUID) | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |   |  |  |

## Problèmes résolus

Les bogues corrigés dans différentes zones sont répertoriés ci-dessous :

### Création

* Navtitle est supprimé du contenu lors du passage de la vue de mise en page à la vue de création ou source. (12174)
* Le bouton Fermer de l’éditeur web ne mène pas à la page de navigation d’AEM. (11948)
* Parfois, une erreur d&#39;application se produit en cliquant sur un plan DITA. (11842)
* Le problème se produit lors du déplacement (glisser-déposer) à la place d’un élément de liste existant avec le suivi des modifications activé. (11570)
* Le problème se produit lors du déplacement (glisser-déposer) en tant que nouvel élément de liste avec le suivi des modifications activé. (11569)
* Le retrait ou le retrait négatif d’éléments de liste ne fonctionne pas comme prévu lorsque le suivi des modifications est activé. (11568)
* L’ajout de contenu sur une ligne avec le suivi des modifications activé puis la désactivation du suivi des modifications ne le désactive pas réellement. (11567)
* Difficulté à faire glisser et à déposer un élément de liste, le texte est déplacé à la place de l’élément de liste. (11566)
* Lors de la création dans l’élément affiché en vert (Suivi des modifications), le nouveau contenu s’affiche en tant que suivi des modifications même si ce dernier est désactivé. (7021)
* Le navigateur (éditeur web) se fige lors du chargement du contenu avec le schéma personnalisé. (11211)
* PDF natif | Lors de la création d’un paramètre prédéfini de sortie avec l’option « Ajouter au profil de dossier », la génération PDF échoue avec une exception de pointeur Null. (10950)
* PDF natif | La balise d’image ajoute un attribut display-inline à toutes les images. (10653)
* L’insertion des fichiers multimédias audio et vidéo échoue au format YouTube sous l’icône **Insérer un fichier multimédia**. (11320)
* Une erreur de validation se produit lorsqu’une carte est créée à l’aide du modèle qui comporte un élément de titre spécialisé. (11212)
* Éditeur web | Un espace insécable est ajouté dans l’éditeur XML lors de la modification d’une rubrique. (11786)

### Gestion

* L&#39;onglet Rapports de l&#39;interface utilisateur de l&#39;éditeur Web n&#39;affiche pas la liste de rubriques des anciens plans DITA créés avant la mise à niveau vers la version 4.2. (11708)

* La fonctionnalité du bouton Charger des fichiers dans l’interface utilisateur d’Assets interrompt la version 4.2. (11633)


### Publication

* PDF natif | La publication d’un contenu avec une classe de sortie et des crochets () entraîne un gel de la publication. (11936)
* Sortie JSON | Mappez des métadonnées dont la valeur de propriété est `"value in spaces and double quotes"` entraîne une erreur de publication. (11933)
* Le problème se produit dans la recherche de site AEM (ne fonctionne pas au-delà de 2 à 3 nœuds de niveau). (11352)
* Éditeur web | Le chemin de sortie et le modèle ne peuvent pas être sélectionnés dans le paramètre prédéfini AEM. (11530)
* Lors de la mise à niveau de la version 4.1.x vers la version 4.2 , le moteur PDF natif ne fonctionne pas et renvoie la valeur NullPointerException, même pour le système d’exploitation pris en charge.(11526)
* Le processus de téléchargement de PDF ne fonctionne pas correctement dans l’éditeur web. (11496)
* PDF natif | Les commentaires de brouillon sont masqués par défaut dans la sortie générée. (10560)
* PDF natif | navtitle n’est pas honoré pour topichead. (10509)
* PDF natif | L’ajout de `xref` à une image n’effectue pas le rendu de l’image sur le PDF généré. (11346)
* PDF natif | la note de bas de page présente dans l’en-tête du tableau met le texte en gras et aligné au centre dans le pied de page correspondant dans la sortie PDF. (10610)

### Traduction

* Avec la mise à niveau vers la version 4.2, tout le contenu de traduction s’affiche Désynchronisé ou Copie manquante. (11834)

### Révision

* La révision terminée ne s’ouvre pas en mode lecture seule. (11387)
