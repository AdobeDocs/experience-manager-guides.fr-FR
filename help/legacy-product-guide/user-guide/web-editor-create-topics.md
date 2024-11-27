---
title: Création de rubriques
description: Découvrez comment créer des types de rubriques DITA à l’aide de modèles personnalisés dans l’éditeur web d’AEM Guides.
feature: Authoring
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 0%

---

# Création de rubriques {#id2056AL00O5Z}

AEM Guides vous permet de créer des rubriques DITA de type : rubrique, tâche, concept, référence, glossaire, DITAVAL, etc. Outre la création de rubriques basées sur les modèles d’usine, vous pouvez également définir vos modèles personnalisés. Ces modèles doivent être ajoutés au profil de dossier pour s’afficher dans le plan directeur de sélection du modèle et dans l’éditeur web.

Notez que la configuration Global et Profil de dossier n’est disponible que pour les utilisateurs administratifs au niveau du dossier. Pour plus d’informations sur la configuration des profils globaux et de niveau dossier, voir *Configuration des modèles de création* dans Installation et configuration d’Adobe Experience Manager Guides pour votre configuration.

Pour créer une rubrique, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez à l’emplacement où vous souhaitez créer la rubrique.

1. Pour créer une nouvelle rubrique, cliquez sur **Créer** \> **Rubrique DITA**.

1. Sur la page Plan directeur, sélectionnez le type de document DITA que vous souhaitez créer, puis cliquez sur **Suivant**.

   ![](images/create_dita_topic.png){width="800" align="left"}

   Par défaut, AEM Guides fournit les modèles de rubriques DITA les plus couramment utilisés. Vous pouvez configurer d’autres modèles de rubrique en fonction des besoins de votre organisation. Voir *Configuration de modèles de création* dans Installation et configuration d’Adobe Experience Manager Guides pour votre configuration.

   >[!NOTE]
   >
   > En mode Liste de l’interface utilisateur d’Assets, le type de rubrique DITA s’affiche dans la colonne Type sous la forme Rubrique, Tâche, Concept, Référence, Glossentry ou DITAVAL. Le mappage DITA s’affiche sous la forme Carte.

1. Sur la page Propriétés, spécifiez le document **Titre**.

1. \(Facultatif\) Spécifiez le fichier **Name**.

   Si votre administrateur a configuré le nom de fichier automatique en fonction du paramètre UUID , vous ne verrez pas l’option permettant de spécifier le nom de fichier. Un nom de fichier basé sur l’UUID est automatiquement attribué au fichier.

   Si l’option d’affectation de nom de fichier est disponible, le nom est également automatiquement suggéré en fonction du **titre** de votre document. Si vous souhaitez spécifier manuellement le nom du document, assurez-vous que le **nom** ne contient aucun espace, apostrophe ou accolades et se termine par .xml ou.dita. Par défaut, AEM Guides remplace tous les caractères spéciaux par des tirets. Pour connaître les bonnes pratiques en matière de dénomination des fichiers DITA, reportez-vous à la section Noms de fichiers du guide des bonnes pratiques.

1. Cliquez sur **Créer**. Le message Rubrique créée s’affiche.

   Vous pouvez choisir d’ouvrir la rubrique à modifier dans l’éditeur web ou d’enregistrer le fichier de rubrique dans le référentiel AEM.

   Chaque nouvelle rubrique que vous créez à partir de l’interface utilisateur d’Assets **Créer** \> **Rubrique DITA** ou un identifiant de rubrique unique est attribué à l’éditeur Web. La valeur de cet ID est le nom de fichier lui-même. En outre, un nouveau document est enregistré comme la dernière copie de travail de la rubrique dans la gestion des ressources numériques. Tant que vous n’enregistrez pas de révision d’une nouvelle rubrique, vous ne verrez aucun numéro de version dans l’historique de versions. Si vous ouvrez la rubrique pour la modifier, les informations de version s’affichent dans le coin supérieur droit de l’onglet du fichier de rubrique :

   ![](images/topic-version-none_cs.png){width="550" align="left"}

   Les informations de version d’une nouvelle rubrique s’affichent sous la forme *none*. Lorsque vous enregistrez une nouvelle version, un numéro de version 1.0 lui est affecté. Pour plus d’informations sur l’enregistrement d’une nouvelle version, voir [Enregistrer comme nouvelle version](web-editor-features.md#save-as-new-version-id209ME400GXA).


>[!NOTE]
>
> Si votre administrateur a configuré l’éditeur web pour extraire des fichiers avant de les modifier, vous ne pourrez pas modifier un fichier tant que vous ne l’aurez pas extrait. De même, s’il est configuré, vous serez invité à archiver n’importe quel fichier extrait avant de le fermer.

>[!IMPORTANT]
>
> Une fois que vous avez créé votre rubrique DITA, continuez à enregistrer les modifications dans votre copie de travail et créez une nouvelle version une fois les mises à jour apportées à votre rubrique.

**Rubrique parente :**[ Créer et prévisualiser des rubriques](create-preview-topics.md)
