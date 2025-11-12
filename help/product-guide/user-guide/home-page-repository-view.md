---
title: Référentiel sur la page d’accueil
description: Découvrez le référentiel sur la page d’accueil d’. Découvrez l’interface et les fonctionnalités du référentiel dans Adobe Experience Manager Guides sur la page d’accueil.
feature: Authoring
role: User
source-git-commit: 1919e622b1b148d16bcdb85f79e2a1cd706fe33e
workflow-type: tm+mt
source-wordcount: '1298'
ht-degree: 0%

---

# Connaître l’interface du référentiel

Le référentiel sert d’espace centralisé pour améliorer la visibilité des dossiers et des fichiers. Il fournit une vue tabulaire complète des dossiers et des fichiers à plusieurs colonnes, offrant des détails contextuels pour tous les fichiers et ressources.

Cette interface unifiée simplifie plusieurs fonctions, notamment la création de fichiers ou de dossiers, la modification de fichiers, le chargement de ressources et la recherche de fichiers avec des options de filtrage robustes, assurant ainsi l’efficacité et la facilité d’utilisation.

![](images/repository-view-home.png){align="left"}

L’interface du référentiel est divisée en plusieurs sections :

- Barre de navigation du référentiel
- Vue tabulaire du référentiel

## Barre de navigation du référentiel

La barre de navigation Référentiel, située en haut de l’interface du référentiel, permet d’accéder rapidement aux actions essentielles répertoriées.

![](images/tab-bar-repository-view.png){align="left"}


- **Panneau de navigation Dossier** : affiche une arborescence hiérarchique de dossiers dans le référentiel pour une navigation transparente. Ce panneau affiche uniquement des informations au niveau du dossier. Lorsqu’un dossier est sélectionné à partir de là, son contenu, ses fichiers et ses sous-dossiers s’affichent dans la vue du référentiel. Vous pouvez afficher ou masquer ce panneau à l’aide de l’icône mise en surbrillance ci-dessous.

  ![](images/folder-navigation-panel.png){align="left"}

- **Chemin de navigation** : indique le chemin d’accès actuel dans le référentiel, indiquant la hiérarchie des dossiers menant à votre dossier actuel. Vous pouvez la sélectionner pour revenir à un dossier spécifique dans la hiérarchie.

  ![](images/breadcrumbs.png){width="650" align="left"}

- **Actualiser** : met à jour le référentiel pour prendre en compte les dernières modifications.
- **Télécharger Assets** : permet de charger des ressources directement dans le dossier actif, comme indiqué dans les chemins de navigation.
- **Nouveau** : permet la création de nouvelles rubriques, cartes et dossiers dans le dossier actif, comme indiqué dans les chemins de navigation.
- **Assistant IA** : puissant outil optimisé par l’IA, conçu pour améliorer votre productivité grâce à des fonctionnalités d’aide intelligentes. La fonctionnalité [Assistant AI](./ai-assistant.md) n’est actuellement disponible que pour Adobe Experience Manager as a Cloud Service.
- **Autres actions** : permet d’accéder à des options supplémentaires. Si vous sélectionnez ce bouton, un menu s’ouvre avec les options suivantes :
   - **Assets** : vous dirige vers une destination en fonction de votre configuration.
      - **Services cloud** : si vous utilisez des services cloud, la sélection de l’option **Assets** vous conduit à la page de navigation d’AEM.
      - **Logiciel On-premise** : si vous utilisez Adobe Experience Manager Guides (4.2.1 et versions ultérieures), la sélection de l’option **Assets** vous conduit au chemin d’accès actuel au fichier dans l’interface utilisateur d’Assets.
   - **Paramètres Workspace** : vous conduit à la boîte de dialogue **Paramètres Workspace**. Pour plus d’informations, consultez [Configuration des paramètres de Workspace](../cs-install-guide/workspace-settings.md).
