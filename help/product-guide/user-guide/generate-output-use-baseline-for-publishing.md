---
title: Utiliser la ligne de base
description: Connaître l’utilisation des références dans AEM Guides. Découvrez comment créer, afficher le contenu, modifier, dupliquer, supprimer, ajouter des libellés et exporter les références traduites.
exl-id: 0554947f-3038-4fd2-8a62-ac0d4b858e94
feature: Publishing
role: User
source-git-commit: f6ff978305d9a1587366acbe96d274408bf457f4
workflow-type: tm+mt
source-wordcount: '1790'
ht-degree: 0%

---

# Utiliser la ligne de base depuis le tableau de bord des cartes {#id1825FI0J0PF}

Experience Manager Guides fournit la fonction Ligne de base qui permet aux utilisateurs de créer des lignes de base et de les utiliser pour publier ou traduire des rubriques de différentes versions. Ils peuvent également publier plusieurs paramètres prédéfinis de sortie du même plan DITA en parallèle.

>[!TIP]
>
> Consultez la section *Ligne de base* du guide des bonnes pratiques pour connaître les bonnes pratiques relatives à l&#39;utilisation des lignes de base.

Votre administrateur peut configurer l’onglet Ligne de base dans le tableau de bord des cartes. Pour plus d&#39;informations, consultez la section *Onglet Configurer la ligne de base sur le tableau de bord du plan DITA* du Guide d&#39;installation et de configuration.

Dans l&#39;onglet **Lignes de base**, vous pouvez effectuer les actions suivantes :

