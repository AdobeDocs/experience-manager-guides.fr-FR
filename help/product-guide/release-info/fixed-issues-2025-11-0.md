---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides, version 2025.11.0
description: Découvrez les correctifs de bugs de la version 2025.11.0 d’Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: d9a46a009477b1110208a509d4ad8c0616139661
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 3%

---

# Correction de problèmes dans la version 2025.11.0

Cet article couvre les bugs corrigés dans différentes zones de la version 2025.11.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2025.11.0](whats-new-2025-11-0.md).

Découvrez les [instructions de mise à niveau pour la version 2025.11.0](upgrade-instructions-2025-11-0.md).

## Création

- Si un élément de `prop` vide sans attribut ni valeur est ajouté à un fichier DITAVAL, les éléments de `prop` supplémentaires ne peuvent pas être ajoutés. (GUIDES-33597)
- Après la mise à niveau de Experience Manager Guides vers la version 2025.08.0, l’option permettant d’activer ou de désactiver l’onglet personnalisé **Acrolinx** ne s’affiche plus dans les paramètres de **Workspace**. (GUIDES-35261)
- Le CSS personnalisé appliqué à un profil au niveau du dossier pour les rubriques ou les mappages est rétabli au style par défaut dans le mode Aperçu lors de l’actualisation du navigateur. (GUIDES-31098)
- Les opérations **Annuler** et **Rétablir** ne fonctionnent pas comme prévu dans la vue Source de l&#39;éditeur pour les fichiers DITA. (GUIDES-24914, GUIDES-25034)
- Lors du référencement d&#39;un plan DITA dans une rubrique à l&#39;aide de l&#39;élément `Xref`, le nom de fichier du plan référencé est affiché à la place du titre du plan. (GUIDES-21759)
- Lors de l’ajout de plusieurs fichiers Schematron à des fins de validation via le panneau de droite de l’interface de l’éditeur, une erreur **les fichiers Schematron n’existent pas ou contiennent des erreurs** s’affiche même si les fichiers ajoutés sont valides et ne comportent aucune erreur. (GUIDES-33731)
- Les équations MathML volumineuses ou complexes ne s’affichent pas dans l’éditeur. (GUIDES-29095)

## Gestion des ressources numériques

- Lorsque vous chargez à nouveau une image modifiée via l’interface utilisateur de Experience Manager Guides, le rendu d’origine de l’image est mis à jour, mais le contenu DITA associé continue d’afficher la version précédente de l’image. (GUIDES-33693)
- Lorsque vous tentez de déplacer plusieurs dossiers de leur emplacement source vers un autre emplacement (à l’aide de l’outil de déplacement en bloc), l’opération échoue si les noms de dossier commencent par la même chaîne (par exemple, Product et ProductImages). (GUIDES-29096)
- La suppression d’une ressource recherchée dans l’interface utilisateur d’Omnisearch Assets contourne la boîte de dialogue d’avertissement **Forcer la suppression** et supprime directement la ressource, même si elle est référencée dans du contenu DITA existant. (GUIDES-17232)

## Publication

- Lors de la publication d&#39;un plan DITA à l&#39;aide de la ligne de base sur AEM Sites (avec le mappage de composant hérité), les éléments de plan avec l&#39;attribut `processing-role = resource-only` sont également publiés. (GUIDES-37649)
- Dans certains cas, la propriété `jcr:content/fmUuidOfSource` est absente des pages de sortie AEM Sites (avec le mappage des composants hérités), ce qui entraîne la création de pages de contenu indétectables.
- Le filtrage de contenu à l’aide de filtres DITAVal et de paramètres prédéfinis conditionnels ne fonctionne pas pour la publication Salesforce. (GUIDES-33515)
- Impossible de créer un paramètre prédéfini PDF natif pour un mappage si un dossier portant le même nom existe dans sa hiérarchie de contenu. (GUIDES-33012)
- Lorsque la sortie native de PDF est générée à l’aide d’une ligne de base dynamique, le terme **PDFProject** s’affiche en tant que titre de PDF au lieu du titre de mappage réel. (GUIDES-31102)
- La génération d’une sortie PDF native avec certaines valeurs d’attribut `print` dans les références de rubrique ne fonctionne pas comme prévu. (GUIDES-31101)
- Lorsqu&#39;un dossier contenant des mappages DITA est déplacé à l&#39;aide de l&#39;interface utilisateur d&#39;Assets ou de l&#39;option **Déplacement en bloc**, les collections de mappages existantes et les collections d&#39;activation en bloc qui font référence à ces mappages ne se chargent pas. (GUIDES-28355)
- Lorsque vous déplacez un dossier contenant une carte avec des paramètres prédéfinis de condition, les conditions ne sont pas appliquées à la sortie générée après le déplacement. (GUIDES-28352)
- Lorsque vous générez une sortie AEM Sites à l’aide du mappage des composants hérités, les rubriques qui utilisent l’attribut `copy-to` sont publiées avec le nom de la rubrique `copy-from` au lieu du nom défini dans l’attribut `copy-to`. (GUIDES-22155)
- L&#39;activation d&#39;un ou plusieurs plans DITA à partir du **tableau de bord de publication en masse** génère des journaux trop volumineux. (GUIDES-20746)

## Plateforme

- Les journaux d’erreurs générés lors du chargement d’une ressource via l’interface utilisateur d’Assets ou de la création d’un nouveau fichier à partir de l’interface utilisateur de l’éditeur utilisent incorrectement le terme `predecessor` au lieu de `successor` dans le message du journal. (GUIDES-35607)

## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 2025.11.0 :

- La création d’une rubrique en double à l’aide d’`copy-to` attribut et de son référencement avec `scope=peer` attribut entraîne des problèmes de redirection dans la sortie AEM Sites, où les liens sont redirigés d’AEM Sites (avec le mappage de composants composites) vers AEM Sites (avec le mappage de composants hérité), et vice versa. (GUIDES-37656)











