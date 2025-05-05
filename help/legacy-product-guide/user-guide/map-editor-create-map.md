---
title: Créer un mappage
description: Création d’une carte avec l’éditeur de cartes dans AEM Guides. Recherchez les étapes de création d’un fichier de mappage basé sur un modèle de mappage.
feature: Authoring, Map Editor
role: User
hide: true
exl-id: 981ecaeb-9b1f-4c7a-8336-7746a739bedc
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Créer un mappage {#id176FEN0D05Z}

AEM Guides fournit deux modèles de carte prêts à l&#39;emploi : un plan DITA et un plan de signets. Vous pouvez également créer vos propres modèles de carte et les partager avec vos auteurs pour créer des fichiers de carte.

Pour créer un fichier de mappage, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez à l’emplacement où vous souhaitez créer le fichier de mappage.

1. Cliquez sur **Créer** \> **Plan DITA**.

1. Sur la page Plan directeur, sélectionnez le type de modèle de carte à utiliser, puis cliquez sur **Suivant**.

   >[!NOTE]
   >
   > La manière dont les rubriques sont référencées dans un fichier de mappage dépend du modèle de mappage. Par exemple, si vous sélectionnez le modèle Mappage, les références de rubrique \(`topicref`\) sont utilisées pour faire référence aux rubriques. Dans le cas d&#39;un Bookmap, les références de rubrique sont créées à l&#39;aide de l&#39;élément `chapter` dans DITA.

   ![](images/map-template.png){width="650" align="left"}

1. Sur la page Propriétés , spécifiez le mappage **Titre**.

1. \(Facultatif\) Spécifiez le fichier **Nom**.

   Si votre administrateur a configuré le nom de fichier automatique en fonction du paramètre UUID, vous ne verrez pas l’option permettant de spécifier le nom du fichier. Un nom de fichier basé sur l&#39;UUID est automatiquement attribué au fichier.

   Si l’option d’affectation de nom au fichier est disponible, le nom est également automatiquement suggéré en fonction du Titre de votre carte. Si vous souhaitez spécifier manuellement le nom du fichier de mappage, assurez-vous que le nom du fichier ne contient pas d’espaces, d’apostrophes ou de crochets et se termine par `.ditamap`.

1. Cliquez sur **Créer**.

   Le message Mappage créé s’affiche.

   Chaque nouveau fichier de mappage que vous créez à partir de l’interface utilisateur d’Assets **Créer** \> **Mappage DITA** ou de l’éditeur web se voit attribuer un identifiant de mappage unique. En outre, la nouvelle carte est enregistrée comme dernière copie de travail dans la gestion des ressources numériques. Tant que vous n’avez pas enregistré une révision d’un mappage nouvellement créé, vous ne verrez aucun numéro de version dans l’historique des versions. Si vous ouvrez la carte pour la modifier, les informations de version s’affichent dans le coin supérieur droit de l’onglet du fichier de carte :

   ![](images/first-version-map-none.png){width="650" align="left"}

   Les informations de version d’un mappage nouvellement créé s’affichent sous la forme *aucune*. Lorsque vous enregistrez une nouvelle version, un numéro de version 1.0 lui est attribué. Pour plus d’informations sur l’enregistrement d’une nouvelle version, voir [Enregistrer comme nouvelle version](web-editor-features.md#save-as-new-version-id209ME400GXA).

   Vous pouvez choisir d’ouvrir le mappage pour le modifier dans l’éditeur de mappages configuré ou d’enregistrer le fichier de mappage dans le référentiel AEM.

   >[!NOTE]
   >
   > Pour utiliser l’éditeur de mappages avancé, accédez au fichier de mappage dans l’éditeur web. Si votre administrateur a configuré l’éditeur de carte avancé comme éditeur par défaut dans les fichiers de carte, le fichier de carte est ouvert directement dans l’éditeur de carte avancé pour être modifié. Consultez la section *Définition de l’éditeur de carte avancé par défaut* dans Installation et configuration d’Adobe Experience Manager Guides as a Cloud Service.


**Rubrique parente :**&#x200B;[ Utilisation de l’éditeur de cartes](map-editor.md)