- **Développer la vue** : permet de développer la page vue à l’aide de l’icône **Développer**. Dans cette vue, la barre d’en-tête est masquée, ce qui maximise l’espace de contenu. Pour revenir à la vue standard, utilisez l’icône Quitter la vue développée .

## Vue tabulaire du référentiel

Le Référentiel sert d’espace central et fournit une liste tabulaire de tous les dossiers et fichiers. Il offre les fonctionnalités suivantes :

- **Personnaliser** : vous pouvez modifier les colonnes affichées à l’aide de l’option **Personnaliser** située dans le coin supérieur droit de la vue Référentiel. Cette option vous permet d’afficher ou de masquer n’importe quelle colonne et de réorganiser les colonnes selon vos besoins. Les colonnes **Nom** ou **Titre** sont obligatoires et ne peuvent pas être désactivées ensemble. D’autres champs, tels que **Type de fichier**, **UUID**, **État du document**, **Verrouillé par**, **Créé le** et **Modifié le**, peuvent être activés ou désactivés si nécessaire. Vous pouvez les réorganiser en procédant simplement par glisser-déposer.

  ![](images/customize-repo-view.png){width="350" align="left"}

- **Redimensionnement des colonnes** : les colonnes peuvent être redimensionnées en sélectionnant des options dans le menu déroulant des colonnes.

- **Tri** : les colonnes Nom, Titre, Date de création et Dernière modification prennent en charge le tri par ordre croissant ou décroissant, accessible via leur menu déroulant de colonne.

- **Modification du fichier** :

   - Vous pouvez sélectionner un ou plusieurs fichiers de la liste à modifier.
   - Après avoir sélectionné les fichiers souhaités à l’aide de la case à cocher, l’option **Modifier** devient disponible dans le coin supérieur droit de la vue Référentiel.
   - Sélectionnez **Modifier** pour ouvrir le ou les fichiers sélectionnés dans l’interface de l’éditeur, où vous pouvez commencer à modifier le fichier.

     ![](images/edit-repo-view.png){align="left"}

- **Menu Options des dossiers** : vous pouvez effectuer les actions suivantes à l’aide du menu **Options** disponible pour un dossier :

  ![](images/options-folder-repo.png){width="350" align="left"}

   - **Nouveau** : créez une rubrique DITA, un plan DITA ou un dossier.
   - **Télécharger Assets** : chargez un fichier depuis votre système local vers le dossier sélectionné dans le référentiel.
   - **Ajouter aux collections** : ajoute le dossier sélectionné aux favoris. Vous pouvez choisir de l’ajouter à une collection existante ou nouvelle.
   - **Retraiter les ressources** : déclenche le traitement de toutes les ressources nouvellement créées et non traitées.

- **Menu Options des fichiers** : vous pouvez effectuer les actions suivantes à l’aide du menu **Options** d’un fichier :

  ![](images/options-file-repo.png){width="350" align="left"}

   - **Modifier** : ouvrez le fichier pour le modifier.
   - **Modifier dans Oxygen** : sélectionnez cette option pour modifier le fichier sélectionné dans le plug-in Oxygen Connector.

     >[!NOTE]
     >
     >Contactez votre équipe du succès client pour que cette fonctionnalité soit activée dans l’environnement. Cette fonctionnalité n’est pas activée dans le cadre de la prise en charge prête à l’emploi. Pour plus d&#39;informations, consultez la section [Configurer l&#39;option à modifier dans Oxygen](../cs-install-guide/conf-edit-in-oxygen.md) du Guide d&#39;installation et de configuration.

   - **Ouvrir dans la console de mappage** : si le fichier sélectionné est un mappage DITA, cette option ouvre la console de mappage.
   - **Ouvrir dans le tableau de bord des cartes** : si le fichier sélectionné est un plan DITA, cette option ouvre le tableau de bord des cartes.
   - **Verrouiller** : verrouillez le fichier sélectionné pour le modifier.
   - **Aperçu** : obtenez un aperçu rapide du fichier (.dita, .xml, audio, vidéo ou image) sans l’ouvrir.
   - **Dupliquer** : utilisez cette option pour créer un doublon ou une copie du fichier sélectionné.
   - **Déplacer vers** : utilisez cette option pour déplacer le fichier sélectionné vers un autre dossier.
   - **Renommer** : utilisez cette option pour renommer le fichier sélectionné.
   - **Supprimer** : utilisez cette option pour supprimer le fichier sélectionné.
   - **Ajouter à** : choisissez d’ajouter aux collections ou au contenu réutilisable.
   - **Copier** : copie l’UUID ou le chemin d’accès complet du fichier.
   - **Propriétés** : utilisez cette option pour ouvrir la page Propriétés du fichier sélectionné.
   - **Télécharger sous forme de PDF** : utilisez cette option pour générer la sortie PDF et la télécharger.

