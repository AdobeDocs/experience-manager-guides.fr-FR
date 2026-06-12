---
title: Suppression de l’option « Supprimer » du menu contextuel des fichiers dans l’éditeur web pour des utilisateurs spécifiques
description: Découvrez comment personnaliser l’éditeur web en supprimant l’option Supprimer du menu contextuel de fichier pour des utilisateurs/groupes spécifiques
exl-id: 31b4dd53-3938-42e1-bbc6-64806d668696
TQID: https://experienceleague.adobe.com/dzbMsXUoEibR5QxKB-Z-h4qGnQaX2NmIYLTtxVJHE-A
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 241
ht-degree: 0%

---

# Supprimer l’option « Supprimer » du menu contextuel du fichier dans l’éditeur web

Dans cet article, nous allons découvrir comment masquer l’option « Supprimer » du menu contextuel des fichiers dans l’éditeur web d’AEM Guides pour des utilisateurs ou des groupes spécifiques. Pour d’autres personnalisations des options de menu contextuel de fichier, consultez la section Framework d’extension Guides. Vous trouverez plus de détails [ici](https://github.com/adobe/guides-extension/tree/main).

Comme vous pouvez le voir dans le fragment de code ci-dessous, le menu contextuel du fichier propose l’option « Supprimer » pour cet utilisateur spécifique.

![Menu contextuel Fichier avec Supprimer](../../../assets/authoring/file-contextmenu-Delete.png)

Voyons maintenant comment masquer l’option « Supprimer » pour cet utilisateur.

## Étapes de mise en œuvre :

- Accédez à Outils > Sécurité > Autorisations à partir de la page d’accueil d’AEM.
- Sélectionnez le groupe ou l’utilisateur dans la zone de recherche.
- Cliquez sur « Ajouter un ACE » dans le coin supérieur droit.
- Choisissez le chemin du dossier.
- Incluez les privilèges « jcr :removeChildNodes » et « jcr :removeNode ».
- Choisissez « Type d’autorisation » comme « Refuser », puis cliquez sur « Ajouter », comme illustré ci-dessous.

![Refuser l’autorisation de l’utilisateur à ACE](../../../assets/authoring/permission-ACE-Delete.png)

![Liste de contrôle d’accès dans les autorisations &#x200B;](../../../assets/authoring/delete-acl.png)

### Tests

- Connectez-vous à AEM en tant qu’utilisateur pour lequel les entrées de contrôle d’accès ont été ajoutées.
- Ouvrez l’éditeur web.
- Accédez à la vue du référentiel et sélectionnez le dossier pour lequel les entrées de contrôle d’accès ont été ajoutées.
- Ouvrez le menu contextuel du fichier.
- L&#39;option &#39;Supprimer&#39; n&#39;apparaîtra pas dans le menu contextuel.

Le menu contextuel du fichier se présente comme suit :

![Menu contextuel du fichier sans supprimer](../../../assets/authoring/file-contextmenu-Delete-removed.png)

```
Please note that these steps would also remove 'move' and 'rename' options from the Web Editor as they are also tied to delete process at the backend.
```
