---
title: Utilisation de l’éditeur DITAVAL
description: Découvrez comment créer et modifier des fichiers DITAVAL à l’aide de DIVATAL Editor dans AEM Guides. Découvrez comment l’éditeur DITAVAL prend en charge les fichiers DITAVAL dans les vues d’auteur et source.
feature: Authoring, DITAVAL Editor
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---

# Éditeur DITAVAL {#ditaval-editor}

Les fichiers DITAVAL sont utilisés pour générer une sortie conditionnelle. Dans une même rubrique, vous pouvez ajouter des conditions à l’aide d’attributs d’élément pour conditionner le contenu. Ensuite, vous créez un fichier DITAVAL dans lequel vous spécifiez les conditions à sélectionner pour générer le contenu et la condition à exclure de la sortie finale.

AEM Guides vous permet de créer et de modifier facilement des fichiers DITAVAL à l’aide de l’éditeur DITAVAL. L’éditeur DITAVAL récupère les attributs \(ou balises\) définis dans votre système et vous pouvez les utiliser pour créer ou modifier des fichiers DITAVAL. Pour plus d’informations sur la création et la gestion des balises dans AEM, voir la section [Administration des balises](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=en) dans la documentation AEM.

## Créer un fichier DITAVAL

Effectuez les étapes suivantes pour créer un fichier DITAVAL :

1. Dans l’interface utilisateur d’Assets, accédez à l’emplacement où vous souhaitez créer le fichier DITAVAL.

1. Cliquez sur **Créer** \> **Rubrique DITA**.

1. Sur la page Plan directeur, sélectionnez le modèle de fichier DITAVAL et cliquez sur **Suivant**.

1. Sur la page Propriétés, spécifiez les **Titre** et **Nom** pour le fichier DITAVAL.

   >[!NOTE]
   >
   > Le nom est automatiquement proposé en fonction du titre de votre fichier. Si vous souhaitez spécifier manuellement le nom de fichier, assurez-vous que le nom ne contient aucun espace, apostrophe ou accolades et se termine par .ditaval.

1. Cliquez sur **Créer**. Le message Rubrique créée s’affiche.

   Vous pouvez choisir d’ouvrir le fichier DITAVAL à modifier dans l’éditeur DITAVAL ou d’enregistrer le fichier de rubrique dans le référentiel AEM.


## Modifier le fichier DITAVAL

Effectuez les étapes suivantes pour modifier un fichier DITAVAL :

1. Dans l’interface utilisateur d’Assets, accédez au fichier DITAVAL que vous souhaitez modifier.

1. Pour obtenir un verrou exclusif sur le fichier, sélectionnez le fichier et cliquez sur **Extraire**.

1. Sélectionnez le fichier et cliquez sur **Modifier** pour ouvrir le fichier dans l’éditeur AEM Guides DITAVAL.

   L’éditeur DITAVAL vous permet d’effectuer les tâches suivantes :

   A : Activer/désactiver le panneau de gauche
Activez/désactivez l’affichage du panneau de gauche. Si vous avez ouvert le fichier DITAVAL via le mappage DITA, le mappage et le référentiel s’affichent dans ce panneau. Pour plus d’informations sur l’ouverture d’un fichier via le mappage DITA, voir [Modification de rubriques via le mappage DITA](map-editor-advanced-map-editor.md#id17ACJ0F0FHS).

   B : Enregistrer
Enregistre les modifications que vous avez apportées au fichier. Toutes vos modifications sont enregistrées dans la version actuelle de votre fichier.

   C : Ajouter une propriété
Ajoutez une seule propriété dans votre fichier DITAVAL.

   ![](images/ditaval-editor-props.png)

   La première liste déroulante répertorie les attributs DITA autorisés que vous pouvez utiliser dans le fichier DITAVAL. Il existe cinq attributs pris en charge : `audience`, `platform`, `product`, `props` et `otherprops`.

   La seconde liste déroulante affiche les valeurs configurées pour l’attribut sélectionné. La liste déroulante suivante répertorie ensuite les actions que vous pouvez configurer sur l’attribut sélectionné. Les valeurs autorisées dans la liste déroulante des actions sont : `include`, `exclude`, `passthrough` et `flag`. Pour plus d’informations sur ces valeurs, voir la définition de l’élément [prop](http://docs.oasis-open.org/dita/dita/v1.3/errata01/os/complete/part3-all-inclusive/langRef/ditaval/ditaval-prop.html#ditaval-prop) dans la documentation OASIS DITA

   D : Ajouter toutes les propriétés
Si vous souhaitez ajouter en un seul clic toutes les propriétés ou attributs conditionnels définis dans votre système, utilisez la fonction Ajouter toutes les propriétés .

   >[!NOTE]
   >
   > Si toutes les propriétés conditionnelles définies existent déjà dans le fichier DITAVAL, vous ne pouvez pas ajouter d’autres propriétés. Vous recevez un message d’erreur dans ce scénario.

   ![](images/ditaval-all-props.png)

1. Une fois que vous avez terminé de modifier votre fichier DITAVAL, cliquez sur **Enregistrer**.

   >[!NOTE]
   >
   > Si vous fermez le fichier sans l’enregistrer, les modifications seront perdues. Si vous ne souhaitez pas valider les modifications dans AEM référentiel, cliquez sur **Fermer**, puis sur **Fermer sans enregistrement** dans la boîte de dialogue **Modifications non enregistrées**.


## Vues de l’éditeur DITAVAL

L’éditeur DITAVAL d’AEM Guides prend en charge l’affichage de fichiers DITAVAL dans deux modes ou vues différents :

**Auteur** :   Il s’agit d’une vue standard de ce que vous voyez est ce que vous obtenez \(WYSISYG\) de l’éditeur DITAVAL. Vous pouvez ajouter ou supprimer des propriétés à l’aide de l’interface utilisateur simple, qui présente les propriétés, leurs valeurs et les actions dans la liste déroulante. Dans la vue Auteur, vous avez la possibilité d’insérer une propriété individuelle et toutes les propriétés en un seul clic.

Vous pouvez également trouver la version du fichier DITAVAL sur lequel vous travaillez actuellement en pointant le pointeur de la souris sur le nom du fichier.

**Source** :   La vue Source affiche le code XML sous-jacent qui constitue le fichier DITAVAL. En plus d’apporter des modifications de texte standard dans cette vue, un auteur peut également ajouter ou modifier des propriétés à l’aide du catalogue dynamique.

Pour appeler le catalogue dynamique, placez le curseur à la fin d’une définition de propriété et saisissez &quot;&lt;&quot;. L’éditeur affiche la liste de tous les éléments XML valides que vous pouvez insérer à cet emplacement.

![](images/ditaval-source-view.png)
