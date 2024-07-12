---
title: Notes de mise à jour | Nouveautés de la version 2024.4.0 d’Adobe Experience Manager Guides
description: Découvrez les nouvelles fonctionnalités et les fonctionnalités améliorées de la version 2024.4.0 d’Adobe Experience Manager Guides as a Cloud Service.
exl-id: e9db535a-5ad5-4ff0-94af-b4425594316a
source-git-commit: 5d99274da8fdacbd255d426fa4913b5773ca45f8
workflow-type: tm+mt
source-wordcount: '1806'
ht-degree: 28%

---

# Nouveautés de la version 2024.4.0

Cet article couvre les nouvelles fonctionnalités et les fonctionnalités améliorées de la version 2024.4.0 d’Adobe Experience Manager Guides.

Pour connaître la liste des problèmes résolus dans cette version, voir la section [Problèmes résolus dans la version 2024.4.0](fixed-issues-2024-04-0.md).

Découvrez les [instructions de mise à niveau pour la version 2024.4.0](upgrade-instructions-2024-04-0.md).

## Possibilité de traduire du contenu dans plusieurs langues à l’aide de groupes de langues préconfigurés

Experience Manager Guides permet désormais de créer des groupes de langues et de traduire facilement votre contenu dans plusieurs langues. Cette fonctionnalité permet d’organiser et de gérer les traductions en fonction des besoins de votre organisation.

Par exemple, si vous devez traduire votre contenu pour certains pays d’Europe, vous pouvez créer un groupe de langues pour les langues européennes telles que l’anglais (EN), le français (FR), l’allemand (DE), l’espagnol (ES) et l’italien (IT).



![Panneau de traduction](assets/translation-languages-2404.png){width="300" align="left"}

*Sélectionnez les groupes de langues ou les langues que vous souhaitez utiliser pour traduire vos documents.*

>[!NOTE]
>
>Si le dossier cible d’une langue est manquant ou si la langue cible est identique à la langue source, elle est grisée et un signe d’avertissement est affiché.

En tant qu’administrateur ou administratrice, vous pouvez créer des groupes de langues et les configurer sur plusieurs profils de dossiers. En tant qu’auteur ou autrice, vous pouvez afficher les groupes de langues configurés sur votre profil de dossier.


Dans l’ensemble, la création de groupes de langues renforce l’efficacité et la productivité des projets de traduction, améliorant ainsi le processus de localisation dans plusieurs langues.


Découvrez comment [traduire des documents à partir de l’éditeur Web](../user-guide/translate-documents-web-editor.md).



## Supprimer ou désactiver automatiquement le projet de traduction après la traduction

Désormais, en tant qu’administrateur, vous pouvez configurer les projets de traduction pour qu’ils soient désactivés ou supprimés automatiquement après avoir terminé la traduction. Cette fonctionnalité vous permet d’utiliser efficacement les ressources et de gérer les fichiers après avoir terminé la traduction.

La suppression d’un projet supprime définitivement tous les fichiers et dossiers présents dans le projet. La suppression des projets de traduction permet également de libérer l’espace disque occupé.

Vous pouvez désactiver les projets de traduction si vous souhaitez les utiliser ultérieurement.

![](assets/editor-setting-translation.png){width="550" align="left"}


*Configurez les groupes de langues et les paramètres de nettoyage pour les projets de traduction.*


