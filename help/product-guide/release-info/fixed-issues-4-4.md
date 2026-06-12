---
title: Notes de mise à jour | Correction de problèmes dans la version 4.4.0 d’Adobe Experience Manager Guides
description: Découvrez les correctifs de bugs dans la version 4.4.0 d’Adobe Experience Manager Guides
role: Leader
exl-id: ff3083d3-062b-4a79-875f-86991978a18e
TQID: https://experienceleague.adobe.com/0mdTs2Pg1Zos-Y-jMaYUEasFRhyF2kzl6Sz8MBisJ5Q
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d6596f3f-92a7-43ec-b444-237db6adad05id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 1439
ht-degree: 5%

---

# Correction de problèmes dans la version 4.4.0 (janvier 2024)


Cet article couvre les bugs corrigés dans différentes zones de la version 4.4.0 d’Adobe Experience Manager Guides.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, consultez [Nouveautés de la version 4.4.0](./whats-new-4-4.md).

Découvrez les [instructions de mise à niveau pour la version 4.4.0](../release-info/upgrade-instructions-4-4.md).


## Création

- La vérification orthographique dans l’éditeur ne permet pas de sélectionner des suggestions. (15045)
- Le bouton de navigation globale ne fonctionne pas et le chargement du tableau de bord échoue. (14968)
- Dans l’éditeur web, la fonctionnalité de carte de téléchargement ne déclenche pas de notification pop-up lorsqu’elle est prête à être téléchargée. (14626)
- Dans l’éditeur web, la fonction de téléchargement de carte ne parvient pas à télécharger une carte avec une ligne de base. (14622)
- Erreur DTD non valide dans le Experience Manager Guides. (14482)
- Le titre dans l’onglet Éditeur web est tronqué après un point(.) caractère. (14372)
- Le message d’erreur pour les noms de mappage en double dans l’interface utilisateur d’Assets n’est pas mis à jour. (14320)
- Une erreur se produit dans la logique de création de version lors du glisser-déposer des ressources. (14291)
- Le contenu réutilisable ignore les identifiants d’élément. (14213)
- Le contrôle de paramètre permettant de masquer le panneau **Variables de langue** sous l’onglet **Sortie** est manquant. (14194)
- L’éditeur web renvoie des erreurs d’application lors de l’ajout d’une nouvelle référence ou rubrique à l’aide d’un schéma spécialisé en mode **Disposition**. (14094)
- L’espace après l’élément `<ph>` conref disparaît lors de l’enregistrement de la rubrique. (13642)
- Une erreur d&#39;application se produit lors de la tentative d&#39;enregistrement de fichiers DITA avant la fin du post-traitement. (13571)
- Un lien d’ancrage vers `<dlentry>` ou `<dt>` élément n’affiche pas le texte du lien. (13543)
- Le chargement de la collection **Favoris** dans l’éditeur web échoue. (13495)
- Si le titre d&#39;une rubrique contient une barre oblique `/`, l&#39;onglet de l&#39;éditeur Web n&#39;affiche que les lettres qui suivent. (13455)
- L’aperçu de l’image ne disparaît pas après l’affichage de l’aperçu dans l’éditeur web. (13454)
- Les citations affichent des liens non cliquables lorsqu’elles sont créées avec un ID unique et des espaces. (13447)
- Lorsque vous fermez une rubrique après l’avoir modifiée, vous êtes redirigé vers la page d’accueil d’AEM au lieu de revenir à la vue des dossiers. (13306)
- La fenêtre contextuelle Insérer un mot-clé n’apparaît pas lors de l’utilisation de clés définies par une carte racine dans d’autres rubriques. (12950)
- Les icônes de fermeture ne sont pas visibles lorsque des graphiques très hauts sont prévisualisés dans le panneau **Historique des versions**. (12867)
- Impossible de modifier le fuseau horaire de la colonne **Version créée le** pour les lignes de base. (12711)
- Les fichiers Zip ne sont pas reconnus dans l’éditeur web et vous ne pouvez pas les faire glisser et les déposer. (12709)
- Le panneau **Historique des versions** de l’interface utilisateur d’Assets affiche un horodatage incorrect pour le champ **Actuel**. (12624)
- Dans la vue **Disposition** d’une structure Bookmap, l’utilisation de l’option **Déplacer vers la droite** pour transformer un chapitre sélectionné en sous-élément ne fonctionne pas. (12567)
- La création d&#39;un fichier DITA à partir d&#39;un modèle dont le nom de fichier commence par des caractères numériques entraîne une erreur d&#39;espace de noms. (12188)
- Le paramètre de feuille de route persiste dans l’éditeur web même si l’utilisateur ne l’a pas défini explicitement à partir des **Préférences utilisateur**. (11551)
- Le contenu auquel certains attributs sont appliqués n’est pas mis en surbrillance en mode **Création** ou **Aperçu**. (11063)
- Dans l’éditeur web, la fenêtre **Références clés** s’ouvre lors de l’insertion de la balise `varname`. (10940)
- Faire glisser une rubrique de glossaire du référentiel vers un glossaire map crée des `topicref`. (10767)
- La fenêtre d’aperçu de l’éditeur XML est tronquée dans les navigateurs Google Chrome et Microsoft Edge. (10755)
- L’éditeur web ne peut pas encapsuler un élément dans les éventuels éléments parents. (8791)
- L’éditeur web est désinstallé après la réinstallation d’Adobe Experience Manager Guides version 4.3.1. (14519)
- Le programme d’installation de la version 4.3.1 rencontre un conflit de filtres, ce qui entraîne le remplacement de `apps/cq/core/content/projects/properties`. (14517)
- Un lien d’auto-référence s’affiche sous la liste des **liens rompus** dans les rapports. (13539)
- L’écran d’aperçu des fragments de code est figé. (14840)
- Des caractères rompus apparaissent lors de la création des fragments de code en coréen. (13489)

