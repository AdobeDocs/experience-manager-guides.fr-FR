---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides, version 2025.04.0
description: Découvrez les correctifs de bugs de la version 2025.04.0 d’Adobe Experience Manager Guides as a Cloud Service.
exl-id: ad3e95b5-4903-4387-8e4d-c4b9ba77fee2
TQID: https://experienceleague.adobe.com/v7tg4-eP4JVt9bR0S4Ld4lWb0YbdlT-uJc7PrXPT4Wg
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 764
ht-degree: 6%

---

# Correction de problèmes dans la version 2025.04.0

Cet article couvre les bugs corrigés dans différentes zones de la version 2025.04.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir la section [Nouveautés de la version 2025.04.0](whats-new-2025-04-0.md).

Découvrez les [instructions de mise à niveau pour la version 2025.04.0](upgrade-instructions-2025-04-0.md).

## Création

- Le chargement de la zone d’insertion de caractères spéciaux dans l’éditeur échoue pour les paramètres régionaux allemands. (24537)
- Les commentaires et les étiquettes ajoutés lors de l&#39;enregistrement d&#39;une nouvelle version d&#39;un fichier DITAVAL ne sont pas enregistrés dans l&#39;historique des versions avec la nouvelle version. (24076)
- Les références entrantes et sortantes sous **Propriétés du fichier** dans le panneau de droite ne s’actualisent pas correctement lors du changement entre les fichiers de mappage. Ce problème se produit spécifiquement lorsque les fichiers de mappage contiennent un grand nombre de références. (23344)
- Le filtre Référentiel ne conserve pas l’ordre des filtres personnalisés définis dans le `ui_config.json`. (21193)
- La suppression de plusieurs lignes de texte dans un élément de `codeblock` crée un espace vide qui ne peut pas être supprimé de la vue de création. (20672)
- La génération de nouveaux identifiants pour les éléments échoue lorsque ces éléments sont ajoutés via des fragments de code ou créés via des modèles, même si l’option **générer automatiquement l’identifiant** est activée dans `XMLEditorConfig`. (21734)
- La création d&#39;une ressource DITA à partir de modèles DITA copie les propriétés de réplication des modèles DITA correspondants. (25145)
- Impossible d’accéder aux propriétés du fichier à partir du panneau du référentiel si le nom du dossier parent inclut le caractère «&amp; ». (25762)
- La fermeture d&#39;un fichier de rubrique permet de l&#39;enregistrer en tant que nouvelle version, même lorsque la rubrique est verrouillée. Ce problème se produit spécifiquement lorsque l’option **Demander une nouvelle version à la fermeture** est activée dans `XMLEditorConfig`. (23875)
- La largeur maximale actuelle du panneau du référentiel masque les titres de rubrique et de mappage lorsque la hiérarchie de contenu est profondément imbriquée. (27751)

## Publication

- Dans la sortie AEM Sites héritée, les liens de section dans les rubriques imbriquées d’une carte ne sont pas résolus correctement lorsqu’ils sont définis manuellement en mode Source ou que le contenu est importé à partir d’une source externe. Au lieu d’accéder à la section prévue, il redirige vers la rubrique principale qui contient la rubrique imbriquée. (26103)
- Si l&#39;attribut `scope=external` est absent des liens externes dans une rubrique DITA, la publication HTML5 échoue sans indiquer les fichiers dans lesquels cet attribut est absent des journaux d&#39;erreurs, en particulier lorsque le microservice est activé. (25969)
- Impossible d’incorporer des liens vidéo dans le PDF natif, même si l’option **Incorporer des fichiers multimédias** est activée dans le paramètre prédéfini de PDF. (9989)
- Impossible de transmettre les propriétés de métadonnées pour mapper les pages de destination générées à l’aide d’une nouvelle publication AEM Sites. (27288)

## Gestion

- L’état du document de la copie de travail d’une rubrique est affiché en regard de toutes les versions de cette rubrique dans l’interface utilisateur de traduction et de ligne de base. (20674)


## Révision

- La mise à jour des détails d’une tâche de révision dans le tableau de bord de révision ne confirme pas si la mise à jour a réussi ou non. (8051)

## Traduction

- Les traductions envoyées via Experience Manager Guides n’incluent pas les ressources jointes, ce qui rend le bouton **Démarrer** de la tâche de traduction indisponible pour les utilisateurs.

## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 2025.04.0 :

- Le nombre de références dans l&#39;interface utilisateur de ligne de base n&#39;est pas mis à jour lors de la modification de la ligne de base. Il n’est mis à jour que lorsque les modifications sont enregistrées. (28015)
- Lorsque plusieurs onglets sont ouverts dans l’éditeur, l’exécution d’une opération **Annuler** dans la vue **Source** d’un fichier rétablit la dernière modification, mais bascule également vers l’onglet précédemment ouvert. (27891)
- L’option **Vérification orthographique d’** apparaît dans la liste déroulante **Menu**, même si l’option **Vérification orthographique du navigateur** est activée dans les paramètres de l’éditeur. (27993)
- Une version supplémentaire est créée et affichée dans le panneau **Historique des versions** lorsque vous modifiez une image dans l’interface utilisateur d’Assets et que vous l’enregistrez. (28001)
- Une ligne vide est automatiquement insérée lors du collage d&#39;un nouveau contenu dans une nouvelle ligne au sein d&#39;un élément `codeblock`.(27842)
- Le fait de basculer entre des paramètres prédéfinis qui utilisent la même ligne de base désactive le bouton **Enregistrer** du paramètre prédéfini actuel. (28025)
- Une rubrique dans un plan DITA ne parvient pas à publier dans la sortie AEM Sites lorsqu&#39;elle est utilisée à la fois comme `keydef` et comme `topicref` dans ses sous-plans. (22269)
- Une erreur d&#39;application se produit lorsque plusieurs rubriques d&#39;une carte sont modifiées, puis fermées à l&#39;aide de l&#39;option **Fermer tout**, avec le paramètre **Demander lors de l&#39;enregistrement de la version lors de la fermeture** activé.(27931)

Adobe a identifié le problème connu suivant lié à une solution :

+++Dans la sortie AEM Sites, les images s’interrompent lorsque la ligne de base n’est pas appliquée lors de la publication. (28043)
***Solution :*** vous pouvez publier ces ressources à partir de l’**interface utilisateur d’Assets**, après quoi le lien devient opérationnel.
+++
