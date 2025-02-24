---
title: Génération incrémentielle de la sortie
description: Découvrez comment fonctionne la génération de sortie incrémentielle pour AEM Sites dans AEM Guides.
exl-id: 019d9fbf-2f23-4669-8022-d693be75c1c3
feature: Publishing
role: User
source-git-commit: b061bcbcefba1700665bed33f017a962e84a0433
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 0%

---


# Génération incrémentielle de la sortie

>[!NOTE]
>
> La génération de sortie incrémentielle s’applique uniquement à la sortie AEM Sites. En outre, vous ne pouvez régénérer que les rubriques DITA \(.dita/.xml\) à partir d&#39;un plan DITA ou de sous-plans. Si vous sélectionnez un plan DITA, un sous-plan, un groupe de sujets ou un sujet avec `@processing-role="resource-only"`, l&#39;option de régénération n&#39;est pas disponible.

Dans certains cas, vous pouvez mettre à jour seulement quelques rubriques dans votre plan DITA et activer uniquement ces rubriques mises à jour. Pour gérer ces scénarios, Experience Manager Guides vous permet de créer des sorties incrémentielles. Si vous avez mis à jour quelques rubriques, vous n&#39;avez pas besoin de régénérer l&#39;ensemble du plan DITA. Vous pouvez sélectionner uniquement les rubriques mises à jour et les générer de nouveau.

Si votre mappage est segmenté et que vous avez mis à jour une seule rubrique dans ce mappage, vous devez régénérer l’ensemble du mappage pour que la rubrique ou le contenu mis à jour soit reflété dans la sortie. Vous n’obtiendrez pas l’option de régénération de sortie au niveau d’une rubrique, elle est uniquement disponible au niveau du mappage \(chunked\). Ceci s&#39;applique au mappage parent et à tous les sous-mappages.

Effectuez les étapes suivantes pour régénérer la sortie d’une rubrique spécifique ou d’un groupe de rubriques :

>[!IMPORTANT]
>
> Lorsque vous régénérez la sortie AEM Sites, elle est créée à l’aide de la version actuelle des fichiers et non de la ligne de base jointe.

## Générer une sortie incrémentielle à partir de la console Map

Effectuez les étapes suivantes pour générer une sortie incrémentielle pour AEM Sites à l’aide de la console Map :

1. [Ouvrez le fichier de mappage DITA dans la console de mappage](./open-files-map-console.md).
1. Sélectionnez le paramètre prédéfini AEM Sites pour lequel vous souhaitez générer une sortie incrémentielle.
1. Dans l’onglet **Rubriques**, sélectionnez les rubriques que vous souhaitez publier.

   ![liste de rubriques aem sites](images/aem-presets-topic-list.png) {width="800" align="left"}

   >[!NOTE]
   >
   > Lorsqu&#39;une ligne de base est sélectionnée dans l&#39;onglet **Contenu**, la liste des rubriques affiche les rubriques et leurs versions à partir de la ligne de base jointe<br><br>
   > La publication incrémentielle à partir de la liste Rubriques ne doit être utilisée que lorsqu’il n’y a aucune modification de la structure du mappage. Si la structure de la carte/table des matières est modifiée, la carte entière doit être publiée une seule fois pour mettre à jour la table des matières.
1. Sélectionnez **Enregistrer** pour enregistrer les modifications.
1. Sélectionnez **Générer la sortie** pour générer la sortie.


## Générer une sortie incrémentielle à partir du tableau de bord de mappage

Effectuez les étapes suivantes pour générer une sortie incrémentielle pour AEM Sites à l’aide du tableau de bord de mappage :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de plan DITA et sélectionnez-le.

   La console de mappage DITA s&#39;affiche avec la liste des paramètres prédéfinis de sortie disponibles pour générer la sortie.

1. Sélectionnez l’onglet **Rubriques**.

   Une liste des rubriques disponibles dans le plan DITA s&#39;affiche.

1. Sélectionnez les rubriques à régénérer.

   >[!NOTE]
   >
   > Si vous avez ajouté de nouvelles rubriques au plan DITA, vous ne pourrez pas générer ces nouvelles rubriques à partir d&#39;ici. Vous devez d&#39;abord publier les rubriques nouvellement ajoutées à l&#39;aide de la fonction de publication de plan DITA.

   ![](images/regenerate-topics.png){width="800" align="left"}

1. Sélectionnez **Régénérer**.

   La page **Régénérer les rubriques sélectionnées** s&#39;affiche.

1. Sélectionnez le paramètre prédéfini de sortie à utiliser pour générer de nouveau les rubriques sélectionnées.

1. Sélectionnez **Régénérer** pour lancer le processus de génération de sortie.


>[!IMPORTANT]
>
> Si vous renommez un titre de rubrique et que vous régénérez la rubrique, le titre de rubrique mis à jour n&#39;apparaît pas dans la table des matières du plan DITA. Pour mettre à jour le titre de la rubrique dans la table des matières, vous devez générer l&#39;ensemble du plan DITA.

Vous pouvez consulter le statut actuel de la demande de génération de sortie dans l’onglet **Sorties**. Pour plus d’informations, voir [Afficher l’état de la tâche de génération de sortie](#view-the-status-of-the-output-generation-task).



**Rubrique parente :** [Présentation des paramètres prédéfinis de sortie](generate-output-understand-presets.md)
