---
title: Notes de mise à jour | Adobe Experience Manager Guides as a Cloud Service, version d’octobre 2022
description: Version d’octobre d’Adobe Experience Manager Guides as a Cloud Service
exl-id: 38638080-625c-49c3-9e54-56cc23831546
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 1%

---

# Version d’octobre d’Adobe Experience Manager Guides as a Cloud Service

## Mise à niveau vers la version d’octobre

Mettez à niveau votre configuration Adobe Experience Manager Guides as a Cloud Service actuelle (appelée plus tard *AEM Guides as a Cloud Service*) en procédant comme suit :
1. Extrayez le code Git des Cloud Service et passez à la branche configurée dans le pipeline Cloud Service correspondant à l’environnement que vous souhaitez mettre à niveau.
1. Mettez à jour la propriété `<dox.version>` dans le fichier `/dox/dox.installer/pom.xml` de votre code Git Cloud Service vers 2022.10.183.
1. Validez les modifications et exécutez le pipeline Cloud Service pour effectuer la mise à niveau vers la version d’octobre d’AEM Guides as a Cloud Service.

## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par la version as a Cloud Service d’AEM Guides d’octobre 2022.

### FrameMaker et FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Non compatible | Mise à jour 4 et ultérieure 2020 |
| | |

*Les conditions de base et créées dans AEM sont prises en charge dans les versions FMPS à partir de 2020.2.

### Connecteur Oxygen

| Version AEM Guides as a Cloud | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2022.10.0 | 2,7.13 | 2,7.13 | 2,3 | 2,3 |
|  |  |  |  |


## Nouvelles fonctionnalités et améliorations

AEM Guides as a Cloud Service contient des améliorations et de nouvelles fonctionnalités dans la version d’octobre :


### Panneau Génération rapide

Désormais, AEM Guides fournit le panneau **Quick Generate** qui vous permet de générer et d’afficher rapidement la sortie des paramètres prédéfinis créés pour votre carte DITA.

![Icône de génération rapide](assets/quick-generate-icon.png)

Dans le panneau **Quick Generate** , vous pouvez voir la liste de tous les paramètres prédéfinis de sortie créés pour votre mappage DITA.

![Panneau de génération rapide](assets/quick-generate-panel.png)

Sélectionnez un ou plusieurs paramètres prédéfinis et générez rapidement la sortie. Vous pouvez également afficher rapidement la sortie générée pour les paramètres prédéfinis. Un message de réussite s’affiche lors de la génération de la sortie. Un message d’erreur s’affiche si la génération de la sortie échoue. Vous pouvez également afficher le journal des erreurs pour afficher les détails de l’erreur qui s’est produite dans le processus de génération.


## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :

* PDF natif | Une erreur se produit lors de la suppression des rubriques de ressources uniques de la sortie du PDF. (10554)
* PDF natif | Les Keyrefs vides apparaissent dans la sortie du PDF. 10553)
* PDF natif | `navtitle` pour `topichead` n&#39;est pas honoré. 10509)
* PDF natif | Prise en charge nécessaire pour les versions du JDK amd64. (10465)
* PDF natif | Impossible de masquer les rubriques de première ligne de la table des matières. 10355
* PDF natif | Le redémarrage du numéro de page dans la mise en page du chapitre commence aléatoirement la numérotation à partir de la fin du chapitre précédent. 10154
* Explorateur Chrome | L’écran devient vide lorsque vous faites glisser un élément de l’interface utilisateur. Par exemple, lorsque vous faites glisser une condition à partir du panneau Conditions. 10524)
* Les propriétés de noeud sont supprimées après l’opération de copier-coller d’une ressource. (10053)
* En cliquant sur **Fermer**, les utilisateurs étaient redirigés vers des ressources : l’expérience a été corrigée afin d’amener les utilisateurs vers la page d’accueil d’AEM. (9654)
