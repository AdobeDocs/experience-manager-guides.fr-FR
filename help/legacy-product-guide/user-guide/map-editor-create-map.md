---
title: Création d’une carte
description: Créez une carte avec l’éditeur de cartes dans AEM Guides. Recherchez les étapes de création d’un fichier map basé sur un modèle map .
feature: Authoring, Map Editor
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Création d’une carte {#id176FEN0D05Z}

AEM Guides fournit deux modèles de mappage prêts à l’emploi : mappage DITA et mappage d’applet. Vous pouvez également créer vos propres modèles de carte et les partager avec vos auteurs pour créer des fichiers de carte.

Pour créer un fichier map, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez à l’emplacement où vous souhaitez créer le fichier de mappage.

1. Cliquez sur **Créer** \> **Carte DITA**.

1. Sur la page Plan directeur, sélectionnez le type de modèles de carte à utiliser et cliquez sur **Suivant**.

   >[!NOTE]
   >
   > La manière dont les rubriques sont référencées dans un fichier map dépend du modèle map . Par exemple, si vous sélectionnez le modèle Carte , les références de rubrique \(`topicref`\) sont utilisées pour faire référence aux rubriques. Dans le cas d’un Bookmap, les références de rubrique sont créées à l’aide de l’élément `chapter` dans DITA.

   ![](images/map-template.png){width="650" align="left"}

1. Sur la page Propriétés, spécifiez la carte **Title**.

1. \(Facultatif\) Spécifiez le fichier **Name**.

   Si votre administrateur a configuré le nom de fichier automatique en fonction du paramètre UUID , vous ne verrez pas l’option permettant de spécifier le nom de fichier. Un nom de fichier basé sur l’UUID est automatiquement attribué au fichier.

   Si l’option d’affectation de nom de fichier est disponible, le nom est également automatiquement suggéré en fonction du titre de votre mappage. Si vous souhaitez spécifier manuellement le nom de fichier map, assurez-vous que le nom de fichier ne contient aucun espace, apostrophe ou accolades et se termine par `.ditamap`.

1. Cliquez sur **Créer**.

   Le message Mapper créé s’affiche.

   Chaque nouveau fichier de mappage que vous créez à partir de l’interface utilisateur d’Assets **Créer** \> **Carte DITA** ou un identifiant de mappage unique est attribué à l’éditeur Web. En outre, la nouvelle carte est enregistrée en tant que dernière copie de travail dans la gestion des ressources numériques. Tant que vous n’enregistrez pas de révision d’un nouveau mappage, vous ne verrez aucun numéro de version dans l’historique de versions. Si vous ouvrez la carte pour la modifier, les informations de version s’affichent dans le coin supérieur droit de l’onglet du fichier de carte :

   ![](images/first-version-map-none.png){width="650" align="left"}

   Les informations de version d’une carte nouvellement créée s’affichent sous la forme *none*. Lorsque vous enregistrez une nouvelle version, un numéro de version 1.0 lui est affecté. Pour plus d’informations sur l’enregistrement d’une nouvelle version, voir [Enregistrer comme nouvelle version](web-editor-features.md#save-as-new-version-id209ME400GXA).

   Vous pouvez choisir d’ouvrir le mappage en vue de le modifier dans l’éditeur de mappage configuré ou d’enregistrer le fichier de mappage dans le référentiel AEM.

   >[!NOTE]
   >
   > Pour utiliser l’éditeur de mappage avancé, accédez au fichier de mappage dans l’éditeur web. Si votre administrateur a configuré l’éditeur de mappage avancé comme éditeur par défaut dans les fichiers de mappage, le fichier de mappage est ouvert directement dans l’éditeur de mappage avancé pour modification. Voir la section *Définition de l’éditeur de mappage avancé comme valeur par défaut* dans Installation et configuration d’Adobe Experience Manager Guides as a Cloud Service.


**Rubrique parente :**[ Utilisation de l’éditeur de cartes](map-editor.md)
