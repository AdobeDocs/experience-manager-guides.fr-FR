---
title: Notes de mise à jour | Nouveautés de la version 4.4.0 d’Adobe Experience Manager Guides
description: Découvrez les nouvelles fonctionnalités et les fonctionnalités améliorées de la version 4.4.0 d’Adobe Experience Manager Guides
role: Leader
source-git-commit: 57c3b39f0ab0fde5b18e4d4ae0e1501738997e68
workflow-type: tm+mt
source-wordcount: '3050'
ht-degree: 15%

---

# Nouveautés de la version 4.6.0 (septembre 2024)

Cet article traite des nouvelles fonctionnalités et des fonctionnalités améliorées introduites dans la version 4.6.0 d’Adobe Experience Manager Guides.

Pour obtenir la liste des problèmes qui ont été corrigés dans cette version, consultez la section [Problèmes résolus dans la version 4.6.0](../release-info/fixed-issues-4-6-0.md).

Découvrez les [instructions de mise à niveau pour la version 4.6.0](../release-info/upgrade-instructions-4-6-0.md).


## Améliorations apportées à la publication

Les améliorations suivantes ont été apportées à la publication de contenu dans la version 4.6.0 :



### Publish d’une rubrique ou de ses éléments dans un fragment d’expérience

Un fragment d’expérience est une unité de contenu modulaire au sein de Adobe Experience Manager qui intègre le contenu et la mise en page. Les fragments d’expérience jouent un rôle essentiel dans la création d’expériences cohérentes et attrayantes, qui peuvent être réutilisées sur plusieurs canaux. Vous pouvez, par exemple, créer des fragments d’expérience pour les en-têtes ou pieds de page avec des éléments de marque, des bannières promotionnelles, des témoignages de clients et des promotions d’événement.

![ Onglet Options des propriétés de fichier ](./assets/file-properties-outputs-4-6.png) {width="300" align="left"}

*Publish et afficher les fragments d’expérience d’une rubrique à partir de la section **Sorties**dans les **Propriétés du fichier**.*

Experience Manager Guides vous permet désormais de publier une rubrique ou ses éléments dans un fragment d’expérience. Vous pouvez créer un mappage JSON entre une rubrique ou ses éléments et un modèle de fragment d’expérience. Vous pouvez également créer des variations de fragments d’expérience à l’aide des filtres de condition.

Découvrez comment [Fragments d’expérience Publish](../user-guide/publish-experience-fragment.md).



### Améliorations de la publication de fragments de contenu

Experience Manager Guides fournit également quelques améliorations utiles dans les fragments de contenu :

- Experience Manager Guides vous permet de publier une rubrique ou ses éléments dans un fragment de contenu.

- Vous pouvez publier et afficher les fragments de contenu d’une rubrique à partir de la section **Sorties** dans les **Propriétés du fichier**.


- Vous pouvez facilement créer des variations de fragment de contenu en filtrant le contenu avec des conditions lors de la publication sur un fragment de contenu.

- Utilisez la nouvelle interface de mappage pour sélectionner et publier facilement les éléments dans un fragment de contenu.

Désormais, la publication de fragments de contenu remplace uniquement le contenu mappé au lieu d’écraser l’intégralité du fragment de contenu. Cette fonctionnalité permet à un fragment de contenu de contenir des données provenant de plusieurs sources, telles que plusieurs rubriques ou l’éditeur de fragment de contenu.

![Ajoutez le modèle de fragment et les détails de mappage dans la boîte de dialogue Publish en tant que fragment de contenu](assets/content-fragment-mapping.png)

Pour plus d’informations, voir [Fragments de contenu Publish](../user-guide/publish-content-fragment.md).

### Réorganisation du paramètre prédéfini AEM Sites pour en faciliter l’utilisation

Les paramètres ont été réorganisés afin de vous aider à configurer rapidement le paramètre prédéfini de sortie et à générer la sortie AEM Sites.
Vous pouvez créer les paramètres prédéfinis AEM Sites existants en sélectionnant l’option **Utiliser le mappage de composant hérité** dans la boîte de dialogue **Nouveau paramètre prédéfini de sortie** .

