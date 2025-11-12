---
title: Configuration de profils globaux ou au niveau du dossier
description: Découvrez comment configurer des profils globaux ou au niveau du dossier
exl-id: 19f63d67-89ef-4c5e-bc9a-cf40dd8d7979
feature: Profiles
role: Admin
level: Experienced
source-git-commit: 1ea27a0ca99e61049d08f89a0cf5e0584b38edae
workflow-type: tm+mt
source-wordcount: '5127'
ht-degree: 0%

---

# Configuration de profils globaux ou au niveau du dossier {#id181AH2003PF}

Dans une entreprise, différents groupes ou produits peuvent utiliser différents modèles de création, modèles de sortie, profils d’attributs conditionnels \(ou schémas d’objet\) et configurations de l’éditeur web. Leur configuration uniquement au niveau de l’entreprise \(ou global\) peut rendre l’expérience des auteurs difficile, car ils verront des modèles ou des profils qui ne les concernent pas.

AEM Guides vous permet de configurer les modèles de création \(rubrique ou mappage\), les modèles de sortie, les attributs conditionnels et les configurations de l’éditeur web au niveau de l’entreprise \(global\) ainsi qu’au niveau des dossiers. Vous pouvez ainsi séparer les configurations pour différents services ou produits de votre entreprise.

Vous pouvez également déléguer les configurations spécifiques aux dossiers à un service ou à des administrateurs de produit afin de décentraliser l’administration.

À l’aide de la mosaïque Profils de dossier dans les paramètres Guides, vous pouvez configurer les paramètres dans les onglets suivants :

![](assets/folder-profile-tabs.png){width="800" align="left"}

- **Général** : l’onglet général n’est disponible que lorsque vous configurez des paramètres \(ou projet/produit\) au niveau du dossier. Vous pouvez configurer des paramètres tels que les chemins d’accès aux dossiers sur lesquels les paramètres seront applicables et les utilisateurs disposant de droits d’administration pour créer ou mettre à jour des configurations.

- **Attributs conditionnels** : utilisez cet onglet pour configurer des attributs conditionnels au niveau global ou du dossier. Un attribut conditionnel est une combinaison du nom et de la valeur de l’attribut et vous pouvez également définir un libellé pour celui-ci. Vous pouvez utiliser les attributs DITA standard ou vos propres attributs personnalisés. Les attributs conditionnels que vous définissez au niveau global sont mis à la disposition de tous les utilisateurs dans les projets. Si vous avez défini des attributs conditionnels au niveau du dossier, ils sont fusionnés avec les attributs conditionnels définis globalement.

- **Modèles** : utilisez cet onglet pour configurer les modèles que vos auteurs utiliseront pour créer ou publier du contenu DITA. Les modèles de rubrique suivants sont disponibles prêts à l’emploi :

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
  > Vous pouvez utiliser n’importe quel modèle existant comme base pour créer de nouveaux modèles. Le modèle DITA vierge ne contient aucune structure ni aucun élément comme les autres modèles. Vous pouvez utiliser n&#39;importe quel modèle DITA prêt à l&#39;emploi comme base, y apporter des modifications et l&#39;enregistrer sous un autre nom. Après avoir apporté les modifications requises, ajoutez le modèle mis à jour à la configuration des modèles de création globale ou au niveau du dossier, puis il devient disponible pour la création.

  Outre les modèles de rubrique, vous pouvez également définir les modèles de carte qui seront mis à la disposition des auteurs. Les modèles de carte suivants sont disponibles prêts à l’emploi :

   - Map

   - Carte Graphique

- **Paramètre prédéfini de sortie** : comme pour les modèles, il existe cinq paramètres prédéfinis de sortie préconfigurés :

   - Site AEM

   - PDF

   - HTML5

   - EPUB

   - Personnalisé

  Les éditeurs peuvent utiliser ces paramètres prédéfinis de sortie prêts à l’emploi pour publier du contenu. Ces paramètres prédéfinis peuvent être configurés par un administrateur du profil global ou au niveau du dossier. Une fois configurés, les paramètres prédéfinis de publication sont mis à la disposition des éditeurs pour les nouveaux plans DITA. Vous pouvez également appliquer des paramètres prédéfinis de publication à des plans DITA existants. Pour plus d&#39;informations, voir [Appliquer les modifications de paramètres prédéfinis](#id18AGD0K0OHS).

- **Configurations de l’éditeur XML** : utilisez cet onglet pour personnaliser l’aspect et les différentes fonctionnalités de l’éditeur web. Les paramètres configurables suivants sont disponibles pour l’éditeur web :

   - Configuration de l’interface utilisateur de l’éditeur XML
   - Mise en page de l’éditeur XML
   - Configuration de l’éditeur XML
   - Disposition du modèle CSS
   - Fragments de code de l’éditeur XML
   - Étiquettes de version du contenu XML
   - Rootmap \(uniquement au niveau du dossier\)

Vous pouvez configurer les deux types de profil : profil global et profil au niveau du dossier. Dans un profil au niveau du dossier, vous pouvez définir les dossiers auxquels les paramètres seront applicables. Ces paramètres incluent les attributs conditionnels, les modèles, les paramètres prédéfinis de sortie et les paramètres de l’éditeur XML. Les paramètres prédéfinis conditionnels, les modèles et les configurations de l’éditeur XML sont ensuite mis à la disposition des auteurs qui travaillent dans les dossiers configurés. De même, les éditeurs auront accès aux paramètres prédéfinis de sortie configurés dans les dossiers configurés.

