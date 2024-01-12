---
title: Utilisation de la ligne de base
description: Découvrez l’utilisation des lignes de base dans AEM Guides. Découvrez comment créer, afficher des contenus, modifier, dupliquer, supprimer, ajouter des étiquettes et exporter des lignes de base traduites.
exl-id: 0554947f-3038-4fd2-8a62-ac0d4b858e94
feature: Publishing
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1960'
ht-degree: 0%

---

# Utilisation de la ligne de base {#id1825FI0J0PF}

La fonctionnalité de ligne de base vous permet de créer une version de vos rubriques et ressources qui peuvent ensuite être utilisées pour la publication ou la traduction. Par exemple, si votre mappage DITA comporte `topicA` et `imageA`, vous pouvez créer une ligne de base pour utiliser la 3e version de la `topicA`, mais la 4e version de `ImageA`. Une fois que vous avez mis en place une ligne de base, vous pouvez publier ou traduire des rubriques de différentes versions en un seul clic.

La sélection d’une ligne de base est facultative pour les paramètres prédéfinis de sortie et un mappage DITA peut comporter plusieurs lignes de base. Cependant, chaque paramètre prédéfini de sortie dans un mappage DITA peut être associé à une seule ligne de base. Si aucune ligne de base n’est spécifiée au moment de la publication, la sortie est publiée à l’aide de la dernière version du contenu.