Découvrez comment [supprimer ou désactiver automatiquement le projet de traduction](../user-guide/translate-documents-web-editor.md#automatically-delete-or-disable-a-completed-translation-project).


## Activation de la sortie de vos cartes dans la collection d’activation en bloc sur l’instance Aperçu

Désormais, en plus d’activer la sortie de votre collection d’activation en bloc sur l’instance de publication, Experience Manager Gudies as Cloud Service fournit la fonctionnalité permettant de l’activer sur l’instance **Preview**.


Cette fonctionnalité vous permet d’activer votre contenu vers une instance d’aperçu, ce qui vous permet de vérifier son aspect et son fonctionnement avant de l’activer vers l’instance **Publish**.


![ onglet historique d’audit de collection d’activation en bloc créé](assets/bulk-collection-audit-history.png){width="800" align="left"}

*Affichez les informations sur les sorties de mappage activées dans l’onglet **Historique d’audit**.*


En savoir plus sur [l’activation en masse](../user-guide/conf-bulk-activation-publish-map-collection.md).

## Améliorations des connecteurs de source de données

Les améliorations suivantes ont été apportées aux connecteurs de sources de données dans la version 2024.4.0 :

### Connexion aux sources de données Salsify, Akeneo et Microsoft Azure Dev Ops Board (ADO)

Outre les connecteurs prêts-à-l’emploi existants, Experience Manager Guides fournit également des connecteurs pour les sources de données Salsify, Akeneo et Microsoft Azure DevOps (ADO) Boards. En tant qu’administrateur ou administratrice, vous pouvez télécharger et installer ces connecteurs. Configurez ensuite les connecteurs installés.

### Copiez et collez l’exemple de requête pour créer un fragment de contenu ou une rubrique.

Vous pouvez facilement copier et coller un exemple de requête de données dans le générateur pour créer un extrait de contenu ou une rubrique. Grâce à cette fonction, vous n’avez pas à mémoriser la syntaxe ni à créer une requête manuellement. Au lieu de saisir une requête manuellement, vous pouvez copier et coller un exemple de requête, le modifier et l’utiliser pour récupérer des données selon vos besoins.

![Boîte de dialogue Insérer un extrait de contenu](assets/insert-content-snippet.png){width="800" align="left"}

*Copiez et modifiez un exemple de requête pour créer l’extrait de contenu.*

### Connexion aux fichiers de données JSON à l’aide d’un connecteur de fichier


Désormais, en tant qu’administrateur ou administratrice, vous pouvez configurer un connecteur de fichier JSON pour qu’il utilise les fichiers de données JSON comme source de données. Utilisez le connecteur pour importer les fichiers JSON de votre ordinateur ou d’Adobe Experience Manager Assets. Ensuite, en tant qu’auteur ou autrice, vous pouvez créer des extraits de contenu ou des rubriques à l’aide des générateurs.

Cette fonctionnalité vous permet d’utiliser les données stockées dans vos fichiers JSON et de les réutiliser dans divers extraits de code. Le contenu est également mis à jour de manière dynamique à chaque fois que vous actualisez les fichiers JSON.

### Configuration de plusieurs URL de ressource pour un connecteur afin de créer des fragments de contenu ou des rubriques

En tant qu’administrateur, vous pouvez configurer plusieurs URL de ressources pour certains connecteurs tels que Generic REST Client, Salsify, Akeneo et Microsoft Azure DevOps Board (ADO).

Ensuite, en tant qu’auteur ou autrice, connectez-vous aux sources de données pour créer des extraits de contenu ou des rubriques à l’aide des générateurs. Cette fonctionnalité est pratique, car vous n’avez pas à créer de source de données pour chaque URL. Cela vous permet de récupérer rapidement des données d’une source de données spécifique dans un fragment de contenu ou une rubrique unique.

Affichez plus d’informations sur les connecteurs de source de données et sur la [configuration d’un connecteur de source de données à partir de l’interface utilisateur](../cs-install-guide/conf-data-source-connector-tools.md).

Découvrez comment [utiliser les données de votre source de données](../user-guide/web-editor-content-snippet.md).

## Personnalisation de l’expérience de l’éditeur web grâce à la nouvelle interface utilisateur des préférences utilisateur

La boîte de dialogue **Préférences utilisateur** de l’éditeur web comprend désormais un nouvel onglet **Apparence**. Ce nouvel onglet vous permet de configurer facilement les préférences d’apparence les plus courantes de l’interface de l’éditeur web.

Vous pouvez configurer pour afficher les fichiers par titre ou par nom de fichier, et modifier le thème de l’application et la vue source. Il vous permet également de configurer les paramètres pour localiser un fichier ouvert dans la vue du référentiel et de gérer les espaces insécables.

![onglet apparence des préférences utilisateur](assets/user_preference_editor_appearance.png){width="550" align="left"}

*Personnalisez l’aspect selon vos préférences.*

Pour en savoir plus sur la description de la fonctionnalité **Préférences utilisateur** dans la section [Panneau de gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .

## Localisez un fichier ouvert dans la vue du référentiel de l’éditeur Web.

Sélectionnez l’option **Toujours localiser les fichiers dans le référentiel** dans les **Préférences utilisateur** pour parcourir et localiser rapidement votre fichier dans la vue du référentiel. Vous n’avez pas à le rechercher manuellement.

Lors de la modification, cette fonctionnalité vous permet également d’afficher facilement l’emplacement du fichier dans la hiérarchie du référentiel.

Pour plus d’informations, consultez [recherchez un fichier ouvert dans la vue de référentiel](../user-guide/web-editor-edit-topics.md#locate-an-open-file-in-the-repository-view).


## Amélioration de la gestion des espaces insécables dans l’éditeur web

Experience Manager Guides vous permet d’afficher un indicateur d’espace insécable lors de la modification de documents dans l’éditeur web. Il améliore également la gestion des espaces insécables.
Il convertit plusieurs espaces blancs consécutifs en un seul espace afin de conserver l’affichage WYSIWYG du document dans l’éditeur web. Cette fonctionnalité contribue également à améliorer l’aspect général et le professionnalisme du document.


Pour plus d’informations, consultez les [autres fonctionnalités de l’éditeur web](../user-guide/web-editor-other-features.md).




## Désactivation du post-traitement pour les dossiers sélectionnés sur Adobe Experience Manager Assets


En tant qu’administrateur, vous pouvez désormais désactiver le post-traitement et la génération des UUID pour les dossiers sélectionnés sur Experience Manager Assets. Cette configuration peut s’avérer utile, en particulier lorsque vous traitez de nombreuses ressources ou de structures de dossiers complexes. Cela permet également à plusieurs utilisateurs de charger rapidement les ressources simultanément sans interférer les uns avec les autres.  

La désactivation du post-traitement d’un dossier affecte également tous ses dossiers enfants. Toutefois, Experience Manager Guides offre désormais la possibilité d’activer le posttraitement sélectif pour des dossiers enfants individuels dans le dossier ignoré.

Découvrez comment [désactiver le posttraitement pour un dossier](../cs-install-guide/conf-folder-post-processing.md).

## Expérience restructurée pour rechercher et filtrer des fichiers dans la vue du référentiel

Le filtrage des fichiers est maintenant amélioré. La redéfinition de la fonctionnalité de filtrage des fichiers facilite les recherches et la navigation dans les fichiers.


![Recherche de fichiers dans la vue du référentiel](assets/repository-filter-search-2404.png){width="300" align="left"}

*Rechercher des fichiers contenant le texte « `general purpose.`* »

Profitez d’avantages tels qu’un accès plus rapide aux fichiers importants et une interface utilisateur plus intuitive. Votre expérience de recherche devient plus fluide et plus efficace.

![ ](assets/repository-filter-search-quick.png) {width="300" align="left"} filtre de recherche rapide

*Utilisez les filtres rapides pour rechercher des fichiers DITA et non DITA.*

En savoir plus sur la fonction **Filtrer la recherche** dans la section [Panneau de gauche](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Liste segmentée pour afficher et insérer des éléments valides en fonction de leur position

Lors de la modification d’un document dans l’éditeur web, vous pouvez désormais afficher une liste séparée d’éléments valides à l’emplacement actuel et en dehors de l’emplacement actuel. Selon vos besoins, vous choisissez un élément parmi les options suivantes :

* **Éléments valides à l’emplacement actuel** que vous pouvez insérer à l’emplacement actuel du curseur lui-même.
* **Éléments valides en dehors de l’emplacement actuel** que vous pouvez insérer après l’un des parents de l’élément actuel dans la hiérarchie des éléments.

![Boîte de dialogue Insérer un élément](assets/insert-element-dialog.png){width="300" align="left"}

*Affichez les listes séparées d’éléments valides pour insérer un élément à l’emplacement actuel.*


Cette liste divisée d’éléments valides vous aide à conserver la structure de contenu et à respecter les normes DITA.

En savoir plus sur la fonction **Insérer l’élément** dans la section [Barre d’outils Secondaire](../user-guide/web-editor-features.md#2051ea0j0y4) .


## Type de propriétés du contenu apparaît dans un menu déroulant.

Désormais, les propriétés de contenu **Type** s’affichent dans un menu déroulant. Vous pouvez afficher et sélectionner les balises de la hiérarchie complète de la balise active dans la liste déroulante.

Ce menu déroulant vous permet d’accéder rapidement aux balises pertinentes dans la structure hiérarchique.


![menu déroulant de type dans les propriétés de contenu](assets/content-properties-type.png){width="300" align="left"}

*Sélectionnez une balise dans la hiérarchie pour la balise actuelle.*

Pour en savoir plus sur la fonction **Propriétés du contenu** dans la section [Panneau de droite](../user-guide/web-editor-features.md#id2051eb003yk) .



## Amélioration des performances lors de la vérification de fichiers en masse à partir de l’éditeur de cartes

Experience Manager Guides améliore les performances et l’expérience de la fonction d’archivage de fichiers en masse à partir de l’éditeur de cartes. Cette amélioration vous permet d’archiver plus rapidement les fichiers en bloc.
Vous pouvez également afficher la progression de l’opération d’archivage pour les fichiers à partir de la boîte de dialogue **Enregistrer comme nouvelle version et Déverrouiller**. Enfin, le message de réussite s’affiche une fois l’opération terminée et tous les fichiers extraits sont archivés.

![Enregistrer comme nouvelle version et déverrouiller la boîte de dialogue](./assets/save-version-lock.png){width="300" align="left"}

*Affichez la liste et l’état des fichiers archivés en bloc à partir de l’éditeur de cartes.*

Découvrez comment [travailler avec l’éditeur de carte avancé](../user-guide/map-editor-advanced-map-editor.md)

## Téléchargez le fichier temporaire lors de la génération de la sortie via DITA-OT.

Vous pouvez également télécharger les fichiers temporaires générés lorsque vous publiez la sortie AEM Site, HTML, Personnalisé, JSON ou PDF via DITA-OT. Cette fonctionnalité vous aide à analyser les problèmes qui peuvent se produire pendant le processus de génération de sortie et à résoudre les problèmes de manière efficace.  
Vous pouvez également télécharger le fichier metadata.xml si vous avez sélectionné des propriétés de métadonnées qui ont été transmises à la sortie générée à l’aide de DITA-OT. 

Pour plus d’informations sur les paramètres prédéfinis, voir [Présentation des paramètres prédéfinis de sortie](../user-guide/generate-output-understand-presets.md).


## Remplacez les informations d’identification JWT IMS par les informations d’identification OAuth IMS pour la publication basée sur Microservice.


Les informations d’identification du compte de service (JWT) ont été abandonnées au profit des informations d’identification **OAuth Server-to-Server**. Vos applications utilisant les informations d’identification du compte de service (JWT) cesseront de fonctionner après le 1er janvier 2025. Vous devez migrer vers les nouvelles informations d’identification d’ici le 1er janvier 2025, afin de vous assurer que votre application continue à fonctionner.


Le service de publication dans le cloud pour Experience Manager Guides est désormais sécurisé par l’authentification Adobe IMS OAuth. Découvrez comment [configurer la publication basée sur un microservice avec l’authentification OAuth](../knowledge-base/publishing/configure-microservices-imt-config.md).