Un profil au niveau du dossier remplace les paramètres configurés dans le profil global. En d’autres termes, si un dossier possède un profil au niveau du dossier, il affichera les modèles, les modèles de sortie et les paramètres de l’éditeur XML configurés dans son profil de dossier correspondant. Les paramètres configurés dans le profil global ne s’affichent pas. Toutefois, cela ne s’applique pas aux attributs conditionnels. Dans le cas d’attributs conditionnels, les attributs conditionnels sont fusionnés au niveau global et au niveau du dossier.

Les sections suivantes vous guident tout au long du processus de configuration des profils globaux et des profils au niveau des dossiers.

## Configurer le profil global

Pour configurer le profil global, procédez comme suit :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils, puis cliquez sur la mosaïque **Profils de dossier**.

   Pour la première fois, la page Profils de dossier s’affiche avec uniquement la mosaïque Profil global .

   ![](assets/folder-profile-global.png){width="800" align="left"}

1. Cliquez sur la mosaïque **Profil global**.

1. Pour configurer les **attributs conditionnels**, voir [Configurer des attributs conditionnels pour les profils globaux ou au niveau du dossier](#id1889D0I305Z).

1. Pour configurer **Modèles**, voir [Configurer des modèles de création](#id1889D0IL0Y4).

1. Pour configurer **paramètres prédéfinis de sortie**, voir [Configuration des paramètres prédéfinis de sortie](#id18AGD0IH0Y4).

1. Pour configurer la configuration de l’éditeur XML, voir [Configuration et personnalisation de l’éditeur XML](#id2065G300O5Z).

1. Après avoir effectué toutes les mises à jour requises, enregistrez et fermez le **profil global**.


## Création et configuration d’un profil au niveau du dossier

Pour configurer un profil au niveau du dossier, procédez comme suit :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils, puis cliquez sur la mosaïque **Profils de dossier**.

   Pour la première fois, la page Profils de dossier s’affiche avec la mosaïque Profil global par défaut uniquement.

1. Cliquez sur **Créer**.

   ![](assets/create-folder-profile.png){width="300" align="left"}

1. Saisissez les informations suivantes dans la boîte de dialogue **Créer un profil de dossier** :
   - Nom du profil de dossier.
   - Chemin d’accès au dossier auquel le profil sera applicable.

     >[!NOTE]
     >
     > Vous ne pouvez pas appliquer plusieurs profils de dossier à un dossier. Assurez-vous qu’aucun autre profil n’est appliqué au dossier que vous sélectionnez ici. Dans le cas d’un dossier parent-enfant ayant ses propres profils spécifiques, le dossier enfant utilisera les configurations de son propre profil. Les configurations du dossier parent ne remplacent pas celles d’un dossier enfant.

1. Cliquez sur **Créer**.

   Une nouvelle mosaïque portant le nom du profil de dossier est créée dans la page Profils de dossier

1. Cliquez sur la mosaïque du profil de dossier à modifier.

   Un onglet Général contenant le nom du profil de dossier et les informations sur le dossier configuré s’affiche.

1. Cliquez sur **Modifier** pour ajouter plusieurs dossiers et utilisateurs disposant d’un accès administratif afin de modifier le profil de dossier.

   >[!NOTE]
   >
   > Les utilisateurs que vous ajoutez ici disposeront des droits d’administration pour mettre à jour les attributs conditionnels, les modèles et les paramètres prédéfinis de sortie configurés pour ce profil de dossier.

1. Pour ajouter un dossier, cliquez sur l’icône Parcourir dans le Chemin du dossier et accédez à un dossier, sélectionnez-le, puis cliquez sur Ajouter pour ajouter le dossier à ce profil.

   >[!NOTE]
   >
   > Assurez-vous que le dossier que vous choisissez ici n’est associé à aucun autre profil au niveau du dossier.

1. Pour ajouter un utilisateur, sélectionnez-le dans la liste déroulante **Utilisateurs administrateurs**, puis cliquez sur **Ajouter**.

   >[!NOTE]
   >
   > Vous pouvez ajouter plusieurs utilisateurs au profil du dossier dans la liste déroulante. Vous pouvez également supprimer un utilisateur administrateur existant de la liste en cliquant sur l’icône de suppression en regard de l’ID d’utilisateur.

1. Après avoir ajouté tous les dossiers et utilisateurs requis au profil de dossier, cliquez sur **Enregistrer**.


Vous êtes maintenant prêt à configurer les attributs conditionnels, les modèles, les paramètres prédéfinis de sortie et l’éditeur XML.

>[!IMPORTANT]
>
> Lorsque vous créez un profil de dossier, il ne contient par défaut aucun modèle. Vous devez ajouter les modèles requis dans le profil de dossier pour les rendre disponibles pour vos auteurs.

## Configurer des attributs conditionnels pour les profils globaux ou au niveau du dossier {#id1889D0I305Z}

Pour configurer les attributs conditionnels standard pris en charge par DITA au niveau global ou du dossier, procédez comme suit :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur ou en tant qu’utilisateur disposant de droits d’administration sur un profil au niveau du dossier.

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils, puis cliquez sur la mosaïque **Profils de dossier**.

1. Cliquez sur la mosaïque de profil que vous souhaitez configurer.

   >[!NOTE]
   >
   > Vous pouvez choisir de configurer des attributs conditionnels dans le profil global ou un profil au niveau du dossier.

1. Sur la page du profil, cliquez sur l’onglet **Attributs conditionnels**.

1. Cliquez sur **Modifier**.

1. Cliquez sur **Ajouter**.

1. Saisissez les **Nom**, **Valeur** et un **Libellé** pour l’attribut conditionnel.

   Vous pouvez enregistrer un profil avec uniquement le nom d’attribut. Cependant, un attribut ne peut être utilisé que lorsqu’une valeur lui est spécifiée. Si vous spécifiez à la fois - valeur et libellé pour un attribut, l’éditeur web affiche le libellé de l’attribut conditionnel. En outre, le libellé est présenté à l’administrateur de publication au moment de la création d’un paramètre prédéfini conditionnel.

   La capture d’écran suivante montre la définition de l’attribut `platform` avec les valeurs et libellés possibles.

   ![](assets/add_profile.png)

1. Si vous souhaitez ajouter d’autres valeurs pour le même attribut, cliquez sur l’icône **+** et saisissez la valeur et le libellé supplémentaires.

1. Si vous souhaitez ajouter d’autres attributs, cliquez sur **Ajouter**.

1. Cliquez sur **Enregistrer**.


Si vous utilisez un attribut personnalisé, il doit s&#39;agir d&#39;un attribut DITA valide pris en charge par la DTD. Si vous souhaitez utiliser un attribut qui n&#39;est pas un attribut DITA standard, effectuez les étapes supplémentaires suivantes :

1. Ajoutez l’attribut personnalisé au fichier DTD. Par exemple, si votre fichier DTD est commonElements.mod, vous devez localiser ce fichier dans le répertoire DTD. Le chemin d&#39;accès par défaut du fichier DTD système est :

   /libs/fmdita/dita\_resources/DITA-1.3/dtd/base/dtd/commonElements.mod

   >[!IMPORTANT]
   >
   > Le fichier DTD spécialisé doit faire partie du déploiement du code personnalisé. Les DTD situées sous /apps font partie du déploiement du produit. Elles sont donc remplacées lors de l’installation d’une nouvelle version. Il est recommandé d&#39;ajouter la DTD spécialisée sous /var/dxml/dita\_resources dans le dossier du projet et d&#39;inclure le chemin DTD/catalog dans le profil DITA. Pour plus d&#39;informations, consultez [Intégration de la spécialisation DITA](dita-ot-specialization.md#id211MB0E00XA).

1. Utilisez le gestionnaire de packages pour télécharger le fichier /libs/fmdita/config/condAttrList.xml :

1. Créez une copie du fichier condAttrList.xml à l’emplacement suivant dans votre référentiel Git Cloud Manager :

   `/apps/fmdfmdita/config/condAttrList.xml`

1. Enregistrez le fichier.

1. Ajoutez des attributs personnalisés au profil global ou au niveau du dossier.


## Configurer des modèles {#id1889D0IL0Y4}

AEM Guides est fourni avec 7 modèles de rubrique prêts à l&#39;emploi, 2 modèles de plan DITA et 3 modèles PDF. Vous pouvez choisir de ne laisser que quelques modèles à la disposition de vos auteurs et éditeurs. Si vous utilisez un modèle personnalisé, celui-ci peut être configuré et mis à disposition pour la création et la publication. Utilisez l’onglet **Modèles** dans la configuration des profils de dossier pour ajouter ou supprimer des modèles de rubrique, de mappage ou de PDF des profils globaux ou au niveau du dossier.

Avant même de configurer les modèles de rubrique, de mappage ou de PDF au niveau global ou du dossier, vous pouvez également définir un emplacement pour stocker vos modèles personnalisés. Pour configurer un emplacement personnalisé afin de stocker les modèles, voir [Configurer le chemin d&#39;accès au dossier de modèles DITA personnalisés](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z).

Pour ajouter les modèles de rubrique, de mappage ou PDF à un profil de dossier, procédez comme suit :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur ou en tant qu’utilisateur disposant de droits d’administration sur un profil au niveau du dossier.

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils, puis cliquez sur la mosaïque **Profils de dossier**.

1. Cliquez sur la mosaïque de profil que vous souhaitez configurer.

   >[!NOTE]
   >
   > Vous pouvez choisir de configurer un modèle dans le profil global ou un profil au niveau du dossier.

1. Sur la page du profil, cliquez sur l’onglet **Modèles**.
1. Cliquez sur **Modifier**.

   Vous avez la possibilité d’ajouter des modèles Rubrique, Carte et PDF en effectuant une recherche à partir de l’emplacement par défaut ou en effectuant une recherche.

   >[!NOTE]
   >
   > Par défaut, tous les modèles sont stockés dans le dossier /content/dam/dita-templates . Le dossier `dita-templates` contient des sous-dossiers `topics`, `maps` et `PDF` pour stocker la rubrique, le mappage et les modèles PDF. Vous pouvez ajouter vos modèles personnalisés \(.dita,.xml ou .ditamapfiles\) dans les dossiers de modèles par défaut. Une fois que vous avez ajouté votre modèle dans le dossier par défaut, vous pourrez l’ajouter dans le profil global ou de dossier. Pour plus d’informations sur la création de modèles personnalisés à l’aide de l’éditeur web, voir [Créer un modèle de création personnalisé](#id1917D0EG0HJ).

   ![](assets/search-author-temp.png){width="800" align="left"}

1. Ajoutez les modèles de rubrique, de mappage et de PDF requis à votre profil.

   Pour ajouter un modèle, effectuez l’une des opérations suivantes :

   - Choisissez **Rechercher ou Saisir** puis saisissez ou sélectionnez le nom d’un modèle dans la liste déroulante. La liste déroulante se compose de tous les modèles par défaut et de tout nouveau modèle que vous avez créé.

     ![](assets/default-template-list.png){width="800" align="left"}

   - Cliquez sur **Parcourir** et sélectionnez un modèle dans la gestion des ressources numériques.

1. Cliquez sur **Ajouter**.

   Les modèles sélectionnés sont ajoutés à la liste des modèles.

   ![](assets/author-templ-added-list.png){width="800" align="left"}

   >[!NOTE]
   >
   > Vous pouvez modifier l’ordre des modèles en les faisant glisser et en les déposant à l’emplacement souhaité dans la liste. La position des modèles contrôle l’ordre dans lequel ils s’affichent dans la page Plan directeur du workflow de création de rubrique ou de carte.

1. Pour définir les règles de traduction, parcourez l’emplacement SRX pour trouver le dossier contenant les fichiers SRX. Le format SRX \(Segmentation Rules eXchange\) est une norme pour échanger des règles de segmentation entre différents utilisateurs et différents environnements de traduction. Vous pouvez créer un dossier et y ajouter vos fichiers SRX personnalisés.

   Une fois que vous avez créé le dossier contenant les fichiers SRX, vous pouvez ajouter le chemin du dossier dans la configuration **Emplacement SRX de traduction** dans votre profil de dossier.

   AEM Guides sélectionne les règles SRX en fonction de la langue source du projet de traduction. Il recherche un fichier SRX personnalisé pour une langue, et si vous ne définissez pas de fichier SRX personnalisé, il sélectionne les règles selon les règles de traduction prêtes à l’emploi.

1. Cliquez sur **Enregistrer**.


Si vous avez configuré les modèles sur un profil au niveau du dossier, les modèles configurés sont associés au dossier configuré. Tous les projets créés sous le dossier configuré auront accès uniquement aux modèles configurés sous le profil au niveau du dossier.

## Créer un modèle de création personnalisé {#id1917D0EG0HJ}

AEM Guides permet de créer facilement des modèles. En tant qu’administrateur ou administratrice système, vous pouvez utiliser l’éditeur web pour créer des modèles à partir de zéro. Vous pouvez ensuite ajouter le nouveau modèle dans le profil global ou l’affecter à un dossier spécifique à l’aide du profil spécifique au dossier.

Pour créer un modèle de création personnalisé, procédez comme suit :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Dans l’interface utilisateur d’Assets, accédez au dossier configuré pour stocker les fichiers de modèle. Par défaut, tous les modèles de rubrique sont stockés dans le dossier /content/dam/dita-templates/topics.

   >[!NOTE]
   >
   > Pour configurer un emplacement personnalisé afin de stocker des modèles de rubrique ou de mappage, consultez [Configurer le chemin d&#39;accès au dossier de modèles DITA personnalisés](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z)

1. Cliquez sur **Créer** \> **Modèle DITA**.

1. Sur la page Plan directeur, sélectionnez le type de modèle de rubrique DITA à créer.

   >[!NOTE]
   >
   > Vous pouvez utiliser le modèle vierge pour commencer à partir de zéro. Le modèle vierge ne comporte aucune structure ni aucun élément.

1. Cliquez sur **Suivant**.

1. Sur la nouvelle page Propriétés du modèle, saisissez un **Titre**, un **Nom** et un **Description** pour le modèle.

   >[!NOTE]
   >
   > Le nom est automatiquement suggéré en fonction du Titre de votre modèle. Si vous souhaitez spécifier le nom manuellement, assurez-vous que le Nom ne contient pas d&#39;espaces, d&#39;apostrophe ou de crochets et se termine par .dita.

1. *\(Facultatif\)* Cliquez sur le bouton **Ajouter une miniature** dans le navigateur et sélectionnez une miniature à associer à votre modèle.

1. Cliquez sur **Créer**.

   Le message Rubrique créée s’affiche.

   Vous pouvez choisir d’ouvrir le modèle pour le modifier dans l’éditeur web ou d’enregistrer le fichier de modèle à l’emplacement du magasin de modèles. Une fois le modèle créé, vous pouvez utiliser l’éditeur web pour le personnaliser en fonction de vos besoins de création. Une fois qu’un modèle est en place, veillez à l’associer à un profil global ou au niveau du dossier.


## Configuration des paramètres prédéfinis de sortie {#id18AGD0IH0Y4}

Dans une configuration d’entreprise standard, différents modèles de sortie peuvent être utilisés pour différents produits ou guides d’utilisation. En outre, il pourrait y avoir certains processus communs de génération de sortie qui devraient être utilisés par tous les éditeurs et un ensemble de processus spécifiques de génération de sortie pour un groupe spécifique d’éditeurs ou de projets.

AEM Guides permet à l’administrateur de créer des paramètres prédéfinis de sortie avec des paramètres spécifiques qui peuvent ensuite être utilisés par l’ensemble des éditeurs ou un ensemble spécifique d’éditeurs et éditrices pour générer une sortie. Par exemple, l’administrateur peut créer un paramètre prédéfini de sortie pour générer un guide de l’utilisateur commun à tous les éditeurs. Et un autre pour créer les manuels d&#39;utilisation de programmation qui sont spécifiques à un ensemble d&#39;éditeurs. Ces deux paramètres prédéfinis peuvent être configurés pour utiliser différents modèles de sortie. Dans cet exemple, le paramètre prédéfini de publication commun pour la génération du guide d’utilisation peut être configuré au niveau global. De plus, le paramètre prédéfini de sortie pour générer le manuel d’utilisation de programmation peut être configuré au niveau du dossier.

Une fois les paramètres prédéfinis de sortie par défaut créés dans le système, tous les plans DITA créés par la suite utiliseront les paramètres prédéfinis par défaut pour générer la sortie. Cependant, tous les mappages DITA existants continueront à utiliser les paramètres prédéfinis de sortie qui ont été configurés précédemment avec eux. Si vous souhaitez appliquer le nouveau paramètre prédéfini de sortie à tous les plans DITA existants, vous devez exécuter le workflow Appliquer les modifications de paramètre prédéfini .

Outre les paramètres prédéfinis configurés au niveau global ou d’entreprise, un éditeur disposerait toujours des droits nécessaires pour créer d’autres paramètres prédéfinis de sortie. Toutefois, ces paramètres prédéfinis sont liés au plan DITA pour lequel ils sont créés. Pour plus d&#39;informations sur la création de paramètres prédéfinis de sortie standard pour un plan DITA, voir *Créer, modifier, dupliquer ou supprimer un paramètre prédéfini de sortie* dans le guide Utilisation d&#39;Adobe Experience Manager Guides as a Cloud Service.

Effectuez les étapes suivantes pour configurer des paramètres prédéfinis de sortie globaux ou spécifiques à un dossier :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur ou en tant qu’utilisateur disposant de droits d’administration sur un profil spécifique au dossier.

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils, puis cliquez sur la mosaïque **Profils de dossier**.

1. Cliquez sur la mosaïque de profil que vous souhaitez configurer.

   >[!NOTE]
   >
   > Vous pouvez choisir de configurer des paramètres prédéfinis de sortie dans le profil global ou dans un profil spécifique à un dossier.

1. Sur la page du profil. Cliquez sur l’onglet **Paramètres prédéfinis de sortie**.

   Une liste de paramètres prédéfinis de sortie prêts à l’emploi s’affiche, qui inclut AEM Site, PDF, HTML5, EPUB et CUSTOM.

1. Effectuez l’une des opérations suivantes pour créer ou modifier un paramètre prédéfini de sortie :

   - Cliquez sur **Créer** pour créer un nouveau paramètre prédéfini de sortie à partir de zéro.
   - Cliquez sur Dupliquer pour créer une copie du paramètre prédéfini de sortie sélectionné. Vous pouvez apporter des modifications au paramètre prédéfini en double et l’enregistrer.

   - Cliquez sur **Modifier** pour ouvrir la configuration du paramètre prédéfini sélectionné en vue de la modifier.

     Pour plus d’informations sur les paramètres prédéfinis de sortie, voir *Présentation des paramètres prédéfinis de sortie* dans le guide Utilisation d’Adobe Experience Manager Guides as a Cloud Service .

1. Cliquez sur **Enregistrer** pour enregistrer les paramètres prédéfinis.


Tous les plans DITA créés ou chargés par la suite auront le nouveau paramètre de sortie prédéfini ou celui mis à jour.

## Application des modifications de paramètre prédéfini {#id18AGD0K0OHS}

Un nouveau paramètre prédéfini de sortie créé au niveau global est disponible pour tous les nouveaux plans DITA que vous créerez à l&#39;avenir. De même, si un nouveau paramètre prédéfini de sortie est créé au niveau d’un dossier, il est mis à la disposition de tous les mappages qui seront créés dans le dossier configuré. Par défaut, aucun nouveau paramètre prédéfini de sortie n&#39;est disponible pour les plans DITA existants.

Si vous avez mis à jour un paramètre prédéfini de sortie existant ou si vous souhaitez rendre un nouveau paramètre prédéfini de sortie disponible pour les plans DITA existants, effectuez les étapes suivantes :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur ou en tant qu’utilisateur disposant de droits d’administration sur un profil spécifique au dossier.

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils, puis cliquez sur la mosaïque **Profils de dossier**.

1. Cliquez sur la mosaïque de profil que vous souhaitez configurer.

   >[!NOTE]
   >
   > Vous pouvez choisir de configurer des paramètres prédéfinis de sortie dans le profil global ou dans un profil spécifique à un dossier.

1. Sur la page du profil. Cliquez sur l’onglet **Paramètres prédéfinis de sortie**.

   Une liste de paramètres prédéfinis de sortie prêts à l’emploi s’affiche, qui inclut AEM Site, PDF, HTML5, EPUB et CUSTOM.

1. Sélectionnez le paramètre prédéfini de sortie à appliquer aux plans DITA existants.

1. Cliquez sur **Appliquer les modifications de paramètre prédéfini** dans la barre d’outils principale.

1. Dans la boîte de dialogue Appliquer les modifications de paramètre prédéfini , vous pouvez choisir parmi les options suivantes :

   - **Sélection de l&#39;option Remplacer le paramètre prédéfini existant** : si vous sélectionnez cette option, toutes les mises à jour effectuées dans les paramètres prédéfinis de sortie existants remplaceront les paramètres dans tous les plans DITA existants dans lesquels ce paramètre prédéfini est utilisé. Toutefois, cela entraînera la perte de tous les paramètres prédéfinis conditionnels existants et des informations de base associées à la carte.

   - **Sans sélectionner l’option Remplacer le paramètre prédéfini existant** : si vous ne sélectionnez pas cette option, les mises à jour apportées aux paramètres prédéfinis de sortie existants n’auront pas d’impact sur les plans DITA existants. Seuls les paramètres prédéfinis nouvellement ajoutés sont ajoutés aux plans DITA existants. Notez que le plan DITA nouvellement créé obtient à la fois les paramètres prédéfinis de sortie mis à jour et les paramètres prédéfinis nouvellement ajoutés.

1. Cliquez sur **OK** pour appliquer les modifications des paramètres prédéfinis de sortie sélectionnés à tous les plans DITA existants.



## Configurer l’assistant AI pour l’aide et la création intelligentes

Pour Experience Manager Guides as a Cloud Service (![](assets/aem-cloud-icon.svg) cloud AEM).

L’assistant AI d’Adobe Experience Manager Guides est un puissant outil piloté par l’IA conçu pour améliorer votre contenu grâce à des expériences de création et de réutilisation de contenu intelligentes. Il associe deux puissantes fonctionnalités d’IA (**Création** et **Aide**) à l’interface de Experience Manager Guides, ce qui vous permet de créer des documents et d’accéder aux informations plus rapidement et plus efficacement.

Pour plus d’informations sur la configuration, voir [&#x200B; Configuration de l’assistant AI &#x200B;](./conf-smart-suggestions.md).

**Configurer des suggestions intelligentes optimisées par l’IA**

Vous pouvez configurer les suggestions intelligentes optimisées par l’IA et aider les auteurs à réutiliser le contenu existant et à créer facilement des références de contenu correctes et cohérentes. L’onglet **Configuration de l’IA** vous permet de contrôler les paramètres de **Suggérer du contenu réutilisable** à partir du panneau de l’assistant d’IA dans l’éditeur.

Effectuez les étapes suivantes pour configurer la configuration d’IA standard au niveau du profil global ou du dossier :
1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur ou utilisateur disposant de droits d’administration sur un profil au niveau du dossier.
1. Sélectionnez le lien **Adobe Experience Manager** en haut et choisissez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils, puis sélectionnez la mosaïque **Profils de dossier**.
1. Sélectionnez la mosaïque de profil à configurer.

   >[!NOTE]
   >
   >Vous pouvez configurer des suggestions intelligentes basées sur l’IA pour le profil global ou au niveau du dossier.

1. Sur la page du profil, sélectionnez l’onglet **Configuration de l’IA** .

   ![Onglet Configuration de l’IA dans le profil global](assets/global-profile-AI-configuration-cs.png) {width="800" align="left"}

1. Sélectionnez **Modifier**.
1. En tant qu’administrateur, vous pouvez configurer les paramètres suivants :

   **Nombre minimum de caractères** : saisissez le nombre minimum de caractères que les auteurs doivent sélectionner pour obtenir les suggestions. Par exemple, si ce nombre est de 40, l’auteur doit sélectionner au moins 40 caractères pour afficher une suggestion dynamique.

   Pour les sélections qui ne répondent pas aux exigences minimales en termes de caractères, le message suivant s’affiche dans le panneau de l’assistant d’IA :

   ![](assets/smart-suggestions-character-limit.png)

   Toutefois, pour les sélections générales où aucune suggestion n’est disponible, le message suivant s’affiche :

   ![](assets/smart-suggestions-select-another-text-message.png)

   Cela permet aux auteurs de comprendre si les suggestions sont indisponibles en raison d’une sélection de caractères insuffisante ou de l’absence réelle de contenu correspondant.

   **Nombre maximal de suggestions** : saisissez le nombre maximal de suggestions que les auteurs peuvent obtenir lors de la création du contenu. Par exemple, si ce nombre est de 5, l’auteur peut afficher cinq suggestions intelligentes ou moins.

   **Fichiers et dossiers** : sélectionnez les dossiers à partir desquels afficher les suggestions intelligentes. Seuls les dossiers enfants du chemin de dossier spécifié dans un profil de dossier peuvent être sélectionnés. Pour plus d’informations, consultez la section [Restrictions du profil de dossier](#folder-profile-restrictions).

   *Pour maintenir la cohérence du contenu, il est recommandé qu’aucune entrée de la liste ne comporte de fichiers communs*. Une fois les fichiers et les dossiers sélectionnés, ils sont répertoriés.

1. Cliquez sur **Enregistrer**.

   >[!NOTE]
   >
   > Le dernier statut indexé du profil de dossier s’affiche en haut après l’enregistrement du fichier.

Découvrez comment afficher et ajouter des suggestions intelligentes [basées sur l’IA](../user-guide/authoring-ai-based-smart-suggestions.md) pour ajouter des références de contenu lors de la création dans l’éditeur web.

### Restrictions du profil de dossier

Pour que les suggestions intelligentes fonctionnent efficacement, tenez compte des points suivants lors de l’indexation des dossiers :

1. Le contenu doit être indexé via des profils de dossier pour que l’assistant d’IA puisse fournir des suggestions intelligentes aux auteurs.
2. Lors de la spécification d’un dossier pour l’indexation, seuls les dossiers situés sous le profil de dossier actif peuvent être ajoutés. Toute tentative d’ajout de dossiers en dehors de ce profil de dossier déclenche un avertissement.

   ![](assets/warning-message-indexing.png)

   Cette restriction s’applique uniquement aux profils au niveau du dossier. Le profil global n’applique pas les limites de chemin d’accès et peut indexer des dossiers qui ne se trouvent sous aucun autre profil de dossier.
3. Si un dossier parent est ajouté pour l’indexation, tous les dossiers enfants déjà répertoriés sont automatiquement supprimés afin d’éviter la duplication. L’ajout d’un dossier enfant d’un parent déjà indexé déclenche également un avertissement.

   ![](assets/parent-child-warning-message-indexing.png)
4. Toute mise à jour, déplacement ou suppression de fichiers dans les dossiers indexés déclenche une réindexation ou une suppression automatique de l’index.
5. Pour chaque tentative d’indexation, les statuts d’indexation suivants s’affichent :

   - En cours : indique que l’indexation est en cours.
   - Indexation terminée : indique que l’indexation s’est terminée avec succès.
   - Échec de l’indexation : indique que l’indexation a échoué.
   - Pas synchronisé : indique que l’indexation n’est pas synchronisée, généralement observée après une mise à niveau ou une migration, lorsque le statut d’indexation actuel n’a pas pu être vérifié. Vous pouvez réessayer d’indexer pour actualiser et mettre à jour le statut.

   Lorsque l’indexation échoue, les options **Afficher les journaux d’erreurs** et **Réessayer l’indexation** vous sont fournies pour résoudre le problème.

   ![](assets/indexing-failed-options.png)

   Les journaux d’erreurs s’affichent comme illustré ci-dessous :

   ![Texte de remplacement](index-error-log.png)

6. Un horodatage de la dernière heure d’index s’affiche pour chaque profil de dossier.

**Personnaliser les questions par défaut pour l’aide dynamique**

Pour Experience Manager Guides as a Cloud Service (![](assets/aem-cloud-icon.svg) cloud AEM).

Vous pouvez configurer l’aide intelligente optimisée par l’IA **Aide** pour aider les auteurs à poser des questions et à rechercher facilement le contenu requis à partir de la documentation de [Experience Manager Guides](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/overview).

L’onglet **Configuration de l’éditeur XML** vous permet de configurer les questions par défaut du panneau **Aide**.

>[!NOTE]
>
>Vous pouvez configurer jusqu’à 10 questions par défaut.

Pour configurer les questions par défaut, procédez comme suit :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur ou utilisateur disposant de droits d’administration sur un profil au niveau du dossier.
1. Sélectionnez le lien **Adobe Experience Manager** en haut et choisissez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils, puis sélectionnez la mosaïque **Profils de dossier**.
1. Sélectionnez la mosaïque de profil à configurer.

   >[!NOTE]
   >
   >Vous pouvez configurer les questions par défaut pour le **panneau d’aide dynamique** au profil global ou au niveau du dossier.

1. Sélectionnez l’onglet **Configuration de l’éditeur XML**.

1. Cliquez sur l’icône **Modifier** en haut.
1. Dans la section **Configuration de l’interface utilisateur de l’éditeur XML**, sélectionnez l’icône **Télécharger** pour télécharger le fichier `ui_config.json` sur votre système local.
1. Dans le fichier `ui_config.json`, ajoutez les exemples de questions.

   **Exemple de questions** :

   ```json
   "assistantSampleQuestions": [
   "How to create a new topic",
   "How to create a new map",
   "What is a baseline" ]
   ```

1. Enregistrez le fichier et chargez-le.

   >[!NOTE]
   >
   > Les questions par défaut s’affichent dans le panneau **Aide dynamique** après l’enregistrement du fichier.


Pour en savoir plus sur l’utilisation de l’aide intelligente optimisée par [IA](../user-guide/ai-based-smart-help.md) afin de rechercher le contenu requis, consultez la documentation de Experience Manager Guides.


## Configuration et personnalisation de l’éditeur XML {#id2065G300O5Z}

Par défaut, l&#39;éditeur XML est fourni avec de nombreuses fonctions pour aider vos auteurs à créer des documents DITA. Si vous travaillez dans un environnement restrictif, vous pouvez choisir les fonctionnalités exposées à vos auteurs. L’onglet Configuration de l’éditeur XML vous permet de contrôler facilement les fonctionnalités et de modifier également l’aspect de votre éditeur. En tant qu’administrateur, vous pouvez personnaliser les composants suivants de l’éditeur :

**Configuration de l’interface utilisateur de l’éditeur XML**

Ce paramètre vous permet de créer des extensions JSON qui reflètent les modifications apportées au fichier `ui_config.json`. Vous pouvez charger ces extensions indépendamment au niveau du profil du dossier, offrant ainsi une flexibilité et une personnalisation améliorées. Par exemple, lorsque vous apportez des modifications à la configuration de l’éditeur **XML**, comme la mise à jour d’un bouton, le système identifie automatiquement les différences. En chargeant ces modifications dans la **Configuration de l’interface utilisateur de l’éditeur XML** et en les convertissant en extensions JSON à l’aide du bouton **Convertir la configuration de l’interface utilisateur en JSON**, le système génère une extension qui incorpore la nouvelle fonctionnalité.

En savoir plus sur [la personnalisation des configurations JSON et la conversion des configurations de l’interface utilisateur pour le nouvel éditeur AEM Guides](https://experienceleague.adobe.com/en/docs/experience-manager-guides-learn/videos/advanced-user-guide/conver-ui-config).

>[!NOTE]
>
> Lors de la personnalisation de l’application à l’aide du framework d’extension, il est recommandé d’utiliser uniquement les composants essentiels pris en charge du spectre React, tels que l’arborescence, le tableau, la case à cocher, le bouton radio et le groupe de cases d’option, etc., afin d’éviter tout problème lors du déploiement.

**Mise en page de l’éditeur XML**

Cette fonctionnalité vous permet de charger des fichiers CSS pour appliquer un style aux nouvelles extensions chargées sous la **Configuration de l’interface utilisateur de l’éditeur XML**. La feuille de style CSS chargée est appliquée de manière cohérente dans toutes les applications pertinentes, ce qui garantit une apparence unifiée et soignée pour vos personnalisations de l’interface utilisateur.

**Configuration de l’éditeur XML**

Ce paramètre contrôle la barre d’outils et les autres éléments de l’interface utilisateur de l’éditeur. Sélectionnez l’icône **Télécharger** pour télécharger le fichier `ui\_config.json` sur votre système local. Vous pouvez ensuite apporter des modifications au fichier et le charger. Selon l’endroit où vous téléchargez le fichier, le profil global ou le profil au niveau du dossier, les modifications sont appliquées en conséquence. Pour plus d’informations sur la personnalisation de l’éditeur XML à l’aide de l’`ui\_config.json file`, consultez la section [Personnaliser la barre d’outils](conf-web-editor-customize-toolbar.md#).

>[!NOTE]
>
> Pour la version AEM Guides 2502 et les versions plus récentes, il est recommandé d’utiliser l’extension JSON au lieu de `ui_config.json` pour la personnalisation. Pour plus d’informations, consultez la section **Configuration de l’interface utilisateur de l’éditeur XML** ci-dessus.

**Disposition du modèle CSS**

Téléchargez le fichier disponible dans cette section pour personnaliser l’aspect de votre document lorsqu’il est prévisualisé ou ouvert pour modification dans l’éditeur web. Le fichier CSS par défaut disponible au téléchargement est uniquement un fichier test, qui ne doit pas être utilisé à des fins de personnalisation. Vous pouvez créer un fichier CSS avec des personnalisations pour l’éditeur web et le charger. Par exemple, vous pouvez créer un fichier .css avec le code suivant :

```
.title {    font-size: 9em;}
```

Enregistrez ce fichier et chargez-le dans la section Disposition du modèle CSS. La prochaine fois que vous téléchargerez le fichier , vous obtiendrez le dernier fichier CSS utilisé dans l’éditeur web.

**Fragments de code de l’éditeur XML**

À l’aide du fichier de configuration de cette section, vous pouvez créer des fragments de code par défaut et les partager avec les auteurs. La structure par défaut du fichier est présentée ci-dessous :

```
{
   "snippetID": {
      "name": "snippet Name",
      "description": "snippet Description",
      "value": "<i>this is snippet value</i>"
  }
}
```

Les informations suivantes sont requises pour créer un fragment de code :

**snippetID** : ID unique du fragment de code. Elle peut prendre une valeur alphanumérique.

**name** - Nom descriptif pour identifier le fragment de code. Ce nom s’affiche dans le panneau Fragments de code.

**description** - Ajoutez une description du fragment de code.

**value** - Indiquez le code XML du fragment de code.

>[!NOTE]
>
> Vous pouvez ajouter d’autres fragments de code en ajoutant une virgule \(,\) à la fin de votre définition de fragment de code et en répétant la même structure pour le fragment de code suivant.

**Libellés de version du contenu XML**

Par défaut, les auteurs sont autorisés à créer les libellés de leur choix et à les associer à leurs fichiers de rubrique. Cependant, cela peut entraîner de nombreuses variations d’un même libellé, par exemple des libellés « Version 1.0 », « Version 1.0 », « Version 1 » pour identifier la même étape d’une rubrique. Pour éviter une telle incohérence dans les libellés du système, vous pouvez créer une liste prédéfinie de libellés parmi lesquels les créateurs et créatrices seront ensuite autorisés à choisir. L’étiquetage cohérent permet une meilleure gestion des fichiers dans votre système.

La configuration des libellés de version vous permet de charger une liste de libellés valides pour votre organisation. Téléchargez le fichier label.json par défaut et modifiez-le comme illustré ci-dessous :

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

Dans l’exemple ci-dessus, « label1 » est l’identifiant de la séquence de libellés et il est ajouté par le libellé affiché pour les auteurs lorsqu’un libellé est requis. Enregistrez ce fichier et chargez-le dans la section Libellés de version du contenu XML .

>[!IMPORTANT]
>
> Pour que les configurations au niveau du dossier prennent effet, les utilisateurs doivent sélectionner le profil dans leurs Préférences utilisateur dans l’éditeur web.

**Rootmap**

Si vos auteurs utilisent une carte racine spécifique, vous pouvez accéder à cette carte racine et la sélectionner ici. Notez que vous ne pouvez définir la feuille de route que pour un profil au niveau du dossier.
