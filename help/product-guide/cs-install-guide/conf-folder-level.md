---
title: Configuration de profils globaux ou au niveau du dossier
description: Découvrez comment configurer des profils globaux ou de niveau dossier
exl-id: 19f63d67-89ef-4c5e-bc9a-cf40dd8d7979
feature: Profiles
role: Admin
level: Experienced
source-git-commit: 3bdc3c6370bbad67f9c31f538a49bee105fec0f9
workflow-type: tm+mt
source-wordcount: '4285'
ht-degree: 0%

---

# Configuration de profils globaux ou au niveau du dossier {#id181AH2003PF}

Dans une entreprise, différents groupes ou produits peuvent utiliser différents modèles de création, modèles de sortie, profils d’attributs conditionnels \(ou schémas d’objet\) et configurations de l’éditeur web. La configuration de ces éléments au niveau d’une entreprise \(ou globale\) peut rendre l’expérience des auteurs difficile, car ils verront des modèles ou des profils qui ne sont pas pertinents pour eux.

AEM Guides vous permet de configurer la création de modèles \(rubrique ou mappage\), de modèles de sortie, d’attributs conditionnels et de configurations d’éditeur web au niveau de l’entreprise \(globale\) ainsi qu’au niveau des dossiers. Ainsi, vous pouvez séparer les configurations pour différents services ou produits de votre entreprise.

Vous pouvez également déléguer les configurations spécifiques aux dossiers à un service ou à des administrateurs de produit pour décentraliser l’administration.

À l’aide de la mosaïque Profils de dossier dans les paramètres des guides, vous pouvez configurer les paramètres sous les onglets suivants :

![](assets/folder-profile-tabs.png){width="800" align="left"}

- **Général**: l’onglet général n’est disponible que lorsque vous configurez les paramètres au niveau du dossier \(ou projet/produit\). Vous pouvez configurer des paramètres tels que les chemins d’accès aux dossiers auxquels les paramètres s’appliqueront et les utilisateurs qui auront les droits d’administration pour créer ou mettre à jour des configurations.

- **Attributs conditionnels**: utilisez cet onglet pour configurer les attributs conditionnels au niveau global ou au niveau du dossier. Un attribut conditionnel est une combinaison du nom et de la valeur de l’attribut, et vous pouvez également définir un libellé pour celui-ci. Vous pouvez utiliser les attributs DITA standard ou vos propres attributs personnalisés. Les attributs conditionnels que vous définissez au niveau global sont mis à la disposition de tous les utilisateurs dans l’ensemble des projets. Si vous avez défini des attributs conditionnels au niveau du dossier, ils sont fusionnés avec les attributs conditionnels définis globalement.

- **Modèles**: utilisez cet onglet pour configurer les modèles que vos auteurs utiliseront pour créer ou publier du contenu DITA. Les modèles de rubrique suivants sont disponibles prêts à l’emploi :

   - Glossaire

   - Référence

   - Thème

   - Concept

   - Tâche

   - Résolution des problèmes

   - Vide

   - DITAVAL

  >[!NOTE]
  >
  > Vous pouvez utiliser n’importe lequel des modèles existants comme base pour créer de nouveaux modèles. Le modèle DITA vierge ne contient aucune structure ni aucun élément comme les autres modèles. Vous pouvez utiliser n’importe quel modèle DITA prêt à l’emploi comme base, y apporter des modifications et l’enregistrer sous un autre nom. Après avoir apporté les modifications requises, ajoutez le modèle mis à jour à la configuration de modèles de création globale ou au niveau du dossier, puis rendez-le disponible pour la création.

  Avec les modèles de rubrique, vous pouvez également définir les modèles de mappage qui seront mis à la disposition des auteurs. Les modèles de mappage suivants sont disponibles prêts à l’emploi :

   - Map

   - Bookmap

