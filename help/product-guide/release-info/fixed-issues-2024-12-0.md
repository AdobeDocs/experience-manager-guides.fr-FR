---
title: Notes de mise à jour | Correction de problèmes dans la version 2024.12.0 d’Adobe Experience Manager Guides
description: Découvrez les correctifs de bugs de la version 2024.12.0 d’Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: f643a4a22151af2ff14288ab3885c1a6657a80ca
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 1%

---

# Correction de problèmes dans la version 2024.12.0

Cet article couvre les bugs corrigés dans différentes zones de la version 2024.12.0 d’Adobe Experience Manager Guides as a Cloud Service.

Découvrez les [instructions de mise à niveau pour la version 2024.12.0](./upgrade-instructions-2024-12-0.md).

## Création

- La création d&#39;un plan DITA sur une instance UUID échoue lorsque le `xmleditor.uniquefilenames` est activé dans `XMLEditorConfig`. (21201)
- Lors de la fermeture d’un fichier, les commentaires et les libellés ajoutés dans la boîte de dialogue **Enregistrer les modifications et déverrouiller le fichier** ne sont pas enregistrés dans l’historique des versions avec la nouvelle version. Ceci est spécifique à un cas d’utilisation où **Demander l’archivage à la fermeture** ou **Demander une nouvelle version à la fermeture** est activé dans `XMLEditorConfig`. (20065)
- L’état du document marqué comme **Terminé** revient à **Brouillon** avant d’enregistrer une nouvelle version. L’état **Terminé** ne persiste dans aucune version du document. (20006)
- Impossible d’ajouter un fichier de PDF en tant que référence d’image dans une rubrique de l’éditeur web. (21206)
- La sélection d&#39;un fichier DITA dans l&#39;interface utilisateur d&#39;Assets affiche l&#39;option **Ouvrir dans le FrameMaker**, même lorsqu&#39;elle est désactivée dans la configuration. (20082)

## Publication

- Dans la sortie du PDF natif, les titres des chapitres sont absents de la table des matières, ce qui entraîne une hiérarchie incorrecte. (21840)


## Gestion

- Des fuites de ressources se produisent en raison d’erreurs **Unclosed ResourceResolver** dans les journaux. (18488)
- Lors de la création d&#39;une nouvelle ligne de base ou d&#39;une ligne de base en double, les libellés s&#39;affichent dans un ordre aléatoire. (19307)


## Ligne de base

- La modification et l’enregistrement d’une ligne de base sur une configuration cloud expirent au bout d’une minute si la ligne de base comporte un grand nombre de rubriques ou de cartes. (19558)

## Traduction

- La traduction des cartes à l’aide de la ligne de base devient lente et ne parvient finalement pas à charger la liste de toutes les rubriques et de tous les fichiers de cartes associés. (19733)
