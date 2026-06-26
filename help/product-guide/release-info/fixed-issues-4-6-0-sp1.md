---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides 4.6.0 Service Pack 1
description: Découvrez les correctifs de bugs dans la version 4.6.0 Service Pack 1 d’Adobe Experience Manager Guides
role: Leader
exl-id: ab45ac10-8a97-4ade-accc-2b884da0e973
TQID: https://experienceleague.adobe.com/-PGxudGeachzaYoru1fHTObZcwRuXzle5s7KRRJlfBA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 311
ht-degree: 4%

---

# Correction de problèmes dans la version 4.6.0 Service Pack 1 (octobre 2024)


Cet article couvre les bugs corrigés dans différentes zones de la version 4.6.0 Service Pack 1 d’Adobe Experience Manager Guides.

Découvrez les [instructions de mise à niveau pour la version 4.6.0 du Service Pack 1](upgrade-instructions-4-6-0-sp1.md).

## Création

- La création d&#39;un plan DITA sur une instance UUID échoue lorsque `xmleditor.uniquefilenames`est activé dans `XMLEditorConfig`. (21201)
- Lors de la fermeture d’un fichier, les commentaires et les libellés ajoutés dans la boîte de dialogue **Enregistrer les modifications et déverrouiller le fichier** ne sont pas enregistrés dans l’historique des versions avec la nouvelle version. Ceci est spécifique à un cas d’utilisation où **Demander l’archivage à la fermeture** ou **Demander une nouvelle version à la fermeture** est activé dans `XMLEditorConfig`. (20065)
- L’état du document marqué comme **Terminé** revient à **Brouillon** avant d’enregistrer une nouvelle version, ce qui fait que l’état **Terminé** ne persiste dans aucune version du document. (20006)
- Impossible d’ajouter un fichier PDF en tant que référence d’image dans une rubrique de l’éditeur. (21206)
- La sélection d&#39;un fichier DITA dans l&#39;interface utilisateur d&#39;Assets affiche l&#39;option **Ouvrir dans FrameMaker**, même si elle est désactivée dans la configuration. (20082)


## Publication

- Le chargement des pièces jointes vers Salesforce échoue si le chemin d’accès à la pièce jointe dépasse la longueur autorisée. (19420)
- Lors de la publication d’une rubrique dans Salesforce, la résolution des liens de fichier PDF échoue. (19304)
- L’erreur `DUPLICATE_VALUE` se produit par intermittence lors de la tentative de republication d’un article existant dans Salesforce. (17932)
- Dans la sortie PDF native, les titres des chapitres sont absents de la table des matières, ce qui entraîne une hiérarchie incorrecte. (21840)
- Lors de la publication d’AEM Sites, seul un nombre limité d’attributs peut être inclus dans la table des matières. (7483)

## Gestion

- Des fuites de ressources se produisent en raison d’erreurs Unclosed **ResourceResolver** dans les journaux. (18488)
- Lors de la création d&#39;une nouvelle ligne de base ou d&#39;une ligne de base en double, les libellés s&#39;affichent dans un ordre aléatoire. (19307)
