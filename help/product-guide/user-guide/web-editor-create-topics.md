---
title: Créer des rubriques
description: Découvrez comment créer des types de rubriques DITA à l'aide de modèles personnalisés dans Adobe Experience Manager Guides.
exl-id: 84e9cfdf-e188-487f-9181-68708029c101
feature: Authoring
role: User
source-git-commit: c6709ffb8e415c88931e732456e2f2a5e6b63729
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 0%

---

# Créer des rubriques {#id2056AL00O5Z}

Adobe Experience Manager Guides vous permet de créer des rubriques DITA de type : rubrique, tâche, concept, référence, glossaire, DITAVAL, Markdown, etc. Outre la création de rubriques basées sur des modèles prêts à l’emploi, vous pouvez également définir vos modèles personnalisés. Ces modèles doivent être ajoutés au profil du dossier pour s’afficher dans le plan directeur de sélection de modèles et dans l’éditeur.

>[!NOTE]
>
> La configuration globale et de profil de dossier n’est disponible que pour les utilisateurs administratifs au niveau du dossier. Pour plus d’informations sur la configuration des profils globaux et au niveau du dossier, consultez *Configuration des modèles de création* dans Installation et configuration d’Adobe Experience Manager Guides pour votre configuration.


Il existe deux manières de créer des rubriques dans Experience Manager Guides :

- [Créer des rubriques à partir de l’éditeur](#create-topics-from-the-editor)
- [Créer des rubriques à partir de l’interface utilisateur d’Assets](#create-topics-from-the-assets-ui)

## Créer des rubriques à partir de l’éditeur

Pour créer une rubrique à partir de l’éditeur, procédez comme suit :

1. Dans le panneau Référentiel, sélectionnez l’icône **Nouveau fichier** puis sélectionnez **Rubrique** dans le menu déroulant.

   ![](images/create-topic-option.png){width="500" align="left"}

   Vous pouvez également accéder à cette option à partir de la page d&#39;accueil [Experience Manager Guides](./intro-home-page.md) et du menu d&#39;options d&#39;un dossier dans la vue Référentiel.

2. La boîte de dialogue **Nouvelle rubrique** s&#39;affiche.

3. Dans la boîte de dialogue **Nouvelle rubrique**, fournissez les détails suivants :
   - Titre de la rubrique.
   - \(Facultatif\)* Nom de fichier de la rubrique. Le nom du fichier est suggéré automatiquement en fonction du titre de la rubrique. Si votre administrateur a activé les noms de fichiers automatiques en fonction du paramètre UUID, vous ne verrez pas le champ Nom .
   - Modèle sur lequel la rubrique sera basée. Par exemple, pour une configuration prête à l’emploi, vous pouvez choisir parmi les modèles Vierge, Concept, DITAVAL, Référence, Tâche, Rubrique, Markdown, Glossaire et Dépannage. Si un profil de dossier est configuré sur votre dossier, seuls les modèles de rubrique configurés sur le profil de dossier sont affichés.
   - Chemin d’accès où enregistrer le fichier de rubrique. Par défaut, le chemin du dossier actuellement sélectionné dans le référentiel s’affiche dans le champ Chemin .

4. Sélectionnez **Créer**.

   ![](images/create-topic-dialog-new.png){width="300" align="left"}

La rubrique est créée au chemin d’accès spécifié. En outre, la rubrique est ouverte dans l’éditeur pour modification.

![](images/new-topic-editor.png){align="left"}

## Créer des rubriques à partir de l’interface utilisateur d’Assets

Pour créer une rubrique à partir de l’interface utilisateur d’Assets, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez à l’emplacement où vous souhaitez créer la rubrique.

1. Pour créer une rubrique, sélectionnez **Créer** \> **Rubrique DITA**.

1. Sur la page Plan directeur, sélectionnez le type de document DITA à créer, puis sélectionnez **Suivant**.

   ![](images/create_dita_topic.png){align="left"}

   Par défaut, Experience Manager Guides fournit les modèles de rubriques DITA les plus couramment utilisés. Vous pouvez configurer d’autres modèles de rubrique en fonction des exigences de votre organisation, afficher *Configurer des modèles de création* dans Installer et configurer Adobe Experience Manager Guides pour votre configuration.

   >[!NOTE]
   >
   > Dans la vue Liste de l&#39;interface utilisateur d&#39;Assets, le type de rubrique DITA s&#39;affiche dans la colonne Type sous la forme Rubrique, Tâche, Concept, Référence, Glossentry, Markdown ou DITAVAL. Le mappage DITA s&#39;affiche sous la forme Map.

1. Sur la page Propriétés , spécifiez le document **Titre**.

1. \(Facultatif\) Spécifiez le fichier **Nom**.

   Si votre administrateur a configuré le nom de fichier automatique en fonction du paramètre UUID, vous ne verrez pas l’option permettant de spécifier le nom du fichier. Un nom de fichier basé sur l&#39;UUID est automatiquement attribué au fichier.

   Si l’option de dénomination de fichier est disponible, le nom est également automatiquement suggéré en fonction du **Titre** de votre document. Si vous souhaitez spécifier manuellement le nom du document, assurez-vous que le **Nom** ne contient pas d&#39;espaces, d&#39;apostrophe ou de crochets et se termine par .xml ou .dita. Par défaut, Experience Manager Guides remplace tous les caractères spéciaux par des tirets. Consultez la section Noms de fichier dans le guide des bonnes pratiques pour connaître les bonnes pratiques relatives à l&#39;attribution de noms aux fichiers DITA.

1. Sélectionnez **Créer**. Le message Rubrique créée s’affiche.

   Vous pouvez choisir d’ouvrir la rubrique pour la modifier dans l’éditeur ou d’enregistrer le fichier de rubrique dans le référentiel Adobe Experience Manager.

**Informations supplémentaires**

1. Chaque nouvelle rubrique créée à partir de l&#39;interface utilisateur d&#39;Assets **Créer** \> **Rubrique DITA** ou de l&#39;éditeur se voit attribuer un identifiant de rubrique unique. La valeur de cet identifiant est le nom du fichier lui-même. En outre, un nouveau document est enregistré comme la dernière copie de travail de la rubrique dans la gestion des ressources numériques. Tant que vous n’avez pas enregistré une révision d’une rubrique nouvellement créée, vous n’afficherez aucun numéro de version dans l’historique des versions. Si vous ouvrez la rubrique pour la modifier, les informations de version s’affichent dans le coin supérieur droit de la barre d’outils :

   ![](images/topic-version-none_cs.png){width="550" align="left"}

2. Les informations de version d’une rubrique nouvellement créée s’affichent sous la forme *aucune*. Lorsque vous enregistrez une nouvelle version, un numéro de version 1.0 lui est attribué.

3. Si votre administrateur a configuré votre éditeur pour verrouiller les fichiers avant de les modifier, vous ne pourrez pas modifier un fichier tant que vous ne l’aurez pas verrouillé. De même, s’il est configuré, il vous sera demandé de déverrouiller tout fichier verrouillé avant de le fermer.

4. Une fois que vous avez créé votre rubrique DITA, continuez à enregistrer les modifications apportées à votre copie de travail et créez une nouvelle version une fois que vous avez terminé les mises à jour de votre rubrique.

**Rubrique parente :**&#x200B;[ Créer et prévisualiser des rubriques](create-preview-topics.md)
