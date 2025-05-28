---
title: Créer et gérer des lignes de base à partir de la console Carte
description: Créez et gérez des lignes de base à partir de la console de mappage dans Adobe Experience Manager Guides. Découvrez comment créer des lignes de base sur la base de libellés et appliquer des filtres aux lignes de base.
exl-id: 14f87bdd-3042-46f9-853e-e9ded81b10ed
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: c7e76de14a3dd63eff794ecca16ebbccb3cb2d8a
workflow-type: tm+mt
source-wordcount: '1881'
ht-degree: 0%

---

# Créer et gérer des lignes de base à partir de la console Map {#id223MB0ZF043}

La fonction Ligne de base vous permet de créer une version de vos rubriques et ressources qui peut ensuite être utilisée pour la publication ou la traduction. Par exemple, si votre plan DITA comporte des `topicA` et des `imageA`, vous pouvez créer une ligne de base afin d&#39;utiliser la 3e version de `topicA`, mais la 4e version de `ImageA`. Une fois que vous avez défini une ligne de base, vous pouvez publier ou traduire les rubriques de différentes versions en une seule étape.

La sélection d&#39;une ligne de base est facultative pour les paramètres prédéfinis de sortie et un plan DITA peut avoir plusieurs lignes de base. Cependant, chaque paramètre prédéfini de sortie dans un plan DITA ne peut être associé qu&#39;à une seule ligne de base. Si aucune ligne de base n’est spécifiée au moment de la publication, la sortie est publiée à l’aide de la dernière version du contenu.

De même, la sélection d’une ligne de base pour traduire le contenu est facultative. Cependant, si vous choisissez de traduire le contenu à l’aide d’une ligne de base, le contenu de cette dernière est également enregistré avec les copies traduites. Vous pouvez ensuite utiliser la ligne de base traduite pour effectuer d’autres opérations, telles que le partager avec des éditeurs externes ou l’archiver.


>[!TIP]
>
> Il est recommandé d’utiliser cette fonction de ligne de base à partir de la console Mappage. Cependant, vous pouvez également [utiliser le tableau de bord de mappage pour créer et gérer des lignes de base](./generate-output-use-baseline-for-publishing.md).

Dans l’onglet **Ligne de base**, vous pouvez effectuer les actions suivantes :