### Expérience de recherche et de filtrage

L’option **Rechercher** permet de rechercher les fichiers requis dans le référentiel principalement sur la base des **Titre du fichier**, **Nom du fichier** et **Contenu**. Vous pouvez utiliser n’importe quel critère de recherche, deux ou les trois. Si aucun des critères n’est sélectionné, les résultats incluront les critères communs aux trois critères.

![](images/search-in-repository.png){align="left"}

Sélectionnez l’icône **Filtrer la recherche** \(![Icône Filtrer la recherche](images/filter-search-icon.svg)\) pour ouvrir le panneau Filtre à droite.

![](images/Search-filters-repo.png){align="left"}

Vous disposez des options suivantes pour filtrer les fichiers et affiner votre recherche :

- **Rechercher dans** : sélectionnez le chemin d’accès où vous souhaitez rechercher les fichiers présents dans le référentiel.

- **Type de fichier** : vous pouvez rechercher toutes les **rubriques DITA**, **cartes DITA**, **fichiers DITAVAL**, **fichiers image**, **Multimedia**, **Documents** et **JSON**.

- **Verrouillé par** : affiche une liste d’utilisateurs. La liste est paginée et se charge de manière asynchrone, affichant un ensemble limité d’utilisateurs à la fois et en récupérant d’autres au fur et à mesure que vous faites défiler ou naviguez. Cela améliore la vitesse de chargement et les performances globales, en particulier lorsque vous travaillez avec un grand nombre d’utilisateurs.

- **Dernière modification** : filtrez le contenu en fonction de la date de modification. Sélectionnez une période dans le calendrier ou choisissez l’une des options de période suivantes :
   - La semaine dernière
   - Le mois dernier
   - L&#39;année dernière

- **Balises** : filtrez le contenu en fonction des balises.

- **Élément DITA** : filtrez le contenu en fonction de divers éléments DITA.

Après avoir appliqué tous les filtres requis, sélectionnez **Appliquer** dans le coin inférieur droit du panneau Filtres.

Les résultats de recherche personnalisés en fonction du filtre sélectionné s’affichent sous la forme d’une **liste tabulaire de fichiers uniquement** (les dossiers ne s’affichent pas). Vous pouvez supprimer n’importe quel filtre individuellement ou plusieurs filtres en même temps et les résultats sont actualisés pour refléter la sélection mise à jour.

![](images/search-results-with-filters.png){align="left"}

Une fois les résultats de la recherche affichés, vous pouvez sélectionner plusieurs fichiers et les ouvrir dans l’éditeur à l’aide de l’icône **Modifier** ou utiliser tous les résultats en envoyant les résultats de la recherche à l’éditeur via l’option **Afficher dans le panneau de recherche**.

![](images/post-search-operation.png){align="left"}

**Afficher dans le panneau de recherche**

L’option **Afficher dans le panneau de recherche** devient disponible après avoir effectué une recherche dans le référentiel. Cette fonctionnalité vous permet d’afficher tous les résultats recherchés dans le **panneau de recherche** dans l’éditeur. Pour plus d’informations, consultez [Panneau de recherche](./search-panel-explorer.md).

![](images/search-panel-repo.png){align="left"}