Affichez les onglets **Général**, **Contenu** et **Référence de mappage croisé** dans les paramètres prédéfinis AEM Sites :
- **Général** : contient les configurations générales pour générer la sortie. Vous pouvez spécifier le site et le chemin de sortie, supprimer ou remplacer les pages de sortie existantes, supprimer les pages précédemment générées pour les rubriques supprimées, sélectionner le modèle de conception, conserver les fichiers temporaires et spécifier le workflow de post-génération.
- **Contenu** : contient les paramètres applicables au contenu pour la génération de sortie. Vous pouvez sélectionner les filtres, la ligne de base du mappage DITA et les propriétés de métadonnées pour la publication.
- **Références de mappage croisé** : cette liste contient des rubriques contenant des références de mappage croisé avec portée =&quot;peer&quot;. Vous pouvez spécifier le contexte de publication d’une liste de références croisées avec scope=&quot;peer&quot; pour les rubriques disponibles dans d’autres mappages DITA. Cet onglet s’affiche si vous utilisez la version Experience Manager Guides (UUID).



### Références de mappage croisé à partir de paramètres prédéfinis AEM Sites dans l’éditeur web

La dernière amélioration apportée à Experience Manager Guides introduit des références croisées dans les paramètres prédéfinis AEM Sites de l’éditeur web.
Les références de mappage croisé dans Experience Manager Guides permettent d’améliorer la navigation du contenu, d’augmenter la réutilisation du contenu et d’améliorer l’expérience utilisateur.


Vous pouvez spécifier le contexte de publication pour une liste de références croisées à des rubriques disponibles dans d’autres mappages DITA avec scope=&quot;peer&quot;. Par exemple, la rubrique 1 de la carte A contient une référence à la rubrique 2. La rubrique 2 peut être présente dans une ou plusieurs cartes.  Vous pouvez sélectionner le mappage parent et un paramètre prédéfini spécifique ou la sortie publiée le plus récemment pour chaque lien.

Si la même rubrique est référencée plusieurs fois dans un fichier, vous pouvez ajouter un contexte de publication différent pour chaque instance. Vous bénéficiez ainsi d’une plus grande flexibilité et d’un meilleur contrôle sur leur contenu. Par exemple, la rubrique 3 est présente dans les cartes B et C. La rubrique 1 contient deux références à la rubrique 3. Vous pouvez choisir la carte B comme mappage parent pour le premier lien et la carte C comme parent pour le second lien.

![Paramètre prédéfini AEM Sites hérité](assets/aem-sites-legacy.png)

*Spécifiez le contexte de publication pour les rubriques liées à partir de l’onglet **Références croisées**du paramètre prédéfini **AEM Sites**.*






### Possibilité de transmettre des métadonnées des propriétés de fichier de rubrique à la sortie de PDF natif.

Désormais, Experience Manager Guides vous permet d’ajouter les métadonnées des propriétés de fichier d’une rubrique aux mises en page lors de la génération de la sortie du PDF natif. Utilisez cette fonction pour ajouter des métadonnées spécifiques à une rubrique, telles que le titre, les balises et la description, aux mises en page. Vous pouvez également personnaliser votre PDF publié en fonction des métadonnées de la rubrique, par exemple en ajoutant un filigrane à l’arrière-plan de la rubrique en fonction de l’état du document de la rubrique.

![ajouter des métadonnées PDF natives](./assets/add-metadata-native-pdf.png) {width="300" align="left"}

*Ajoutez des métadonnées aux champs dans les mises en page de votre page.*

