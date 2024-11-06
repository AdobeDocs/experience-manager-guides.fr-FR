---
title: Notes de mise à jour | Correction de problèmes dans la version Adobe Experience Manager Guides 4.6.0 Service Pack 1
description: Découvrez les correctifs dans la version 4.6.0 Service Pack 1 d’Adobe Experience Manager Guides
role: Leader
source-git-commit: 2362870e0e3e6c08df03e8c547bb77de7faa0a02
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 0%

---


# Correction de problèmes dans la version 4.6.0 Service Pack 1 (octobre 2024)


Cet article couvre les bogues corrigés dans différentes zones de la version 4.6.0 Service Pack 1 d’Adobe Experience Manager Guides.

Découvrez les [instructions de mise à niveau pour la version 4.6.0 Service Pack 1](upgrade-instructions-4-6-0-sp1.md).

## Création

- La création de mappage DITA sur une instance UUID échoue lorsque `xmleditor.uniquefilenames` est activé dans `XMLEditorConfig`. (21201)
- Lors de la fermeture d’un fichier, les commentaires et les libellés ajoutés dans la boîte de dialogue **Enregistrer les modifications et déverrouiller le fichier** ne sont pas enregistrés dans l’historique de versions avec la nouvelle version. Ceci est spécifique à un cas d’utilisation où **Demander l’archivage lors de la fermeture** ou **Demander la nouvelle version lors de la fermeture** est activé dans `XMLEditorConfig`. (20065)
- L’état du document marqué comme **Terminé** revient à **Brouillon** avant d’enregistrer une nouvelle version, ce qui signifie que l’état **Terminé** ne persiste dans aucune version de document. (2006)
- Impossible d’ajouter un fichier de PDF en tant que référence d’image dans une rubrique de l’éditeur web. (21206)
- La sélection d’un fichier DITA dans l’interface utilisateur d’Assets affiche l’option **Ouvrir dans le FrameMaker** , même si elle est désactivée dans la configuration. (20082)


## Publication

- Le téléchargement de pièces jointes vers Salesforce échoue si le chemin de la pièce jointe dépasse la longueur autorisée. (19420)
- Lors de la publication d’une rubrique sur Salesforce, les liens de fichier du PDF ne sont pas résolus. (19304)
- L’erreur `DUPLICATE_VALUE` se produit par intermittence lors de la tentative de republication d’un article existant dans Salesforce. (17932)
- Dans la sortie du PDF natif, les titres de chapitre sont absents de la table des matières, ce qui entraîne une hiérarchie incorrecte. (21840)
- Lors de la publication d’AEM Sites, seul un nombre limité d’attributs peuvent être inclus dans la table des matières. (7483)

## Gestion

- Des fuites de ressources se produisent en raison d’erreurs **ResourceResolver** non fermées dans les journaux. (18488)
- Lors de la création d’une ligne de base ou d’une ligne de base en double, les libellés sont affichés dans un ordre aléatoire. (19307)









