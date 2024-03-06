---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans la version 4.4.0 des guides Adobe Experience Manager
description: Découvrez les correctifs et comment mettre à niveau vers la version 4.4.0 des Guides Adobe Experience Manager.
source-git-commit: 1b25f1df67fa2442ab79830dc2ac5a6eabd0394c
workflow-type: tm+mt
source-wordcount: '1820'
ht-degree: 0%

---

# Version 4.4.0 des guides Adobe Experience Manager (février 2024)

Cette note de mise à jour traite des instructions de mise à niveau, de la matrice de compatibilité et des problèmes résolus dans la version 4.4.0 des Guides Adobe Experience Manager (ultérieurement appelés *Guides du Experience Manager*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version 4.4.0 des guides Adobe Experience Manager](./whats-new-4-4.md).

## Mise à niveau vers la version 4.4.0 des guides du Experience Manager


Vous pouvez facilement mettre à niveau votre version actuelle des guides du Experience Manager vers la version 4.4.0. Avant de procéder à la mise à niveau vers la version 4.4.0 des Guides du Experience Manager, vous devez tenir compte des points suivants :


- Si vous utilisez la version 4.3.1, 4.3.0 ou 4.2.1 (correctif 4.2.1.3), vous pouvez directement effectuer la mise à niveau vers la version 4.4.0.
- Si vous utilisez les versions 4.2, 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers les versions 4.3.1, 4.3.0 ou 4.2.1 (correctif 4.2.1.3) avant de passer à la version 4.4.0.
- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant de passer à la version 4.3.x.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à 3.8.5, reportez-vous à la section Guides du Experience Manager de mise à niveau du guide d’installation spécifique au produit disponible dans la section [Archivage du PDF d’aide des guides Adobe Experience Manager](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).



>[!NOTE]
>
>Vous devez installer AEM Service Pack avant de mettre à niveau la version des guides du Experience Manager.

Pour plus d’informations, voir [Instructions de mise à niveau](../install-guide/upgrade-xml-documentation.md).

## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par la version 4.4.0 de Experience Manager Guides.

### Adobe Experience Manager

**4.4.0 Non UID**
Version 6.5 Service Pack 19, 18, 17

**UUID 4.4.0**
Version 6.5 Service Pack 19, 18, 17

Pour plus d’informations, voir *Exigences techniques* dans le guide d’installation et de configuration de Adobe Experience Manager Guides.

### FrameMaker et FrameMaker Publishing Server

