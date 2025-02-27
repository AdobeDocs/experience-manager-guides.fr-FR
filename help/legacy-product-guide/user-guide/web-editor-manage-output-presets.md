---
title: Gestion des paramètres prédéfinis de sortie de profil global et de dossier
description: Découvrez comment créer, modifier, renommer, dupliquer et supprimer des paramètres prédéfinis de sortie de profil global et de dossier en tant qu’utilisateurs administratifs dans AEM Guides.
feature: Authoring, Features of Web Editor, Publishing
role: User
hide: true
exl-id: 4e9cd1d5-1c28-4363-917d-f58511c4f809
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# Gestion des paramètres prédéfinis de sortie de profil global et de dossier {#id22BLJ0D0V1U}

Les paramètres prédéfinis de profil global et de dossier ne sont disponibles que pour les utilisateurs administratifs au niveau du dossier.

En tant qu’administrateur, AEM Guides vous permet de créer et de gérer des paramètres prédéfinis de sortie pour les profils globaux et de dossiers. Vous pouvez ensuite facilement utiliser ces paramètres prédéfinis de sortie pour générer une sortie pour tous les mappages liés à ce profil global ou de dossier.

Pour créer un paramètre prédéfini de sortie pour les profils globaux et de dossier, procédez comme suit :

1. Sélectionnez le plan DITA pour lequel vous souhaitez créer un paramètre prédéfini de sortie.
1. Sélectionnez l’option **Modifier les rubriques** dans le menu **Options** du fichier de mappage. Le fichier de mappage est ouvert pour modification dans l’éditeur web.
1. Dans l&#39;onglet **Sortie**, sélectionnez l&#39;icône + pour créer un paramètre prédéfini de sortie pour votre plan DITA.

   ![](images/add-global-output-preset.png){width="350" align="left"}

1. Saisissez les informations suivantes dans la boîte de dialogue **Ajouter un paramètre prédéfini** :
   - Type
   - Nom
   - Cible \(pour le paramètre prédéfini de la base de connaissances\)
1. Cochez la case **Ajouter au profil de dossier** pour créer un paramètre prédéfini de sortie pour le profil de dossier associé, puis cliquez sur **Ajouter**. Le paramètre prédéfini est créé et s’affiche sous l’onglet **Sortie** de tous les mappages associés. L’icône \( ![](images/global-preset-icon.svg)\) indique un paramètre prédéfini de niveau de profil de dossier.
1. Saisissez les détails de la configuration. Pour plus d’informations sur les paramètres prédéfinis de sortie, consultez la section [Présentation des paramètres prédéfinis de sortie](./generate-output-understand-presets.md).

   >[!NOTE]
   >
   > Ces paramètres prédéfinis ajoutés au profil de dossier sont indépendants des mappages. Par conséquent, les configurations spécifiques au mappage ne sont pas présentes pour ces paramètres prédéfinis.

1. Vous pouvez sélectionner l’icône **Générer le paramètre prédéfini** en haut pour générer la sortie des mappages liés au paramètre prédéfini de sortie créé. Vous verrez le statut du processus de génération de sortie. Pour afficher la sortie, placez le pointeur de la souris sur la rubrique et cliquez sur **Afficher la sortie**.

>[!NOTE]
>
> AEM Guides fournit également un paramètre prédéfini de sortie PDF prêt à l&#39;emploi pour générer la sortie de vos plans DITA.

**Autres opérations du menu Options**

Vous pouvez également effectuer les opérations suivantes sur le paramètre prédéfini à partir du menu Options :

- Sélectionnez le paramètre prédéfini comme paramètre prédéfini de pdf par défaut. Le paramètre prédéfini sélectionné est ensuite utilisé comme paramètre prédéfini par défaut pour générer la sortie PDF à l’aide de l’option **Télécharger en tant que PDF** pour une carte.
- **Modifier**, **Renommer**, **Dupliquer** ou **Supprimer** un paramètre prédéfini de sortie existant à partir du menu **Options**.

>[!NOTE]
>
> Lorsqu’un paramètre prédéfini de sortie dans les profils globaux et de dossier est supprimé, il est répercuté dans tous les mappages associés et n’apparaît pas sous l’onglet **Sortie**.

**Rubrique parente :**[ Utiliser l’éditeur web](web-editor.md)
