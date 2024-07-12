---
title: Notes de mise à jour | Correction de problèmes dans la version 4.4.0 d’Adobe Experience Manager Guides
description: Découvrez les correctifs de la version 4.4.0 d’Adobe Experience Manager Guides
role: Leader
exl-id: ff3083d3-062b-4a79-875f-86991978a18e
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '1434'
ht-degree: 0%

---

# Correction de problèmes dans la version 4.4.0 (janvier 2024)


Cet article couvre les bogues corrigés dans différentes zones de la version 4.4.0 d’Adobe Experience Manager Guides.

Pour plus d&#39;informations sur les nouvelles fonctionnalités et améliorations, consultez la section [Nouveautés de la version 4.4.0](./whats-new-4-4.md).

Découvrez les [instructions de mise à niveau pour la version 4.4.0](../release-info/upgrade-instructions-4-4.md).


## Création

- La vérification orthographique dans l’éditeur n’autorise pas la sélection de suggestions. 15045
- Le bouton de navigation globale ne fonctionne pas et le tableau de bord ne se charge pas. (14968)
- Dans l’éditeur web, la fonction de mappage de téléchargement ne parvient pas à déclencher une notification contextuelle lorsqu’elle est prête à être téléchargée. 14626
- Dans l’éditeur web, la fonction de mappage de téléchargement ne parvient pas à télécharger un mappage avec la ligne de base. 14622
- Erreur DTD non valide dans Experience Manager Guides. (14482)
- Le titre de l’onglet Éditeur web est tronqué après un point(.) caractère « ? » supplémentaire. 14372
- Les messages d’erreur relatifs aux noms de mappage en double dans l’interface utilisateur d’Assets ne sont pas mis à jour. (14320)
- Une erreur se produit dans la logique de création de version lors du glisser-déposer des ressources. (14291)
- Le contenu réutilisable ignore les identifiants d’élément. (14213)
- Le contrôle de paramètre pour masquer le panneau **Variables de langue** sous l’onglet **Output** est manquant. (14194)
- L’éditeur web renvoie des erreurs d’application lors de l’ajout d’une nouvelle référence ou d’une nouvelle rubrique à l’aide d’un schéma spécialisé dans la vue **Disposition**. 14094
- L’espace après l’élément `<ph>` disparaît lors de l’enregistrement de la rubrique. 13642
- Une erreur d’application se produit lors de la tentative d’enregistrement des fichiers DITA avant la fin du post-traitement. 13571
- Un lien d’ancrage vers l’élément `<dlentry>` ou `<dt>` n’affiche pas le texte du lien. (13543)
- Échec du chargement de la collection **Favoris** dans l’éditeur web. (13495)
- Si le titre d’une rubrique contient une barre oblique `/`, l’onglet de l’éditeur web n’affiche que les lettres qui lui succèdent. (13455)
- L’aperçu de l’image ne disparaît pas après l’affichage de l’aperçu dans l’éditeur web. (13454)
- Les citations affichent des liens non cliquables lorsqu’elles sont créées avec un identifiant unique avec des espaces. (13447)
- Lorsque vous fermez une rubrique après l’avoir modifiée, vous êtes redirigé vers la page d’accueil AEM au lieu de revenir à la vue du dossier. (13306)
- La fenêtre contextuelle Insérer un mot-clé n’apparaît pas lors de l’utilisation de clés définies par la carte racine dans d’autres rubriques. (12950)
- Les icônes de fermeture ne sont pas visibles lorsque de très grands graphiques sont prévisualisés dans le panneau **Historique de version**. (12867)
- Impossible de modifier le fuseau horaire de la colonne **Version créée le** pour les lignes de base. (12711)
- Les fichiers ZIP ne sont pas reconnus dans l’éditeur web et vous ne pouvez pas les faire glisser et les déposer. 12709
- Le panneau **Historique de version** de l’interface utilisateur d’Assets affiche un horodatage incorrect pour le champ **Actuel**. 12624
- Dans la vue **Disposition** d’une carte de contenu, l’utilisation de **Déplacer à droite** pour faire d’un chapitre sélectionné un sous-élément ne fonctionne pas. (12567)
- La création d’un fichier DITA à partir d’un modèle dont le nom commence par des caractères numériques entraîne une erreur d’espace de noms. (12188)
- Le paramètre rootmap persiste dans l’éditeur web même si l’utilisateur ne l’a pas défini explicitement à partir des **préférences utilisateur**. (11551)
- Le contenu avec certains attributs appliqués n’est pas mis en surbrillance en mode **Auteur** ou **Aperçu**. (11063)
- Dans l’éditeur Web, la fenêtre **Références clés** s’ouvre lors de l’insertion de la balise `varname`. (10940)
- Le fait de faire glisser une rubrique de glossaire du référentiel vers une carte de glossaire crée `topicref`. 10767
- La fenêtre Aperçu de l’éditeur XML est tronquée dans les navigateurs Google Chrome et Microsoft Edge. 10755)
- L’éditeur web n’a pas la possibilité de placer un élément à l’intérieur des éléments parents possibles. (8791)
- L’éditeur web est désinstallé après la réinstallation d’Adobe Experience Manager Guides version 4.3.1. 14519)
- Le programme d’installation de la version 4.3.1 rencontre un conflit de filtre, ce qui entraîne le remplacement de `apps/cq/core/content/projects/properties`. (14517)
- Un lien d’auto-référence s’affiche sous la liste de **Liens rompus** dans les rapports. 13539)
- L’écran d’aperçu des fragments de code est figé. (14840)
- Des caractères rompus apparaissent lors de la création des fragments de code en coréen. 13489