- [Créer une ligne de base](#create-a-baseline)
- [Afficher le contenu d&#39;une ligne de base](#view-contents-of-a-baseline)
- [Modifier, dupliquer ou supprimer des niveaux de référence](#edit-duplicate-or-remove-baselines)
- [Ajouter des libellés à une ligne de base](#add-labels-to-a-baseline)

## Créer une ligne de base

Vous pouvez créer une ligne de base avec une version spécifique des rubriques et du contenu référencé disponible à une date et une heure spécifiques, ou avec un libellé défini pour une version des rubriques. Vous pouvez spécifier individuellement les versions des rubriques sélectionnées dans une ligne de base de sorte que chaque fois que vous appliquez la ligne de base dans un workflow de publication ou de traduction, les rubriques sélectionnées et leurs versions correspondantes sont incluses pour la génération ou la traduction de sortie.

Pour créer une ligne de base, procédez comme suit :

1. Ouvrez un fichier de plan DITA dans l&#39;interface utilisateur d&#39;Assets et accédez à la page **Lignes de base**.
2. Sélectionnez **Créer** en haut à gauche.
3. Sur la page Ligne de base, entrez le nom de la ligne de base dans le champ **Nom de la ligne de base**.

   ![](images/create-baseline-assets-ui.png){width="300" align="left"}

4. Dans **Définir la version en fonction de**, sélectionnez l’une des options suivantes :

   - **Libellé** : sélectionnez cette option pour sélectionner les rubriques en fonction du libellé qui leur est appliqué. Saisissez un libellé pour filtrer la liste en fonction de la chaîne saisie. Dans la liste filtrée, vous pouvez choisir un libellé pour sélectionner les rubriques et les autres ressources portant le libellé spécifié.

     Lorsque vous sélectionnez Libellé, vous avez également la possibilité d&#39;utiliser la dernière version des rubriques sur lesquelles le libellé spécifié n&#39;est pas appliqué. Si vous ne sélectionnez pas cette option et qu&#39;un sujet ou un fichier multimédia ne porte pas le libellé spécifié, le processus de création de la ligne de base échouera. Pour plus d’informations sur l’ajout de libellés, voir Utiliser des libellés.

   - **Version activée** : sélectionne la version des rubriques en fonction de la date et de l’heure spécifiées. Notez que l’heure que vous indiquez ici correspond au fuseau horaire de votre serveur Adobe Experience Manager. Si votre serveur se trouve dans un fuseau horaire différent, les rubriques sont sélectionnées en fonction du fuseau horaire de votre serveur et non de votre fuseau horaire local.

     Une fois que vous avez sélectionné un libellé ou une version en fonction de la date, toutes les rubriques et tous les fichiers multimédias référencés dans la carte sont sélectionnés en conséquence. Cette sélection de rubriques ne s’affiche pas dans l’interface utilisateur, mais elle est enregistrée en arrière-plan.
5. Sélectionnez **Enregistrer**.

## Afficher le contenu d&#39;une ligne de base

Vous pouvez afficher le contenu d&#39;une ligne de base existante en sélectionnant l&#39;onglet Ligne de base et en sélectionnant la version de ligne de base souhaitée dans la liste. La page Lignes de base est divisée en trois parties : le fichier de plan DITA, le contenu ou les rubriques du plan et le contenu référencé. Si votre carte contient des sous-cartes, les rubriques référencées à partir de la sous-carte sont également affichées dans la section Contenu. Les différentes colonnes de la page Ligne de base sont décrites ci-dessous :

- **Nom** : répertorie le plan DITA, le titre de la rubrique ou le nom de la ressource, tel que le nom de fichier d&#39;une image.

- **Kind** : répertorie le type de ressource dans le mappage comme un mappage DITA, une rubrique DITA ou un format d’image.

- **Version** : répertorie la version de la ressource disponible dans la ligne de base.

- **Date et heure de version** : répertorie la date et l’heure de création de la ressource pour la version sélectionnée.

- **La plus récente** : indique si la dernière version de la ressource est utilisée dans la ligne de base.

- **Mappage parent** : si votre fichier de mappage contient des sous-mappages, cette colonne contient le nom du mappage dans lequel une rubrique est référencée.

- **Libellé** : répertorie le ou les libellés appliqués à la version de la rubrique.

- **Référencé par** : cette colonne est disponible uniquement pour le contenu référencé. Indique la rubrique parente de la ressource référencée. Si une ressource est référencée par plusieurs rubriques, celles-ci sont séparées par des virgules.

## Modifier, dupliquer ou supprimer des niveaux de référence

**Modifier niveaux de référence**

Pour modifier une ligne de base existante, procédez comme suit :

1. Sélectionnez la ligne de base, puis sélectionnez **Modifier**.
1. Effectuez les modifications requises dans la ligne de base. Vous pouvez modifier le nom et la version de la rubrique ou du contenu référencé.
1. Si vous souhaitez utiliser une version différente pour une ou plusieurs rubriques, vous pouvez le faire en sélectionnant manuellement ces rubriques. Sélectionnez **Parcourir la rubrique**, puis sélectionnez la rubrique pour laquelle vous souhaitez utiliser une autre version. Dans la liste déroulante Sélectionner une version de la rubrique sélectionnée, sélectionnez une version de la rubrique à utiliser dans la ligne de base et sélectionnez **OK**.

   ![](images/baseline-select-version-drop-down.png){width="800" align="left"}

   Les informations sur la rubrique et sa version sélectionnée sont stockées dans le serveur principal. Vous pouvez répéter cette étape pour modifier la version sélectionnée pour plusieurs rubriques.

1. Pour charger toutes les rubriques et tous les fichiers multimédias référencés à partir du plan DITA, sélectionnez le lien **Parcourir toutes les rubriques**. L’UUID des rubriques et des fichiers multimédias s’affiche également sous le titre de la rubrique ou le nom du fichier \(media\).

   >[!NOTE]
   >
   > Si votre plan DITA comporte un très grand nombre de fichiers avec des plans et des rubriques imbriqués, la sélection de Parcourir toutes les rubriques peut prendre un certain temps pour charger tous les fichiers.

   Le contenu de votre mappage est présenté dans les trois sections suivantes : le fichier de mappage, Contenu \(références de rubrique\) et Contenu référencé \(rubriques imbriquées, mappages et autres ressources\). Une fois que tout le contenu référencé est disponible, vous pouvez sélectionner individuellement la version de la rubrique à utiliser dans votre ligne de base.

   La liste déroulante **Version** affiche les versions disponibles des rubriques ou du contenu référencé. Pour le contenu référencé, vous avez la possibilité de choisir automatiquement une version.

   Si vous choisissez **Sélectionner automatiquement** pour le contenu référencé, le système sélectionne automatiquement la version du contenu référencé correspondant à la version du contenu dans lequel il est référencé. Par exemple, supposons qu’une rubrique A contienne une référence à une image B. Lorsque la version 1.5 de la rubrique A a été créée, la version de l’image B était 1.2 dans le référentiel. Désormais, lorsqu’une ligne de base est créée avec la version 1.5 de la rubrique A avec l’image B définie sur **Sélection automatique**, le système sélectionne automatiquement la version 1.2 de l’image B.

   Si vous créez une ligne de base à l’aide des libellés, **Choisir automatiquement** est appliqué à la version de tout le contenu référencé.

   Si le contenu ou les ressources référencés \(rubrique, sous-cartes, images ou vidéos\) ne disposent pas d’une version \(par exemple, contenu récemment chargé\), la création d’une ligne de base crée une version pour ces fichiers. Cependant, si vos fichiers sont versionnés, aucune version incrémentielle n’est créée pour ces fichiers. Ce comportement est contrôlé par le paramètre de création automatique de version, qui est activé par défaut. Cela est également nécessaire pour traduire le contenu dans lequel le processus de traduction s’attend à ce que tous les fichiers aient une version.

   >[!NOTE]
   >
   > Si vous souhaitez spécifier une version différente pour une ressource particulière, vous pouvez le faire en choisissant la version souhaitée dans la liste déroulante **Version**.
1. Sélectionnez **Enregistrer**.

**Dupliquer les références**

Sélectionnez la ligne de base et sélectionnez **Dupliquer** pour créer une copie d&#39;une ligne de base existante. Spécifiez un autre nom pour la ligne de base et choisissez le numéro de version pour les rubriques et le contenu référencé, puis sélectionnez **Enregistrer**.

**Supprimer niveaux de référence**

Sélectionnez la version Lignes de base et sélectionnez **Supprimer** pour supprimer une ligne de base.

## Ajouter des libellés à une ligne de base

L’ajout de libellés à chaque sujet peut prendre du temps. Experience Manager Guides offre un mécanisme de clic unique permettant d&#39;ajouter des libellés à plusieurs rubriques et au contenu référencé dans un plan DITA.

Effectuez les étapes suivantes pour ajouter un libellé à plusieurs rubriques et au contenu référencé dans un plan DITA :

1. Sur la page Lignes de base, sélectionnez une ligne de base contenant les rubriques et le contenu référencé sur lesquels vous souhaitez ajouter un libellé.

   >[!NOTE]
   >
   > Assurez-vous que votre ligne de base ne dispose pas de la dernière version d&#39;une rubrique ou d&#39;une ressource. Un libellé ne peut être ajouté qu’à une rubrique ou une ressource versionnée.

1. Sélectionnez **Ajouter des libellés**.

   ![](images/add-label-baseline-uuid.png){width="800" align="left"}

1. Dans la boîte de dialogue **Ajouter un libellé**, spécifiez un libellé unique à associer à cette ligne de base.

   Si votre administrateur a configuré des libellés prédéfinis, ces libellés s’affichent dans une liste déroulante. Vous devez choisir un libellé dans la liste.

1. Si vous souhaitez appliquer le libellé aux rubriques référencées à partir des sous-mappages, sélectionnez l&#39;option **Appliquer le libellé aux mappages enfants et à leurs personnes à charge**.

   - Sélectionnez **Ajouter**.
Le libellé spécifié est ajouté au plan DITA ainsi qu&#39;aux rubriques et au contenu référencés.

     ![](images/label-added-baseline-uuid.png){width="650" align="left"}


## Exporter la ligne de base traduite

Vous pouvez utiliser la ligne de base pour traduire le contenu. Par exemple, vous pouvez créer une ligne de base pour la version 1.1 prête à être traduite en français. Dans l’onglet Traduction , vous devez utiliser Ligne de base pour filtrer votre contenu, puis sélectionner Ligne de base pour la version 1.1 de votre contenu. L’utilisation de la ligne de base pour traduire le contenu facilite la gestion de votre contenu.

Une fois le contenu traduit, vous pouvez exporter la ligne de base traduite pour l’archiver ou la partager avec différentes équipes de votre organisation. Vous devez tenir compte des points suivants avant d&#39;exporter une ligne de base traduite :

- L’exportation d’une ligne de base n’est possible qu’une fois le contenu de la ligne de base traduit. Si vous essayez d’exporter une ligne de base pour laquelle la traduction n’a pas commencé ou n’est pas terminée, une erreur s’affiche.
- Vous ne pouvez transférer la ligne de base que pour une version déjà traduite. Par exemple, si vous avez créé une ligne de base pour la version 1.1 de votre contenu et que celle-ci est traduite, vous pouvez exporter cette ligne de base. Cependant, si vous avez créé une ligne de base pour la version 1.2, qui n&#39;est pas traduite, vous ne pouvez pas exporter cette ligne de base.
- Si une ligne de base est déjà exportée, vous pouvez la remplacer en sélectionnant l&#39;option *Remplacer la ligne de base existante* lors de l&#39;exportation.

Effectuez les étapes suivantes pour exporter une ligne de base traduite :

1. Ouvrez le plan DITA contenant la ligne de base traduite.

1. Dans l’onglet **Traduction**, développez l’option **Ligne de base** disponible dans le rail de gauche.

   ![](images/export-baseline-new.png){width="800" align="left"}

1. Sélectionnez l&#39;option **Utiliser niveau de référence** et choisissez le niveau de référence à exporter.

1. Sélectionnez **Exporter la ligne de base**.

   Le statut d’exportation s’affiche. Si le processus réussit, un message mentionnant la langue pour laquelle la ligne de base est exportée s’affiche. En cas d’échec, la cause de l’échec s’affiche.

   Si vous essayez d’exporter la ligne de base déjà exportée, le message Échec de la création de la ligne de base s’affiche également.

1. \(Facultatif\) Pour exporter une ligne de base déjà exportée, sélectionnez **Remplacer la ligne de base existante** puis **Exporter la ligne de base**.


**Rubrique parente :**[ Génération de sortie](generate-output.md)
