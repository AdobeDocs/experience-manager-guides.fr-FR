---
title: Notes de mise à jour | Nouveautés de la version Adobe Experience Manager Guides de novembre 2023
description: Découvrez les nouvelles fonctionnalités et les fonctionnalités améliorées de la version de novembre 2023 d’Adobe Experience Manager Guides as a Cloud Service.
exl-id: 83c04e01-92f1-41b0-8866-a202f4106b51
feature: What's New
role: Leader
source-git-commit: 12ba7129255257970ddd7a0989149be664ce9803
workflow-type: tm+mt
source-wordcount: '811'
ht-degree: 0%

---

# Nouveautés de la version de novembre 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cet article couvre les nouvelles fonctionnalités et les fonctionnalités améliorées de la version de novembre 2023 d’Adobe Experience Manager Guides (plus tard appelée *Experience Manager Guides as a Cloud Service*).

Pour plus d’informations sur les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans cette version, consultez [Notes de mise à jour](release-notes-2023-11-0.md).

## Améliorations du PDF natif

Les améliorations du PDF natif suivantes ont été apportées à la version de novembre 2023 :

### Utiliser et dupliquer des modèles PDF prêts à l’emploi

Experience Manager Guides fournit des modèles PDF prêts à l’emploi ou d’usine. Dupliquez les modèles PDF d’usine pour créer les modèles PDF personnalisés.

Vous pouvez désormais également prévisualiser la miniature d’un modèle lors de la création et de la duplication d’un modèle. Vous pouvez également modifier ou supprimer cette image. Cette fonctionnalité est utile pour marquer ou distinguer les modèles portant des noms similaires.
En savoir plus sur le modèle [](../native-pdf/pdf-template.md).

![ Boîte de dialogue Dupliquer le modèle PDF ](assets/duplicate-template.png){width="550"}

*Dupliquez un modèle PDF existant.*


### Modifier l’ordre des pages et publier plusieurs pages par feuille

Outre la publication des pages en fonction du document source, vous pouvez également modifier l’ordre des pages dans PDF lors de la publication d’un document de plusieurs pages.  Vous avez ainsi la possibilité de publier les pages dans différents ordres, comme toutes les pages impaires ou paires en premier. Vous pouvez également publier sous forme de livret et lire les pages comme un livre. Vous pouvez également décider du nombre de pages que vous souhaitez publier sur une seule feuille de papier. Pour plus d’informations, consultez la section [ Organisation de la page ](../native-pdf/components-pdf-template.md#page-organization).

### Trier les termes du glossaire en fonction des clés de tri

Vous pouvez désormais également trier les termes du glossaire en fonction des clés de tri. Vous pouvez utiliser la balise « sort-as » pour définir une clé de tri pour les termes du glossaire. Ensuite, vous pouvez les trier en fonction des clés de tri à la place des termes. Vous pouvez ainsi trier les termes du glossaire en fonction des termes utilisés dans différentes langues. Vous pouvez également définir une clé de tri unique pour un terme du glossaire avec une expression ou un groupe de mots.
Pour plus d’informations, voir [Paramètres avancés de PDF](../native-pdf/components-pdf-template.md#advanced-pdf-settings).


### Amélioration de la gestion des ressources pour les modèles PDF natifs

Experience Manager Guides a amélioré la gestion des ressources pour les modèles PDF natifs. Vous pouvez désormais partager et réutiliser des ressources, telles que des images, des fichiers CSS et des fichiers de polices, sur plusieurs modèles Native PDF. Grâce à cette amélioration, la gestion des ressources d’un grand nombre de modèles est beaucoup plus simple. Vous n’avez pas besoin de créer des ressources en double pour chaque modèle. Vous pouvez également les conserver dans un dossier partagé et les utiliser dans tous les modèles PDF natifs.
Pour plus d&#39;informations, voir [Modèle ](../native-pdf/pdf-template.md).

## Améliorations de l’éditeur web

Les améliorations suivantes ont été apportées à l’éditeur web dans la version de novembre 2023 :


### Afficher les fichiers par titre ou nom de fichier

Vous pouvez désormais choisir la manière d’afficher les fichiers par défaut dans l’éditeur web. Vous pouvez afficher la liste des fichiers en fonction des titres ou des noms de fichier à partir des différents panneaux à partir de la vue Création.

![ Boîte de dialogue Préférences utilisateur ](assets/user-preferences-2311.png){width="550"}

*Modifiez la manière d’afficher les fichiers par défaut à partir de la boîte de dialogue **Préférences utilisateur**.*


### Gestion des paramètres prédéfinis de condition

Vous pouvez définir des attributs de condition dans vos rubriques DITA. Ensuite, utilisez les attributs de condition dans le paramètre prédéfini de condition pour publier le contenu dans un plan DITA. Experience Manager Guides vous permet désormais de créer et de gérer des paramètres prédéfinis de condition à partir de l’éditeur web. Vous pouvez également facilement les modifier, les dupliquer ou les supprimer.

![Paramètres prédéfinis de condition) dans l’onglet Gérer de l’éditeur web ](assets/web-editor-manage-condition-presets.png){width="550"}

Pour plus d’informations, consultez la section [Utilisation de paramètres prédéfinis de condition](../user-guide/generate-output-use-condition-presets.md).

### Restaurer les onglets de fichiers lors de l’actualisation du navigateur

Experience Manager Guides restaure l’état des onglets de fichiers ouverts dans l’éditeur web lorsque vous actualisez le navigateur. Pour plus d’informations, consultez la section **Actualiser le navigateur lors de la modification des fichiers** sous [Modifier les rubriques dans l’éditeur web](../user-guide/web-editor-edit-topics.md).

### Déplier facilement un élément

Vous pouvez désormais facilement déplier un élément à l’aide de l’option du menu contextuel d’un élément dans l’éditeur web. Vous pouvez ainsi fusionner facilement le texte de l’élément avec son élément parent.
Pour plus d’informations, reportez-vous à la section **Déplier un élément** des [autres fonctionnalités de l’éditeur web](../user-guide/web-editor-other-features.md).

### Raccourcis clavier pour déplacer le curseur

Experience Manager Guides vous permet désormais également d’utiliser des raccourcis clavier pour déplacer le curseur dans l’éditeur web. Vous pouvez utiliser les raccourcis clavier pour déplacer rapidement un mot vers la gauche ou la droite. Vous pouvez également vous déplacer au début ou à la fin de la ligne à l’aide des raccourcis clavier.
Désormais, vous pouvez également utiliser des raccourcis clavier pour déplacer le curseur au début de l’élément suivant ou à la fin de l’élément précédent.
En savoir plus sur les [raccourcis clavier dans l’éditeur web](../user-guide/web-editor-keyboard-shortcuts.md).