## Publication

- La publication d’AEM Sites échoue et entraîne des erreurs d’étendue pour les fichiers ayant `xref` au fichier DITA commençant par « HTTP ». (15154)
- Dans la publication native PDF, les propriétés de métadonnées de plan DITA ne peuvent pas être utilisées pour renseigner les métadonnées pour la sortie de fichier PDF. (15159)
- Dans la publication Native PDF, les attributs personnalisés contenus dans les paramètres prédéfinis de condition ne fonctionnent pas pour la publication Native PDF. (14943)
- Impossible d’ajouter un modèle personnalisé à partir de l’onglet **Sorties** dans l’éditeur. (14846)
- Le préréglage **Site** ne fonctionne pas en raison d’un chemin d’accès au modèle vide. (14804)
- La régénération du site AEM échoue pour les plans DITA avec des rubriques contenant des équations MathML. (14790)
- Dans la publication Native PDF, la génération de PDF renvoie des erreurs d’obtention des dépendances pour la publication `Node.js`. (14445)
- Le préréglage **Site** ne permet pas de sélectionner un modèle en dehors de la hiérarchie `/content` dans l’éditeur web. (14260)
- La fonctionnalité de publication en tant que fragment de contenu ne fonctionne pas pour les fichiers répertoriés dans les résultats de recherche. (14090)
- Les composants Fmdita ont un chemin d’accès codé en dur de `delegator.jsp`, ce qui empêche la superposition des composants AEM Sites. (13993)
- La vue balisée du réacteur PDF dans la sortie de publication Native PDF ne fonctionne pas comme prévu. (13622)
- Dans la publication Native PDF, la sélection de la couleur d’arrière-plan dans la disposition **Modèle** nécessite un rechargement de page lors du retour à la `None`. (13621)
- La publication sur le site AEM rencontre un problème lors de la validation dans le magasin de données pour les cartes volumineuses avec des liens d’homologue de portée. (13531)
- Un problème se produit lors de la validation dans le magasin de données d&#39;un plan DITA volumineux avec des liens d&#39;homologue de portée dans la publication sur le site AEM. (13530)
- Une icône et une info-bulle incorrectes s’affichent pour l’option **Modifier le contenu** dans la barre d’outils **Mises en page** des modèles utilisés dans la publication native de PDF. (13492)
- Impossible d’activer un site à l’aide de Experience Manager Guides **Tableau de bord de publication en bloc**. (13439)
- Dans la publication Native PDF, l’accessibilité est compromise, car les images de l’en-tête et du pied de page n’affichent pas de texte secondaire. (12829)
- Dans la sortie AEM Sites, le style ou les sauts de ligne ont été perdus pour l’élément `<lines>` comportant des sous-éléments.(12542)
- La duplication de la mise en page dans le PDF natif ne fonctionne pas si aucune extension n’est ajoutée automatiquement. (12534)
- La localisation des libellés d’élément ne fonctionne pas correctement dans la sortie AEM Sites. (12144)
- Les métadonnées personnalisées ne sont pas disponibles dans la sortie finale. (12116)
- `fmdita rewriter` est en conflit avec la configuration de réécriture de l’utilisateur et entraîne l’affichage d’URL longues au lieu des liens. (12076)
- Option **ditaval** manquante dans les paramètres prédéfinis de sortie au niveau du profil de dossier créés via l’interface utilisateur de l’éditeur web. (11903)
- Dans le préréglage **Site**, l’option **Générer un PDF distinct pour chaque rubrique** n’est pas fonctionnelle. (11555)
- La publication native de PDF ne prend pas en charge la conversion de l’espace colorimétrique CMJN. (10754)
- Lors de la mise à niveau vers la version 4.3.1, certaines exceptions se produisent dans le nœud PDF natif. (14492)
- Lors de la génération de la sortie PDF avec publication Native PDF, le nom du fichier est tronqué après un point. (13620)