Découvrez comment [ajouter des champs et des métadonnées](../native-pdf/design-page-layout.md#add-fields-metadata) dans une mise en page.





### Prise en charge des documents Markdown dans la publication en PDF natif

Experience Manager Guides prend également en charge les documents Markdown dans la publication en mode natif dans PDF. Cette fonctionnalité est pratique et vous aide à générer des PDF pour les fichiers Markdown dans votre mappage DITA.

Pour plus d’informations, consultez la [prise en charge des documents Markdown](../web-editor/native-pdf-web-editor.md#support-for-markdown-documents).


### Téléchargez le fichier temporaire lors de la génération de la sortie via DITA-OT.

Vous pouvez également télécharger les fichiers temporaires générés lorsque vous publiez la sortie AEM Sites, HTML, Personnalisé, JSON ou PDF via DITA-OT. Cette fonctionnalité vous aide à analyser les problèmes qui peuvent se produire pendant le processus de génération de sortie et à résoudre les problèmes de manière efficace.  
Vous pouvez également télécharger le fichier metadata.xml si vous avez sélectionné des propriétés de métadonnées qui ont été transmises à la sortie générée à l’aide de DITA-OT. 

Pour plus d’informations sur les paramètres prédéfinis, voir [Présentation des paramètres prédéfinis de sortie](../user-guide/generate-output-understand-presets.md).


### Option permettant de choisir une hiérarchie de fichiers plate ou imbriquée pour la sortie HTML5

Désormais, Experience Manager Guides vous permet de conserver l’arborescence des dossiers plats pour les fichiers temporaires, dans laquelle l’ensemble du contenu est publié au format de sortie HTML5 et enregistré dans un seul dossier.
Si vous ne choisissez pas d’aplatir la hiérarchie de fichiers, la sortie HTML5 est générée dans une hiérarchie de dossiers imbriquée. Cela signifie que la structure de dossiers d’origine du contenu, avec des fichiers organisés en sous-dossiers, est répliquée dans la sortie. Cette hiérarchie de dossiers imbriqués permet une organisation et une catégorisation des fichiers plus complexes, ce qui facilite la gestion et la navigation de grands volumes de données.


En savoir plus sur la [génération de sortie HTML5](../user-guide/generate-output-html5.md)


## Améliorations de l’éditeur

Les améliorations de l’éditeur suivantes ont été ajoutées à la version 4.6.0 :

### Accès en lecture seule aux modes Auteur et Source pour les fichiers verrouillés

Si un fichier DITA ou Markdown est verrouillé ou extrait par un autre utilisateur, vous ne pouvez pas modifier le contenu. Outre l’aperçu, vous pouvez également l’afficher sous la forme d’un fichier en lecture seule en mode Auteur ou Source .
En mode lecture seule, vous pouvez afficher le contenu avec les balises et les attributs dans le mode **Auteur** ou **Source** et modifier les propriétés du fichier.

Vous pouvez également accéder à la vue **Disposition** pour les mappages DITA en lecture seule.
>[!NOTE]
>
> Les administrateurs de votre profil de dossier doivent mettre à jour *ui_config.json* afin que vous puissiez accéder harmonieusement aux fichiers en lecture seule dans les modes Auteur, Source et Mise en page.

![Éditeur de fichiers verrouillé](./assets/locked-file-editor.png)
*Affichez les fichiers verrouillés en mode Auteur et Source.*


Découvrez comment [ouvrir des fichiers verrouillés en modes Auteur et Source](../user-guide/web-editor-edit-topics.md#open-locked-files-in-author-and-source-modes).



### Sélection de contenu partiel pour les éléments d’opérations

Experience Manager Guides améliore votre expérience de sélection du contenu dans les éléments de l’éditeur web. Vous pouvez facilement sélectionner le contenu parmi différents éléments et effectuer des opérations, comme le mettre en gras, en italique ou souligné.

Cette fonctionnalité vous permet d’appliquer ou de supprimer facilement la mise en forme d’un contenu partiellement sélectionné. Vous pouvez également supprimer rapidement le contenu que vous avez sélectionné dans plusieurs éléments. Une fois le contenu supprimé, au besoin, le contenu restant est automatiquement fusionné sous un seul élément valide. Vous pouvez également sélectionner du contenu partiel sur plusieurs éléments, puis entourer le contenu sous un élément DITA valide.

Globalement, ces améliorations offrent une meilleure expérience et vous aident à améliorer votre efficacité lors de la modification de vos documents.
Pour plus d’informations, voir [Sélection partielle de contenu sur l’élément ](../user-guide/web-editor-edit-topics.md#partial-selection-of-content-across-elements).



### Liste segmentée pour afficher et insérer des éléments valides en fonction de leur position

Lors de la modification d’un document dans l’éditeur web, vous pouvez désormais afficher une liste séparée d’éléments valides à l’emplacement actuel et en dehors de l’emplacement actuel. Selon vos besoins, vous choisissez un élément parmi les options suivantes :

- **Éléments valides à l’emplacement actuel** que vous pouvez insérer à l’emplacement actuel du curseur lui-même.
- **Éléments valides en dehors de l’emplacement actuel** que vous pouvez insérer après l’un des parents de l’élément actuel dans la hiérarchie des éléments.

![Boîte de dialogue Insérer un élément](assets/insert-element-dialog.png){width="300" align="left"}

*Affichez les listes séparées d’éléments valides pour insérer un élément à l’emplacement actuel.*


Cette liste divisée d’éléments valides vous aide à conserver la structure de contenu et à respecter les normes DITA.

En savoir plus sur la fonction **Insérer l’élément** dans la section [Barre d’outils Secondaire](../user-guide/web-editor-features.md#2051ea0j0y4) .


### Expérience restructurée pour rechercher et filtrer des fichiers dans la vue du référentiel

Le filtrage des fichiers est maintenant amélioré. La redéfinition de la fonctionnalité de filtrage des fichiers facilite les recherches et la navigation dans les fichiers.


![Recherche de fichiers dans la vue du référentiel](assets/repository-filter-search-2404.png){width="300" align="left"}

*Rechercher des fichiers contenant le texte « `general purpose.`* »

Profitez d’avantages tels qu’un accès plus rapide aux fichiers importants et une interface utilisateur plus intuitive. Votre expérience de recherche devient plus fluide et plus efficace.

![ ](assets/repository-filter-search-quick.png) {width="300" align="left"} filtre de recherche rapide

*Utilisez les filtres rapides pour rechercher des fichiers DITA et non DITA.*


>[!NOTE]
>
> Les administrateurs de votre profil de dossier doivent mettre à jour *ui_config.json* afin que vous puissiez accéder harmonieusement à cette fonctionnalité.

En savoir plus sur la fonction **Filtrer la recherche** dans la section [Panneau de gauche](../user-guide/web-editor-features.md#id2051EA0M0HS).

### Conditions groupées pour une organisation de contenu améliorée

Experience Manager Guides vous permet désormais de regrouper des conditions et de les présenter dans une hiérarchie imbriquée, ce qui vous permet d’ajouter plusieurs conditions à un seul groupe. En regroupant les conditions, vous pouvez mieux les organiser et les appliquer dans l’ensemble de votre contenu.

![conditions organisées dans une hiérarchie imbriquée](assets/conditions-nested-hierarchy.png){width="300" align="left"}

Pour en savoir plus sur la description de la fonction **Conditions** dans la section [Panneau de gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .

### Personnalisation de l’expérience de l’éditeur web à l’aide d’une nouvelle interface utilisateur de préférences utilisateur

La boîte de dialogue **Préférences utilisateur** de l’éditeur web comprend désormais un nouvel onglet **Apparence**. Ce nouvel onglet vous permet de configurer facilement les préférences d’apparence les plus courantes de l’interface de l’éditeur web.

Vous pouvez configurer pour afficher les fichiers par titre ou par nom de fichier, et modifier le thème de l’application et la vue source. Il vous permet également de configurer les paramètres pour localiser un fichier ouvert dans la vue du référentiel et de gérer les espaces insécables.

![onglet apparence des préférences utilisateur](assets/user_preference_editor_appearance.png){width="550" align="left"}

*Personnalisez l’aspect selon vos préférences.*

Pour en savoir plus sur la description de la fonctionnalité **Préférences utilisateur** dans la section [Panneau de gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .


### Localisez un fichier ouvert dans la vue du référentiel de l’éditeur Web.

Sélectionnez l’option **Toujours localiser les fichiers dans le référentiel** dans les **Préférences utilisateur** pour naviguer rapidement et localiser votre fichier dans la vue du référentiel. Vous n’avez pas à le rechercher manuellement.

Lors de la modification, cette fonctionnalité vous permet également d’afficher facilement l’emplacement du fichier dans la hiérarchie du référentiel.

Pour plus d’informations, consultez [recherchez un fichier ouvert dans la vue de référentiel](../user-guide/web-editor-edit-topics.md#locate-an-open-file-in-the-repository-view).

### Amélioration de la gestion des espaces insécables dans l’éditeur web

Experience Manager Guides vous permet d’afficher un indicateur d’espace insécable lors de la modification de documents dans l’éditeur web. Il améliore également la gestion des espaces insécables.
Il convertit plusieurs espaces blancs consécutifs en un seul espace afin de conserver la vue WYSIWYG du document dans l’éditeur web. Cette fonctionnalité contribue également à améliorer l’aspect général et le professionnalisme du document.


Pour plus d’informations, consultez les [autres fonctionnalités de l’éditeur web](../user-guide/web-editor-other-features.md).


### Possibilité d’afficher les propriétés d’un élément à partir de la hiérarchie d’éléments

Désormais, les propriétés de contenu **Type** s’affichent dans un menu déroulant. Vous pouvez afficher et sélectionner les balises de la hiérarchie complète de la balise active dans la liste déroulante.

Ce menu déroulant vous permet d’accéder rapidement aux propriétés de contenu de la balise sélectionnée.


![menu déroulant de type dans les propriétés de contenu](assets/content-properties-type.png){width="300" align="left"}

*Sélectionnez une balise dans la hiérarchie pour la balise actuelle.*

Pour en savoir plus sur la fonction **Propriétés du contenu** dans la section [Panneau de droite](../user-guide/web-editor-features.md#id2051eb003yk) .



### Amélioration des performances lors de l’archivage des fichiers en masse à partir de l’éditeur de cartes

Experience Manager Guides améliore les performances et l’expérience de la fonction d’archivage de fichiers en masse à partir de l’éditeur de cartes. Cette amélioration vous permet d’archiver plus rapidement les fichiers en bloc.
Vous pouvez également afficher la progression de l’opération d’archivage pour les fichiers à partir de la boîte de dialogue **Enregistrer comme nouvelle version et Déverrouiller**. Enfin, le message de réussite s’affiche une fois l’opération terminée et tous les fichiers extraits sont archivés.

![Enregistrer comme nouvelle version et déverrouiller la boîte de dialogue](./assets/save-version-lock.png){width="300" align="left"}

*Affichez la liste et l’état des fichiers archivés en bloc à partir de l’éditeur de cartes.*

Découvrez comment [travailler avec l’éditeur de carte avancé](../user-guide/map-editor-advanced-map-editor.md)





## Améliorations de la gestion du cycle de vie du contenu

La gestion du cycle de vie du contenu a été améliorée comme suit :

### Possibilité de traduire du contenu dans plusieurs langues à l’aide de groupes de langues préconfigurés

Experience Manager Guides permet désormais de créer des groupes de langues et de traduire facilement votre contenu dans plusieurs langues. Cette fonctionnalité permet d’organiser et de gérer les traductions en fonction des besoins de votre organisation.

Par exemple, si vous devez traduire votre contenu pour certains pays d’Europe, vous pouvez créer un groupe de langues pour les langues européennes telles que l’anglais (EN), le français (FR), l’allemand (DE), l’espagnol (ES) et l’italien (IT).



![Panneau de traduction](assets/translation-languages-2404.png){width="300" align="left"}

*Sélectionnez les groupes de langues ou les langues que vous souhaitez traduire vos documents.*

>[!NOTE]
>
>Si le dossier cible d’une langue est manquant ou si la langue cible est identique à la langue source, elle est grisée et un signe d’avertissement est affiché.

En tant qu’administrateur ou administratrice, vous pouvez créer des groupes de langues et les configurer sur plusieurs profils de dossiers. En tant qu’auteur ou autrice, vous pouvez afficher les groupes de langues configurés sur votre profil de dossier.


Dans l’ensemble, la création de groupes de langues renforce l’efficacité et la productivité des projets de traduction, améliorant ainsi le processus de localisation dans plusieurs langues.


Découvrez comment [traduire des documents à partir de l’éditeur Web](../user-guide/translate-documents-web-editor.md).


### Amélioration des performances et de l’évolutivité pour les projets de traduction volumineux

La fonction de traduction est plus rapide et plus évolutive que jamais. Il s’accompagne d’une nouvelle architecture qui offre des performances améliorées. Le temps de création du projet est désormais plus rapide qu&#39;auparavant, et les conflits au cours du processus sont quasi inexistants. Cette amélioration des performances vous permet d’accélérer les traductions, ce qui garantit un fonctionnement fluide même pour les projets de traduction volumineux.

Cette amélioration est très bénéfique, car elle améliore la productivité et l’expérience globale.

Découvrez comment [traduire des documents à partir de l’éditeur Web](../user-guide/translate-documents-web-editor.md).

### Supprimer ou désactiver automatiquement le projet de traduction après la traduction

Désormais, en tant qu’administrateur, vous pouvez configurer les projets de traduction pour qu’ils soient désactivés ou supprimés automatiquement après avoir terminé la traduction. Cette fonctionnalité vous permet d’utiliser efficacement les ressources et de gérer les fichiers après avoir terminé la traduction.

La suppression d’un projet supprime définitivement tous les fichiers et dossiers présents dans le projet. La suppression des projets de traduction permet également de libérer l’espace disque occupé.

Vous pouvez désactiver les projets de traduction si vous souhaitez les utiliser ultérieurement.

![](assets/editor-setting-translation.png){width="550" align="left"}


*Configurez les groupes de langues et les paramètres de nettoyage pour les projets de traduction.*


Découvrez comment [supprimer ou désactiver automatiquement le projet de traduction](../user-guide/translate-documents-web-editor.md#automatically-delete-or-disable-a-completed-translation-project).


### Désactivation du post-traitement pour les dossiers sélectionnés sur Adobe Experience Manager Assets


En tant qu’administrateur, vous pouvez désormais désactiver le post-traitement et la génération des UUID pour les dossiers sélectionnés sur Experience Manager Assets. Cette configuration peut s’avérer utile, en particulier lorsque vous traitez de nombreuses ressources ou de structures de dossiers complexes. Cela permet également à plusieurs utilisateurs de charger rapidement les ressources simultanément sans interférer les uns avec les autres.  

La désactivation du post-traitement d’un dossier affecte également tous ses dossiers enfants. Toutefois, Experience Manager Guides offre désormais la possibilité d’activer le posttraitement sélectif pour des dossiers enfants individuels dans le dossier ignoré.

Découvrez comment [désactiver le posttraitement pour un dossier](../cs-install-guide/conf-folder-post-processing.md).


## Améliorations des connecteurs de source de données

Les améliorations suivantes ont été apportées aux connecteurs de sources de données dans la version 2024.4.0 :

### Connexion aux sources de données Salsify, Akeneo et Microsoft Azure Dev Ops Board (ADO)

Outre les connecteurs prêts-à-l’emploi existants, Experience Manager Guides fournit également des connecteurs pour les sources de données Salsify, Akeneo et Microsoft Azure DevOps (ADO) Boards. En tant qu’administrateur ou administratrice, vous pouvez télécharger et installer ces connecteurs. Configurez ensuite les connecteurs installés.

### Copiez et collez l’exemple de requête pour créer un fragment de contenu ou une rubrique.

Vous pouvez facilement copier et coller un exemple de requête de données dans le générateur pour créer un extrait de contenu ou une rubrique. Avec cette fonction, vous n’avez pas à mémoriser la syntaxe ni à créer une requête manuellement. Au lieu de saisir une requête manuellement, vous pouvez copier et coller un exemple de requête, le modifier et l’utiliser pour récupérer des données selon vos besoins.

![Boîte de dialogue Insérer un extrait de contenu](assets/insert-content-snippet.png){width="800" align="left"}

*Copiez et modifiez un exemple de requête pour créer l’extrait de contenu.*

### Connexion aux fichiers de données JSON à l’aide d’un connecteur de fichier


Désormais, en tant qu’administrateur ou administratrice, vous pouvez configurer un connecteur de fichier JSON pour qu’il utilise les fichiers de données JSON comme source de données. Utilisez le connecteur pour importer les fichiers JSON de votre ordinateur ou d’Adobe Experience Manager Assets. Ensuite, en tant qu’auteur ou autrice, vous pouvez créer des extraits de contenu ou des rubriques à l’aide des générateurs.

Cette fonctionnalité vous permet d’utiliser les données stockées dans vos fichiers JSON et de les réutiliser dans divers extraits de code. Le contenu est également mis à jour de manière dynamique à chaque fois que vous actualisez les fichiers JSON.

### Configuration de plusieurs URL de ressource pour un connecteur afin de créer des fragments de contenu ou des rubriques

En tant qu’administrateur, vous pouvez configurer plusieurs URL de ressources pour certains connecteurs tels que Generic REST Client, Salsify, Akeneo et Microsoft Azure DevOps Board (ADO).

Ensuite, en tant qu’auteur ou autrice, connectez-vous aux sources de données pour créer des extraits de contenu ou des rubriques à l’aide des générateurs. Cette fonctionnalité est pratique, car vous n’avez pas à créer de source de données pour chaque URL. Il vous permet de récupérer rapidement des données à partir de l’une des ressources d’une source de données spécifique dans un seul fragment de contenu ou une seule rubrique.

Affichez plus d’informations sur les connecteurs de source de données et sur la [configuration d’un connecteur de source de données à partir de l’interface utilisateur](../cs-install-guide/conf-data-source-connector-tools.md).

Découvrez comment [utiliser les données de votre source de données](../user-guide/web-editor-content-snippet.md).

