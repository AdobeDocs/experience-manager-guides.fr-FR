---
title: Gestion des paramètres prédéfinis de sortie de profil global et de dossier
description: Découvrez comment créer, modifier, renommer, dupliquer et supprimer des paramètres prédéfinis de sortie de profil global et de dossier en tant qu’utilisateurs administratifs dans AEM Guides.
exl-id: 549c9fe2-77f8-423c-8b3e-b43e56055732
feature: Authoring, Features of Web Editor, Publishing
role: User
TQID: https://experienceleague.adobe.com/FCtMWJZh9bc9sayuHsMWnd-c6mZ0Uvi0ZAgv2lOSu-4
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0efid: f9dbea21-a714-40dd-bc90-080d8046c93fid: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 478
ht-degree: 0%

---

# Gestion des paramètres prédéfinis de sortie de profil global et de dossier {#id22BLJ0D0V1U}

Les paramètres prédéfinis de profil global et de dossier ne sont disponibles que pour les utilisateurs administratifs au niveau du dossier.

En tant qu’administrateur, Adobe Experience Manager Guides vous permet de créer et de gérer des paramètres prédéfinis de sortie pour les profils globaux et de dossiers. Vous pouvez ensuite facilement utiliser ces paramètres prédéfinis de sortie pour générer une sortie pour tous les mappages liés à ce profil global ou de dossier.

Pour créer un paramètre prédéfini de sortie pour les profils globaux et de dossier, procédez comme suit :

1. Sélectionnez le plan DITA pour lequel vous souhaitez créer un paramètre prédéfini de sortie.
1. Sélectionnez l’option **Modifier les rubriques** dans le menu **Options** du fichier de mappage. Le fichier de mappage est ouvert pour modification dans l’éditeur.
1. Sélectionnez l’icône **Ouvrir dans la console de mappage** pour ouvrir le fichier de mappage dans la console de mappage.
1. Dans la console Mappage, accédez à l’onglet **Paramètres prédéfinis de sortie**, puis sélectionnez l’icône + pour créer un paramètre prédéfini de sortie pour votre mappage DITA.

   ![](images/add-global-output-preset.png){width="350"}

1. Saisissez les informations suivantes dans la boîte de dialogue **Ajouter un paramètre prédéfini** :
   - Type
   - Nom
   - Cible \(pour le paramètre prédéfini de la base de connaissances\)
1. Cochez la case **Ajouter au profil de dossier** pour créer un paramètre prédéfini de sortie pour le profil de dossier associé, puis sélectionnez **Ajouter**. Le paramètre prédéfini est créé et il apparaît sous l’onglet **Paramètres prédéfinis de sortie** de tous les mappages associés. L’icône \( ![](images/global-preset-icon.svg)\) indique un paramètre prédéfini de niveau de profil de dossier.
1. Saisissez les détails de la configuration. Pour plus d’informations sur les paramètres prédéfinis de sortie, consultez la section [Présentation des paramètres prédéfinis de sortie](./generate-output-understand-presets.md).

   >[!NOTE]
   >
   > Ces paramètres prédéfinis ajoutés au profil de dossier sont indépendants des mappages. Par conséquent, les configurations spécifiques au mappage ne sont pas présentes pour ces paramètres prédéfinis.

1. Vous pouvez sélectionner l’icône **Générer la sortie** dans le coin supérieur droit pour générer la sortie des mappages liés au paramètre prédéfini de sortie créé. Vous pouvez afficher l’état du processus de génération de sortie. Pour afficher la sortie, sélectionnez **Afficher la sortie** dans la boîte de dialogue **Succès**.

>[!NOTE]
>
> Experience Manager Guides fournit également un paramètre prédéfini de sortie PDF prêt à l&#39;emploi pour générer la sortie de vos plans DITA.

**Autres opérations du menu Options**

Vous pouvez également effectuer les opérations suivantes sur le paramètre prédéfini à partir du menu Options :

- **Générer la sortie** : permet de générer une sortie pour un paramètre prédéfini existant.
- **Afficher la sortie** et **Afficher le journal** : liens rapides pour afficher la sortie générée et les journaux.
- **Renommer**, **Dupliquer** ou **Supprimer** un paramètre prédéfini de sortie existant à partir du menu **Options**.
- PDF par défaut **: vous permet de sélectionner le paramètre prédéfini PDF existant en tant que paramètre prédéfini de pdf par défaut.** Le paramètre prédéfini sélectionné est , puis utilisé comme paramètre prédéfini par défaut pour générer la sortie PDF à l’aide de l’option **Télécharger en tant que PDF** pour une carte.

>[!NOTE]
>
> Lorsqu’un paramètre prédéfini de sortie dans les profils globaux et de dossier est supprimé, il est répercuté dans tous les mappages associés et n’apparaît pas sous l’onglet **Paramètres prédéfinis de sortie**.

**Rubrique parente :**[ Utiliser l’éditeur web](web-editor.md)