## Gestion

- La référence au contenu est rompue lors du copier-coller des fichiers DITA ayant des liens d&#39;auto-référence sans GUID. (13540)
- Les fichiers **Filtre de ligne de base** ne fonctionnent pas avec le nom de fichier dans l’éditeur web. (13486)
- Dans l&#39;éditeur Web, la ligne de base affiche le titre de la version précédente au lieu de la version sélectionnée du fichier DITA. (13444)
- La désactivation de l&#39;indexation du plan DITA parent pour obtenir de meilleures performances peut avoir un impact sur les fonctionnalités de certaines fonctionnalités.(12213)
- Les paramètres prédéfinis de condition pour les plans DITA volumineux ne sont pas créés. (10936)
- Impossible de modifier les paramètres prédéfinis des premiers mappages de la collection lors de la modification d’une collection de mappages. (10649)
- Les libellés du fichier `labels.json` s’affichent dans un ordre aléatoire dans l’éditeur web. (10508)
- Les appels de base dynamiques utilisent le nom au lieu du titre, ce qui entraîne l’échec de l’exportation de l’API map DITA. (14268)

## Révision

- Le menu contextuel contextuel ne fonctionne pas pour les modifications de suivi **Accepter** ou **Refuser**. (14607)
- Le bouton (bascule) permettant de fermer les rubriques DITA dans l&#39;écran de révision ne fonctionne pas dans la version 4.3.1 d&#39;Adobe Experience Manager Guides. (14537)
- Les problèmes de symétrie se produisent dans les panneaux de révision côte à côte des versions précédente et actuelle dans l’éditeur web. (14156)
- La personnalisation des modèles d’e-mail pour le workflow de révision ne fonctionne pas avec la superposition. (13954)
- Vous ne pouvez pas cliquer sur les pièces jointes coréennes dans l’écran de révision Experience Manager Guides. (13436)
- Le titre de la carte est tronqué dans l’écran de révision et de collaboration, sans possibilité d’afficher le titre complet. (13012)

## Traduction

- Les boutons **Accepter/Rejeter** s’affichent par erreur pour la traduction humaine approuvée automatiquement. (14318)
- Les problèmes d&#39;internationalisation (i18n) se produisent lors de la transformation de fichiers DITA non anglais en pages AEM. (14286)
- L’approbation automatique ne fonctionne pas toujours et des exceptions se produisent si une valeur incorrecte est définie sur **Statut de traduction**. (13607)
- La ligne de base exportée à partir du tableau de bord de traduction échoue et ne s’ouvre pas dans la langue cible. (12993)
- Les contenus traduits ne peuvent pas être synchronisés à partir de projets de traduction temporaires et l&#39;assistant de traduction de l&#39;éditeur XML DITA affiche incorrectement le statut **En cours** pour les tâches approuvées. (9938)

## Problème Connu

Adobe a identifié le problème connu suivant pour la version 4.4.0 :

- La version 1.0 n&#39;est pas affichée dans l&#39;interface utilisateur pour le fichier DITA dupliqué.
