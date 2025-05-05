---
title: Créer des rubriques
description: Découvrez comment créer des types de rubriques DITA à l'aide de modèles personnalisés dans l'éditeur web d'AEM Guides.
feature: Authoring
role: User
hide: true
exl-id: 70ab9226-82d4-4e6a-aa0b-0e298f266c2a
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 0%

---

# Créer des rubriques {#id2056AL00O5Z}

AEM Guides vous permet de créer des rubriques DITA de type rubrique, tâche, concept, référence, glossaire, DITAVAL, etc. Outre la création de rubriques basées sur des modèles prêts à l’emploi, vous pouvez également définir vos modèles personnalisés. Ces modèles doivent être ajoutés au profil du dossier pour s’afficher dans le plan directeur de sélection des modèles et dans l’éditeur web.

Notez que la configuration globale et de profil de dossier n’est disponible que pour les utilisateurs administratifs au niveau du dossier. Pour plus d’informations sur la configuration des profils globaux et au niveau du dossier, voir *Configuration des modèles de création* dans Installation et configuration d’Adobe Experience Manager Guides pour votre configuration.

Pour créer une rubrique, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez à l’emplacement où vous souhaitez créer la rubrique.

1. Pour créer une rubrique, cliquez sur **Créer** \> **Rubrique DITA**.

1. Dans la page Plan directeur, sélectionnez le type de document DITA à créer et cliquez sur **Suivant**.

   ![](images/create_dita_topic.png){width="800" align="left"}

   Par défaut, AEM Guides fournit les modèles de rubriques DITA les plus couramment utilisés. Vous pouvez configurer d’autres modèles de rubrique en fonction des exigences de votre organisation. Voir *Configurer des modèles de création* dans Installer et configurer Adobe Experience Manager Guides pour votre configuration.

   >[!NOTE]
   >
   > Dans la vue Liste de l&#39;interface utilisateur d&#39;Assets, le type de rubrique DITA s&#39;affiche dans la colonne Type sous la forme Rubrique, Tâche, Concept, Référence, Glossentry ou DITAVAL. Le mappage DITA s&#39;affiche sous la forme Map.

1. Sur la page Propriétés , spécifiez le document **Titre**.

1. \(Facultatif\) Spécifiez le fichier **Nom**.

   Si votre administrateur a configuré le nom de fichier automatique en fonction du paramètre UUID, vous ne verrez pas l’option permettant de spécifier le nom du fichier. Un nom de fichier basé sur l&#39;UUID est automatiquement attribué au fichier.

   Si l’option de dénomination de fichier est disponible, le nom est également automatiquement suggéré en fonction du **Titre** de votre document. Si vous souhaitez spécifier manuellement le nom du document, assurez-vous que le **Nom** ne contient pas d&#39;espaces, d&#39;apostrophe ou de crochets et se termine par .xml ou .dita. Par défaut, AEM Guides remplace tous les caractères spéciaux par des tirets. Voir la section Noms de fichier dans le guide des bonnes pratiques pour connaître les bonnes pratiques relatives à l&#39;attribution de noms aux fichiers DITA.

1. Cliquez sur **Créer**. Le message Rubrique créée s’affiche.

   Vous pouvez choisir d’ouvrir la rubrique pour la modifier dans l’éditeur web ou d’enregistrer le fichier de rubrique dans le référentiel AEM.

   Chaque nouvelle rubrique créée à partir de l&#39;interface utilisateur d&#39;Assets **Créer** \> **Rubrique DITA** ou de l&#39;éditeur Web se voit attribuer un ID de rubrique unique. La valeur de cet identifiant est le nom du fichier lui-même. En outre, un nouveau document est enregistré comme la dernière copie de travail de la rubrique dans la gestion des ressources numériques. Tant que vous n’avez pas enregistré une révision d’une rubrique nouvellement créée, vous ne verrez aucun numéro de version dans l’historique des versions. Si vous ouvrez la rubrique pour la modifier, les informations de version s’affichent dans le coin supérieur droit de l’onglet du fichier de rubrique :

   ![](images/topic-version-none_cs.png){width="550" align="left"}

   Les informations de version d’une rubrique nouvellement créée s’affichent sous la forme *aucune*. Lorsque vous enregistrez une nouvelle version, un numéro de version 1.0 lui est attribué. Pour plus d’informations sur l’enregistrement d’une nouvelle version, voir [Enregistrer comme nouvelle version](web-editor-features.md#save-as-new-version-id209ME400GXA).


>[!NOTE]
>
> Si votre administrateur a configuré votre éditeur web pour extraire les fichiers avant de les modifier, vous ne pourrez pas modifier un fichier tant que vous ne l&#39;aurez pas extrait. De même, s’il est configuré, vous devrez archiver tout fichier extrait avant de le fermer.

>[!IMPORTANT]
>
> Une fois que vous avez créé votre rubrique DITA, continuez à enregistrer les modifications apportées à votre copie de travail et créez une nouvelle version une fois que vous avez terminé les mises à jour de votre rubrique.

**Rubrique parente :**&#x200B;[ Créer et prévisualiser des rubriques](create-preview-topics.md)
