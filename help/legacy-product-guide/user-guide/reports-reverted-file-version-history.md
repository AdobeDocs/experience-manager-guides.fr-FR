---
title: Rapport Historique des versions des fichiers restaurés
description: Affichez les rapports Historique des versions de fichiers restaurés dans AEM Guides. Découvrez comment accéder aux journaux de version rétablie à partir de l’interface utilisateur d’Assets, de l’aperçu de la rubrique et de la sélection des outils d’AEM.
feature: Report Generation
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Rapport Historique des versions des fichiers restaurés {#id205BBC00PRK}

Lorsque vous travaillez sur plusieurs versions simultanées avec plusieurs auteurs, votre contenu est lié à plusieurs versions. Il peut y avoir des informations communes sur plusieurs versions, que différents auteurs peuvent utiliser dans leur projet. Pour gérer ces affectations de travail, les auteurs peuvent obtenir plusieurs versions de fichiers. Ces versions peuvent simplement être une version plus récente d’un fichier ou un retour à une version antérieure. Il est complexe d’identifier le moment où un fichier a été restauré et pourquoi.

AEM Guides vous permet de générer un rapport d’historique des versions pour un fichier individuel ou tous les fichiers d’un dossier. Cet historique des versions vous donne une vue consolidée de toutes les versions d’un fichier qui ont été restaurées et qui a créé ces versions, ainsi que la raison de leur création.

Vous pouvez accéder à ce rapport à partir des emplacements suivants :

- **Interface utilisateur d’Assets** : en sélectionnant un fichier et en ouvrant l’ **historique de version** dans le rail de gauche. La vue **Historique de version** contient le lien **Rétablir les journaux de version** au bas du panneau. Lorsque vous cliquez sur ce lien, l’historique des versions rétablies du fichier sélectionné s’affiche.

  ![](images/revert-log-from-assets-ui.png){width="300" align="left"}

- **Aperçu de la rubrique** : lorsque vous prévisualisez une rubrique, vous pouvez également afficher le panneau **Historique de version** à partir du rail de gauche. Vous obtiendrez un panneau similaire à l’interface utilisateur d’Assets à partir duquel vous pouvez cliquer sur le lien **Rétablir les journaux de version** pour accéder à l’historique de version rétabli du document actif.

- **Section Outils d’AEM** : vous pouvez également accéder à ce rapport à partir de la section Outils d’AEM. La procédure suivante explique comment accéder à l’historique des versions restaurées à partir de la section Outils AEM.


Effectuez les étapes suivantes pour accéder au rapport Rétablir l’historique :

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et sélectionnez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils.

1. Cliquez sur la mosaïque **Historique de rétablissement de version** .

   Une page Rétablir l’historique de version vierge s’affiche, dans laquelle vous devez rechercher et sélectionner un fichier ou un dossier pour générer le rapport.

1. Cliquez sur **Afficher les journaux** pour générer le rapport pour le fichier ou le dossier sélectionné.

   ![](images/revert-version-history-report.png){width="800" align="left"}

   Le rapport contient les détails suivants :

   - **Nom de fichier** : titre de la rubrique. Cliquez sur le lien de titre de la rubrique pour ouvrir l’aperçu de la rubrique.

   - **Horodatage** : date et heure auxquelles la rubrique a été rétablie sur une version antérieure.

   - **User** : nom de l’utilisateur qui a restauré une version antérieure.

   - **Rétablir à partir de** : numéro de version d’origine du fichier à partir duquel il a été restauré.

   - **Revenir à** : version vers laquelle le fichier a été restauré.

   - **Commentaire** : tout commentaire fourni par l’utilisateur qui a restauré le fichier.


**Rubrique parente :**[ Rapports](reports-intro.md)
