---
title: Notes de mise à jour | Correction de problèmes dans la version 2024.10.0 Service Pack 1 d’Adobe Experience Manager Guides.
description: Découvrez les correctifs de bogues de la version 2024.10.0 Service Pack 1 d’Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 2362870e0e3e6c08df03e8c547bb77de7faa0a02
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 1%

---

# Correction de problèmes dans 2024.10.0 Service Pack 1

Cet article couvre les bogues corrigés dans différentes zones de la version 2024.10.0 Service Pack 1 d’Adobe Experience Manager Guides as a Cloud Service.

## Création

- La création de mappage DITA sur une instance UUID échoue lorsque `xmleditor.uniquefilenames` est activé dans `XMLEditorConfig`. (21201)
- Lors de la fermeture d’un fichier, les commentaires et les libellés ajoutés dans la boîte de dialogue **Enregistrer les modifications et déverrouiller le fichier** ne sont pas enregistrés dans l’historique de versions avec la nouvelle version. Ceci est spécifique à un cas d’utilisation où **Demander l’archivage lors de la fermeture** ou **Demander la nouvelle version lors de la fermeture** est activé dans `XMLEditorConfig`. (20065)
- L’état du document marqué comme **Terminé** revient à **Brouillon** avant d’enregistrer une nouvelle version, ce qui signifie que l’état **Terminé** ne persiste dans aucune version de document. (2006)
- Impossible d’ajouter un fichier de PDF en tant que référence d’image dans une rubrique de l’éditeur web. (21206)
- La sélection d’un fichier DITA dans l’interface utilisateur d’Assets affiche l’option **Ouvrir dans le FrameMaker** , même si elle est désactivée dans la configuration. (20082)

## Publication

- Dans la sortie du PDF natif, les titres de chapitre sont absents de la table des matières, ce qui entraîne une hiérarchie incorrecte. (21840)


## Gestion

- Des fuites de ressources se produisent en raison d’erreurs **Unclosed ResourceResolver** dans les journaux. (18488)
- Lors de la création d’une ligne de base ou d’une ligne de base en double, les libellés sont affichés dans un ordre aléatoire. (19307)


## Ligne de base

- Modification, puis enregistrement d’une ligne de base sur une configuration cloud expiration après 1 minute si la ligne de base comporte un grand nombre de rubriques ou de mappages. (19558)

## Traduction

- La traduction des cartes à l’aide de la ligne de base devient lente et ne parvient pas à charger la liste de toutes les rubriques et tous les fichiers de mappage associés. (19733)