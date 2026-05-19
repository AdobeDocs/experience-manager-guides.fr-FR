---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides version 5.0.0
description: Découvrez les correctifs de la version 5.0.0 d’Adobe Experience Manager Guides.
exl-id: dcc97f9b-f1c0-45bc-84eb-8c0c1a857b6a
TQID: https://experienceleague.adobe.com/L91ThAocmv3mZYa905W4PM5dtK2katbFjGiY0Mi73qg
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 1246
ht-degree: 5%

---

# Correction de problèmes dans la version 5.0.0 (mars 2025)

Cet article couvre les bugs corrigés dans différentes zones de la version 5.0.0 d’Adobe Experience Manager Guides.


Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 5.0.0](whats-new-5-0-0.md).

Découvrez les instructions de mise à niveau de la version [.0.0](upgrade-instructions-5-0-0.md).


## Création

- Lors de la mise à jour des conditions à partir du profil de dossier, tous les groupes de conditions sont perdus et les conditions sont aplaties. (23526)
- La modification de la valeur des lignes d’en-tête d’un tableau dans le panneau **Propriétés du contenu** n’applique pas la valeur mise à jour. (23213)
- Pour les transitions d’état suivantes du document Guides, une actualisation de page est requise. (19421)
- Lors de l&#39;ajout de rubriques dans un plan DITA à l&#39;aide de la boîte de dialogue d&#39;élément **Référence de rubrique** dans la vue **Auteur**, les rubriques sélectionnées sont insérées dans l&#39;ordre inverse de la sélection. (8031)
- Lors du passage de la vue **Auteur** à la vue **Source**, les espaces de début dans les éléments `<pre>` ou `<codeblock>` sont supprimés et le fichier est enregistré avec cette suppression. (19987)
- L’état du document marqué comme **Terminé** revient à **Brouillon** avant d’enregistrer une nouvelle version, ce qui fait que l’état **Terminé** ne persiste dans aucune version du document. (20006)
- Lorsque des éléments de liste sont déplacés en dehors de la balise para, le contenu de l’élément de liste est perdu. (22764)
- Lors de l&#39;ajout de rubriques dans un plan DITA à l&#39;aide de la boîte de dialogue d&#39;élément **Référence de rubrique** dans la vue **Auteur**, les rubriques sélectionnées sont insérées dans l&#39;ordre inverse de la sélection. (22858)
- Lors de l&#39;ajout de nouvelles références de rubrique dans un plan DITA à l&#39;aide de la boîte de dialogue d&#39;élément **Référence de rubrique** dans la vue **Disposition**, les références ajoutées s&#39;affichent sous la forme de liens rompus. (22859)
- Lorsque vous cliquez avec le bouton droit de la souris sur la balise `<simpletable>` d’une rubrique, l’option **Renommer** ne s’affiche pas. (22860)
- Lorsque vous insérez un `xref` qui utilise des références à clé avec du texte de lien, le texte du lien ne s’affiche pas dans Experience Manager Guides. (18775)
- Faire glisser et déposer une image dans une rubrique en mode **Auteur** rompt la référence de l’image, ce qui entraîne une perte de données. (25769)
- Lors de la recherche de fichiers dans le référentiel à l’aide de la fonctionnalité **Rechercher et filtrer**, plusieurs fichiers ne peuvent pas être sélectionnés. (25104)
- Lors de la copie d’une image à partir d’un produit externe (par exemple, MS PowerPoint) et de son collage dans Guides, la fonctionnalité permettant de charger la ressource à la volée pour l’utiliser dans les fichiers est interrompue. (24983)
- Faire glisser un `topicref` sur un autre (en mode **Auteur** ou **Mise en page**) invite à confirmer le remplacement au lieu de l’imbrication. Sélectionner **Non** dans la boîte de dialogue de confirmation entraîne toujours le remplacement du contenu, ce qui entraîne une perte de données. (18602)
- Vous ne pouvez pas ajouter plusieurs raccourcis à un seul événement, ni ajouter un argument à un événement lors de son déclenchement à partir d’un raccourci. (19066)
- Lors du rechargement du navigateur, l’onglet image précédemment fermé s’ouvre à nouveau. (19267)
- La sélection partielle d’un texte dans un élément de paragraphe ou de liste et son déplacement en dehors de l’élément entraînent une perte de contenu lors du passage de la vue **Auteur** à la vue **Source**. (25790)

## Publication