## Publication

- La publication d’AEM Sites échoue et entraîne des erreurs d’étendue pour les fichiers dont le `xref` commence par &quot;HTTP&quot; dans le fichier DITA. 15154
- Dans la publication avec un PDF natif, les propriétés de métadonnées de mappage DITA ne peuvent pas être utilisées pour renseigner les métadonnées pour la sortie du fichier de PDF. 15159)
- Dans la publication avec des PDF natifs, les attributs personnalisés dans les paramètres prédéfinis de condition ne fonctionnent pas pour la publication avec des PDF natifs. (14943)
- Impossible d’ajouter un modèle personnalisé à partir de l’onglet **Sorties** de l’éditeur. (14846)
- Le paramètre prédéfini **AEM Site** ne fonctionne pas en raison d’un chemin de modèle vide. (14804)
- La régénération AEM site échoue pour les mappages DITA avec des rubriques contenant des équations MathML. (14790)
- Dans la publication de PDF natif, la génération de PDF renvoie des erreurs lors de l’obtention des dépendances pour la publication `Node.js`. (14445)
- Le paramètre prédéfini **AEM Site** n’autorise pas la sélection d’un modèle en dehors de la hiérarchie `/content` de l’éditeur web. (14260)
- La fonctionnalité de publication en tant que fragment de contenu ne fonctionne pas pour les fichiers répertoriés dans les résultats de recherche. (14090)
- Les composants de formulaire ont un chemin d’accès codé en dur `delegator.jsp`, ce qui empêche la superposition des composants AEM Sites. (13993)
- La vue balisée du réacteur PDF dans la sortie de publication du PDF natif ne fonctionne pas comme prévu. 13622
- Dans la publication avec un PDF natif, la sélection de couleur d’arrière-plan sur la disposition **Modèle** nécessite un rechargement de page lors du rétablissement de `None`. 13621
- AEM La publication sur site rencontre un problème lors de la validation de la banque de données pour les cartes volumineuses avec des liens de portée partagée. 13531
- Un problème se produit lors de la validation de la banque de données pour un mappage DITA volumineux avec des liens de portée par rapport à la publication d’AEM site. (13530)
- L’icône et l’info-bulle incorrectes s’affichent pour l’option **Modifier le contenu** dans la barre d’outils **Mises en page** des modèles utilisés dans la publication de PDF natif. 13492
- Impossible d’activer un site à l’aide du tableau de bord Experience Manager Guides **Bulk Publish**. 13439
- Dans la publication avec un PDF natif, l’accessibilité est compromise, car les images dans l’en-tête et le pied de page n’affichent pas de texte secondaire. (12829)
- Dans la sortie AEM Sites, le style ou les sauts de ligne ont été perdus pour l’élément `<lines>` ayant des sous-éléments.12542
- La duplication de la mise en page dans le PDF natif ne fonctionne pas si aucune extension n’est ajoutée automatiquement. 12534
- La localisation des libellés d’élément ne fonctionne pas correctement dans la sortie AEM Sites. (12144)
- Les métadonnées personnalisées ne sont pas disponibles dans la sortie finale. (12116)
- `fmdita rewriter` entre en conflit avec la configuration de réécriture de l’utilisateur et entraîne l’affichage de longues URL au lieu des liens. (12076)
- Option **ditaval** manquante dans les paramètres prédéfinis de sortie au niveau du profil de dossier créés via l’interface utilisateur de l’éditeur web. (11903)
- Dans le paramètre prédéfini **AEM Site**, l’option **Générer un PDF distinct pour chaque rubrique** n’est pas fonctionnelle. (11555)
- La publication de PDF natif ne prend pas en charge la conversion de l’espace colorimétrique CMJN. 10754)
- Lors de la mise à niveau vers la version 4.3.1, certaines exceptions se produisent dans le noeud de PDF natif. (14492)
- Lors de la génération de la sortie du PDF avec la publication d’un PDF natif, le nom de fichier est tronqué après un point. (13620)


