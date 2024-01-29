---
title: Notes de mise à jour | Nouveautés de la version 4.4.0 des guides Adobe Experience Manager
description: Découvrez les nouvelles fonctionnalités et les fonctionnalités améliorées de la version 4.4.0 des Guides Adobe Experience Manager
source-git-commit: 027e8e6a6119145a5b2255449514a76488c90463
workflow-type: tm+mt
source-wordcount: '2307'
ht-degree: 0%

---

# Nouveautés de la version 4.4.0 des guides Adobe Experience Manager (janvier 2024)

Cet article couvre les nouvelles fonctionnalités et les fonctionnalités améliorées de la version 4.4.0 des Guides Adobe Experience Manager (ultérieurement appelées *Guides du Experience Manager*).

Pour plus d’informations sur les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans cette version, voir [Notes de mise à jour](./release-notes-4.4.md).

## Fonctionnalité d’historique des versions restructurée de l’éditeur web

Désormais, Experience Manager Guides fournit une fonctionnalité d’historique des versions améliorée qui vous permet de comparer les modifications apportées à un document au fil du temps. Dans la nouvelle vue côte à côte, vous pouvez facilement comparer le contenu et les métadonnées de la version actuelle à n’importe quelle version précédente du même document. Vous pouvez également afficher les libellés et les commentaires pour les versions comparées. En tant qu’administrateur, vous pouvez contrôler les métadonnées de version de la rubrique et leurs valeurs à afficher dans le **Historique des versions** de la boîte de dialogue

![Boîte de dialogue Historique des versions](assets/version-history-dialog-web-editor.png){width="800" align="left"}
*Prévisualisez les modifications dans les différentes versions d’une rubrique.*