- **Paramètre prédéfini de sortie**: à l’instar des modèles, il existe cinq paramètres prédéfinis de sortie préconfigurés :

   - AEM site

   - PDF

   - HTML5

   - EPUB

   - Personnalisé

  Les éditeurs peuvent utiliser ces paramètres prédéfinis de sortie prêts à l’emploi pour publier du contenu. Ces paramètres prédéfinis peuvent être configurés par un administrateur du profil global ou au niveau du dossier. Une fois configurés, les paramètres prédéfinis de publication sont disponibles pour les éditeurs pour les mappages DITA nouvellement créés. Vous pouvez également appliquer des paramètres prédéfinis de publication aux mappages DITA existants, voir [Appliquer les modifications prédéfinies](#id18AGD0K0OHS) pour plus d’informations.

- **Configurations de l’éditeur XML**: utilisez cet onglet pour personnaliser l’aspect et les différentes fonctionnalités de l’éditeur web. Les paramètres configurables suivants sont disponibles pour l’éditeur web :

   - Configuration de l’interface utilisateur de l’éditeur XML
   - Disposition du modèle CSS
   - Fragments de code de l’éditeur XML
   - Étiquettes de version de contenu XML
   - Rootmap \(uniquement au niveau du dossier\)

Vous pouvez configurer les deux profils : profil global et profil au niveau du dossier. Dans un profil de niveau dossier, vous pouvez définir les dossiers sur lesquels les paramètres seront applicables. Ces paramètres comprennent les attributs conditionnels, les modèles, les paramètres prédéfinis de sortie et les paramètres de l’éditeur XML. Les paramètres prédéfinis conditionnels, les modèles et les configurations de l’éditeur XML sont ensuite mis à la disposition des auteurs qui travaillent dans les dossiers configurés. De même, les éditeurs auront accès aux paramètres prédéfinis de sortie configurés définis dans les dossiers configurés.

Un profil au niveau du dossier remplace les paramètres configurés dans le profil global. En d’autres termes, si un dossier comporte un profil au niveau du dossier, il affichera les modèles, les modèles de sortie et les paramètres de l’éditeur XML configurés dans son profil de dossier correspondant. Il n’affichera pas les paramètres configurés dans le profil global. Toutefois, cela ne s’applique pas aux attributs conditionnels. Dans le cas d’attributs conditionnels, les attributs conditionnels sont fusionnés aux niveaux global et de dossier.

Les sections suivantes vous guident tout au long du processus de configuration des profils globaux et des profils au niveau du dossier.

## Configurer le profil global

Effectuez les étapes suivantes pour configurer le profil global :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et choisissez **Outils**.

1. Sélectionner **Guides** dans la liste des outils, puis cliquez sur l’icône **Profils de dossier**.

   Pour la première fois, la page Profils de dossier s’affiche avec uniquement la mosaïque Profil global .

   ![](assets/folder-profile-global.png){width="800" align="left"}

1. Cliquez sur le bouton **Profil global** mosaïque.

1. Pour configurer **Attributs conditionnels**, voir [Configuration d’attributs conditionnels pour les profils globaux ou au niveau du dossier](#id1889D0I305Z).

1. Pour configurer **Modèles**, voir [Configuration de modèles de création](#id1889D0IL0Y4).

1. Pour configurer **Paramètres prédéfinis de sortie**, voir [Configuration des paramètres prédéfinis de sortie](#id18AGD0IH0Y4).

1. Pour configurer la configuration de l’éditeur XML, voir [Configuration et personnalisation de l’éditeur Web XML](#id2065G300O5Z).

1. Après avoir effectué toutes les mises à jour requises, enregistrez et fermez la variable **Profil global**.


## Créer et configurer un profil au niveau du dossier

Effectuez les étapes suivantes pour configurer un profil au niveau du dossier :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et choisissez **Outils**.

1. Sélectionner **Guides** dans la liste des outils, puis cliquez sur le **Profils de dossier** mosaïque.

   Pour la première fois, la page Profils de dossier s’affiche avec la mosaïque Profil global par défaut uniquement.

1. Cliquez sur **Créer**.

   ![](assets/create-folder-profile.png){width="300" align="left"}

1. Saisissez les informations suivantes dans la variable **Créer un profil de dossier** dialog :
   - Nom du profil de dossier.
   - Chemin du dossier dans lequel le profil sera applicable.

     >[!NOTE]
     >
     > Vous ne pouvez pas appliquer plusieurs profils de dossier à un dossier. Assurez-vous que le dossier que vous sélectionnez ici ne comporte aucun autre profil. Si un dossier parent-enfant possède ses propres profils spécifiques, le dossier enfant utilise les configurations de son propre profil. Les configurations du dossier parent ne remplacent pas celles d’un dossier enfant.

1. Cliquez sur **Créer**.

   Une nouvelle mosaïque portant le nom du profil de dossier est créée dans la page Profils de dossier

1. Cliquez sur la mosaïque du profil de dossier à modifier.

   Un onglet Général avec le nom du profil de dossier et les informations de dossier configurées s’affiche.

1. Cliquez sur **Modifier** pour ajouter plusieurs dossiers et utilisateurs disposant d’un accès administratif pour modifier le profil de dossier.

   >[!NOTE]
   >
   > Les utilisateurs que vous ajoutez ici auront les droits d’administration pour mettre à jour les attributs conditionnels, les modèles et les paramètres prédéfinis de sortie configurés pour ce profil de dossiers.

1. Pour ajouter un dossier, cliquez sur l’icône Parcourir dans Chemin d’accès au dossier et sélectionnez un dossier, puis cliquez sur Ajouter pour ajouter le dossier à ce profil.

   >[!NOTE]
   >
   > Assurez-vous que le dossier que vous choisissez ici n’est associé à aucun autre profil au niveau du dossier.

1. Pour ajouter un utilisateur, sélectionnez-le dans le **Utilisateurs administrateurs** menu déroulant et clic **Ajouter**.

   >[!NOTE]
   >
   > Vous pouvez ajouter plusieurs utilisateurs au profil de dossiers à partir de la liste déroulante. Vous pouvez également supprimer un utilisateur administrateur existant de la liste en cliquant sur l’icône de suppression en regard de l’ID utilisateur.

1. Après avoir ajouté tous les dossiers et utilisateurs requis au profil de dossier, cliquez sur **Enregistrer**.


Vous êtes maintenant prêt à configurer les attributs conditionnels, les modèles, les paramètres prédéfinis de sortie et l’éditeur XML.

>[!IMPORTANT]
>
> Lorsque vous créez un profil de dossier, il ne contient par défaut aucun modèle. Vous devez ajouter les modèles requis dans le profil de dossier pour les rendre disponibles à vos auteurs.

## Configuration d’attributs conditionnels pour les profils globaux ou au niveau du dossier {#id1889D0I305Z}

Effectuez les étapes suivantes pour configurer les attributs conditionnels standard pris en charge par DITA au niveau global ou au niveau du dossier :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur ou que l’utilisateur disposant de droits d’administration sur un profil de niveau dossier.

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et choisissez **Outils**.

1. Sélectionner **Guides** dans la liste des outils, puis cliquez sur le **Profils de dossier** mosaïque.

1. Cliquez sur la mosaïque du profil que vous souhaitez configurer.

   >[!NOTE]
   >
   > Vous pouvez choisir de configurer des attributs conditionnels dans le profil global ou un profil au niveau du dossier.

1. Sur la page du profil, cliquez sur le **Attributs conditionnels** .

1. Cliquez sur **Modifier**.

1. Cliquez sur **Ajouter**.

1. Saisissez le **Nom**, **Valeur**, et a **Libellé** pour l’attribut conditionnel.

   Vous pouvez enregistrer un profil avec uniquement le nom de l’attribut. Cependant, un attribut ne peut être utilisé que s’il a une valeur qui lui est spécifiée. Si vous spécifiez à la fois la valeur et le libellé d’un attribut, l’éditeur web affiche le libellé de l’attribut conditionnel. En outre, le libellé s’affiche pour l’administrateur de publication au moment de la création d’un paramètre prédéfini conditionnel.

   La capture d’écran suivante montre la définition de la variable `platform` avec les valeurs et les libellés possibles.

   ![](assets/add_profile.png)

1. Si vous souhaitez ajouter d’autres valeurs pour le même attribut, cliquez sur le bouton **+** et saisissez la valeur et le libellé supplémentaires.

1. Pour ajouter d’autres attributs, cliquez sur **Ajouter**.

1. Cliquez sur **Enregistrer**.


Si vous utilisez un attribut personnalisé, il doit s’agir d’un attribut DITA valide pris en charge par la DTD. Si vous souhaitez utiliser un attribut, qui n’est pas un attribut DITA standard, effectuez les étapes supplémentaires suivantes :

1. Ajoutez l’attribut personnalisé au fichier DTD. Par exemple, si votre fichier DTD est commonElements.mod, vous devez le localiser dans le répertoire DTD. Le chemin par défaut du fichier DTD système est le suivant :

   /libs/fmdita/dita\_resources/DITA-1.3/dtd/base/dtd/commonElements.mod

   >[!IMPORTANT]
   >
   > Le fichier DTD spécialisé doit faire partie du déploiement de code personnalisé. Les DTD sous /apps font partie du déploiement du produit et sont donc remplacées par l’installation de toute nouvelle version. Il est recommandé d’ajouter une DTD spécialisée sous /var/dxml/dita\_resources dans le dossier du projet et d’inclure le chemin DTD/catalogue dans le profil DITA. Pour plus d’informations, voir [Intégration de la spécialisation DITA](dita-ot-specialization.md#id211MB0E00XA).

1. Utilisez le gestionnaire de modules pour télécharger le fichier /libs/fmdita/config/condAttrList.xml :

1. Créez une copie du fichier condAttrList.xml à l’emplacement suivant dans le référentiel Git de Cloud Manager :

   `/apps/fmdfmdita/config/condAttrList.xml`

1. Enregistrez le fichier.

1. Ajoutez des attributs personnalisés au profil global ou au niveau du dossier.


## Configurer des modèles {#id1889D0IL0Y4}

AEM Guides est fourni avec 7 modèles de rubrique prêts à l’emploi, 2 modèles de mappage DITA et 3 modèles de PDF. Vous pouvez choisir de n’avoir que quelques modèles disponibles pour les auteurs et les éditeurs. Si vous utilisez un modèle personnalisé, celui-ci peut être configuré et rendu disponible pour la création et la publication. Vous utilisez la variable **Modèles** dans la configuration Profils de dossier pour ajouter ou supprimer des modèles de rubrique, de mappage ou de PDF de profils globaux ou de niveau dossier.

Avant même de configurer les modèles de rubrique, de mappage ou de PDF au niveau global ou au niveau du dossier, vous pouvez également définir un emplacement pour stocker vos modèles personnalisés. Pour configurer un emplacement personnalisé pour stocker les modèles, reportez-vous à la section [Configuration du chemin d’accès au dossier de modèle DITA personnalisé](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z).

Effectuez les étapes suivantes pour ajouter des modèles de rubrique, de mappage ou de PDF à un profil de dossier :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur ou que l’utilisateur disposant de droits d’administration sur un profil de niveau dossier.

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et choisissez **Outils**.

1. Sélectionner **Guides** dans la liste des outils, puis cliquez sur le **Profils de dossier** mosaïque.

1. Cliquez sur la mosaïque du profil que vous souhaitez configurer.

   >[!NOTE]
   >
   > Vous pouvez choisir de configurer un modèle dans le profil global ou un profil au niveau du dossier.

1. Sur la page du profil, cliquez sur le **Modèles** .
1. Cliquez sur **Modifier**.

   Vous avez la possibilité d’ajouter des modèles de rubrique, de carte et de PDF en effectuant des recherches à partir de l’emplacement par défaut ou en le recherchant.

   >[!NOTE]
   >
   > Par défaut, tous les modèles sont stockés dans le dossier /content/dam/dita-templates . La variable `dita-templates` Le dossier contient `topics`, `maps`, et `PDF` sous-dossiers pour stocker la rubrique, le mappage et les modèles de PDF. Vous pouvez ajouter vos modèles personnalisés \(.dita,.xml ou .ditamapfiles\) dans les dossiers de modèles par défaut. Une fois que vous avez ajouté votre modèle dans le dossier par défaut, vous pouvez le faire dans le profil global ou de dossier. Pour plus d’informations sur la création de modèles personnalisés à l’aide de l’éditeur web, voir [Créer un modèle de création personnalisé](#id1917D0EG0HJ).

   ![](assets/search-author-temp.png){width="800" align="left"}

1. Ajoutez la rubrique, le mappage et les modèles de PDF requis à votre profil.

   Pour ajouter un modèle, effectuez l’une des opérations suivantes :

   - Choisir **Recherche ou type** et saisissez ou sélectionnez le nom d’un modèle dans la liste déroulante. La liste déroulante se compose de tous les modèles par défaut et de tout nouveau modèle que vous avez créé.

     ![](assets/default-template-list.png){width="800" align="left"}

   - Cliquez sur **Parcourir** et sélectionnez un modèle dans DAM.

1. Cliquez sur **Ajouter**.

   Les modèles sélectionnés sont ajoutés à la liste des modèles.

   ![](assets/author-templ-added-list.png){width="800" align="left"}

   >[!NOTE]
   >
   > Vous pouvez modifier l’ordre des modèles en les faisant glisser et en les déposant à l’emplacement souhaité dans la liste. La position des modèles contrôle l’ordre dans lequel ils s’affichent dans la page Plan directeur du workflow de création de rubrique ou de mappage.

1. Pour définir les règles de traduction, parcourez l’emplacement SRX pour trouver le dossier contenant les fichiers SRX. Le format SRX \(exchange de règles de segmentation\) est une norme d’échange de règles de segmentation entre différents utilisateurs et différents environnements de traduction. Vous pouvez créer un dossier et y ajouter vos fichiers SRX personnalisés.

   Une fois que vous avez créé le dossier contenant les fichiers SRX, vous pouvez ajouter le chemin du dossier dans le dossier **Emplacement de traduction SRX** dans votre profil de dossiers.

   AEM Guides sélectionne les règles SRX en fonction de la langue source du projet de traduction. Il recherche un fichier SRX personnalisé pour une langue. Si vous ne définissez pas de fichier SRX personnalisé, il sélectionne les règles conformément aux règles de traduction prêtes à l’emploi.

1. Cliquez sur **Enregistrer**.


Si vous avez configuré les modèles sur un profil au niveau du dossier, les modèles configurés sont associés au dossier configuré. Tous les projets créés sous le dossier configuré auront accès uniquement aux modèles configurés sous le profil au niveau du dossier.

## Créer un modèle de création personnalisé {#id1917D0EG0HJ}

AEM Guides permet de créer facilement des modèles de création. En tant qu’administrateur système, vous pouvez utiliser l’éditeur web pour créer des modèles entièrement nouveaux. Vous pouvez ensuite ajouter le nouveau modèle dans le profil global ou l’affecter à un dossier spécifique à l’aide du profil spécifique au dossier.

Pour créer un modèle de création personnalisé, procédez comme suit :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Dans l’interface utilisateur d’Assets, accédez au dossier configuré pour stocker les fichiers de modèle. Par défaut, tous les modèles de rubrique sont stockés dans le dossier /content/dam/dita-templates/topics .

   >[!NOTE]
   >
   > Pour configurer un emplacement personnalisé pour stocker des modèles de rubrique ou de mappage, voir [Configuration du chemin d’accès au dossier de modèle DITA personnalisé](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z)

1. Cliquez sur **Créer** \> **Modèle DITA**.

1. Sur la page Plan directeur, sélectionnez le type de modèle de rubrique DITA que vous souhaitez créer.

   >[!NOTE]
   >
   > Vous pouvez utiliser le modèle vierge pour partir de zéro. Le modèle vierge ne contient aucune structure ni aucun élément.

1. Cliquez sur **Suivant**.

1. Sur la nouvelle page Propriétés du modèle, saisissez une **Titre**, **Nom**, et **Description** pour le modèle.

   >[!NOTE]
   >
   > Le nom est automatiquement proposé en fonction du titre de votre modèle. Si vous souhaitez spécifier manuellement le nom, assurez-vous que le nom ne contient aucun espace, apostrophe ou accolades et qu’il se termine par .dita.

1. *\(Facultatif\)* Cliquez sur le bouton **Ajout d’une miniature** pour naviguer et sélectionner une miniature à associer à votre modèle.

1. Cliquez sur **Créer**.

   Le message Rubrique créée s’affiche.

   Vous pouvez choisir d’ouvrir le modèle à modifier dans l’éditeur Web ou d’enregistrer le fichier dans l’emplacement de stockage du modèle. Une fois le modèle créé, vous pouvez utiliser l’éditeur Web pour le personnaliser selon vos besoins de création. Une fois qu’un modèle est en place, veillez à l’associer à un profil global ou de niveau dossier.


## Configuration des paramètres prédéfinis de sortie {#id18AGD0IH0Y4}

Dans une configuration d’entreprise classique, différents modèles de sortie peuvent être utilisés pour différents produits ou guides d’utilisation. En outre, certains processus de génération de sortie courants pourraient être utilisés par tous les éditeurs et un ensemble de processus de génération de sortie spécifiques pour un groupe spécifique d’éditeurs ou de projets.

AEM Guides permet à l’administrateur de créer des paramètres prédéfinis de sortie avec des paramètres spécifiques qui peuvent ensuite être utilisés par tous les éditeurs ou un ensemble spécifique d’éditeurs pour générer la sortie. Par exemple, l’administrateur peut créer un paramètre prédéfini de sortie afin de générer un guide de l’utilisateur commun à tous les éditeurs. Et une autre pour créer les manuels d’utilisation de la programmation qui sont spécifiques à un ensemble d’éditeurs. Ces deux paramètres prédéfinis peuvent être configurés pour utiliser différents modèles de sortie. Dans cet exemple, le paramètre prédéfini de publication commun pour la génération du guide de l’utilisateur peut être configuré au niveau global. De plus, le paramètre prédéfini de sortie pour la génération du manuel d’utilisation de la programmation peut être configuré au niveau du dossier.

Une fois que les paramètres prédéfinis de sortie par défaut ont été créés dans le système, tous les paramètres prédéfinis DITA créés par la suite utilisent les paramètres prédéfinis par défaut pour générer la sortie. Cependant, tous les mappages DITA existants continueraient à utiliser les paramètres prédéfinis de sortie qui avaient été configurés auparavant avec eux. Si vous souhaitez appliquer le nouveau paramètre prédéfini de sortie sur tous les mappages DITA existants, vous devez exécuter le workflow Appliquer les modifications prédéfinies .

Outre les paramètres prédéfinis configurés au niveau global ou au niveau de l’entreprise, un éditeur aurait toujours les droits de créer d’autres paramètres prédéfinis de sortie. Cependant, ces paramètres prédéfinis sont liés au mappage DITA pour lequel ils sont créés. Pour plus d’informations sur la création de paramètres prédéfinis de sortie standard pour un mappage DITA, voir *Créer, modifier, dupliquer ou supprimer un paramètre prédéfini de sortie* dans le guide d’utilisation des guides Adobe Experience Manager as a Cloud Service.

Effectuez les étapes suivantes pour configurer des paramètres prédéfinis de sortie globaux ou spécifiques à un dossier :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur ou l’utilisateur disposant de droits d’administration sur un profil spécifique au dossier.

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et choisissez **Outils**.

1. Sélectionner **Guides** dans la liste des outils, puis cliquez sur le **Profils de dossier** mosaïque.

1. Cliquez sur la mosaïque du profil que vous souhaitez configurer.

   >[!NOTE]
   >
   > Vous pouvez choisir de configurer des paramètres prédéfinis de sortie dans le profil global ou un profil spécifique au dossier.

1. Sur la page du profil. cliquez sur le bouton **Paramètres prédéfinis de sortie** .

   Une liste des paramètres prédéfinis de sortie prêts à l’emploi s’affiche, qui comprend AEM Site, PDF, HTML5, EPUB et PERSONNALISÉ.

1. Pour créer ou modifier un paramètre prédéfini de sortie, effectuez l’une des opérations suivantes :

   - Cliquez sur **Créer** pour créer un nouveau paramètre prédéfini de sortie à partir de zéro.
   - Cliquez sur Dupliquer pour créer une copie du paramètre prédéfini de sortie sélectionné. Vous pouvez apporter des modifications au paramètre prédéfini dupliqué et l’enregistrer.

   - Cliquez sur **Modifier** pour ouvrir la configuration du paramètre prédéfini sélectionné à des fins de modification.

     Pour plus d’informations sur les paramètres prédéfinis de sortie, voir *Présentation des paramètres prédéfinis de sortie* dans le guide d’utilisation des guides Adobe Experience Manager as a Cloud Service.

1. Cliquez sur **Enregistrer** pour enregistrer les paramètres prédéfinis.


Tous les mappages DITA créés ou chargés par la suite auront le nouveau paramètre prédéfini de sortie ou mis à jour.

## Appliquer les modifications prédéfinies {#id18AGD0K0OHS}

Un nouveau paramètre prédéfini de sortie créé au niveau global est mis à la disposition de tous les nouveaux mappages DITA que vous créez à l’avenir. De même, si un nouveau paramètre prédéfini de sortie est créé au niveau du dossier, ce paramètre prédéfini est mis à la disposition de tous les mappages qui seront créés dans le dossier configuré. Par défaut, un nouveau paramètre prédéfini de sortie n’est rendu disponible pour aucun mappage DITA existant.

Si vous avez mis à jour un paramètre prédéfini de sortie existant ou si vous souhaitez rendre un nouveau paramètre prédéfini de sortie disponible pour les mappages DITA existants, effectuez les étapes suivantes :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur ou l’utilisateur disposant de droits d’administration sur un profil spécifique au dossier.

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et choisissez **Outils**.

1. Sélectionner **Guides** dans la liste des outils, puis cliquez sur le **Profils de dossier** mosaïque.

1. Cliquez sur la mosaïque du profil que vous souhaitez configurer.

   >[!NOTE]
   >
   > Vous pouvez choisir de configurer des paramètres prédéfinis de sortie dans le profil global ou un profil spécifique au dossier.

1. Sur la page du profil. cliquez sur le bouton **Paramètres prédéfinis de sortie** .

   Une liste des paramètres prédéfinis de sortie prêts à l’emploi s’affiche, qui comprend AEM Site, PDF, HTML5, EPUB et PERSONNALISÉ.

1. Sélectionnez le paramètre prédéfini de sortie à appliquer aux mappages DITA existants.

1. Cliquez sur **Appliquer les modifications prédéfinies** dans la barre d’outils principale.

1. Dans la boîte de dialogue Appliquer les modifications prédéfinies , vous pouvez choisir parmi les options suivantes :

   - **Sélection de l’option Remplacer les paramètres prédéfinis existants**: si vous sélectionnez cette option, toutes les mises à jour effectuées dans les paramètres prédéfinis de sortie existants remplaceront les paramètres de toutes les cartes DITA existantes dans lesquelles ce paramètre prédéfini est utilisé. Toutefois, cela entraînera la perte de tout paramètre prédéfini conditionnel et des informations de base existants associés à la carte.

   - **Pas de sélection de l’option Remplacer les paramètres prédéfinis existants**: si vous ne sélectionnez pas cette option, les mises à jour que vous avez effectuées dans les paramètres prédéfinis de sortie existants n’auront aucune incidence sur les mappages DITA existants. Seuls les nouveaux paramètres prédéfinis ajoutés sont ajoutés aux mappages DITA existants. Notez que le nouveau mappage DITA est obtenu à la fois : les paramètres prédéfinis de sortie mis à jour et les paramètres prédéfinis nouvellement ajoutés.

1. Cliquez sur **OK** pour appliquer les modifications des paramètres prédéfinis de sortie sélectionnés sur tous les mappages DITA existants.



## Configuration des suggestions intelligentes optimisées par l’IA dans l’éditeur web {#conf-ai-smart-suggestions}

Pour ![AEM cloud ](assets/aem-cloud-icon.svg) Guides du Experience Manager as a Cloud Service .

Vous pouvez configurer les suggestions intelligentes optimisées par l’IA et aider les auteurs à réutiliser le contenu existant et à créer facilement des références de contenu correctes et cohérentes. La variable **Configuration de l’IA** vous permet de contrôler les paramètres du panneau Suggestions intelligentes dans l’éditeur web.

Effectuez les étapes suivantes pour configurer la configuration standard de l’IA au niveau du profil global ou au niveau du dossier :
1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur ou utilisateur disposant de droits d’administration sur un profil de niveau dossier.
1. Sélectionnez la variable **Adobe Experience Manager** lien dans la partie supérieure et choisissez **Outils**.
1. Sélectionner **Guides** dans la liste des outils, puis sélectionnez l’option **Profils de dossier** mosaïque.
1. Sélectionnez la mosaïque de profil que vous souhaitez configurer.

   >[!NOTE]
   >
   >Vous pouvez configurer des suggestions intelligentes basées sur l’IA sur le profil global ou au niveau du dossier.

1. Sur la page du profil, sélectionnez la variable **Configuration de l’IA** .
   ![Onglet de configuration AI dans le profil global](assets/global-profile-AI-configuration-cs.png) {width="800" align="left"}

1. Cliquez sur **Modifier**.
1. En tant qu’administrateur, vous pouvez configurer les paramètres suivants :

   **Caractères minimum**: saisissez le nombre minimum de caractères que les auteurs doivent saisir pour obtenir les suggestions. Par exemple, si ce nombre est de 7, l’auteur doit ajouter au moins 7 caractères pour afficher une suggestion dynamique.

   **Suggestions maximales**: saisissez le nombre maximal de suggestions que les auteurs peuvent obtenir lors de la création du contenu. Par exemple, si ce nombre est de 5, l’auteur peut afficher cinq suggestions intelligentes ou moins.

   **Fichiers et dossiers**: sélectionnez les fichiers ou les dossiers à partir desquels les suggestions intelligentes doivent s’afficher. *Pour assurer la cohérence du contenu, il est recommandé qu’aucune des deux entrées de la liste ne comporte de fichiers communs.*. Une fois que vous avez sélectionné les fichiers et les dossiers, ils sont répertoriés.

1. Cliquez sur **Enregistrer**.

   >[!NOTE]
   >
   > Les derniers détails d’état indexé s’affichent en haut après l’enregistrement du fichier.

En savoir plus sur l’affichage et l’ajout de [Suggestions intelligentes basées sur l’IA](../user-guide/authoring-ai-based-smart-suggestions.md) pour ajouter des références de contenu lors de la création dans l’éditeur web.




<!--## Configure AI-powered Guides Assistant in the Web Editor {#conf-ai-guides-assistant}

For ![AEM cloud ](assets/aem-cloud-icon.svg) Experience Manager Guides as a Cloud Service.

You can configure the AI-powered **Guides Assistant** to help the authors ask questions and easily find the required content from the [ Experience Manager Guides Documentation](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/overview).

The **XML Editor Configuration** tab allows you to configure the default questions of the **Guides Assistant panel** in the Web Editor.

>[!NOTE]
>
>You can configure up to 10 default questions. 

Perform the following steps to configure the default questions:

1. Log into Adobe Experience Manager as an administrator or user with administrative rights on a folder-level profile.
1. Select the **Adobe Experience Manager** link at the top and choose **Tools**.
1. Select **Guides** from the list of tools and select the **Folder Profiles** tile.
1. Select the profile tile that you want to configure.

    >[!NOTE]
    >
    >You can configure default questions for the **Guides assistant panel** to the global or a folder-level profile.

1.  Select the **XML Editor Configuration** tab. 

1. Click the **Edit** icon on the top.
1.  In the **XML Editor UI configuration** section, select the **Download** icon to download the `ui_config.json` file on your local system.
1.  In the `ui_config.json` file, add the sample questions.

    **Example of sample questions**:

    ```json
    "assistantSampleQuestions": [
    "How to create a new topic",
    "How to create a new map",
    "What is a baseline" ]
    ```

1. Save the file and upload it.

    >[!NOTE]
    >
    > The default questions appear in the **Guides assistant** panel after you save the file. 


Learn more about using the [AI-powered Guides assistant](../user-guide/ai-based-guides-assistant.md) to find the required content from the Experience Manager Guides documentation. -->


## Configuration et personnalisation de l’éditeur Web XML {#id2065G300O5Z}

Par défaut, l’éditeur Web XML est fourni avec de nombreuses fonctionnalités pour aider les auteurs à créer des documents DITA. Si vous travaillez dans un environnement restrictif, vous pouvez choisir les fonctionnalités qui sont exposées à vos auteurs. L’onglet Configuration de l’éditeur XML vous permet de contrôler facilement les fonctionnalités et de modifier l’aspect de votre éditeur Web. En tant qu’administrateur, vous pouvez personnaliser les composants suivants de l’éditeur web :

**Configuration de l’interface utilisateur de l’éditeur XML**

Ce paramètre contrôle la barre d’outils et les autres éléments de l’interface utilisateur de l’éditeur web. Cliquez sur l’icône Télécharger pour télécharger le fichier ui\_config.json sur votre système local. Vous pouvez ensuite apporter des modifications au fichier et charger le même. Selon l’emplacement où vous chargez le fichier au niveau du profil, global ou de dossier, les modifications sont appliquées en conséquence. Pour plus d’informations sur la personnalisation de l’éditeur XML à l’aide du fichier ui\_config.json, voir [Barre d’outils Personnaliser](conf-web-editor-customize-toolbar.md#).

**Disposition du modèle CSS**

Téléchargez le fichier disponible dans cette section pour personnaliser l’aspect du document lorsqu’il est prévisualisé ou ouvert pour modification dans l’éditeur web. Le fichier CSS par défaut disponible au téléchargement n’est qu’un fichier test, qui ne doit pas être utilisé pour la personnalisation. Vous pouvez créer un fichier CSS avec des personnalisations pour l’éditeur Web et charger le même fichier. Par exemple, vous pouvez créer un fichier .css avec le code suivant :

```
.title {    font-size: 9em;}
```

Enregistrez ce fichier et téléchargez-le dans la section Mise en page du modèle CSS . La prochaine fois que vous téléchargerez le fichier, vous obtiendrez le dernier fichier CSS utilisé dans l’éditeur web.

**Fragments de code de l’éditeur XML**

À l’aide du fichier de configuration de cette section, vous pouvez créer des fragments de code par défaut et les partager avec vos auteurs. La structure par défaut du fichier est présentée ci-dessous :

```
{
   "snippetID": {
      "name": "snippet Name",
      "description": "snippet Description",
      "value": "<i>this is snippet value</i>"
  }
}
```

Les détails suivants sont requis pour créer un fragment de code :

snippetID : identifiant unique du fragment de code. Il peut s’agir d’une valeur alphanumérique.

name : nom descriptif pour identifier le fragment de code. Ce nom apparaît dans le panneau Fragments de code.

description : ajoutez une information descriptive pour le fragment de code.

value : saisissez le code XML du fragment de code.

>[!NOTE]
>
> Vous pouvez ajouter d’autres fragments de code en ajoutant une virgule \(,\) à la fin de votre définition de fragment de code et en répétant la même structure pour le fragment de code suivant.

**Étiquettes de version de contenu XML**

Par défaut, les auteurs sont autorisés à créer des libellés de leur choix et à les associer à leurs fichiers de rubrique. Cependant, cela peut entraîner de nombreuses variantes d’une même étiquette, par exemple, il peut y avoir des étiquettes &quot;Version 1.0&quot;, &quot;Version 1.0&quot;, &quot;Version 1&quot; pour identifier la même étape d’une rubrique. Pour éviter des libellés aussi incohérents dans le système, vous pouvez créer une liste prédéfinie d’libellés dans laquelle les auteurs pourront effectuer leur choix. L’utilisation d’étiquettes cohérentes facilite la gestion des fichiers dans votre système.

À l’aide de la configuration des étiquettes de version, vous pouvez charger une liste d’étiquettes valides pour votre organisation. Téléchargez le fichier label.json par défaut et modifiez-le comme illustré ci-dessous :

```
{
"label1":"Draft",
"label2":"PM-Review",
"label3":"Engg-Review",
"label4":"QE-Review",
"label5":"Ready for Loc",
"label6":"Ready for Publish"
}
```

Dans l’exemple ci-dessus, &quot;label1&quot; est l’identifiant de la séquence d’étiquettes et il est ajouté par le libellé qui s’affiche pour les auteurs lorsqu’une étiquette est requise. Enregistrez ce fichier et téléchargez-le dans la section Libellés de version du contenu XML .

>[!IMPORTANT]
>
> Pour que les configurations au niveau du dossier prennent effet, les utilisateurs doivent sélectionner le profil sous leurs préférences utilisateur dans l’éditeur web.

**Rootmap**

Si vos auteurs travaillent sur une carte racine spécifique, vous pouvez rechercher et sélectionner cette carte racine ici. Notez que vous ne pouvez définir le rootmap que pour un profil au niveau du dossier.
