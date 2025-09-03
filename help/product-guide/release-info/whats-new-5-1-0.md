---
title: Notes de mise à jour | Nouveautés de la version Adobe Experience Manager Guides 5.1.0
description: Découvrez les fonctionnalités nouvelles et améliorées de la version 5.1.0 d’Adobe Experience Manager Guides
role: Leader
source-git-commit: f6617b727d385d31ba66d575ee48f29e77ac716f
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 0%

---

# Nouveautés de la version 5.1.0 (septembre 2025)

Cet article présente les nouvelles fonctionnalités améliorées introduites dans la version 5.1.0 d’Adobe Experience Manager Guides.

Pour obtenir la liste des problèmes qui ont été résolus dans cette version, voir [Problèmes résolus dans la version 5.1.0](fixed-issues-5-1-0.md).

Découvrez les [instructions de mise à niveau pour la version 5.1.0](../release-info/upgrade-instructions-5-1-0.md).


## Workflow de révision amélioré

Avec cette version, le workflow de révision a été considérablement amélioré afin de mieux prendre en charge la communication transparente entre les auteurs et les réviseurs. Les principales mises à jour sont les suivantes :

- Workflows de gestion des tâches avec notifications exploitables
- Possibilité de baliser les utilisateurs pour demander une attention immédiate
- Accès aux détails des projets et des tâches depuis le panneau de révision pour plus de facilité d’utilisation

Grâce à ces améliorations, les utilisateurs peuvent maintenant s’attendre à :

- Cycles d’examen efficaces et opportuns
- Réduction de l’effort manuel lors des échanges de commentaires

Pour plus d’informations, voir [Présentation de la révision](../user-guide/review.md)

## Amélioration de l’expérience de création et d’utilisation des fichiers DITAVAL

Cette mise à jour introduit plusieurs améliorations qui simplifient la création, la gestion et l’application des fichiers DITAVAL, permettant un meilleur contrôle du contenu conditionnel et du style sur les sorties.

Les principaux points forts sont les suivants :

