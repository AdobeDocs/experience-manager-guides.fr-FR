---
title: Notes de mise à jour | Adobe Experience Manager Guides as a Cloud Service, version d’avril 2022
description: Version d’avril des guides Adobe Experience Manager as a Cloud Service
exl-id: c735ba24-a803-454b-8723-57dacf90061b
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 0%

---

# Version d’avril des guides Adobe Experience Manager as a Cloud Service

## Mise à niveau vers la version d’avril

Mettre à niveau votre [!DNL Adobe Experience Manager Guides] as a Cloud Service (plus tard appelé *[!DNL AEM Guides]as a Cloud Service*) en procédant comme suit :
1. Extrayez le code Git des Cloud Service et passez à la branche configurée dans le pipeline Cloud Service correspondant à l’environnement que vous souhaitez mettre à niveau.
1. Mettre à jour `<dox.version>` dans `/dox/dox.installer/pom.xml` du code Git Cloud Service vers la version 2022.4.133.
1. Validez les modifications et exécutez le pipeline Cloud Service pour effectuer la mise à niveau vers la version d’avril de [!DNL AEM Guides] as a Cloud Service.

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité des applications logicielles prises en charge par [!DNL AEM Guides] Version as a Cloud Service d’avril 2022.

### FrameMaker et FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Non compatible | Mise à jour 4 et ultérieure 2020 |
| | |


### Connecteur Oxygen

| Version d’AEM Guides Cloud | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen |
| --- | --- | --- |
| 2022.4.0 | 2.5.6 | 2.5.6 |
|  |  |  |

*Les conditions de base et créées dans AEM sont prises en charge dans les versions FMPS à partir de 2020.2.

## Nouvelles fonctionnalités et améliorations

De nombreuses améliorations et nouvelles fonctionnalités ont été ajoutées à l’éditeur web :

### Amélioration de la résolution des clés

Une référence de clé de contenu DITA insère une partie du contenu d’une rubrique dans une autre. Elle utilise une clé pour localiser le contenu. Les références clés associées à une rubrique DITA doivent être résolues. La carte racine sélectionnée a la priorité la plus élevée pour résoudre les références clés.

![boîte de dialogue des préférences utilisateur](assets/user-preferences.png)

Désormais, les références clés sont résolues sur la base de la carte racine définie dans l’ordre de priorité suivant :

1. Préférences utilisateur
1. Panneau Vue Carte
1. Profil de dossier

Pour plus d’informations, voir *Résoudre les références de clés* dans le guide de l’utilisateur.

### Ajouter un panneau personnalisé dans le panneau de gauche

Vous pouvez maintenant ajouter un panneau personnalisé dans le panneau de gauche de l’éditeur Web. Vous pouvez utiliser un panneau personnalisé à diverses fins, par exemple pour fournir de l’aide ou effectuer les tests pour un projet. Si un panneau personnalisé a été configuré, il apparaît également dans la liste des panneaux de la variable **Paramètres de l’éditeur**. Vous pouvez activer ou désactiver le commutateur pour afficher ou masquer le panneau personnalisé.

### Possibilité de modifier l’état du document des rubriques dans un mappage DITA

Vous pouvez désormais facilement modifier l’état du document des rubriques sélectionnées dans un mappage DITA. Vous pouvez également ouvrir et modifier les propriétés des rubriques sélectionnées dans un mappage DITA à partir du **Plus d’options** au bas du panneau Vue Carte.

![propriétés de rubrique sélectionnées](assets/map-view-properties.png)

### Informations de version affichées en mode Aperçu

L’éditeur web vous aide à gérer vos versions. Vous pouvez désormais également voir la version de la rubrique active ou du mappage DITA dans le coin supérieur droit de l’onglet Fichier de la rubrique en mode Aperçu d’une rubrique.

![version d’aperçu](assets/preview-version.png)

## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :

* Les nouveaux libellés ne sont pas répercutés automatiquement dans la liste déroulante Ajouter/Supprimer un libellé . Une actualisation de ligne de base est alors requise. (9249)
* Impossible de modifier le titre de la ligne de base si une ligne de base est créée par critère de libellé. (9171)
* La tâche de publication utilisant une ligne de base est bloquée à l’état &quot;en attente&quot; si l’état de la ligne de base passe à &quot;échec&quot;. (9194)
* La suppression des libellés sur les références directes supprime également les libellés des références indirectes. (9257)
* La recherche en cours de frappe entraîne des requêtes de recherche indésirables dans la vue Repository. (9307)
* Des problèmes se produisent lorsqu’un mot-clé est utilisé dans le titre de l’onglet . (9318)
* La ligne de base échoue lors de l’ajout d’un libellé avec des espaces. (9362)
* AEM sortie du site n’affiche pas correctement l’élément glossusages . (8936)
* L’erreur de la console se produit lors de l’ouverture de **Sortie** dans l’éditeur Web. (8715)
* Le message d’erreur affiché lors de la publication d’un type d’enregistrement manuel via Salesforce n’est pas intuitif. (8952)
* Le paramètre Valider avec des attributs de condition n’est pas ouvert immédiatement. À la place, l’utilisateur doit rouvrir le fichier pour afficher les validations. (9300)
* Les métadonnées ne peuvent pas être supprimées une fois qu’un mappage DITA est publié avec des métadonnées.  (9178)
* Le panneau de traduction est visible même lors de l’ouverture du mappage DITA dans l’éditeur de cartes. (9053)
* La DTD personnalisée définie par l’utilisateur n’a pas la priorité sur la DTD DITA standard incorporée dans DITA-OT. (9104)
* Dans la fonction de PDF natif, le chargement dans les modèles échoue pour les fichiers non DITA et non image. (9070)
* Le mécanisme d’autorisation exécute deux requêtes au lieu d’une, dans certains scénarios spécialisés. (9221)
* La publication de la sortie AEM site échoue lors de l’utilisation de la DTD personnalisée. (9243)
* La note de bas de page de référence utilisée ne fait pas défiler l’écran jusqu’à la section de note de bas de page dans AEM sortie du site. (9234)

## Problèmes connus

Adobe a identifié le problème connu suivant dans la variable [!DNL AEM Guides] Version as a Cloud Service d’avril.

* L’éditeur web ne signale pas d’erreur lorsque plusieurs lignes de base sont créées avec le même nom, mais qu’elles présentent des différences d’espace ou de casse. Par exemple, &quot;adobe&quot; et &quot;Adobe&quot; ou &quot;Adobe&quot;.
* Le connecteur Oxygen se bloque par intermittence lors d’une connexion ou d’une déconnexion fréquentes ou d’un changement entre différents types d’authentification.
