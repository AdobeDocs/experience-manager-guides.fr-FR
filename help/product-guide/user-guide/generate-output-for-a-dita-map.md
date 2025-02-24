---
title: Générer la sortie
description: Générez la sortie d'un plan DITA à partir de la console de plans et du tableau de bord des plans dans AEM Guides.
exl-id: d6cbd44c-e74c-4192-bcc4-fb7752c59508
feature: Publishing
role: User
source-git-commit: f6ff978305d9a1587366acbe96d274408bf457f4
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 0%

---

# Générer la sortie

Il existe deux manières de générer une sortie pour un plan DITA :

- [Générer la sortie d&#39;un plan DITA à partir de la console Plan](#generate-output-for-a-dita-map-from-the-map-console)
- [Générer une sortie pour un plan DITA à partir du tableau de bord Plan](#generate-output-for-a-dita-map-from-the-map-dashboard)

## Générer la sortie d&#39;un plan DITA à partir de la console Plan

Effectuez les étapes suivantes pour générer une sortie pour un plan DITA à l&#39;aide de la console Map :

1. [Ouvrez un fichier map dans la console Mappage](./open-files-map-console.md).
2. La console de mappage DITA s&#39;affiche avec la liste des **paramètres prédéfinis de sortie** disponibles pour générer la sortie.

3. Ouvrez le paramètre prédéfini que vous souhaitez utiliser pour générer la sortie, puis sélectionnez **Générer la sortie** pour lancer le processus de génération.

   <img src="images/generate-output-pdf.png" alt="onglet métadonnées" width="600">

   Vous pouvez également pointer sur le paramètre prédéfini et sélectionner **Générer** dans le menu contextuel du paramètre prédéfini.


   <img src="images/generate-preset-map-console.png" alt="onglet métadonnées" width="600">

Une fois la génération de la sortie terminée, sélectionnez **Afficher la sortie** pour afficher la sortie.

Une boîte de dialogue **Succès** s’affiche dans le coin inférieur droit de l’écran.

Si une sortie échoue, le message d’erreur ci-dessous s’affiche.

<img src="images/error-log.png" alt="journal des erreurs" width="250">

Pour afficher le journal des erreurs, sélectionnez **Ignorer**, survolez l’onglet du paramètre prédéfini sélectionné et sélectionnez **Afficher le journal** dans le menu contextuel du paramètre prédéfini.

## Générer une sortie pour un plan DITA à partir du tableau de bord Plan

Effectuez les étapes suivantes pour générer une sortie pour un plan DITA à l&#39;aide du tableau de bord Map :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de plan DITA à publier et sélectionnez-le.

   La console de mappage DITA s&#39;affiche avec la liste des paramètres prédéfinis de sortie disponibles pour générer la sortie.

1. Sélectionnez un ou plusieurs paramètres prédéfinis de sortie à utiliser pour générer la sortie.

   ![](images/generate-multiple-outputs-uuid.png){width="800" align="left"}

1. Sélectionnez l’icône **Générer** pour lancer le processus de génération de sortie.


Vous pouvez consulter le statut actuel de la demande de génération de sortie dans l’onglet **Sorties**. Pour plus d’informations, voir [Afficher l’état de la tâche de génération de sortie](./generate-output-manage-process.md#view-the-status-of-the-output-generation-task).

>[!IMPORTANT]
>
> Si un processus de génération de sortie pour un paramètre prédéfini est en file d’attente ou en cours, vous ne pouvez pas lancer une autre tâche de génération de sortie pour le même paramètre prédéfini.

Vous pouvez également générer la sortie AEM Sites pour une ou plusieurs rubriques, ou l&#39;ensemble du plan DITA à partir de la console de mappage. Pour plus d’informations, consultez [Générer la sortie de la base de connaissances](web-editor-article-publishing.md#id218CK0U019I).




**Rubrique parente :**[ Génération de sortie](generate-output.md)
