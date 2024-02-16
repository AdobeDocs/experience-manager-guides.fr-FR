---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans la version 4.2.1 des guides Adobe Experience Manager
description: Découvrez les correctifs et comment mettre à niveau vers les versions 4.2.1 des Guides Adobe Experience Manager.
exl-id: a75ec83f-564b-4243-b5c5-341049521adb
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 1%

---

# Version 4.2.1 des guides Adobe Experience Manager (mai 2023)

Cette note de mise à jour traite des instructions de mise à niveau, de la matrice de compatibilité et des problèmes résolus dans la version 4.2.1 des Guides Adobe Experience Manager (appelée ultérieurement *Guides d’AEM*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version 4.2.1 des guides Adobe Experience Manager](whats-new-4-2-1-release.md).

## Mise à niveau vers la version 4.2.1 des Guides AEM


Vous pouvez facilement mettre à niveau votre version actuelle des AEM Guides vers la version 4.2.1. Avant de procéder à la mise à niveau vers la version 4.2.1 des AEM Guides, vous devez tenir compte des points suivants : Vous pouvez mettre à niveau votre version actuelle d’Guides vers la version 4.2.1.
* Si vous utilisez la version 4.1, 4.1.x ou 4.2, vous pouvez directement effectuer la mise à niveau vers la version 4.2.1.
* Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant de passer à la version 4.2.1.
* Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
* Si vous utilisez une version antérieure à 3.8.5, reportez-vous à la section Guides d’AEM de mise à niveau du guide d’installation spécifique au produit.

>[!NOTE]
>
>Vous devez installer AEM Service Pack avant de mettre à niveau AEM version de Guides.

Pour plus d’informations, voir [Instructions de mise à niveau](../install-guide/upgrade-xml-documentation.md).

## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par AEM Guides 4.2. Version 1.

### Adobe Experience Manager

**Non UUID**
Version 6.5 Service Pack 15, 14, 13 ou 12

**UUID**
Version 6.5 Service Pack 15, 14, 13 ou 12

Pour plus d’informations, voir *Exigences techniques* dans le guide d’installation et de configuration de Adobe Experience Manager Guides.

### FrameMaker et FrameMaker Publishing Server

| Version | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.2.1 (non UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.3 ou version ultérieure |
| 4.2.1 (UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.4 ou version ultérieure |
| | | | |

*Les conditions de base et créées dans AEM sont prises en charge dans les versions FMPS à partir de 2020.2.

### Connecteur Oxygen

| Version | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.2.1 (non UUID) | 2.2-normal-3 | 2.2-normal-3 | 1,6 | 1,6 |
| 4.2.1 (UUID) | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |   |

## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :

### Création

* Navtitle est supprimé du contenu lors du passage de la vue de mise en page à la vue de création ou source. (12174)
* Le bouton Fermer de l’éditeur web n’entraîne pas l’AEM de la page de navigation. (11948)
* Parfois, une erreur d’application se produit lorsque vous cliquez sur un mappage DITA. (11842)
* Le problème survient lors du déplacement (par glisser-déposer) à la place d’un élément de liste existant sur lequel le suivi des modifications est activé. (11570)
* Le problème se produit lors du déplacement (par glisser-déposer) en tant que nouvel élément de liste avec le suivi des modifications activé. (11569)
* Les éléments de la liste de retrait ou de retrait ne fonctionnent pas comme prévu lorsque le suivi des modifications est activé. (11568)
* L’ajout de contenu sur une ligne avec le suivi des modifications activé, puis la désactivation du suivi des modifications ne la désactive pas. (11567)
* Difficulté à faire glisser et déposer un élément de liste, le texte est déplacé à la place de l’élément de liste. (11566)
* Lors de la création dans l’élément affiché en vert (Suivi des modifications), le nouveau contenu s’affiche en tant que suivi des modifications, même si le suivi des modifications est désactivé. (7021)
* Le navigateur (éditeur web) se bloque lors du chargement de contenu avec un schéma personnalisé. (11211)
* PDF natif | Lors de la création d’un paramètre prédéfini de sortie avec l’option &quot;Ajouter au profil de dossier&quot;, la génération du PDF échoue avec une exception de pointeur de valeur NULL. (10950)
* PDF natif | La balise d’image ajoute un attribut display-inline à toutes les images. 10653)
* L’insertion pour les fichiers multimédia audio et vidéo échoue au format YouTube sous le **Insérer du contenu multimédia** Icône (11320)
* Une erreur de validation se produit lorsqu’une map est créée à l’aide du modèle qui comporte un élément de titre spécialisé. (11212)
* Éditeur web | Un espace insécable est ajouté dans l’éditeur XML lors de la modification d’une rubrique. (11786)

### Gestion

* L’onglet Rapports de l’interface utilisateur de l’éditeur web n’affiche pas la liste des rubriques des anciens mappages DITA créés avant la mise à niveau 4.2. (11708)

* La fonctionnalité de bouton Télécharger les fichiers de l’interface utilisateur d’Assets est coupée dans la version 4.2. (11633)


### Publication

* PDF natif | La publication de contenu comportant une classe de sortie avec crochets () entraîne un gel de publication. (11936)
* Sortie JSON | Mappage des métadonnées dont la valeur de propriété est `"value in spaces and double quotes"` génère une erreur de publication. (11933)
* Le problème se produit dans AEM recherche de site (ne fonctionne pas au-delà des noeuds de 2 à 3 niveaux). (11352)
* Éditeur web | Le chemin de sortie et le modèle ne peuvent pas être sélectionnés dans le paramètre prédéfini AEM. (11530)
* Lors de la mise à niveau de la version 4.1.x vers la version 4.2, le moteur de PDF natif ne fonctionne pas et renvoie NullPointerException même pour le système d’exploitation pris en charge.(11526)
* Le processus du PDF de téléchargement ne fonctionne pas correctement dans l’éditeur web. (11496)
* PDF natif | Les commentaires en version préliminaire sont masqués par défaut dans la sortie générée. (10560)
* PDF natif | navtitle n’est pas honoré pour topichead. 10509)
* PDF natif | Ajouter `xref` à une image n’effectue pas le rendu de l’image sur le PDF généré. (11346)
* PDF natif | la note de bas de page présente dans l’en-tête du tableau pour afficher le texte en gras aligné au centre dans le pied de page correspondant dans la sortie du PDF. (10610)

### Traduction

* Avec la mise à niveau 4.2, tout le contenu de traduction affiche Désynchronisé ou Copie manquante. (11834)

### Révision

* La révision terminée ne s’ouvre pas en mode lecture seule. (11387)
