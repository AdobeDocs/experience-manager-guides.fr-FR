---
title: Rapport Historique des versions des fichiers rétablis
description: Affichez les rapports de l’historique des versions des fichiers rétablis dans AEM Guides. Découvrez comment accéder aux journaux des versions inversées à partir de l’interface utilisateur d’Assets, de l’aperçu de la rubrique et de la sélection des outils AEM.
exl-id: 74bef625-acd6-49a6-b983-881a782f68d6
feature: Report Generation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 0%

---

# Rapport Historique des versions des fichiers rétablis {#id205BBC00PRK}

Lorsque vous travaillez sur plusieurs versions simultanées avec plusieurs auteurs, votre contenu est lié à plusieurs versions. Il peut y avoir des informations communes dans plusieurs versions, que différents auteurs peuvent utiliser dans leur projet. Pour gérer de telles affectations de travail, les auteurs et autrices peuvent se retrouver avec plusieurs versions de fichiers. Ces versions peuvent simplement être une version plus récente d’un fichier ou un retour à une version antérieure. Il est difficile d’identifier quand et pourquoi un fichier a été restauré.

Adobe Experience Manager Guides vous permet de générer un rapport d’historique de version pour un fichier individuel ou pour tous les fichiers d’un dossier. Cet historique des versions vous donne une vue consolidée de toutes les versions d’un fichier qui ont été rétablies et de ceux qui les ont créées, ainsi que la raison de leur création.

Vous pouvez accéder à ce rapport à partir des emplacements suivants :

- **Interface utilisateur d’Assets** : en sélectionnant un fichier et en ouvrant l’**Historique des versions** dans le rail de gauche. La vue **Historique des versions** contient le lien **Rétablir les journaux de version** au bas du panneau. Lorsque vous sélectionnez ce lien, l’historique des versions rétablies du fichier sélectionné s’affiche.

  ![](images/revert-log-from-assets-ui.png){width="300" align="left"}

- **Aperçu de la rubrique** : lorsque vous prévisualisez une rubrique, vous pouvez également afficher le panneau **Historique des versions** dans le rail de gauche. Vous obtiendrez un panneau similaire à l’interface utilisateur d’Assets à partir duquel vous pourrez sélectionner le lien **Rétablir les journaux de version** pour accéder à l’historique des versions rétablies du document actif.

- **Section Outils Adobe Experience Manager** : vous pouvez également accéder à ce rapport à partir de la section Outils Experience Manager. La procédure suivante explique comment accéder à l’historique des versions rétablies à partir de la section Outils Experience Manager .


Pour accéder au rapport Rétablir l’historique, procédez comme suit :

1. Sélectionnez le logo Adobe Experience Manager en haut et choisissez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils.

1. Sélectionnez la mosaïque **Historique de rétablissement de version**.

   Une page Historique des versions vierge s’affiche. Vous devez alors rechercher et sélectionner un fichier ou un dossier pour générer le rapport.

1. Sélectionnez **Afficher les journaux** pour générer le rapport pour le fichier ou le dossier sélectionné.

   ![](images/revert-version-history-report.png){align="left"}

   Le rapport contient les détails suivants :

   - **Nom de fichier** : titre de la rubrique. En sélectionnant le lien de titre de la rubrique, vous ouvrez l’aperçu de la rubrique.

   - **Horodatage** : date et heure auxquelles la rubrique a été rétablie dans une version antérieure.

   - **Utilisateur** : nom de l’utilisateur qui a rétabli une version antérieure.

   - **Restaurer à partir de** : numéro de version d’origine du fichier à partir duquel il a été restauré.

   - **Rétablir** : la version vers laquelle le fichier a été rétabli.

   - **Commentaire** : tout commentaire fourni par l’utilisateur qui a annulé le fichier.


**Rubrique parente :**[ Présentation des rapports](reports-intro.md)