| Version | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.4.0 (non UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.3 ou version ultérieure |
| 4.4.0 (UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.4 ou version ultérieure |
| | | | |

*Les conditions de base et créées dans AEM sont prises en charge dans les versions FMPS à partir de 2020.2.

### Connecteur Oxygen

| Version | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.4.0 (non UUID) | 2.7-normal-1 | 2.7-normal-1 | 1,6 | 1,6 |
| 4.4.0 (UUID) | 3.4-uuid-1 | 3.4-uuid-1 | 2,3 | 2,3 |
|  |  |   |



### Version du modèle de base de connaissances

| Nom du package de composants | Version des composants | Version du modèle |
|---|---|---|
| Module de contenu des composants des guides du Experience Manager pour Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :

### Création

- La vérification orthographique dans l’éditeur n’autorise pas la sélection de suggestions. 15045
- Le bouton de navigation globale ne fonctionne pas et le tableau de bord ne se charge pas. (14968)
- Dans l’éditeur web, la fonction de mappage de téléchargement ne parvient pas à déclencher une notification contextuelle lorsqu’elle est prête à être téléchargée. 14626
- Dans l’éditeur web, la fonction de mappage de téléchargement ne parvient pas à télécharger un mappage avec la ligne de base. 14622
- Erreur DTD non valide dans les guides du Experience Manager. (14482)
- Le titre de l’onglet Éditeur web est tronqué après un point(.) caractère « ? » supplémentaire. 14372
- Les messages d’erreur relatifs aux noms de mappage en double dans l’interface utilisateur d’Assets ne sont pas mis à jour. (14320)
- Une erreur se produit dans la logique de création de version lors du glisser-déposer des ressources. (14291)
- Le contenu réutilisable ignore les identifiants d’élément. (14213)
- Le contrôle des paramètres à masquer **Variables de langue** panneau sous **Sortie** est manquant. (14194)
- L’éditeur web renvoie des erreurs d’application lors de l’ajout d’une nouvelle référence ou d’une nouvelle rubrique à l’aide d’un schéma spécialisé dans la variable **Disposition** vue. 14094
- Espace après référence `<ph>` disparaît lors de l’enregistrement de la rubrique. 13642
- Une erreur d’application se produit lors de la tentative d’enregistrement des fichiers DITA avant la fin du post-traitement. 13571
- Un lien d’ancrage vers `<dlentry>` ou `<dt>` ne parvient pas à afficher le texte du lien. (13543)
- La variable **Favoris** ne se charge pas dans l’éditeur Web. (13495)
- Si le titre d’une rubrique contient une barre oblique `/`, l’onglet de l’éditeur Web n’affiche que les lettres qui lui succèdent. (13455)
- L’aperçu de l’image ne disparaît pas après l’affichage de l’aperçu dans l’éditeur web. (13454)
- Les citations affichent des liens non cliquables lorsqu’elles sont créées avec un identifiant unique avec des espaces. (13447)
- Lorsque vous fermez une rubrique après l’avoir modifiée, vous êtes redirigé vers la page d’accueil AEM au lieu de revenir à la vue du dossier. (13306)
- La fenêtre contextuelle Insérer un mot-clé n’apparaît pas lors de l’utilisation de clés définies par la carte racine dans d’autres rubriques. (12950)
- Les icônes de fermeture ne sont pas visibles lorsque des graphiques de très grande taille sont prévisualisés dans la **Historique des versions** du panneau. (12867)
- Impossible de modifier le fuseau horaire de **Version créée le** pour les lignes de base. (12711)
- Les fichiers ZIP ne sont pas reconnus dans l’éditeur web et vous ne pouvez pas les faire glisser et les déposer. 12709
- La variable **Historique des versions** Le panneau de l’interface utilisateur d’Assets affiche un horodatage incorrect pour la variable **Actuel** champ . 12624
- Dans le **Disposition** vue d’une carte des actifs numériques, à l’aide de **Déplacer à droite** pour qu’un chapitre sélectionné ne fonctionne pas, un sous-élément . (12567)
- La création d’un fichier DITA à partir d’un modèle dont le nom commence par des caractères numériques entraîne une erreur d’espace de noms. (12188)
- Le paramètre rootmap persiste dans l’éditeur web même si l’utilisateur ne l’a pas défini explicitement à partir de la balise **Préférences utilisateur**. (11551)
- Le contenu auquel certains attributs sont appliqués n’est pas mis en surbrillance dans **Auteur** ou **Aperçu** mode . (11063)
- Dans l’éditeur Web, la variable **Références clés** s’ouvre lors de l’insertion du `varname` balise . (10940)
- Le fait de faire glisser une rubrique de glossaire du référentiel vers un mappage de glossaire crée `topicref`. 10767
- La fenêtre Aperçu de l’éditeur XML est tronquée dans les navigateurs Google Chrome et Microsoft Edge. 10755)
- L’éditeur web n’a pas la possibilité de placer un élément à l’intérieur des éléments parents possibles. (8791)
- L’éditeur web est désinstallé après la réinstallation de Adobe Experience Manager Guides version 4.3.1. 14519)
- Le programme d’installation de la version 4.3.1 rencontre un conflit de filtre, ce qui entraîne le remplacement de `apps/cq/core/content/projects/properties`. (14517)
- Un lien d’auto-référence s’affiche sous la liste de **Liens rompus** dans les rapports. 13539)
- L’écran d’aperçu des fragments de code est figé. (14840)
- Des caractères rompus apparaissent lors de la création des fragments de code en coréen. 13489

### Publication

