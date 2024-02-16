---
title: Notes de mise à jour | Nouveautés des guides Adobe Experience Manager, version de novembre 2023
description: Découvrez les nouvelles fonctionnalités améliorées de la version de novembre 2023 de Adobe Experience Manager Guides as a Cloud Service.
exl-id: 83c04e01-92f1-41b0-8866-a202f4106b51
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 0%

---

# Nouveautés de la version de novembre 2023 de Adobe Experience Manager Guides as a Cloud Service

Cet article couvre les nouvelles fonctionnalités et les fonctionnalités améliorées de la version de novembre 2023 des Guides Adobe Experience Manager (appelée ultérieurement *Guides du Experience Manager as a Cloud Service*).

Pour plus d’informations sur les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans cette version, consultez [Notes de mise à jour](release-notes-2023-11-0.md).

## Améliorations apportées aux PDF natifs

Les améliorations suivantes ont été apportées au PDF natif dans la version de novembre 2023 :

### Utiliser et dupliquer des modèles de PDF prêts à l’emploi

Experience Manager Guides fournit des modèles de PDF prêts à l’emploi ou d’usine. Dupliquez les modèles de PDF d’usine pour créer les modèles de PDF personnalisés.

Vous pouvez désormais également prévisualiser la miniature d’un modèle lors de la création et de la duplication d’un modèle. Vous pouvez également modifier ou supprimer cette image. Cette fonction est utile pour marquer ou distinguer des modèles portant des noms similaires.
En savoir plus sur les [Modèle de PDF](../native-pdf/pdf-template.md).

![Boîte de dialogue Dupliquer le modèle de PDF](assets/duplicate-template.png){width="550" align="left"}

*Dupliquez un modèle de PDF existant.*


### Modifier l’ordre des pages et publier plusieurs pages par feuille

Outre la publication des pages en fonction du document source, vous pouvez modifier l’ordre des pages dans PDF lors de la publication d’un document de plusieurs pages.  Vous avez ainsi la possibilité de publier les pages dans différents ordres, comme toutes les pages impaires ou paires. Vous pouvez également publier en tant que brochure et lire les pages comme un livre. Vous pouvez également décider du nombre de pages que vous souhaitez publier sur une seule feuille de papier. Pour plus d’informations, voir la [Organisation de la page](../native-pdf/components-pdf-template.md#page-organization) .

### Tri des termes du glossaire à l’aide de clés de tri

Vous pouvez également trier les termes du glossaire à partir de touches de tri. Vous pouvez utiliser la balise &quot;sort-as&quot; pour définir une clé de tri pour les termes du glossaire. Vous pouvez ensuite les trier en fonction des clés de tri, plutôt que des termes. Vous pouvez ainsi trier les termes du glossaire en fonction de termes utilisés dans différentes langues. Vous pouvez également définir une clé de tri unique pour un terme de glossaire contenant une expression ou un groupe de mots.
Pour plus d’informations, voir la [Paramètres du PDF avancé](../native-pdf/components-pdf-template.md#advanced-pdf-settings).


### Amélioration de la gestion des ressources pour les modèles de PDF natif

Les guides du Experience Manager ont désormais amélioré la gestion des ressources pour les modèles de PDF natif. Vous pouvez désormais partager et réutiliser des ressources, telles que des images, des fichiers CSS et des fichiers de polices, sur plusieurs modèles de PDF natif. Avec cette amélioration, la gestion des ressources pour un grand ensemble de modèles est beaucoup plus simple. Vous n’avez pas besoin de créer des ressources en double pour chaque modèle. Vous pouvez également les conserver dans un dossier partagé et les utiliser dans tous les modèles de PDF natif.
Pour plus d’informations, voir [Modèle de PDF](../native-pdf/pdf-template.md).

## Améliorations apportées à l’éditeur web

Les améliorations suivantes ont été apportées à l’éditeur Web dans la version de novembre 2023 :


### Affichage des fichiers par titre ou par nom de fichier

Vous pouvez désormais choisir la méthode par défaut pour afficher les fichiers dans l’éditeur Web. Vous pouvez afficher la liste des fichiers selon les titres ou les noms des fichiers dans les différents panneaux depuis la vue Auteur.

![Boîte de dialogue Préférences utilisateur](assets/user-preferences-2311.png){width="550" align="left"}

*Modifiez la manière par défaut d’afficher les fichiers à partir de la fonction **Préférences utilisateur**boîte de dialogue.*


### Gestion des paramètres de condition prédéfinis

Vous pouvez définir des attributs de condition dans vos rubriques DITA. Ensuite, utilisez les attributs de condition dans le paramètre prédéfini de condition pour publier le contenu dans un mappage DITA. Les guides du Experience Manager vous permettent désormais de créer et de gérer des paramètres prédéfinis de condition à partir de l’éditeur web. Vous pouvez également facilement les modifier, les dupliquer ou les supprimer.

![Paramètres prédéfinis de condition de l’onglet Gérer de l’éditeur web ](assets/web-editor-manage-condition-presets.png){width="550" align="left"}

Pour plus d’informations, voir [Utiliser des paramètres prédéfinis de condition](../user-guide/generate-output-use-condition-presets.md).

### Restaurer les onglets de fichier lors de l’actualisation du navigateur

Experience Manager Guides restaure l’état des onglets de fichiers ouverts dans l’éditeur web lorsque vous actualisez le navigateur. Pour plus d’informations, voir la **Actualiser le navigateur lors de la modification des fichiers** section sous [Modification des rubriques dans l’éditeur web](../user-guide/web-editor-edit-topics.md).

### Déencapsuler facilement un élément

Vous pouvez désormais facilement renvoyer à la ligne un élément à l’aide de l’option du menu contextuel d’un élément dans l’éditeur web. Vous pouvez ainsi facilement fusionner le texte de l’élément avec son élément parent.
Pour plus d’informations, voir la **Extraire un élément** de la section [autres fonctionnalités de l’éditeur web](../user-guide/web-editor-other-features.md).

### Raccourcis clavier pour déplacer le curseur

Les guides du Experience Manager vous permettent désormais d’utiliser des raccourcis clavier pour déplacer le curseur dans l’éditeur web. Vous pouvez utiliser les raccourcis clavier pour déplacer rapidement un mot vers la gauche ou la droite. Vous pouvez également passer au début ou à la fin de la ligne à l’aide des raccourcis clavier.
Désormais, vous pouvez également utiliser des raccourcis clavier pour déplacer le curseur au début de l’élément suivant ou à la fin de l’élément précédent.
En savoir plus sur les [raccourcis clavier dans l’éditeur web](../user-guide/web-editor-keyboard-shortcuts.md).