- La publication sur Salesforce échoue lorsque le contenu contient des espaces insécables. (23664)
- Pour les mappages comportant des liens rompus, la publication du Salesforce échoue et la barre de progression s’affiche indéfiniment. (24963)
- Pour les rubriques comportant des erreurs telles que des liens rompus, la publication de Salesforce échoue et la barre de progression s’affiche indéfiniment. (22985)
- La publication native du pdf échoue pour l’option de conformité **PDF/X-4** avec une erreur indiquant que les documents **PDF/X-4 nécessitent un titre non vide**. (16904)
- Lorsque du texte d’espace réservé est utilisé, les références croisées utilisant `<keyref>` dans le PDF natif ne sont pas résolues. (19365)
- La génération native de PDF échoue pour le contenu avec l’attribut **chunk** défini sur **to-content**. (21772)
- Lors de la génération d’une sortie PDF native, l’élément `ditavalref` n’est pas pris en charge. (16320)
- Lors de la modification d’un fichier CSS volumineux dans l’éditeur CSS de PDF natif, un décalage important est observé. (16915)
- Pour la publication basée sur HTML5, l&#39;indicateur DITA-OT generate.copy.outer est appliqué automatiquement. (24299)
- La référence croisée est convertie en lien relatif même lorsque la **portée** du lien est définie sur **externe**. (23059)
- Lorsqu’un fichier ICC est disponible sur un chemin d’accès interne, il ne peut pas être sélectionné dans les paramètres **Imprimer** pour le paramètre prédéfini de PDF natif. (14741)
- Lorsque plusieurs requêtes de publication sont lancées pour différents mappages à l’aide du même paramètre prédéfini de profil de dossier, la publication échoue. (18800)
- Pour les rubriques comportant des métadonnées/propriétés à valeurs multiples lorsqu’elles sont transmises à l’éditeur de texte enrichi DITA, la publication échoue. (19001)
- La boîte de dialogue **Modifier les propriétés** d&#39;une ligne de base n&#39;affiche pas les critères précédemment enregistrés pour la ligne de base dynamique.  (23964)
- La ligne de base n&#39;inclut pas de références indirectes lorsque le contenu est à l&#39;état final du document. (19148)
- Le paramètre **Assainir les noms de page et les noms de fichier pour AEM Sites et d’autres formats de sortie** s’applique à tous les formats de sortie. (7651)
- Si un lien externe contient un UUID, il passe en post-traitement et convertit le lien externe en lien UUID, rompant ainsi le lien dans l’éditeur web ainsi que sur les sites de publication. (22574)


## Gestion

- Le titre et l’icône de la boîte de dialogue **Forcer la suppression** sont mal alignés dans l’interface utilisateur d’Assets. (21933)
- Lorsqu’un fichier JSON est mis à jour dans le profil de dossier pour la configuration de l’éditeur XML, l’opération d’enregistrement interrompt la configuration de l’éditeur XML. (22414)
- Lors de la duplication d’un profil de dossier, sa liste d’utilisateurs administrateurs est également copiée à partir du profil de dossier d’origine. (19067)
- Lors du déplacement de dossiers volumineux (contenant un grand volume de contenu DITA, jusqu’à 200 000 éléments) à partir de l’interface utilisateur d’Assets, une erreur se produit. (20107)
- La modification du profil **Dossier** avec Unified Shell activé entraîne l’affichage d’une interface utilisateur vide. (22212)
- Lors de la suppression de dossiers contenant un grand nombre de fichiers, l’opération échoue. (17107)
- Lorsque vous annulez/supprimez la tâche de traduction ou supprimez le projet, le tableau de bord de traduction affiche le statut **En cours**. (18417)
- Lorsque vous envoyez simultanément deux versions d’une rubrique non traduite à l’aide d’une traduction non héritée et que vous approuvez la seconde version avant la première, le projet de traduction avec la première version est rompu. (22200)


## Révision

- Lors de la sélection de plusieurs rubriques à réviser dans un mappage, la notification par e-mail que le réviseur reçoit indique que toutes les rubriques du mappage sont disponibles pour révision, plutôt que seulement les rubriques sélectionnées. (23214)
- Le titre et l’icône de la rubrique ne sont pas alignés correctement dans l’interface de création de révision. (11670)


## API

- Lors de la création d’une **ligne de base** à l’aide de l’API Guides en déclenchant le service **BaslinUtlis**, une erreur se produit. (19385)

## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 5.0.0 :

- Dans certains cas, la fonctionnalité de verrouillage des fichiers CSS ne fonctionne pas comme prévu, ce qui permet à d’autres utilisateurs de modifier et d’enregistrer les fichiers même s’ils sont verrouillés par un autre utilisateur.
- Impossible de quitter la vue de la console Mappage lorsque la ligne de base est incorrecte avec l’enregistrement automatique activé.
- L’application de modifications de paramètres prédéfinis ne se répercute pas sur les paramètres prédéfinis déjà créés dans la carte si le nom du paramètre prédéfini comporte des caractères majuscules.
- La position de la couleur d’arrière-plan est mal alignée dans l’interface utilisateur du panneau de **Condition**.
- Lorsque vous utilisez une image comme `<keyref>`, le **Type de référence** de l’image n’est pas affiché dans le **Rapport multimédia**.
- Lorsque vous utilisez des images en tant que variables dans le modèle PDF, elles ne sont pas résolues dans la sortie.
- Dans les rapports **Liste des rubriques**, le tri par titre échoue pour les ressources dont le titre contient `<conref>` ou `<conkeyref>`, ce qui fait que ces entrées apparaissent toujours en haut.
- Le changement de profil de dossier ne reflète pas immédiatement les modifications apportées à l’interface utilisateur sans actualiser le navigateur.
- Les personnalisations de la structure d’extension effectuées avant Guides 5.0.0 peuvent ne pas fonctionner comme prévu.
- La table des matières complète de la carte n’est pas mise à jour lors de la publication sélective de rubriques de la carte.
- La publication d’un mappage contenant un fichier Markdown avec des références d’image internes échoue sur les serveurs Windows.
- La conversion de la liste à puces en liste numérotée en Markdown échoue.
- La publication sur un site AEM natif échoue lorsque les fichiers Markdown sont référencés dans une carte.