## Gestion

- La référence au contenu est rompue lors du copier-coller des fichiers DITA comportant des liens d’auto-référence sans GUID. (13540)
- Les fichiers **Filtre de ligne de base** ne fonctionnent pas avec le nom de fichier dans l’éditeur web. (13486)
- Dans l’éditeur Web, la ligne de base affiche le titre de la version précédente au lieu de la version sélectionnée du fichier DITA. (13444)
- La désactivation de l’indexation du mappage DITA parent pour obtenir de meilleures performances peut avoir un impact sur les fonctionnalités de certaines fonctionnalités.(12213)
- Les paramètres de condition prédéfinis pour les cartes DITA volumineuses ne sont pas créés. 10936
- Impossible de modifier les paramètres prédéfinis pour les premiers mappages de la collection lors de la modification d’une collection de mappages. 10649)
- Les libellés du fichier `labels.json` apparaissent dans l’ordre aléatoire dans l’éditeur web. 10508
- Les appels de ligne de base dynamiques utilisent le nom plutôt que le titre, ce qui entraîne l’échec de l’API de mappage d’exportation DITA. (14268)

## Révision

- Le menu contextuel de clic droit ne fonctionne pas pour les modifications de suivi **Accept** ou **Rejeter**. (14607)
- Basculer pour fermer les rubriques DITA dans l’écran de révision ne fonctionne pas dans la version 4.3.1 d’Adobe Experience Manager Guides. (14537)
- Les problèmes de symétrie se produisent dans les panneaux de révision côte à côte des versions précédentes et actuelles de l’éditeur web. (14156)
- La personnalisation des modèles de courrier électronique pour le processus de révision ne fonctionne pas avec la superposition. (13954)
- Il n’est pas possible de cliquer sur les pièces jointes coréennes dans l’écran de révision de Experience Manager Guides. (13436)
- Le titre de la carte est coupé dans l’écran de révision et de collaboration, sans possibilité d’afficher le titre complet. (13012)

## Traduction

- Les boutons **Accepter/Rejeter** s’affichent par erreur pour la traduction humaine approuvée automatiquement. (14318)
- Des problèmes d’internationalisation (i18n) se produisent lors de la transformation de fichiers DITA non anglais en pages AEM. (14286)
- L’approbation automatique ne fonctionne pas parfois et des exceptions se produisent si une valeur incorrecte est définie sur **État de traduction**. (13607)
- La ligne de base exportée à partir du tableau de bord Traduction échoue et ne s’ouvre pas dans la langue cible. (12993)
- La synchronisation du contenu traduit échoue à partir des projets de traduction temporaires, et l’assistant de traduction de l’éditeur XML DITA affiche incorrectement l’état **En cours** pour les tâches approuvées. (9938)

## Problème connu

Adobe a identifié le problème connu suivant pour la version 4.4.0 :

- La version 1.0 ne s’affiche pas dans l’interface utilisateur pour le fichier DITA dupliqué.