- [Créer une ligne de base](#create-a-baseline)
- [Gérer les niveaux de référence](#manage-baselines)


## Créer une ligne de base

Vous pouvez créer une ligne de base à partir de la console Map en procédant comme suit :

1. [Ouvrez le fichier de mappage DITA dans la console de mappage](./open-files-map-console.md).
1. Accédez à l’onglet **Ligne de base** et sélectionnez l’icône + en haut à droite pour commencer à créer une ligne de base.
1. Dans la boîte de dialogue **Nouvelle ligne de base**, fournissez les détails suivants :

   ![Panneau Ligne de base](images/baseline-manage.png){width="500" align="left"}

   - Attribuez un nom à la ligne de base dans le champ **Nom**.
   - Dans **Configuration**, choisissez [Mise à jour manuelle](#configuring-baseline-for-manual-update) ou [Mise à jour automatique](#configuring-baseline-for-automatic-update).
   - Sélectionnez **Appliquer**.

La ligne de base est créée. La création de la ligne de base se produit de manière asynchrone, de sorte que vous pouvez continuer à travailler sur d’autres fichiers. Une fois la ligne de base créée, un message pop-up s’affiche pour confirmer que la ligne de base a été créée. Vous recevez également une notification de boîte de réception pour la même opération.

### Configuration de la ligne de base pour une mise à jour manuelle

Vous pouvez créer manuellement une ligne de base statique avec une version spécifique des rubriques et du contenu référencé disponible à une date et une heure spécifiques, ou avec un libellé défini pour une version des rubriques :

Dans **Sélectionner la version en fonction de** sélectionnez l’une des options suivantes :

- **Date** : sélectionne la version des rubriques à la date et à l’heure spécifiées.
- **Libellé** : sélectionnez cette option pour sélectionner les rubriques en fonction du libellé qui leur est appliqué. Si des libellés sont spécifiés pour les rubriques, les libellés sont répertoriés dans la liste déroulante. Vous pouvez choisir un libellé dans la liste. Vous pouvez également ajouter un libellé dans la zone de texte.

  >[!NOTE]
  >
  > Lors du choix des libellés, le chargeur de libellés reste visible jusqu’à ce que tous les libellés aient été récupérés et complètement chargés. Une fois chargés, les libellés s’affichent dans un ordre alphabétique insensible à la casse. Ils sont récupérés par lots de 20, avec le défilement infini activé dans la liste déroulante pour charger des lots supplémentaires au fur et à mesure que vous faites défiler l’écran.

  Pour les références directes dans les lignes de base statiques, les libellés sont extraits de la dernière version enregistrée de la carte. Par exemple, si vous avez créé les libellés `Label Release 1.0` et `Label Release 1.1` pour les versions 1.0 et 1.1 de la rubrique A, puis ajoutez la rubrique A à la carte enregistrée en tant que version 1.0. Dans ce cas, vous pouvez afficher les libellés `Label Release 1.0` et `Label Release 1.1` dans la liste déroulante pour les libellés de ligne de base statiques.

  Lorsque vous sélectionnez **Libellé** vous pouvez choisir les références directes et indirectes.
   - Pour les références directes dans le plan DITA, vous avez la possibilité d&#39;utiliser la dernière version des rubriques auxquelles le libellé spécifié n&#39;est pas appliqué.

     >[!NOTE]
     >
     > Si vous saisissez un libellé qui n&#39;existe pas et sélectionnez l&#39;option **Ne pas créer de ligne de base** la création de la ligne de base échoue et affiche un message d&#39;erreur à proximité du nom de la ligne de base dans le panneau Ligne de base.

   - Pour les références indirectes dans le plan DITA, vous disposez d&#39;une option supplémentaire pour utiliser la dernière version des rubriques sur lesquelles le libellé spécifié n&#39;est pas appliqué. Vous pouvez également choisir de **Sélectionner automatiquement** pour le contenu référencé. Le système sélectionne alors automatiquement la version du contenu référencé correspondant à la version du contenu dans lequel il est référencé.

Une fois que vous avez sélectionné un libellé ou une version en fonction de la date, toutes les rubriques et tous les fichiers multimédias référencés dans la carte sont sélectionnés en conséquence. Cette sélection de rubriques ne s’affiche pas dans l’interface utilisateur, mais elle est enregistrée en arrière-plan.

### Configuration de la ligne de base pour la mise à jour automatique

Sélectionnez cette option pour la création de la ligne de base afin de sélectionner automatiquement les rubriques en fonction du libellé qui leur est appliqué.

Les références créées à l&#39;aide de la configuration de mise à jour automatique sont mises à jour dynamiquement. Si vous générez une configuration de référence, téléchargez une configuration de référence ou créez un projet de traduction à l’aide d’une configuration de référence, les fichiers sont sélectionnés de manière dynamique en fonction des libellés mis à jour. Par exemple, si vous avez utilisé la version 1.2 d’une rubrique avec le libellé Version 1.0 pour la ligne de base et la version 1.5 mise à jour ultérieurement avec le libellé Version 1.0, la ligne de base sera mise à jour dynamiquement et la version 1.5 sera utilisée.

![Créer une ligne de base](images/dynamic-baseline.png){width="300" align="left"}

- **Libellés** : si des libellés sont spécifiés pour les rubriques, utilisez la liste déroulante **Libellés** pour effectuer une sélection parmi les [libellés répertoriés](#labels-list).

  Les libellés sélectionnés en premier sont prioritaires sur les libellés ultérieurs.

  >[!NOTE]
  >
  >Lorsque les libellés sont extraits, un chargeur s’affiche et la liste déroulante est désactivée.

  Pour les lignes de base dynamiques, les libellés sont extraits de la dernière version enregistrée et de la copie de travail actuelle de la carte. Par exemple, si vous avez créé des libellés   `Label Release A.1.0 ` et `Label Release A.1.1` pour les versions 1.0 et 1.1 de la rubrique A et les libellés `Label Release B.1.0` et `Label Release B.1.1` pour les versions 1.0 et 1.1 de la rubrique B . Vous pouvez ensuite ajouter Topic A à Map A dans la version 1.0 et Topic B à Map A dans la version 1.0* (copie de travail). Dans ce cas, vous pouvez afficher `Label Release A.1.0 `, `Label Release A.1.1`, `Label Release B.1.0` et `Label Release B.1.1` dans la liste déroulante des libellés de ligne de base dynamique.
- **Références indirectes** : pour les références indirectes dans le plan DITA, les options suivantes sont disponibles :

   - **Sélection automatique** : vous pouvez choisir d’effectuer une **Sélection automatique** pour le contenu référencé. Le système sélectionne alors automatiquement la version du contenu référencé correspondant à la version du contenu dans lequel il est référencé.
   - **Utiliser le libellé sélectionné** : vous pouvez créer une ligne de base avec le libellé sélectionné défini pour une version de rubriques.
   - **Utiliser la dernière version ou la copie de travail** : utilisez la dernière version des rubriques auxquelles le libellé spécifié n&#39;est pas appliqué ou, si aucune version n&#39;a été créée, utilisez la copie de travail des rubriques pour créer la ligne de base.

## Gérer les niveaux de référence

Vous pouvez gérer vos lignes de base existantes à l&#39;aide des différentes fonctionnalités du tableau de bord Ligne de base.

- Vous pouvez rechercher une ligne de base existante à l&#39;aide de la zone de texte du panneau Ligne de base. Utilisez l&#39;icône **Appliquer le filtre** pour afficher toutes les lignes de base ou les répertorier avec le statut de création Succès, En cours ou Échec.
- Utilisez l&#39;icône **Actualiser** du panneau Ligne de base pour vérifier toutes les lignes de base et afficher une nouvelle liste de lignes de base pour le plan DITA ouvert en mode Carte.
- Sélectionnez la ligne de base pour afficher ou modifier le contenu d&#39;une ligne de base statique existante dans le panneau **Ligne de base**. La fenêtre de modification de ligne de base affiche le fichier de plan DITA, le contenu ou les rubriques du plan et le contenu référencé.

  >[!NOTE]
  >
  >L&#39;opération de modification des lignes de base statiques n&#39;est recommandée que pour un petit nombre de changements de référence. L&#39;opération Modifier n&#39;est pas recommandée pour modifier la version du plan DITA principal, car il doit recalculer toutes les références. Cela peut entraîner l&#39;échec de la mise à jour de la ligne de base pour les plans DITA volumineux. Pour les plans DITA plus volumineux, vous pouvez créer une nouvelle ligne de base ou modifier les propriétés de la ligne de base.
  >
  >L&#39;opération Modifier en cas de ligne de base dynamique permet de modifier les propriétés de la ligne de base, car les références des lignes de base dynamiques sont générées au moment de l&#39;exécution à l&#39;aide des libellés.

  ![options d&#39;une ligne de base](images/baseline-options.png){width="500" align="left"}

### Actions disponibles pour une ligne de base existante

Vous pouvez également effectuer les opérations suivantes sur la ligne de base à partir du menu Options :

**Dupliquer une base**

Vous pouvez dupliquer une ligne de base et la modifier en fonction de vos besoins.

![dupliquer une base](images/baseline-duplicate.png){width="300" align="left"}
*Dupliquez une ligne de base en fonction d’un libellé ou créez une copie exacte.*

1. Sélectionnez **Dupliquer** dans le menu Options d&#39;une ligne de base. La boîte de dialogue **Dupliquer la ligne de base** s’ouvre.
>[!NOTE]
>
>Le nom par défaut de la ligne de base est `<selected baseline name>`_suffix (comme sample-baseline_1). Vous pouvez modifier le nom en fonction de vos besoins.

   Dans **Sélectionner la version en fonction de**, vous pouvez choisir l’option **Copie exacte** ou l’option **Libellé** :

   - **Copie exacte** : Experience Manager Guides sélectionne la même version de toutes les rubriques et crée une copie exacte de la ligne de base dupliquée.
   - **Libellé** : dans la liste déroulante, vous pouvez choisir l’un des [ libellés répertoriés](#labels-list). Experience Manager Guides sélectionne les versions des rubriques pour lesquelles le libellé sélectionné est défini, tandis que pour les autres rubriques, il sélectionne la version à partir de la ligne de base dupliquée. Par exemple, vous sélectionnez le libellé `Release 1.0` dans la liste déroulante, puis le service sélectionne les versions des rubriques pour lesquelles vous avez défini ce libellé. Pour toutes les autres rubriques, il sélectionne la version de la ligne de base dupliquée.
1. Sélectionnez **Dupliquer**.

- **Renommer** ou **Supprimer** une ligne de base existante**.
- **Gérer les libellés** qui vous permet d’ajouter, de supprimer ou de modifier des libellés existants pour les lignes de base statiques. Si votre administrateur a configuré des libellés prédéfinis, ces libellés s’affichent dans la liste déroulante Ajouter un libellé . Pour plus d’informations sur l’ajout de libellés, voir [ Utiliser des libellés ](web-editor-use-label.md#).

  >[!NOTE]
  >
  > Le processus d’ajout ou de suppression des libellés se produit de manière asynchrone, de sorte que vous pouvez continuer à travailler sur d’autres fichiers. Une fois le libellé ajouté ou supprimé, un message pop-up s’affiche pour confirmer que le libellé a été ajouté ou supprimé. Vous recevez également une notification de boîte de réception pour le même.

- **Modifier les propriétés** d&#39;une ligne de base statique existante que vous avez définie lors de la création de la ligne de base.
- L’option **Exporter la ligne de base** exporte un instantané de la ligne de base dans un fichier Microsoft Excel, y compris tous les détails essentiels tels que le titre, le nom de fichier, le type de fichier, le numéro de version, l’état du document et d’autres informations pertinentes.


### Liste des libellés {#labels-list}

Les libellés répertoriés dans la liste déroulante sont basés sur les critères suivants :
- Les libellés doivent être ajoutés à l&#39;une des versions des rubriques du plan DITA (sur lequel la ligne de base est créée).
- De plus, seules les références de premier niveau (rubriques ou sous-cartes) du plan DITA sont prises en compte pour le choix des libellés.

## Filtres de ligne de base

À l&#39;aide de l&#39;icône Filtres du panneau **Filtres de ligne de base**, vous pouvez appliquer des filtres sur la ligne de base ouverte dans la fenêtre Modification de ligne de base :

![filtres de base](images/baseline-filter.png){width="300" align="left"}

- Filtrez les fichiers en fonction de leur nom ou de leur emplacement.
- Filtrez les fichiers en fonction des valeurs des différentes colonnes telles que Type de fichier, Type de référence, etc.
- Choisissez les colonnes à afficher dans la fenêtre de modification de ligne de base.

>[!NOTE]
>
> Vous pouvez sélectionner un en-tête de colonne et trier les fichiers en fonction des colonnes de la fenêtre de modification de ligne de base.

**Enregistrer ou réinitialiser une ligne de base**

Une fois la ligne de base modifiée, sélectionnez **Enregistrer** pour enregistrer les modifications. Vous pouvez sélectionner **Réinitialiser** si vous ne souhaitez pas enregistrer la modification et réinitialiser la ligne de base. Lorsque vous sélectionnez **Réinitialiser**, un avertissement s’affiche indiquant que les modifications non enregistrées seraient perdues.

**Rubrique parente :**[ Génération de sortie](generate-output.md)

