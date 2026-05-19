---
title: Rapport Historique des versions des fichiers rétablis
description: Affichez les rapports de l’historique des versions des fichiers rétablis dans AEM Guides. Découvrez comment accéder aux journaux des versions inversées à partir de l’interface utilisateur d’Assets, de l’aperçu de la rubrique et de la sélection des outils AEM.
feature: Report Generation
role: User
hide: true
exl-id: c787947a-b235-4c12-a9cc-eac5136d31db
TQID: https://experienceleague.adobe.com/lRZe-xPwSSlgWvk5-YLMZkqLRHwe-lTO8jUsgYQn1dM
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: cdab8659-8d50-4417-b6fd-762f347c13ee
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 468
ht-degree: 0%

---

# Rapport Historique des versions des fichiers rétablis {#id205BBC00PRK}

Lorsque vous travaillez sur plusieurs versions simultanées avec plusieurs auteurs, votre contenu est lié à plusieurs versions. Il peut y avoir des informations communes dans plusieurs versions, que différents auteurs peuvent utiliser dans leur projet. Pour gérer de telles affectations de travail, les auteurs et autrices peuvent se retrouver avec plusieurs versions de fichiers. Ces versions peuvent simplement être une version plus récente d’un fichier ou un retour à une version antérieure. Il est difficile d’identifier quand et pourquoi un fichier a été restauré.

AEM Guides vous permet de générer un rapport d’historique de version pour un fichier individuel ou pour tous les fichiers d’un dossier. Cet historique des versions vous donne une vue consolidée de toutes les versions d’un fichier qui ont été rétablies et de ceux qui les ont créées, ainsi que la raison de leur création.

Vous pouvez accéder à ce rapport à partir des emplacements suivants :

- **Interface utilisateur d’Assets** : en sélectionnant un fichier et en ouvrant l’**Historique des versions** dans le rail de gauche. La vue **Historique des versions** contient le lien **Rétablir les journaux de version** au bas du panneau. Lorsque vous cliquez sur ce lien, l&#39;historique des versions rétablies du fichier sélectionné s&#39;affiche.

  ![](images/revert-log-from-assets-ui.png){width="300"}

- **Aperçu de la rubrique** : lorsque vous prévisualisez une rubrique, vous pouvez également afficher le panneau **Historique des versions** dans le rail de gauche. Un panneau similaire à l’interface utilisateur d’Assets s’affiche à partir duquel vous pouvez cliquer sur le lien **Rétablir les journaux de version** pour accéder à l’historique des versions rétablies du document actif.

- **Section Outils AEM** : vous pouvez également accéder à ce rapport à partir de la section Outils AEM. La procédure suivante explique comment accéder à l’historique des versions rétablies à partir de la section Outils d’AEM.


Pour accéder au rapport Rétablir l’historique, procédez comme suit :

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils.

1. Cliquez sur la mosaïque **Historique de rétablissement de version**.

   Une page Historique des versions vierge s’affiche. Vous devez alors rechercher et sélectionner un fichier ou un dossier pour générer le rapport.

1. Cliquez sur **Afficher les journaux** pour générer le rapport pour le fichier ou le dossier sélectionné.

   ![](images/revert-version-history-report.png){width="800"}

   Le rapport contient les détails suivants :

   - **Nom de fichier** : titre de la rubrique. Cliquez sur le lien du titre de la rubrique pour ouvrir l’aperçu de la rubrique.

   - **Horodatage** : date et heure auxquelles la rubrique a été rétablie dans une version antérieure.

   - **Utilisateur** : nom de l’utilisateur qui a rétabli une version antérieure.

   - **Restaurer à partir de** : numéro de version d’origine du fichier à partir duquel il a été restauré.

   - **Rétablir** : la version vers laquelle le fichier a été rétabli.

   - **Commentaire** : tout commentaire fourni par l’utilisateur qui a annulé le fichier.



**Rubrique parente :**&#x200B;[&#x200B; Rapports](reports-intro.md)
