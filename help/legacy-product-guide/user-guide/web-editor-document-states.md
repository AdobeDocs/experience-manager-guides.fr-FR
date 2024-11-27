---
title: État du document
description: Découvrez les types d’états de document dans AEM Guides. Découvrez comment modifier ou afficher l’état du document et utiliser l’état du document dans DDLC.
feature: Authoring, Features of Web Editor, Document State
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 0%

---

# État du document {#id1821HC00URO}

Pour gérer l’état de préparation des documents, AEM Guides fournit une propriété document state pour indiquer l’état actuel du document. Les états du document vous aident à déterminer rapidement si un document est nouveau, en révision ou s’il est terminé.

## Types d’états de document

Un document peut avoir l’un des états de document définis dans le profil Document State. Par exemple, un document peut avoir l’un des états de document suivants :

- Version préliminaire : indique que le document est créé et enregistré avec de nouvelles modifications.
- En révision : indique qu’un processus de révision a été lancé pour le document.
- Révision : indique que le document a été révisé par les utilisateurs prévus.

Ces états sont définis manuellement ou automatiquement, conformément aux paramètres de profil Document States . Par exemple, si le profil Etat du document est configuré avec l’état de départ comme brouillon et que l’état In-Review est défini pour les documents en cours de révision. Ensuite, lorsque vous créez un document, l’état du document est défini sur *Brouillon*. Si vous lancez une tâche de révision, l’état du document est alors modifié en In-Review.

Vous pouvez également modifier manuellement l’état du document pour un ou plusieurs documents. Cependant, si vous choisissez de modifier l’état du document pour plusieurs documents, l’état autorisé est déterminé par les états communs autorisés pour les documents sélectionnés. Supposons, par exemple, que vous ayez défini les états du document comme Brouillon, En révision, Révisé et Prêt pour Publish, dans le même ordre. Sur le document one.dita, l’état est défini sur *Draft* et sur le document two.dita, l’état est défini sur Reviews. Lorsque vous sélectionnez à la fois : one.dita et two.dita, l’état du document autorisé est *Prêt pour Publish*. Comme two.dita se trouve à l’état *Reviewé*, l’état suivant possible de two.dita est uniquement *Ready to Publish*, qui s’affiche lorsque les deux documents sont sélectionnés.

>[!NOTE]
>
> Un document ne peut exister que dans un seul état à la fois.

## Modifier l’état du document

Pour modifier l’état d’un document, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, sélectionnez un ou plusieurs documents pour lesquels vous souhaitez modifier l’état du document.
1. Dans la barre d’outils principale, cliquez sur **Propriétés**.
1. Sélectionnez le nouvel état dans la liste déroulante **Document State**. Vous ne pouvez sélectionner que les états du document autorisés dans la section Transition de l’état du profil Document State.

   >[!NOTE]
   >
   >Les administrateurs peuvent afficher tous les états du document et le remplacer par n’importe quel état possible.

1. Cliquez sur **Enregistrer et fermer**.

## Affichage de l’état du document

Le mode Carte de l’interface utilisateur d’Assets affiche l’état actuel ainsi que la date et la taille de création de la rubrique DITA ou du mappage DITA correspondant.

![](images/document_state.png){width="800" align="left"}

## Utilisation des états de document dans DDLC

Les états de document jouent un rôle important dans la gestion du cycle de vie des documents dans DDLC. Si votre entreprise suit strictement le DDLC, disposer d’un mécanisme de contrôle de la modification des documents en fonction de leur état devient une fonctionnalité essentielle. Par exemple, vous pouvez autoriser la modification de documents lorsqu’ils se trouvent à l’état *Brouillon* ou *En révision*. Cependant, une fois qu’un document est révisé et prêt à être publié, il doit y avoir un moyen d’empêcher toute modification supplémentaire des documents.

AEM Guides fournit un processus d’approbation de document qui vous aide à contrôler le cycle de vie de votre processus de développement de documents. Une fois qu’un document est prêt à être publié ou qu’il a atteint l’avant-dernier état, vous pouvez le marquer comme approuvé. Une fois qu’un document est approuvé, AEM Guides crée une nouvelle version du document et le rend en lecture seule. Vous pouvez ensuite déplacer le document à des fins de publication ou créer une ligne de base pour un traitement ultérieur.

Pour lancer une nouvelle version à partir des documents marqués comme approuvés, un auteur doit lancer une nouvelle version. Le démarrage d’une nouvelle version modifie à nouveau l’état du document en *Brouillon* . En définissant l’état du document sur *Brouillon*, le document devient à nouveau modifiable et vous pouvez continuer à travailler sur la prochaine version.

Pour utiliser la fonction d’approbation de document, procédez comme suit :

>[!NOTE]
>
> La fonction de workflow d’approbation doit être activée par votre administrateur. Pour plus d’informations, voir la section *Activer le processus d’approbation* dans l’as a Cloud Service Installer et configurer Adobe Experience Manager Guides.

1. Dans l’éditeur Web, ouvrez le document que vous souhaitez marquer pour approbation.

1. Cliquez sur l&#39;icône **Marquer comme approuvé**![](images/mark_approve_icon.svg) .

1. Si votre document doit être marqué comme approuvé, la boîte de dialogue suivante s’affiche :

   ![](images/mark-approved-correct-state.png){width="300" align="left"}

   Si le document ne peut pas être marqué comme approuvé, le message suivant s’affiche :

   ![](images/mark-approved-incorrect-state.png){width="300" align="left"}

1. Si votre document est prêt à être marqué comme approuvé, sélectionnez un libellé dans la liste déroulante et cliquez sur **Approuver**.

   >[!NOTE]
   >
   > Si votre administrateur n’a pas configuré de liste prédéfinie d’étiquettes, un champ de texte en forme libre s’affiche pour vous permettre de saisir un libellé.

1. Une fois que le document est marqué comme approuvé, un **Aperçu** du document s’affiche en mode lecture seule.

   ![](images/approved-doc-read-only.png){width="650" align="left"}

   >[!NOTE]
   >
   > En mode Aperçu , toutes les options de modification sont supprimées de la barre d’outils. En outre, la vue Auteur et Source du document a également été supprimée de la barre de navigation supérieure.


Une fois qu’un document est marqué comme approuvé, il ne peut plus être modifié. Si vous souhaitez utiliser le document pour la prochaine version, vous devez le ramener à l’état *Draft*. Pour rétablir l’état du document d’un document approuvé en mode *Brouillon* , procédez comme suit :

1. Dans un document approuvé, cliquez sur l’icône **Démarrer une nouvelle version** ![](images/approved-restart-draft-mode-icon.svg) .

   Le message Démarrer une nouvelle version s’affiche.

1. Cliquez sur **Confirmer**.

   L’état du document est alors modifié et le document s’ouvre dans l’éditeur Web en mode d’édition.


**Rubrique parente :**[ Utilisation de l’éditeur web](web-editor.md)
