---
title: Rapport Historique des versions des fichiers restaurés
description: Affichez les rapports d’historique des versions de fichiers restaurés dans AEM Guides. Découvrez comment accéder aux journaux de version rétablie à partir de l’interface utilisateur d’Assets, de l’aperçu de la rubrique et de la sélection des outils d’AEM.
exl-id: 74bef625-acd6-49a6-b983-881a782f68d6
feature: Report Generation
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Rapport Historique des versions des fichiers restaurés {#id205BBC00PRK}

Lorsque vous travaillez sur plusieurs versions simultanées avec plusieurs auteurs, votre contenu est lié à plusieurs versions. Il peut y avoir des informations communes sur plusieurs versions, que différents auteurs peuvent utiliser dans leur projet. Pour gérer ces affectations de travail, les auteurs peuvent obtenir plusieurs versions de fichiers. Ces versions peuvent simplement être une version plus récente d’un fichier ou un retour à une version antérieure. Il est complexe d’identifier le moment où un fichier a été restauré et pourquoi.

AEM Guides vous permet de générer un rapport d’historique des versions pour un fichier spécifique ou tous les fichiers d’un dossier. Cet historique des versions vous donne une vue consolidée de toutes les versions d’un fichier qui ont été restaurées et qui a créé ces versions, ainsi que la raison de leur création.

Vous pouvez accéder à ce rapport à partir des emplacements suivants :

- **Interface utilisateur des ressources**: en sélectionnant un fichier et en ouvrant le **Historique des versions** dans le rail de gauche. La variable **Historique des versions** La vue contient la variable **Rétablir les journaux de version** lien au bas du panneau. Lorsque vous cliquez sur ce lien, l’historique des versions rétablies du fichier sélectionné s’affiche.

  ![](images/revert-log-from-assets-ui.png){width="300" align="left"}

- **Aperçu de la rubrique**: lorsque vous prévisualisez une rubrique, vous pouvez également afficher le **Historique des versions** du rail de gauche. Vous obtenez un panneau similaire à l’interface utilisateur d’Assets à partir duquel vous pouvez cliquer sur le bouton **Rétablir les journaux de version** pour accéder à l’historique de version rétabli du document actif.

- **AEM section Outils**: vous pouvez également accéder à ce rapport à partir de la section Outils d’AEM. La procédure suivante explique comment accéder à l’historique des versions de restauration à partir de la section Outils d’AEM.


Effectuez les étapes suivantes pour accéder au rapport Rétablir l’historique :

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et choisissez **Outils**.

1. Sélectionner **Guides** dans la liste des outils.

1. Cliquez sur le bouton **Historique des restaurations de version** mosaïque.

   Une page Rétablir l’historique de version vierge s’affiche, dans laquelle vous devez rechercher et sélectionner un fichier ou un dossier pour générer le rapport.

1. Cliquez sur **Afficher les journaux** pour générer le rapport pour le fichier ou le dossier sélectionné.

   ![](images/revert-version-history-report.png){width="800" align="left"}

   Le rapport contient les détails suivants :

   - **Nom du fichier**: titre de la rubrique. Cliquez sur le lien de titre de la rubrique pour ouvrir l’aperçu de la rubrique.

   - **Horodatage**: date et heure auxquelles la rubrique a été rétablie sur une version antérieure.

   - **Utilisateur**: nom de l’utilisateur qui a restauré une version antérieure.

   - **Revenir de**: numéro de version d’origine du fichier à partir duquel il a été restauré.

   - **Revenir à**: version vers laquelle le fichier a été restauré.

   - **Commentaire**: tout commentaire donné par l’utilisateur qui a restauré le fichier.


**Rubrique parente :**[ Rapports](reports-intro.md)