- La publication d’AEM Sites échoue et entraîne des erreurs de portée pour les fichiers comportant `xref` au fichier DITA commençant par &quot;HTTP&quot;. 15154
- Dans la publication avec un PDF natif, les propriétés de métadonnées de mappage DITA ne peuvent pas être utilisées pour renseigner les métadonnées pour la sortie du fichier de PDF. 15159)
- Dans la publication avec des PDF natifs, les attributs personnalisés dans les paramètres prédéfinis de condition ne fonctionnent pas pour la publication avec des PDF natifs. (14943)
- Impossible d’ajouter un modèle personnalisé à partir du **Sorties** dans l’éditeur. (14846)
- **AEM site** ne fonctionne pas en raison d’un chemin de modèle vide. (14804)
- La régénération AEM site échoue pour les mappages DITA avec des rubriques contenant des équations MathML. (14790)
- Dans la publication de PDF natifs, la génération de PDF génère des erreurs lors de l’obtention des dépendances pour `Node.js` publication. (14445)
- **AEM site** Le paramètre prédéfini n’autorise pas la sélection d’un modèle en dehors de la variable `/content` hiérarchie dans l’éditeur web. (14260)
- La fonctionnalité de publication en tant que fragment de contenu ne fonctionne pas pour les fichiers répertoriés dans les résultats de recherche. (14090)
- Les composants de formulaire ont un chemin d’accès codé en dur pour `delegator.jsp`, empêchant le recouvrement des composants AEM Sites. (13993)
- La vue balisée du réacteur PDF dans la sortie de publication du PDF natif ne fonctionne pas comme prévu. 13622
- Dans la publication avec un PDF natif, la sélection de la couleur d’arrière-plan sur la page **Modèle** La mise en page nécessite un rechargement de page lors du rétablissement de `None`. 13621
- AEM La publication sur site rencontre un problème lors de la validation de la banque de données pour les cartes volumineuses avec des liens de portée partagée. 13531
- Un problème se produit lors de la validation de la banque de données pour un mappage DITA volumineux avec des liens de portée par rapport à la publication d’AEM site. (13530)
- Une icône et une info-bulle incorrectes s’affichent pour  **Modifier le contenu** dans le **Disposition de page** de la barre d’outils des modèles utilisés dans la publication avec PDF natif. 13492
- Impossible d’activer un site à l’aide des guides du Experience Manager **Tableau de bord de publication en bloc**. 13439
- Dans la publication avec un PDF natif, l’accessibilité est compromise, car les images dans l’en-tête et le pied de page n’affichent pas de texte secondaire. (12829)
- Dans la sortie AEM Sites, le style ou les sauts de ligne ont été perdus pour le `<lines>` ayant des sous-éléments.12542
- La duplication de la mise en page dans le PDF natif ne fonctionne pas si aucune extension n’est ajoutée automatiquement. 12534
- La localisation des libellés d’élément ne fonctionne pas correctement dans la sortie AEM Sites. (12144)
- Les métadonnées personnalisées ne sont pas disponibles dans la sortie finale. (12116)
- `fmdita rewriter` entre en conflit avec la configuration de réécriture de l’utilisateur et entraîne l’affichage d’URL longues au lieu de liens. (12076)
- Absente **ditaval** dans les paramètres prédéfinis de sortie au niveau du profil de dossier créés via l’interface utilisateur de l’éditeur web. (11903)
- Dans le **AEM site**  paramètre prédéfini, l’option pour **Générer un PDF distinct pour chaque rubrique** n’est pas fonctionnel. (11555)
- La publication de PDF natif ne prend pas en charge la conversion de l’espace colorimétrique CMJN. 10754)
- Lors de la mise à niveau vers la version 4.3.1, certaines exceptions se produisent dans le noeud de PDF natif. (14492)
- Lors de la génération de la sortie du PDF avec la publication d’un PDF natif, le nom de fichier est tronqué après un point. (13620)


### Gestion

- La référence au contenu est rompue lors du copier-coller des fichiers DITA comportant des liens d’auto-référence sans GUID. (13540)
- **Filtre de ligne de base** Les fichiers ne fonctionnent pas avec le nom de fichier dans l’éditeur web. (13486)
- Dans l’éditeur Web, la ligne de base affiche le titre de la version précédente au lieu de la version sélectionnée du fichier DITA. (13444)
- La désactivation de l’indexation du mappage DITA parent pour obtenir de meilleures performances peut avoir un impact sur les fonctionnalités de certaines fonctionnalités.(12213)
- Les paramètres de condition prédéfinis pour les cartes DITA volumineuses ne sont pas créés. 10936
- Impossible de modifier les paramètres prédéfinis pour les premiers mappages de la collection lors de la modification d’une collection de mappages. 10649)
- Étiquettes des `labels.json` s’affichent dans un ordre aléatoire dans l’éditeur Web. 10508
- Les appels de ligne de base dynamiques utilisent le nom plutôt que le titre, ce qui entraîne l’échec de l’API de mappage d’exportation DITA. (14268)

### Révision

- Le menu contextuel du clic droit ne fonctionne pas pour **Accepter** ou **Rejeter** effectuer le suivi des modifications. (14607)
- Basculer pour fermer les rubriques DITA dans l’écran de révision ne fonctionne pas dans la version 4.3.1 des guides Adobe Experience Manager. (14537)
- Les problèmes de symétrie se produisent dans les panneaux de révision côte à côte des versions précédentes et actuelles de l’éditeur web. (14156)
- La personnalisation des modèles de courrier électronique pour le processus de révision ne fonctionne pas avec la superposition. (13954)
- Il n’est pas possible de cliquer sur les pièces jointes coréennes dans l’écran Révision des guides du Experience Manager. (13436)
- Le titre de la carte est coupé dans l’écran de révision et de collaboration, sans possibilité d’afficher le titre complet. (13012)

### Traduction

- La variable **Accepter/Rejeter** les boutons s’affichent par erreur pour la traduction humaine approuvée automatiquement. (14318)
- Des problèmes d’internationalisation (i18n) se produisent lors de la transformation de fichiers DITA non anglais en pages AEM. (14286)
- L’approbation automatique ne fonctionne pas parfois et des exceptions se produisent si une valeur incorrecte est définie sur **État de traduction**. (13607)
- La ligne de base exportée à partir du tableau de bord Traduction échoue et ne s’ouvre pas dans la langue cible. (12993)
- La synchronisation du contenu traduit échoue à partir des projets de traduction temporaires, et l’assistant de traduction de l’éditeur XML DITA s’affiche incorrectement. **En cours** statut des tâches approuvées. (9938)

## Problème connu

Adobe a identifié le problème connu suivant pour la version 4.4.0 :

- La version 1.0 ne s’affiche pas dans l’interface utilisateur pour le fichier DITA dupliqué.