De même, la sélection d’une ligne de base pour traduire le contenu est facultative. Cependant, si vous choisissez de traduire du contenu à l’aide d’une ligne de base, le contenu de cette dernière est également enregistré avec les copies traduites. Vous pouvez ensuite utiliser la ligne de base traduite pour effectuer d’autres opérations, comme la partager avec des éditeurs externes ou l’archiver. Pour plus d’informations sur l’exportation d’une ligne de base traduite, voir [Exporter la ligne de base traduite](#id196SE600GHS).

>[!TIP]
>
> Voir *Ligne de base* section du guide des bonnes pratiques pour connaître les bonnes pratiques relatives à l’utilisation des lignes de base.

Votre administrateur peut configurer l’onglet Ligne de base dans le tableau de bord de mappage. Pour plus d’informations, voir *Configuration de l’onglet Ligne de base dans le tableau de bord de la carte DITA* dans le Guide d&#39;installation et de configuration.

Vous pouvez accéder à la fonction Ligne de base en procédant comme suit :

1. Dans l’interface utilisateur d’Assets, accédez à et cliquez sur le fichier de mappage DITA.
1. Accédez au **Lignes de base** .

Dans l’onglet Lignes de base , vous pouvez effectuer les actions suivantes :

- [Création d’une ligne de base](#id195FI0I0MUQ)
- [Afficher le contenu d’une ligne de base](#id195FI0I0TLN)
- [Modification, duplication ou suppression des lignes de base](#id195FI0I0YJL)
- [Ajout d’étiquettes à une ligne de base](#id184KD0T305Z)

## Création d’une ligne de base {#id195FI0I0MUQ}

Vous pouvez créer une ligne de base avec une version spécifique des rubriques et du contenu référencé disponible à une date et une heure spécifiques, ou avec un libellé défini pour une version de rubriques. Vous pouvez spécifier individuellement les versions des rubriques sélectionnées dans une ligne de base afin que chaque fois que vous appliquez la ligne de base dans le processus de publication ou de traduction, les rubriques sélectionnées et leurs versions correspondantes soient incluses pour la génération de sortie ou la traduction.

Effectuez les étapes suivantes pour créer une ligne de base :

1. Sur la page Lignes de base , cliquez sur **Créer**.
1. Saisissez un nom pour la ligne de base dans **Nom de la ligne de base**.
   ![création d’une ligne de base](images/create-baseline.png){width="800" align="left"}
1. Dans **Définir la version basée sur**, sélectionnez l’une des options suivantes :

   - **Libellé**: sélectionnez cette option pour sélectionner les rubriques en fonction du libellé qui leur est appliqué. Saisissez un libellé pour filtrer la liste selon la chaîne saisie. Dans la liste déroulante filtrée, vous pouvez choisir un libellé pour sélectionner les rubriques et autres ressources ayant le libellé spécifié.

   Lorsque vous sélectionnez **Libellé**, vous disposez également d’une option supplémentaire pour utiliser la dernière version des rubriques pour lesquelles le libellé spécifié n’est pas appliqué. Si vous ne sélectionnez pas cette option et qu’il existe un fichier de rubrique ou de média qui ne comporte pas le libellé spécifié, le processus de création de ligne de base échoue. Pour plus d’informations sur l’ajout d’étiquettes, voir [Utilisation des libellés](web-editor-use-label.md#).

   - **Version activée** &lt;*horodatage*\> : sélectionne la version des rubriques à la date et à l’heure spécifiées. Notez que l’heure que vous indiquez ici correspond au fuseau horaire de votre serveur AEM. Si votre serveur se trouve dans un fuseau horaire différent, les rubriques seront récupérées en fonction du fuseau horaire de votre serveur et non de votre fuseau horaire local.

   Une fois que vous avez sélectionné un libellé ou une version à la date, toutes les rubriques et tous les fichiers multimédias référencés dans le mappage sont sélectionnés en conséquence. Cette sélection de rubriques n’est pas affichée dans l’interface utilisateur, mais elle est enregistrée dans le serveur principal.

   >[!NOTE]
   >
   >Il est recommandé de ne pas utiliser la variable **Parcourir toutes les rubriques** lors de la création d’une ligne de base.

1. Cliquez sur **Enregistrer**.

## Afficher le contenu d’une ligne de base {#id195FI0I0TLN}

Vous pouvez afficher le contenu d’une ligne de base existante en cliquant sur l’onglet Lignes de base et en sélectionnant la version de base souhaitée dans la liste. La page Lignes de base se divise en trois parties : fichier de mappage DITA, contenu ou rubriques de la carte, et contenu référencé. Si votre carte contient des sous-cartes, les rubriques référencées à partir de la sous-carte s’affichent également dans la section Contenu . Les différentes colonnes de la page Ligne de base sont décrites ci-dessous :

- **Nom**: répertorie le mappage DITA, le titre de la rubrique ou le nom de la ressource, tel que le nom de fichier d’une image.

- **Genre**: répertorie le type ou le type de ressource dans le mappage, comme le mappage DITA, la rubrique DITA ou le format d’image.

- **Version**: répertorie la version de la ressource disponible dans la ligne de base.

- **Date et heure de la version**: répertorie la date et l’heure de création de la ressource pour la version sélectionnée.

- **Dernière**: indique si la dernière version de la ressource est utilisée dans la ligne de base.

- **Carte parente**: si votre fichier map contient des sous-mappages, cette colonne contient le nom de la carte dans laquelle une rubrique est référencée.

- **Libellé**: répertorie le libellé\(s\) appliqué à la version de la rubrique.

- **Référencé par**: cette colonne est disponible uniquement pour le contenu référencé. Elle indique la rubrique parente de la ressource référencée. Si une ressource est référencée par plusieurs rubriques, les rubriques sont séparées par des virgules.

## Modification, duplication ou suppression des lignes de base {#id195FI0I0YJL}

**Modifier les lignes de base**

Effectuez les étapes suivantes pour modifier une ligne de base existante :

1. Sélectionnez la ligne de base et cliquez sur **Modifier**.
1. Effectuez les modifications requises dans la ligne de base. Vous pouvez modifier le nom et la version de la rubrique ou du contenu référencé.
1. Si vous souhaitez utiliser une autre version pour une ou plusieurs rubriques, vous pouvez le faire en sélectionnant manuellement ces rubriques. Cliquez sur **Parcourir la rubrique**, sélectionnez la rubrique pour laquelle vous souhaitez utiliser une autre version. Dans la liste déroulante Sélectionner une version pour la rubrique sélectionnée, sélectionnez une version de la rubrique à utiliser dans la ligne de base, puis cliquez sur **OK**.

   ![](images/baseline-select-version-drop-down.png){width="800" align="left"}

   Les informations sur la rubrique et sa version sélectionnée sont stockées dans le serveur principal. Vous pouvez répéter cette étape pour modifier la version sélectionnée pour plusieurs rubriques.

1. Pour charger toutes les rubriques et tous les fichiers multimédias référencés à partir du mappage DITA, cliquez sur le **Parcourir toutes les rubriques** lien. L’UUID des rubriques et des fichiers multimédia est également affiché sous le titre de la rubrique ou le nom du fichier \(media\).

   >[!NOTE]
   >
   > Si votre carte DITA contient un très grand ensemble de fichiers, avec des mappages imbriqués et des rubriques, le fait de cliquer sur Parcourir toutes les rubriques peut prendre un certain temps pour charger tous les fichiers.

   Le contenu de votre carte est présenté dans les trois sections : le fichier de mappage, le contenu \(références de rubrique\) et le contenu référent \(rubriques imbriquées, mappages et autres ressources\). Une fois que tout le contenu référencé est disponible, vous pouvez sélectionner individuellement la version de la rubrique que vous souhaitez utiliser dans votre ligne de base.

   La variable **Version** La liste déroulante affiche les versions disponibles des rubriques ou du contenu référencé. Pour le contenu référencé, vous avez la possibilité de choisir automatiquement une version.

   Si vous choisissez **Sélectionner automatiquement** pour le contenu référencé, le système sélectionne automatiquement la version du contenu référencé correspondant à la version du contenu dans lequel il est référencé. Par exemple, supposons qu’une rubrique A comporte une référence à une image B. Lorsque la version 1.5 de la rubrique A a été créée, la version de l’image B était 1.2 dans le référentiel. Désormais, lorsqu’une ligne de base est créée avec la version 1.5 de la rubrique A avec l’image B définie sur **Sélectionner automatiquement**, le système sélectionne automatiquement la version 1.2 de l’image B.

   Si vous créez une ligne de base à l’aide des libellés, **Sélectionner automatiquement** s’applique à la version de tout le contenu référencé.

   Si le contenu ou les ressources référencés \(rubrique, sous-plans, images ou vidéos\) ne sont pas versionnés \(par exemple, contenu récemment chargé\), la création d’une ligne de base crée une version pour ces fichiers. Toutefois, si vos fichiers sont versionnés, aucune version incrémentielle n’est créée pour ces fichiers. Ce comportement est contrôlé par le paramètre de création automatique de version, activé par défaut. Cela est également nécessaire pour la traduction du contenu, dans lequel le processus de traduction exige que tous les fichiers aient une version.

   >[!NOTE]
   >
   > Si vous souhaitez spécifier une version différente pour une ressource spécifique, vous pouvez le faire en choisissant la version souhaitée dans la **Version** liste déroulante.
1. Cliquez sur **Enregistrer**.

**Duplication des lignes de base**

Sélectionnez la ligne de base et cliquez sur **Dupliquer** pour créer une copie d’une ligne de base existante. Spécifiez un autre nom pour la ligne de base, choisissez le numéro de version des rubriques et le contenu référencé, puis cliquez sur **Enregistrer**.

**Suppression des lignes de base**

Sélectionnez la version de base et cliquez sur **Supprimer** pour supprimer une ligne de base.

## Ajout d’étiquettes à une ligne de base {#id184KD0T305Z}

L’ajout d’étiquettes à chaque rubrique peut prendre du temps. AEM Guides fournit un mécanisme d’un simple clic pour ajouter des étiquettes à plusieurs rubriques et du contenu référencé dans un mappage DITA.

Effectuez les étapes suivantes pour ajouter un libellé à plusieurs rubriques et du contenu référencé dans un mappage DITA :

1. Sur la page Lignes de base , sélectionnez une ligne de base contenant les rubriques et le contenu référencé sur lesquels vous souhaitez ajouter un libellé.

   >[!NOTE]
   >
   > Assurez-vous que votre ligne de base ne contient pas la dernière version d’une rubrique ou d’une ressource. Un libellé peut uniquement être ajouté à une rubrique ou à une ressource versionnée.

1. Cliquez sur **Ajouter des étiquettes**.

   ![](images/add-label-baseline-uuid.png){width="800" align="left"}

1. Dans le **Ajouter un libellé** , spécifiez un libellé unique à associer à cette ligne de base.

   Si votre administrateur a configuré des étiquettes prédéfinies, ces étiquettes s’affichent dans une liste déroulante. Vous devez choisir un libellé dans la liste.

1. Si vous souhaitez appliquer le libellé aux rubriques référencées à partir des sous-cartes, sélectionnez **Appliquer le libellé aux cartes enfants et aux personnes à charge** .

   - Cliquez sur **Ajouter**.
Le libellé spécifié est ajouté au mappage DITA et aux rubriques et au contenu référencés.

     ![](images/label-added-baseline-uuid.png){width="650" align="left"}


## Exporter la ligne de base traduite {#id196SE600GHS}

Vous pouvez utiliser la ligne de base pour traduire du contenu. Par exemple, vous pouvez créer une ligne de base pour la version 1.1 prête à être traduite en français. Dans l’onglet Traduction, vous devez utiliser la ligne de base pour filtrer votre contenu, puis sélectionner la ligne de base de la version 1.1 de votre contenu. L’utilisation de la ligne de base pour traduire du contenu facilite la gestion du contenu.

Une fois le contenu traduit, vous pouvez exporter la ligne de base traduite pour l’archiver ou la partager avec différentes équipes de votre entreprise. Vous devez tenir compte des points suivants avant d’exporter une ligne de base traduite :

- L’export d’une ligne de base n’est possible qu’après la traduction du contenu de la ligne de base. Si vous essayez d’exporter une ligne de base pour laquelle la traduction n’est pas lancée ou n’est pas terminée, vous obtenez une erreur.
- Vous ne pouvez transférer la ligne de base que pour une version déjà traduite. Par exemple, si vous avez créé une ligne de base pour la version 1.1 de votre contenu et que la même ligne de base est traduite, vous pouvez exporter cette ligne de base. Cependant, si vous avez créé une ligne de base pour la version 1.2, qui n’est pas traduite, vous ne pouvez pas exporter cette ligne de base.
- Si une ligne de base est déjà exportée, vous pouvez la remplacer en sélectionnant l’option *Remplacer la ligne de base existante* lors de l’exportation.

Effectuez les étapes suivantes pour exporter une ligne de base traduite :

1. Ouvrez le mappage DITA qui contient la ligne de base traduite.

1. Dans le **Traduction** , développez la **Ligne de base** option disponible dans le rail de gauche.

   ![](images/export-baseline.png){width="800" align="left"}

1. Sélectionnez la variable **Utilisation de la ligne de base** et sélectionnez la ligne de base à exporter.

1. Cliquez sur **Référence d’exportation**.

   L’état de l’exportation s’affiche. Si le processus est réussi, un message mentionnant la langue pour laquelle la ligne de base est exportée s’affiche. En cas d’échec, la cause de l’échec s’affiche.

   Si vous essayez d&#39;exporter la ligne de base déjà exportée, le message d&#39;échec de création de la ligne de base s&#39;affiche également.

1. \(Facultatif\) Pour exporter une ligne de base déjà exportée, sélectionnez **Remplacer la ligne de base existante** puis cliquez sur **Référence d’exportation**.


**Rubrique parente :**[ Génération de sortie](generate-output.md)