En savoir plus sur les **Historique des versions** description des fonctionnalités dans la section [Panneau gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .

## Gestion des paramètres de condition prédéfinis

Vous pouvez définir des attributs de condition dans vos rubriques DITA. Ensuite, utilisez les attributs de condition dans le paramètre prédéfini de condition pour publier le contenu dans un mappage DITA. Les guides du Experience Manager offrent désormais une expérience enrichie dans l’éditeur web, ce qui vous permet de créer et de gérer plus efficacement les paramètres prédéfinis de condition. Vous pouvez également facilement les modifier, les dupliquer ou les supprimer.

![Paramètres prédéfinis de condition de l’onglet Gérer de l’éditeur web ](assets/web-editor-manage-condition-presets.png){width="550" align="left"}

Pour plus d’informations, voir [Utiliser des paramètres prédéfinis de condition](../user-guide/generate-output-use-condition-presets.md).

## Expérience restructurée pour modifier les attributs

Vous obtenez maintenant une expérience repensée pour ajouter ou modifier les attributs d’un élément à partir de la fonction **Propriétés du contenu** dans l’éditeur Web.

![Panneau Attributs](assets/attributes-multiple-properties.png){width="300" align="left"}

*Ajoutez des attributs dans le panneau Propriétés du contenu .*

Vous pouvez également facilement modifier et supprimer les attributs.
Pour plus d’informations, reportez-vous au **Propriétés du contenu** description des fonctionnalités dans la section [Panneau droit](../user-guide/web-editor-features.md#id2051EB003YK) .

## Modification des métadonnées lors de la création

Désormais, lors de la création, vous pouvez mettre à jour les balises de métadonnées de fichier à l’aide de la liste déroulante du **Propriétés du fichier** dans le panneau de droite. Vous pouvez également sélectionner **Modification d’autres propriétés** pour mettre à jour d’autres métadonnées.

![file-properties](assets/file-properties-general.png){width="300" align="left"}

*Mettez à jour les métadonnées et modifiez les propriétés du fichier à partir du panneau de droite.*

Pour plus d’informations, reportez-vous au **Propriétés du fichier** description des fonctionnalités dans la section [Panneau droit](../user-guide/web-editor-features.md#id2051EB003YK) .

## Affichage des attributs clés dans la vue Carte

Lorsque vous définissez des attributs clés pour la rubrique ou les références de mappage, vous pouvez également afficher le titre, l’icône correspondante et la clé dans le panneau de gauche. La clé s’affiche sous la forme `key=<key-name>`.

![clés dans la vue map](assets/view-key-title-map-view.png) {width="300" align="left"}

*Affichez l’attribut de clé dans la vue Carte.*


Pour plus d’informations, reportez-vous au **Vue Carte** description des fonctionnalités dans la section [Panneau gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .

## Possibilité de dupliquer une ligne de base en fonction d’un libellé

Les guides de Experience Manager offrent désormais une expérience utilisateur améliorée pour la création de lignes de base à partir de l’éditeur web.
Les options **Mise à jour manuelle** et **Mise à jour automatique** sont plus intuitifs et vous aident à choisir facilement entre la création d’une ligne de base statique ou sa mise à jour automatique en fonction des libellés.

![créer une nouvelle ligne de base](assets/dynamic-baseline-4-4.png) {width="300" align="left"}
*Créez une ligne de base à partir de l’éditeur web.*

Il permet également de dupliquer une ligne de base en fonction du libellé. La version de référence est sélectionnée en fonction du libellé donné (s’il existe) lors de la duplication ou sélectionne la version à partir de la ligne de base dupliquée.


![duplication d’une ligne de base ](assets/duplicate-baseline.png) {width="300" align="left"}

*Dupliquez une ligne de base à partir d’un libellé ou créez une copie exacte.*

En savoir plus sur la manière de procéder [créer et gérer des lignes de base à partir de l’éditeur Web ;](../user-guide/web-editor-baseline.md).

## Tableau de bord amélioré de la collecte des cartes

Experience Manager Guides fournit un tableau de bord de collecte de cartes amélioré. Dans une collection de mappages, vous pouvez rapidement configurer les propriétés de métadonnées en bloc pour les mappages DITA. Cette fonctionnalité est pratique, car vous n’avez pas à mettre à jour les propriétés de métadonnées pour chaque mappage DITA individuellement.

Vous pouvez désormais afficher le nom de fichier du mappage DITA. Vous pouvez également afficher les lignes de base. Vous pouvez ainsi trouver rapidement la ligne de base utilisée pour un paramètre prédéfini.

![Tableau de bord de la collecte des cartes](assets/map-collection-dashboard.png){width="800" align="left"}

*Affichez, modifiez et générez la sortie à partir du tableau de bord de la collection de mappages.*

Découvrez comment [Utilisation de la collecte des cartes pour la génération de sortie](../user-guide/generate-output-use-map-collection-output-generation.md).

## Panneau Traduction amélioré

La variable **Traduction** a été amélioré.  Vous pouvez afficher la **Langues disponibles** répertoriez et sélectionnez rapidement les paramètres régionaux dans lesquels vous souhaitez traduire votre projet. Avec une sélection unique, vous pouvez également choisir **Tout sélectionner** pour traduire votre projet dans toutes les langues disponibles.

![panneau de traduction](assets/translation-languages-4.4.png){width="300" align="left"}



*Sélectionnez les paramètres régionaux dans lesquels vous souhaitez traduire votre projet. Choisissez la version par défaut, la ligne de base ou la dernière version des fichiers à traduire.*

En savoir plus sur la manière de procéder [traduire le contenu](../user-guide/translation.md).

## Amélioration de la logique de recherche dans la boîte de dialogue Insérer l’élément

Vous pouvez désormais facilement trouver les éléments dans la boîte de dialogue Insérer un élément .  Vous pouvez saisir une chaîne dans la zone de recherche et obtenir la liste de tous les éléments valides qui commencent par la chaîne saisie.

Par exemple, lors de la modification d’un paragraphe que vous souhaitez insérer, vous pouvez rechercher un caractère &quot;t&quot; pour obtenir tous les éléments valides commençant par &quot;t&quot;.


![Boîte de dialogue Insérer](assets/insert-element.png){width="300" align="left"}

*Saisissez un caractère pour rechercher tous les éléments valides commençant par le caractère.*


Pour plus d’informations, voir la **Insérer un élément** description des fonctionnalités dans la section [Panneau gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .


## Possibilité de diviser une liste au même niveau

Vous pouvez désormais facilement fractionner votre liste dans l’éditeur Web. Sélectionnez la variable **Diviser la liste** dans le menu contextuel d’un élément de liste pour fractionner la liste active. Une nouvelle liste est créée au même niveau, en commençant par l’élément de liste que vous avez sélectionné pour le partage.

![panneau de traduction](assets/context-menu-split-list.png){width="300" align="left"}

*Sélectionnez l’option pour fractionner la liste active.*

Pour plus d’informations, voir la **Insérer une liste** description des fonctionnalités dans la section [Panneau gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .

## Extraire facilement les éléments DITA

Vous pouvez désormais facilement renvoyer à la ligne un élément à l’aide de l’option du menu contextuel d’un élément dans l’éditeur web. Vous pouvez ainsi facilement fusionner le texte de l’élément avec son élément parent.
Pour plus d’informations, voir la **Extraire un élément** de la section [autres fonctionnalités de l’éditeur web](../user-guide/web-editor-other-features.md).

## Accès aux propriétés de fichier dans le mode source de création

Vous pouvez maintenant accéder au **Propriétés du fichier** dans les quatre modes ou modes : Disposition, Auteur, Source et Aperçu.  Vous pouvez ainsi afficher les propriétés de votre fichier même lorsque vous passez d’un mode à l’autre.

Pour plus d’informations, voir la **Propriétés du fichier** description des fonctionnalités dans la section [Panneau droit](../user-guide/web-editor-features.md#id2051EB003YK) .


## Affichage des fichiers par titre ou par nom de fichier

Vous pouvez désormais choisir la méthode par défaut pour afficher les fichiers dans l’éditeur Web. Vous pouvez afficher la liste des fichiers selon les titres ou les noms des fichiers dans les différents panneaux depuis la vue Auteur.

![Boîte de dialogue Préférences utilisateur](assets/user-preferences-2311.png){width="550" align="left"}

*Modifiez la manière par défaut d’afficher les fichiers à partir de la fonction **Préférences utilisateur**boîte de dialogue.*


## Restaurer les onglets de fichier lors de l’actualisation du navigateur

Experience Manager Guides restaure l’état des onglets de fichiers ouverts dans l’éditeur web lorsque vous actualisez le navigateur. Pour plus d’informations, voir la **Actualiser le navigateur lors de la modification des fichiers** section sous [Modification des rubriques dans l’éditeur web](../user-guide/web-editor-edit-topics.md).


## Possibilité de naviguer à l’aide des raccourcis clavier

Les guides du Experience Manager vous permettent désormais d’utiliser des raccourcis clavier pour déplacer le curseur dans l’éditeur web. Vous pouvez utiliser les raccourcis clavier pour déplacer rapidement un mot vers la gauche ou la droite. Vous pouvez également passer au début ou à la fin de la ligne à l’aide des raccourcis clavier.
Désormais, vous pouvez également utiliser des raccourcis clavier pour déplacer le curseur au début de l’élément suivant ou à la fin de l’élément précédent.
En savoir plus sur les [raccourcis clavier dans l’éditeur web](../user-guide/web-editor-keyboard-shortcuts.md).


## Résoudre les liens croisés dans la sortie AEM site

Les liens croisés (XREF avec portée homologue) générés dans la sortie AEM site sont désormais résolus en fonction du titre du fichier du jeu de contexte de publication pour la carte générée.


## Configurez l’URL de la sortie Site AEM pour utiliser le titre du document.

Les guides du Experience Manager vous permettent, en tant qu’administrateur, de configurer l’URL de la sortie du site AEM. Si le nom de fichier n’existe pas ou contient tous les caractères spéciaux, vous pouvez le remplacer par un séparateur dans l’URL de la sortie Site AEM. Vous pouvez également les remplacer par le nom de la première rubrique enfant. Découvrez comment [configurer l’URL de la sortie Site AEM pour utiliser le titre du document ;](../cs-install-guide/conf-output-generation.md#configure-the-url-of-the-aem-site-output-to-use-the-document-title).


## Publication de plusieurs paramètres prédéfinis de sortie en parallèle

Experience Manager fournit la fonctionnalité permettant de créer des lignes de base en sélectionnant automatiquement les rubriques en fonction du libellé qui leur est appliqué. Vous pouvez désormais également publier en toute transparence plusieurs paramètres prédéfinis de sortie avec des lignes de base automatiques d’un même mappage DITA. Vous n’avez pas à publier un seul paramètre prédéfini à la fois, mais vous pouvez facilement publier plusieurs paramètres prédéfinis de sortie en parallèle.

En savoir plus sur la manière de procéder [créer et gérer des lignes de base à partir de l’éditeur Web ;](../user-guide/web-editor-baseline.md).

## Améliorations apportées aux PDF natifs

Les améliorations suivantes ont été apportées au PDF natif dans la version 4.4.0 :

### Utiliser des variables dans la sortie du PDF

Vous pouvez utiliser des variables pour insérer et gérer dynamiquement des informations réutilisables. Les guides de Experience Manager vous aident à créer, modifier et prévisualiser des variables lorsque vous générez la sortie du PDF. Vous pouvez modifier rapidement les valeurs des variables et rendre vos documents portables et faciles à mettre à jour.

![variables pdf natives](assets/add-variable-default.png){width="800" align="left"}

*Créez et gérez des variables dans l’éditeur web.*

Vous pouvez également créer des ensembles de variables qui remplacent les valeurs par défaut et affecter d’autres valeurs à vos variables. Insérez ces variables dans la mise en page et utilisez la même mise en page de PDF. Il n’est pas nécessaire de créer des mises en page distinctes pour chaque ensemble de valeurs. Par exemple, vous pouvez créer un jeu de variables pour chaque version de produit. Ce jeu de variables peut être constitué de variables pour différents détails de produit, tels que le nom, le numéro de version et la date de publication du produit. Vous pouvez ensuite ajouter différentes valeurs pour ces variables.

**Jeu de variables 1 : Adobe-set1**

* ProductName : guides du Experience Manager
* VersionNumber : 2311
* Date de publication : 11/02/2023

**Jeu de variables 2 : Adobe-set2**

* ProductName : guides du Experience Manager
* VersionNumber : 2310
* Date de publication : 09/27/2023



<img src="./assets/native-pdf-variable-output.png" alt="Pied de page en sortie du PDF" width="500" border="2px">

*Générez la sortie du PDF à l’aide de variables dans la mise en page du PDF.*

Vous pouvez appliquer des styles et utiliser des balises de HTML pour formater les variables.  Vous pouvez également mettre rapidement à jour les valeurs de toutes les variables, le cas échéant, et générer à nouveau la sortie. Par exemple, si vous devez mettre à jour les détails d’une version, vous pouvez modifier la valeur de la version dans la variable VersionNumber et générer à nouveau la sortie.


En savoir plus sur l’utilisation [dans la sortie du PDF](../native-pdf/native-pdf-variables.md).


### Propagation des métadonnées de ressources à la sortie du PDF

Experience Manager permet désormais de transférer les propriétés de métadonnées des ressources du mappage DITA vers la sortie PDF.
Dans le paramètre prédéfini de sortie du PDF natif, vous pouvez choisir les métadonnées que vous souhaitez propager au processus de publication du PDF. Vous pouvez sélectionner les propriétés personnalisées et par défaut.  Les propriétés de métadonnées sélectionnées sont transférées vers le fichier de PDF généré à l’aide du PDF natif.

Cette fonctionnalité est pratique, car elle vous permet de préserver la cohérence de vos propriétés de ressources telles que l’auteur, la date de création ou le titre du document. Cela facilite l’organisation, la recherche et la catégorisation de vos documents.

Pour plus d’informations, voir la **Avancé** dans le [Sortie du PDF de publication](../web-editor/native-pdf-web-editor.md).

### Utilisation des métadonnées ajoutées dans la variable `topicmeta` élément pour la sortie du PDF

La fonction de métadonnées de la publication en PDF natif permet de gérer le contenu et de rechercher des fichiers sur Internet.
<img src="assets/pdf-metadata-4-4.png" alt="onglet de métadonnées" width="800">

*Sélectionnez une option pour ajouter et personnaliser des options de métadonnées.*

Les guides Maintenant Experience Manager permettent d’utiliser les métadonnées que vous avez ajoutées dans la `topicmeta` élément du mappage DITA pour renseigner les champs de métadonnées de la sortie du PDF. Cette option est sélectionnée par défaut.

Cette fonctionnalité permet une meilleure gestion des documents, garantit la cohérence et rend vos documents consultables.

Pour en savoir plus, consultez la **Métadonnées** dans le [Sortie du PDF de publication](../web-editor/native-pdf-web-editor.md).

### Utiliser et dupliquer des modèles de PDF prêts à l’emploi

Experience Manager Guides fournit des modèles de PDF prêts à l’emploi ou d’usine. Dupliquez les modèles de PDF d’usine pour créer les modèles de PDF personnalisés.

Vous pouvez désormais également prévisualiser la miniature d’un modèle lors de la création et de la duplication d’un modèle. Vous pouvez également modifier ou supprimer cette image. Cette fonction est utile pour marquer ou distinguer des modèles portant des noms similaires.
En savoir plus sur les [Modèle de PDF](../native-pdf/pdf-template.md).

![Boîte de dialogue Dupliquer le modèle de PDF](assets/duplicate-template.png){width="550" align="left"}

*Dupliquez un modèle de PDF existant.*


### Modifier l’ordre des pages et publier plusieurs pages par feuille

Outre la publication des pages en fonction du document source, vous pouvez modifier l’ordre des pages dans PDF lors de la publication d’un document de plusieurs pages.  Vous avez ainsi la possibilité de publier les pages dans différents ordres, comme toutes les pages impaires ou paires. Vous pouvez également publier en tant que brochure et lire les pages comme un livre. Vous pouvez également décider du nombre de pages que vous souhaitez publier sur une seule feuille de papier. Pour plus d’informations, voir la [Organisation de la page](../native-pdf/components-pdf-template.md#page-organization) .

### Tri des termes du glossaire à l’aide de clés de tri

Vous pouvez également trier les termes du glossaire à partir de touches de tri. Vous pouvez utiliser la balise &quot;sort-as&quot; pour définir une clé de tri pour les termes du glossaire. Vous pouvez ensuite les trier en fonction des clés de tri, plutôt que des termes. Vous pouvez ainsi trier les termes du glossaire en fonction de termes utilisés dans différentes langues. Vous pouvez également définir une clé de tri unique pour un terme de glossaire contenant une expression ou un groupe de mots.
Pour plus d’informations, voir la [Paramètres du PDF avancé](../native-pdf/components-pdf-template.md#advanced-pdf-settings).


### Amélioration de la gestion des ressources pour les modèles de PDF natif

Les guides du Experience Manager ont désormais amélioré la gestion des ressources pour les modèles de PDF natif. Vous pouvez désormais partager et réutiliser des ressources, telles que des images, des fichiers CSS et des fichiers de polices, sur plusieurs modèles de PDF natif. Avec cette amélioration, la gestion des ressources pour un grand ensemble de modèles est beaucoup plus simple. Vous n’avez pas besoin de créer des ressources en double pour chaque modèle. Vous pouvez également les conserver dans un dossier partagé et les utiliser dans tous les modèles de PDF natif.
Pour plus d’informations, voir [Modèle de PDF](../native-pdf/pdf-template.md).































