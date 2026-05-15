---
title: Notes de mise à jour | Correction de problèmes liés à la version 2024.10.0 Service Pack 1 d’Adobe Experience Manager Guides
description: Découvrez les correctifs de bugs de la version 2024.10.0 du Service Pack 1 d’Adobe Experience Manager Guides as a Cloud Service.
exl-id: d5fa200b-1f15-4ec2-adf9-a29382afc3de
TQID: https://experienceleague.adobe.com/ziRAAFKf5Dl-6Hd7ziXwSJepbiVzkXLGz5jDWIILPkU
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 299
ht-degree: 5%

---

# Correction de problèmes dans la version 2024.10.0 du Service Pack 1

Cet article couvre les bugs corrigés dans différentes zones de la version 2024.10.0 du Service Pack 1 d’Adobe Experience Manager Guides as a Cloud Service.

## Création

- La création d&#39;un plan DITA sur une instance UUID échoue lorsque le `xmleditor.uniquefilenames` est activé dans `XMLEditorConfig`. (21201)
- Lors de la fermeture d’un fichier, les commentaires et les libellés ajoutés dans la boîte de dialogue **Enregistrer les modifications et déverrouiller le fichier** ne sont pas enregistrés dans l’historique des versions avec la nouvelle version. Ceci est spécifique à un cas d’utilisation où **Demander l’archivage à la fermeture** ou **Demander une nouvelle version à la fermeture** est activé dans `XMLEditorConfig`. (20065)
- L’état du document marqué comme **Terminé** revient à **Brouillon** avant d’enregistrer une nouvelle version. L’état **Terminé** ne persiste dans aucune version du document. (20006)
- Impossible d’ajouter un fichier PDF en tant que référence d’image dans une rubrique de l’éditeur web. (21206)
- La sélection d&#39;un fichier DITA dans l&#39;interface utilisateur d&#39;Assets affiche l&#39;option **Ouvrir dans FrameMaker**, même si elle est désactivée dans la configuration. (20082)

## Publication

- Dans la sortie PDF native, les titres des chapitres sont absents de la table des matières, ce qui entraîne une hiérarchie incorrecte. (21840)


## Gestion

- Des fuites de ressources se produisent en raison d’erreurs **Unclosed ResourceResolver** dans les journaux. (18488)
- Lors de la création d&#39;une nouvelle ligne de base ou d&#39;une ligne de base en double, les libellés s&#39;affichent dans un ordre aléatoire. (19307)


## Ligne de base

- La modification, puis l’enregistrement d’une ligne de base sur une configuration cloud expirent au bout d’une minute si la ligne de base comporte un grand nombre de rubriques ou de mappages. (19558)

## Traduction

- La traduction des cartes à l’aide de la ligne de base devient lente et ne parvient pas à charger la liste de toutes les rubriques et de tous les fichiers de mappage associés. (19733)