- **Prise en charge améliorée des indicateurs dans la création de fichiers DITAVAL :** Experience Manager Guides offre de nouvelles fonctionnalités de personnalisation de la publication de contenu grâce à la prise en charge améliorée des indicateurs dans les fichiers DITAVAL. Vous pouvez désormais appliquer des indicateurs de début et de fin à un contenu spécifique, y compris des images, et enrichir les sections marquées avec des options de mise en forme telles que le gras, l’italique, etc. Pour gérer les chevauchements de conditions, le **conflit de style** peut être configuré, ce qui inclut la définition d’une couleur d’arrière-plan et de texte par défaut, afin de garantir la clarté et la cohérence de la sortie. Ces indicateurs sont entièrement pris en charge dans la génération du PDF natif et la sortie qui en résulte reflète précisément et entièrement tous les éléments de style appliqués.
Pour plus de détails, voir [Utiliser l&#39;éditeur DITAVAL](../user-guide/ditaval-editor.md).

  ![](assets/ditaval-flag-style-new.png){width="350" align="left"}

- **Prise en charge de plusieurs fichiers DITAVAL pour Native PDF :** pour Native PDF, il est désormais possible d’ajouter plusieurs fichiers DITAVAL, chacun affiché en tant qu’entrée balisée pour une identification et une suppression faciles, offrant ainsi une plus grande flexibilité et un meilleur contrôle du contenu conditionnel dans les sorties PDF

  En outre, cette mise à jour améliore la création de paramètres prédéfinis de sortie en activant les champs DITAVAL modifiables dans tous les formats, ce qui permet aux utilisateurs de spécifier manuellement des chemins DITAVAL.

  Pour plus d’informations, consultez la section [Présentation des paramètres prédéfinis de sortie](../user-guide/generate-output-understand-presets.md) dans Experience Manager Guides.

## Améliorations de la publication

Les améliorations de publication suivantes ont été apportées dans le cadre de la nouvelle version :

### Amélioration du filtrage du journal de génération de sortie

Cette version apporte des améliorations à l’interface utilisateur de la fonctionnalité de filtrage des journaux de génération de sortie. Vous pouvez désormais mieux filtrer les journaux de génération de sortie pour les quatre niveaux distincts : **Info**, **Avertissement**, **Erreur** (y compris les erreurs et les exceptions) et **Fatal** ; avec des indicateurs améliorés et intuitifs avec code de couleur qui simplifient l’analyse et améliorent la visibilité sur le flux de journaux. Cette amélioration vous permet de parcourir les journaux plus efficacement et de localiser les problèmes critiques avec précision.

Pour plus d’informations, consultez la section [Dépannage de base](../user-guide/generate-output-basic-troubleshooting.md).

![](./assets/log-file-new.png){align="left"}


### Les fichiers temporaires pour la sortie publiée incluent désormais les URL de création et de publication dans un nouveau fichier de configuration

Les dernières améliorations de publication apportées à Experience Manager Guides ajoutent désormais un nouveau fichier `system_config.xml` aux fichiers temporaires générés lors de la publication des sorties HTML, PDF et JSON à l’aide de DITA-OT, ainsi que la sortie Native PDF. Ce fichier est automatiquement inclus dans la tâche de publication et également accessible par le biais de fichiers temporaires lorsque vous activez l’option **Conserver les fichiers temporaires** pour les paramètres prédéfinis et que vous générez la sortie.

Le fichier `system_config.xml` contient les détails de l’instance AEM, y compris l’URL de création, l’URL locale et l’URL de publication, ce qui permet de clarifier le contexte et d’améliorer la traçabilité des URL téléchargées.

Pour plus d’informations, consultez la section [Présentation des paramètres prédéfinis de sortie](../user-guide/generate-output-understand-presets.md).

### Nouvelle prise en charge des variables de chemin de sortie pour la génération de sortie

Cette mise à jour introduit une configuration `output path` dynamique pour les paramètres prédéfinis de sortie tels que Native PDF, DITA-OT PDF, JSON, HTML5 et Custom. Au lieu d’utiliser un chemin fixe, les utilisateurs et utilisatrices peuvent désormais définir l’emplacement de sortie à l’aide de la variable `${base_output_path}` lors de l’installation, offrant ainsi une plus grande flexibilité. Le chemin d’accès par défaut précédent `/content/dam/fmdita-outputs` n’est plus obligatoire.

Tous les chemins de sortie associés aux paramètres prédéfinis de profil de dossier global seront automatiquement migrés pour utiliser la nouvelle variable de chemin de sortie de base. Toutefois, pour les profils de dossiers personnalisés, la migration n’est pas automatique. Nous vous conseillons de contacter l’équipe du succès client pour obtenir de l’aide.

Pour plus d’informations, consultez la section [Présentation des paramètres prédéfinis de sortie](../user-guide/generate-output-understand-presets.md).

### La ligne de base exportée inclut désormais l’état du document

La fonction Exporter la ligne de base inclut désormais le **état du document** ainsi que des détails clés tels que le titre, le nom de fichier, le type de fichier et le numéro de version de l’instantané de la ligne de base. Cette amélioration améliore la gestion de la ligne de base en fournissant un aperçu plus complet de la ligne de base.

Pour plus d’informations, voir [Création et gestion des lignes de base à partir de la console Carte](../user-guide/web-editor-baseline.md#manage-baselines).

### Prise en charge de la publication incrémentielle pilotée par les lignes de base via le tableau de bord de mappage pour la sortie AEM Sites à l’aide du mappage des composants hérités

Le processus de génération de sortie incrémentielle a été amélioré afin de prendre en charge la publication de versions spécifiques des rubriques définies dans la ligne de base sélectionnée pour les sites AEM à l’aide du mappage des composants hérités, ce qui permet d’assurer une propagation précise du contenu dans la sortie.

Pour plus d’informations, consultez la section [Génération incrémentale de sortie](../user-guide/generate-output-aem-site.md).

## Améliorations de l’éditeur

Les améliorations suivantes ont été apportées à l’éditeur dans le cadre de la nouvelle version :

### Amélioration de l’expérience de recherche pour le panneau Contenu réutilisable

Experience Manager Guides offre une expérience de recherche améliorée dans le panneau Contenu réutilisable. Avec cette mise à jour, la recherche de n’importe quel mot-clé analyse désormais tous les fichiers ajoutés en tant que contenu réutilisable, et pas seulement les fichiers ouverts, en s’assurant que vous trouvez la position exacte du mot-clé sur toutes les occurrences, que les conteneurs soient ouverts ou réduits. En outre, lorsque vous effacez la barre de recherche, l’état d’origine de tous les conteneurs est conservé, offrant ainsi une fonctionnalité de recherche plus efficace et plus conviviale.

Pour plus d’informations, consultez la section [Contenu réutilisable](../user-guide/web-editor-features.md#reusable-content).

### Attribut &#39;Format&#39; ajouté pour les liens de référence

Adobe Experience Manager Guides ajoute désormais un attribut **format** pour les liens de référence dans l’éditeur. Cet attribut s&#39;affiche dans la vue **Source** et indique clairement le type de fichier, par exemple :

- Pour les fichiers dotés de l’extension **.pdf**, le format est défini sur **pdf**
- Pour les fichiers dotés de l’extension **.html**, le format est défini sur **html**
- Pour les fichiers contenant un fichier **.dita** ou **.ditamap**, le format est défini sur **dita**

En outre, le format des fichiers dotés de l’extension **.xml** est également défini sur **dita**. Pour les fichiers sans extension, le format reste vide. En outre, pour les liens de référence dont la portée est définie sur **externe**, le format est défini sur **html** quelle que soit l’extension de fichier dans les liens de référence.

### Amélioration des options de téléchargement des cartes dans l’éditeur

Experience Manager Guides introduit une nouvelle option **Utiliser les noms de fichiers réels** dans la boîte de dialogue **Télécharger le mappage**. Désormais, lorsque vous téléchargez des fichiers de mappage, vous pouvez choisir de conserver leurs noms de fichier d’origine au lieu des UUID par défaut, ce qui facilite la reconnaissance et la gestion de vos fichiers. Cette option n’est disponible que si vous sélectionnez **Conserver la hiérarchie de fichiers** et est désactivée lorsque vous choisissez **Aplatir la hiérarchie de fichiers**, ce qui vous offre davantage de flexibilité dans l’organisation des cartes téléchargées.

Pour plus d’informations, voir [Télécharger des fichiers](../user-guide/authoring-download-assets.md#download-a-dita-map-file-from-the-editor).

![](assets/download-map-dialog-new.png){width="300" align="left"}

### Invite de temporisation de session pour éviter la perte accidentelle de contenu

Un message pop-up vous avertit désormais lorsque votre session Adobe Experience Manager expire et que vous êtes déconnecté pour cause d’inactivité. Ce message est déclenché lorsque vous tentez de modifier du contenu dans Experience Manager Guides après la fin de la session. Cette fonctionnalité permet de réduire le risque de perdre du travail non enregistré et améliore la fiabilité et la fluidité globales de l’expérience, même pendant les périodes d’inactivité.

![](assets/sign-out-prompt.png)

En savoir plus sur l’[invite de temporisation de session](../user-guide/session-timeout-prompt.md) dans Experience Manager Guides.

### Amélioration de la gestion des `navref` dans l’éditeur

Les dernières améliorations apportées à l&#39;éditeur améliorent la gestion des éléments `navref` dans un plan DITA. Désormais, lorsque vous ajoutez un élément de `navref` à une carte, la boîte de dialogue **Sélectionner le chemin** s’ouvre, ce qui vous permet de choisir facilement les références de carte à inclure comme liens de navigation dans votre carte. Une fois ajouté, le titre de la carte ajoutée est affiché en mode Auteur et en mode Mise en page, ce qui offre une meilleure visibilité de la navigation incluse lors de la création.  En outre, l’élément `navref` ajouté est résolu automatiquement pour afficher la carte référencée dans l’éditeur.

Pour plus d’informations, voir [Ajouter des références de navigation](../user-guide/map-editor-other-features.md#add-navigation-references).


### Améliorations de l’interface utilisateur dans la barre d’outils de l’éditeur et les préférences utilisateur

Avec cette version, les paramètres des onglets **Préférences utilisateur** Page d’accueil pour Général et Apparence ont été restructurés. Vous pouvez notamment renommer le libellé **Ouverture des préférences pour les cartes** et déplacer le bouton (bascule) Espaces insécables vers la barre d’outils de l’éditeur.

En outre, dans la barre d’outils de l’éditeur, certains boutons d’accès rapide permettant d’activer ou de désactiver le suivi des modifications, des balises et des espaces insécables sont désormais regroupés sous l’option **Afficher** dans la liste déroulante Menu pour une meilleure utilisation.

Pour plus d’informations, voir [Barre d’outils dans l’éditeur](../user-guide/web-editor-toolbar.md#menu-dropdown).







