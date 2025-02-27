---
title: Utiliser l’éditeur DITAVAL
description: Découvrez comment créer et modifier des fichiers DIVATAL à l’aide de l’éditeur DIVATAL dans AEM Guides. Savoir comment l'éditeur DITAVAL prend en charge les fichiers DITAVAL dans les vues auteur et source.
feature: Authoring, DITAVAL Editor
role: User
hide: true
exl-id: 8eee347d-840e-4eaf-9441-c7c53a7c3aa0
source-git-commit: 26fa1e52920c1f1abd5655b9ca7341600a9bca67
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---

# Éditeur DITAVAL {#ditaval-editor}

Les fichiers DITAVAL sont utilisés pour générer une sortie conditionnelle. Dans une seule rubrique, vous pouvez ajouter des conditions à l’aide d’attributs d’élément pour conditionner le contenu. Ensuite, vous créez un fichier DITAVAL dans lequel vous spécifiez les conditions qui doivent être sélectionnées pour générer du contenu et quelle condition doit être exclue de la sortie finale.

AEM Guides vous permet de créer et modifier facilement des fichiers DITAVAL à l&#39;aide de l&#39;éditeur DITAVAL. L’éditeur DITAVAL récupère les attributs \(ou balises\) définis dans votre système et vous pouvez les utiliser pour créer ou modifier des fichiers DITAVAL. Pour plus d’informations sur la création et la gestion des balises dans AEM, consultez la section [Administration des balises](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=en) de la documentation AEM.

## Créer un fichier DITAVAL

Pour créer un fichier DITAVAL, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez à l’emplacement où vous souhaitez créer le fichier DITAVAL.

1. Cliquez sur **Créer** \> **Rubrique DITA**.

1. Sur la page Plan directeur, sélectionnez le modèle de fichier DITAVAL et cliquez sur **Suivant**.

1. Sur la page Propriétés, spécifiez les **Titre** et **Nom** pour le fichier DITAVAL.

   >[!NOTE]
   >
   > Le nom est automatiquement suggéré en fonction du Titre de votre fichier. Si vous souhaitez spécifier manuellement le nom du fichier, assurez-vous que le Nom ne contient pas d&#39;espaces, d&#39;apostrophe ou de crochets et se termine par .ditaval.

1. Cliquez sur **Créer**. Le message Rubrique créée s’affiche.

   Vous pouvez choisir d&#39;ouvrir le fichier DITAVAL pour le modifier dans l&#39;éditeur DITAVAL ou d&#39;enregistrer le fichier de rubrique dans le référentiel AEM.


## Modifier le fichier DITAVAL

Pour modifier un fichier DITAVAL, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez au fichier DITAVAL à modifier.

1. Pour obtenir un verrou exclusif sur le fichier, sélectionnez le fichier et cliquez sur **Extraire**.

1. Sélectionnez le fichier et cliquez sur **Modifier** pour ouvrir le fichier dans l&#39;éditeur DITAVAL d&#39;AEM Guides.

   L&#39;éditeur DITAVAL permet d&#39;effectuer les tâches suivantes :

   A : Activer/désactiver le panneau de gauche
Activez/désactivez la vue du panneau de gauche. Si vous avez ouvert le fichier DITAVAL via un plan DITA, le plan et le référentiel sont affichés dans ce panneau. Pour plus d&#39;informations sur l&#39;ouverture d&#39;un fichier via un plan DITA, voir [Modifier les rubriques via un plan DITA](map-editor-advanced-map-editor.md#id17ACJ0F0FHS).

   B : enregistrer
Enregistre les modifications effectuées dans le fichier. Toutes vos modifications sont enregistrées dans la version actuelle de votre fichier.

   C : Ajouter une propriété
Ajoutez une seule propriété dans votre fichier DITAVAL.

   ![](images/ditaval-editor-props.png)

   La première liste déroulante répertorie les attributs DITA autorisés que vous pouvez utiliser dans le fichier DITAVAL. Cinq attributs sont pris en charge : `audience`, `platform`, `product`, `props` et `otherprops`.

   La deuxième liste déroulante affiche les valeurs configurées pour l’attribut sélectionné. Ensuite, la liste déroulante suivante affiche les actions que vous pouvez configurer sur l’attribut sélectionné. Les valeurs autorisées dans le menu déroulant de l’action sont les suivantes : `include`, `exclude`, `passthrough` et `flag`. Pour plus d&#39;informations sur ces valeurs, voir la définition de l&#39;élément [prop](http://docs.oasis-open.org/dita/dita/v1.3/errata01/os/complete/part3-all-inclusive/langRef/ditaval/ditaval-prop.html#ditaval-prop) dans la documentation OASIS DITA

   D : Ajouter toutes les propriétés
Si vous souhaitez ajouter d’un seul clic toutes les propriétés ou tous les attributs conditionnels définis dans votre système, utilisez la fonction Ajouter toutes les propriétés .

   >[!NOTE]
   >
   > Si toutes les propriétés conditionnelles définies existent déjà dans le fichier DITAVAL, vous ne pouvez pas ajouter d’autres propriétés. Un message d’erreur s’affiche dans ce scénario.

   ![](images/ditaval-all-props.png)

1. Une fois la modification du fichier DITAVAL terminée, cliquez sur **Enregistrer**.

   >[!NOTE]
   >
   > Si vous fermez le fichier sans enregistrer, les modifications seront perdues. Si vous ne souhaitez pas valider les modifications dans le référentiel AEM, cliquez sur **Fermer**, puis sur **Fermer sans enregistrer** dans la boîte de dialogue **Modifications non enregistrées**.


## Vues de l’éditeur DITAVAL

L’éditeur DITAVAL d’AEM Guides prend en charge l’affichage des fichiers DITAVAL dans deux modes ou vues différents :

**Auteur** :   Voici une vue standard Ce que vous voyez est ce que vous obtenez \(WYSISYG\) de l’éditeur DITAVAL. Vous pouvez ajouter ou supprimer des propriétés à l’aide de l’interface utilisateur simple, qui présente les propriétés, ses valeurs et les actions dans une liste déroulante. Dans la vue Auteur, vous avez la possibilité d’insérer une propriété individuelle et d’insérer toutes les propriétés en un seul clic.

Vous pouvez également trouver la version du fichier DITAVAL sur lequel vous travaillez actuellement en plaçant le pointeur de la souris sur le nom du fichier.

**Source**:   La vue Source affiche le code XML sous-jacent qui constitue le fichier DITAVAL. Outre les modifications de texte standard effectuées dans cet affichage, un auteur peut également ajouter ou modifier des propriétés à l’aide du catalogue dynamique.

Pour appeler le catalogue dynamique, placez le curseur à la fin de toute définition de propriété et saisissez « &lt; ». L’éditeur affiche une liste de tous les éléments XML valides que vous pouvez insérer à cet emplacement.

![](images/ditaval-source-view.png)
